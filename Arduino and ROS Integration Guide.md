# Connecting Arduino with ROS: Concepts and Legacy ROS 1 Example

**Topic:** Arduino and Robot Operating System (ROS) integration  
**Audience:** Beginner to intermediate  
**Example context:** ROS 1, Linux, Arduino, and `rosserial`

> **Version note:** The workflow below describes a legacy ROS 1 approach using `rosserial`. ROS 1 and ROS 2 use different communication tools and setup procedures. Do not assume ROS 1 commands or packages work with ROS 2. Check the documentation for your exact ROS distribution, operating system, Arduino board, and package versions before building.

## 1. Overview

Arduino boards are useful for small robots because they provide a straightforward way to read sensors and control motors or other hardware. As a robot grows more complex, however, it may need additional computing resources for tasks such as perception, mapping, planning, and coordinating multiple components.

A common design divides work between a computer running ROS and a microcontroller such as an Arduino. ROS can handle higher-level processes, while the Arduino performs real-time or low-level tasks such as reading sensors and controlling outputs. The two systems exchange commands and sensor information over a communication link.

## 2. What Is ROS?

The Robot Operating System (ROS) is an open-source robotics software framework and middleware. It provides tools and communication patterns that help developers integrate robot components without creating every interface from scratch. ROS is commonly used for tasks such as control, perception, planning, and exchanging data among robot software components.

ROS is not an operating system in the conventional desktop sense. It provides a software ecosystem and communication infrastructure for robotics applications.

## 3. What Does Arduino Do in a ROS Robot?

An Arduino is a microcontroller development board commonly used to interface with electronics and peripherals. Depending on the board and project, it can read digital or analog inputs and communicate with devices using interfaces such as UART, SPI, or I²C.

In a ROS-based robot, a computer may run higher-level algorithms, while the Arduino handles embedded functions such as:

- Reading buttons and other sensors
- Controlling LEDs, motors, or actuators
- Reporting basic hardware status
- Responding to commands received from the computer

The division of responsibility depends on the robot design and the capabilities of its hardware.

## 4. Communication Concepts

ROS applications exchange information using communication mechanisms such as topics and services. In a publisher/subscriber pattern, one component publishes messages to a topic and other components subscribe to that topic.

The example in this guide uses `rosserial`, a ROS 1 package that communicates with a microcontroller over a serial connection. Its Arduino library, commonly called `ros_lib`, lets an Arduino program publish ROS messages and subscribe to ROS messages through a host computer running the ROS serial node.

In the example:

- The Arduino publishes button state on the `button_press` topic.
- The Arduino subscribes to the `toggle_led` topic.
- A computer running ROS can observe button messages and send LED commands.

## 5. Software Setup (Legacy ROS 1 Example)

The source example applies to ROS 1 on Linux. Package names and installation instructions vary by ROS distribution. Confirm that the packages are available for the ROS 1 distribution being used before following this workflow.

The example setup consists of:

1. Install a supported ROS 1 distribution on a Linux computer.
2. Install the matching `rosserial` and `rosserial_arduino` packages for that distribution.
3. Install the Arduino IDE.
4. Install or generate the `ros_lib` Arduino library using the instructions for the chosen ROS 1 distribution and `rosserial` version.
5. Confirm that the Arduino IDE can find the library and its example sketches.

The original ROS 1 package installation pattern is:

```bash
sudo apt-get install ros-<distro>-rosserial
sudo apt-get install ros-<distro>-rosserial-arduino
```

Replace `<distro>` with the ROS 1 distribution name used on the computer. These commands are specific to compatible ROS 1 package repositories; they are not ROS 2 installation commands.

## 6. Example Hardware

The demonstration uses a push-button as an Arduino input and an LED as an Arduino output. The exact pin assignments and electrical connections must be checked against the selected Arduino board and circuit.

- **Publisher input:** A button connected to digital pin 8. Its state is sent to the computer as a text message.
- **Subscriber output:** An LED connected to digital pin 13. A ROS message tells the Arduino whether to turn it on or off.
- **Serial connection:** A USB cable connects the Arduino to the computer running ROS.

Use appropriate current-limiting components for LEDs and safe wiring practices for the selected hardware. Disconnect power before changing circuit connections.

## 7. Arduino Example Code

The following is a cleaned-up version of the ROS 1 `rosserial` example. It uses `std_msgs::String` for the button state and `std_msgs::UInt16` for the LED command.

```cpp
#include <ros.h>
#include <std_msgs/String.h>
#include <std_msgs/UInt16.h>

#define BUTTON_PIN 8
#define LED_PIN 13

ros::NodeHandle node_handle;

std_msgs::String button_message;
char button_text[16];

void ledCallback(const std_msgs::UInt16& message) {
  digitalWrite(LED_PIN, message.data == 1 ? HIGH : LOW);
}

ros::Publisher button_publisher("button_press", &button_message);
ros::Subscriber<std_msgs::UInt16> led_subscriber("toggle_led", &ledCallback);

void setup() {
  pinMode(LED_PIN, OUTPUT);
  pinMode(BUTTON_PIN, INPUT);

  node_handle.initNode();
  node_handle.advertise(button_publisher);
  node_handle.subscribe(led_subscriber);
}

void loop() {
  if (digitalRead(BUTTON_PIN) == HIGH) {
    strcpy(button_text, "Pressed");
  } else {
    strcpy(button_text, "Not pressed");
  }

  button_message.data = button_text;
  button_publisher.publish(&button_message);

  node_handle.spinOnce();
  delay(100);
}
```

### Code Notes

The program initializes the ROS node handle, advertises a publisher, and subscribes to the LED command topic. In the main loop, it reads the button input, publishes the current state, and calls `spinOnce()` so the Arduino can process incoming messages and invoke the subscriber callback.

The callback turns the LED on when the received value is `1`; all other values turn it off. This example assumes the button circuit produces a stable HIGH or LOW signal. Depending on the wiring, a pull-up or pull-down resistor and debouncing may be needed.

## 8. Running the Example

After uploading the sketch to the Arduino, connect the board to the computer with USB and identify the correct serial device. Device names vary by operating system and hardware. On Linux, they may look like `/dev/ttyUSB0` or `/dev/ttyACM0`; use the device actually assigned to the board.

For a compatible ROS 1 installation, the example workflow is:

1. Start the ROS master in one terminal:

   ```bash
   roscore
   ```

2. Start the ROS serial node in another terminal, replacing the device path with the Arduino's actual serial device:

   ```bash
   rosrun rosserial_python serial_node.py /dev/ttyACM0
   ```

3. View the button state:

   ```bash
   rostopic echo /button_press
   ```

4. Send a command to turn the LED off:

   ```bash
   rostopic pub -1 /toggle_led std_msgs/UInt16 "data: 0"
   ```

5. Send a command to turn the LED on:

   ```bash
   rostopic pub -1 /toggle_led std_msgs/UInt16 "data: 1"
   ```

These commands are ROS 1 examples. Topic names, package availability, serial device permissions, and command syntax may depend on the ROS distribution and installed package versions. Do not run these commands as a ROS 2 workflow without adapting the architecture and instructions for ROS 2.

## 9. Troubleshooting Pointers

- If the serial device is missing, check the USB cable, board connection, operating-system device list, and Arduino IDE port selection.
- If access to the serial device is denied, check the operating system's device permissions and follow its documented process for serial-port access.
- If the ROS serial node cannot connect, confirm that no other program is using the serial port and that the selected port and baud-rate settings match the Arduino configuration.
- If no messages appear, verify the ROS master, topic names, message types, wiring, and that the Arduino sketch was uploaded successfully.
- If the LED does not respond, check the LED wiring and confirm that the published command uses the expected `std_msgs/UInt16` type and value.
- If the button output flickers, review the circuit's pull-up or pull-down configuration and consider input debouncing.

## 10. ROS 1 and ROS 2 Compatibility

This tutorial's `rosserial`, `roscore`, `rosrun`, and `rostopic` commands describe a ROS 1 workflow. ROS 2 has different tools, package support, and communication setup. Before using an Arduino with ROS 2, check the current ROS 2 documentation and the compatibility guidance for the specific microcontroller library or bridge being considered.

## Summary

An Arduino can provide low-level sensing and actuation for a robot while a computer running ROS handles higher-level processing and coordination. In the legacy ROS 1 example here, `rosserial` connects an Arduino to ROS over USB serial: the Arduino publishes button state and subscribes to LED commands. This is a small demonstration of a broader robotics architecture, not a complete robot-control system. Confirm ROS version compatibility, hardware wiring, package availability, serial permissions, and safety requirements before adapting it to a project.
