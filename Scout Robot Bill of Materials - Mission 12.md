# Scout Robot — Bill of Materials and Build Plan

**Mission:** 12 — Four Robots, One Mission  
**Robot role:** Scout  
**Platform concept:** Desk-sized 6×4 rover, approximately 25 × 23 × 40 cm including the LiDAR mast  
**Compute and software concept:** Raspberry Pi 5 running ROS 2  
**Purpose:** Carry the sensing and mapping workload for a coordinated Scout, Transporter, Manipulator, and Mining Robot mission

> **Planning status:** This is a preliminary bill of materials, not a validated procurement specification. Prices and compatibility are estimates supplied with the source material and should be checked with vendors before ordering. Verify ROS 2 distribution support, chassis interfaces, voltage/current limits, battery compatibility, and local safety requirements before construction.

## Budget at a Glance

| Estimate | Amount | Notes |
|---|---:|---|
| All-in, one Scout | **$968.99** | Includes optional upgrades listed below |
| Minimum viable Scout | **$625.99** | Omits OAK-D Lite, NVMe/HAT, pan-tilt kit, and dedicated Wi-Fi adapter |
| Four-robot fleet estimate supplied | **$2,304** | Described in the source as including shared-tooling savings; see budget note below |

**Budget reconciliation required:** Four all-in Scouts at $968.99 each would total $3,875.96 before shared tooling or discounts. Four minimum-viable Scouts at $625.99 each would total $2,503.96 before any savings. The supplied $2,304 fleet estimate does not directly reconcile with either per-robot figure. Confirm which robots, shared items, and discounts are included before using it as a procurement budget.

## 1. Bill of Materials

### Compute

| Part | Qty. | Unit cost | Line cost | Purpose / notes |
|---|---:|---:|---:|---|
| Raspberry Pi 5, 4 GB RAM | 1 | $110.00 | $110.00 | Proposed ROS 2 computer for Nav2, SLAM Toolbox, and robot coordination. Confirm the selected ROS 2 distribution and OS are supported together. |
| microSD card, 64 GB, A2/U3 | 1 | $12.00 | $12.00 | Boot and operating-system storage. A2-rated media is proposed for logging and map writes. |
| Raspberry Pi Active Cooler | 1 | $6.00 | $6.00 | Cooling for sustained compute workloads. |
| NVMe SSD, 256 GB, with PCIe-to-M.2 HAT+ | 1 | $42.00 | $42.00 | Optional, recommended for rosbag recordings and map storage; source estimate includes approximately $13.95 for the HAT and $26 for the SSD. |
| Raspberry Pi 27 W USB-C PSU or 5 V / 5 A UBEC | 1 | $12.00 | $12.00 | Bench power or flashing. For rover operation, the proposed design uses a regulated 5 V / 5 A supply from the battery system. |

### Chassis and Drive

| Part | Qty. | Unit cost | Line cost | Purpose / notes |
|---|---:|---:|---:|---|
| Waveshare UGV02 6×4 chassis, 252 × 230 × 94 mm, 2 kg | 1 | $149.99 | $149.99 | Proposed aluminum chassis with six wheels, four driven wheels, 80 mm tires, stated 4 kg payload, ESP32 driver board, TB6612FNG, INA219 battery monitor, ICM20948 IMU, OLED, and LiDAR interfaces. Confirm current product specification and connector details. |
| 18650 Li-ion cells, 3500 mAh, 10 A | 3 | $6.50 | $19.50 | Proposed 3S pack cells. Use reputable cells with suitable protection and discharge ratings; confirm fit and charging compatibility with the chassis. |
| 18650 charger or three-cell charging sled | 1 | $20.00 | $20.00 | Charging/pack rotation. The source suggests the charger may be shared across the fleet. |
| DC-DC buck converter, 12 V to 5 V / 5 A | 1 | $16.00 | $16.00 | Proposed regulated Pi supply. Confirm converter capacity, thermal performance, and chassis output limits. |
| XT60 / JST-XH pigtails, 18 AWG wire, 3 A and 5 A inline fuses | 1 set | $12.00 | $12.00 | Power harness and circuit protection. Fuse sizing and wiring should be reviewed against actual loads and component instructions. |

### Perception

| Part | Qty. | Unit cost | Line cost | Purpose / notes |
|---|---:|---:|---:|---|
| 2D LiDAR: Slamtec RPLIDAR C1 | 1 | $90.00 | $90.00 | Proposed 360° scanning LiDAR for mapping and navigation. Source lists 12 m range, 10 Hz, IP54, and USB/UART connection; verify current specifications and suitability for the test environment. |
| Depth AI camera: Luxonis OAK-D Lite | 1 | $269.00 | $269.00 | Optional upgrade. Stereo depth and on-camera inference can support perception while reducing host-compute load. |
| Raspberry Pi Camera Module 3 Wide or USB webcam | 1 | $38.50 | $38.50 | Video feed and visual target identification. Source says this may be omitted if the OAK-D Lite is selected. |
| Pi 5 camera cable, 22-pin to 15-pin, 200 mm | 1 | $4.00 | $4.00 | Required for the Camera Module 3 option; confirm cable orientation and compatibility. |
| Two-axis pan-tilt servo kit, SG90/MG90S and bracket | 1 | $14.00 | $14.00 | Optional camera aiming mechanism. Confirm servo voltage, current, and chassis interface. |
| HC-SR04 ultrasonic sensors ×2 or VL53L1X ToF sensors ×2 | 1 set | $8.00 | $8.00 | Proposed close-range sensing below the LiDAR plane. The source price is for the HC-SR04 option; check the cost and electrical interface of the ToF alternative. |

### Coordination and Communications

| Part | Qty. | Unit cost | Line cost | Purpose / notes |
|---|---:|---:|---:|---|
| Pi 5 onboard 2.4 / 5 GHz Wi-Fi or USB Wi-Fi dongle for AP+STA | 1 | $0.00 | $0.00 | Proposed shared network for the four robots and Mission Control. Validate coverage, network configuration, and ROS 2 DDS behavior. |
| USB Wi-Fi adapter, RTL8812AU / MT7921 class | 1 | $18.00 | $18.00 | Optional dedicated access-point link, intended to separate the robot network from a household network. Verify driver support for the chosen OS. |
| Printed and laminated AprilTag / ArUco markers | 1 set | $5.00 | $5.00 | Low-cost visual identifiers for robots and landmarks. |

### Structure and Wiring

| Part | Qty. | Unit cost | Line cost | Purpose / notes |
|---|---:|---:|---:|---|
| 1020 aluminum extrusion offcuts and corner brackets | 1 set | $18.00 | $18.00 | Proposed LiDAR mast and camera tower materials; chassis is stated to include two 1020 rails. |
| 3D-printed or acrylic sensor deck, LiDAR mast, and camera bracket | 1 set | $15.00 | $15.00 | Custom mounting parts. The source proposes reusable designs across the four-robot fleet. |
| M2.5/M3 screw kit, standoffs, zip ties, and Velcro | 1 set | $15.00 | $15.00 | Mounting, cable strain relief, and assembly hardware. |
| JST-XH / Dupont connector kit and crimper | 1 set | $25.00 | $25.00 | Connector assembly and repair. Source proposes sharing the crimper across the fleet. |
| Heat-shrink, braided sleeving, and spiral wrap | 1 set | $10.00 | $10.00 | Cable protection and management. |
| Anti-vibration rubber feet and grip-tape pads | 1 set | $6.00 | $6.00 | Helps secure electronics and battery components during rover operation. |

### Safety and Operations

| Part | Qty. | Unit cost | Line cost | Purpose / notes |
|---|---:|---:|---:|---|
| Latching, normally closed emergency-stop button | 1 | $9.00 | $9.00 | Proposed hardware stop. Design and test the motor-power interruption path; an E-stop should not be treated as a substitute for safe operating procedures. |
| Inline blade fuse holder and assorted fuses | 1 set | $8.00 | $8.00 | Additional circuit protection. Coordinate with the wiring plan to avoid duplicate fuse purchases. |
| Fire-resistant Li-ion charging bag | 1 | $12.00 | $12.00 | Proposed battery-charging safety item. Follow the cell and charger manufacturers’ instructions and applicable site rules. |
| Cleaning kit: lint-free swabs and lens cloth | 1 | $5.00 | $5.00 | Cleaning LiDAR windows and camera lenses. |

## 2. Substitutions, Upgrades, and Cost-Saving Options

Choose alternatives as substitutions, not as additional purchases, unless the design requires both components.

| Area | Listed item | Alternative or note |
|---|---|---|
| Compute | Raspberry Pi 5, 4 GB | The source suggests two 2 GB Pi 5 units at about $65 each for a split-compute approach. Confirm that the software architecture and total cost justify two computers. |
| Compute | 64 GB microSD | A multi-pack may be useful for spares during development. |
| Chassis | UGV02 6×4 | Lower-cost option: Waveshare WAVE ROVER 4WD, approximately $100 and smaller with a stated 0.8 kg payload. Tracked alternative: UGV01, approximately $170. Verify specifications and compatibility. |
| Power | Buck converter | The source suggests using the chassis 5 V USB rail as an alternative, but warns of possible brownouts during high-load turns. Validate power stability before relying on it. |
| Perception | RPLIDAR C1 | Budget alternatives: RPLIDAR A1M8 (about $79) or YDLIDAR X4 (about $80). Premium alternative: RPLIDAR A2M12 (about $285). Verify operating conditions and compatibility. |
| Perception | OAK-D Lite | Omit for a lower-cost v1 and use a Camera Module 3 with Pi-based processing. The source estimates 5–10 fps for a YOLO workload; benchmark the actual model and hardware. |
| Perception | Pan-tilt kit | Omit for v1; a fixed forward-facing camera can support the initial mission. |
| Communications | Dedicated USB Wi-Fi adapter | Omit if the fleet can use a suitable shared 5 GHz router channel and testing confirms reliable connectivity. |

## 3. Suggested Procurement Sequence

| Wave | Approx. budget | Proposed purchases | Exit goal |
|---|---:|---|---|
| Wave 1 — Prove the compute and camera | $165 | Pi 5 4 GB, microSD, active cooler, PSU, Camera Module 3 Wide, and 22-pin cable | Boot the selected OS, confirm ROS 2 compatibility, run the camera node, and view the camera in RViz2 before buying mechanical parts. |
| Wave 2 — Prove mobility | $200 | UGV02 chassis, 18650 cells and charger, buck converter, fuse/wire kit, and crimper | Test the chassis control application, then bring up the ROS 2 driver and validate odometry and velocity-command interfaces. |
| Wave 3 — Prove mapping and safety | $140 | RPLIDAR C1, extrusion and mast, fasteners, and E-stop | Confirm LiDAR data, build a map with the selected SLAM workflow, and test the stop mechanism. |
| Wave 4 — Prove advanced mission sensing | $300 | OAK-D Lite, pan-tilt kit, Wi-Fi adapter, markers, and printed sensor deck | Add depth/perception and Mission Control identification only after the previous waves are stable. |
| Shared fleet tools | About $90 | NVMe/HAT, spare cards, charger, crimper, fuse kit, charging bag, and lens kit | Buy and allocate shared tools once for the fleet where practical; do not count them both as per-robot and shared costs. |

Wave budgets are approximate planning figures from the supplied material. Some components and prices may overlap with the per-robot BOM; reconcile them against a final purchasing list before ordering.

## 4. Scout’s Role in Mission 12

| Mission requirement | Scout contribution | Proposed implementation |
|---|---|---|
| Four-robot team: Scout, Transporter, Manipulator, Mining Robot | Sensor-heavy scout maps and surveys the environment; payload and manipulation work remain with the other specialized units. | LiDAR and camera, with optional stereo depth and pan-tilt. Keep payload capacity and mast stability in mind. |
| Coordinate roles on one shared mission | Scout supplies route and environment information for teammates. | Proposed ROS 2 topics include `/scout/scan`, `/scout/odom`, `/scout/detections`, `/map`, and `/mission/task_assignments`. Confirm message types, ownership, namespace conventions, and QoS in the system design. |
| Mission Control tracks robots and reassigns tasks | Scout sends pose, telemetry, and detections; visual markers may help identify robots in camera images. | The source proposes 10 Hz telemetry and AprilTag/ArUco identifiers. Define stale-data handling, task acceptance, and safe behavior when disconnected. |

ROS 2 topic names and rates above are design proposals, not validated interfaces. Confirm them against the final ROS 2 distribution, robot drivers, network configuration, and fleet architecture.

## 5. Power and Signal Interfaces

| Connection | Intended function | Design notes to verify |
|---|---|---|
| 3S 18650 pack → UGV02 UPS input | Chassis drive motors and onboard logic | Source lists 11.1 V nominal (9.0–12.6 V) and about 45 minutes at full output. Treat runtime as an estimate and test under the actual mission load. |
| UGV02 12 V switched output → 12 V-to-5 V / 5 A converter → Pi 5 | Regulated power for Pi, NVMe, and camera | Confirm the output can support peak current and that wiring, connector, thermal, and fuse ratings are appropriate. Keep computing power separate from motor-current paths as designed. |
| UGV02 LiDAR USB port → Pi USB-A | LiDAR data and power | Source lists 5 V, 230 mA typical and 800 mA startup for the RPLIDAR C1. Verify the current device datasheet and port capacity. |
| Pi USB 3.0 → OAK-D Lite | Stereo depth and onboard inference | Source lists up to 5 W and USB 3 for full frame rate. Verify the selected cable, port, and power budget. |
| ESP32 UART ↔ Pi UART (GPIO 14/15) | Chassis command/odometry bridge | Source proposes 115200 baud, 8N1, 3.3 V logic. Connect only compatible signal/ground pins; do not connect a 5 V supply pin to 3.3 V GPIO. Confirm the chassis interface documentation. |
| Chassis servo header → pan-tilt servos | Camera pan and tilt | Source estimates up to 2 A peak for two servos and suggests a 470 µF capacitor if supply instability occurs. Validate against servo and driver specifications. |
| Normally-closed E-stop in series with motor supply | Manual motor-power interruption | Mount for quick access and test the actual interruption behavior. The proposed normally-closed arrangement is intended to stop motors if the circuit opens; verify implementation and fail-safe behavior. |

## 6. UGV02 Port Map (Proposed Use)

| Board connector / interface | Proposed use | Notes from supplied material |
|---|---|---|
| LiDAR USB connector | RPLIDAR C1 connection | Described as the simplest connection; verify the operating-system device name rather than assuming `/dev/ttyUSB0`. |
| LiDAR UART interface | LiDAR connection to ESP32 | Use only if the Pi is not hosting the LiDAR, and confirm the required protocol and wiring. |
| Host controller 40-pin header | Pi 5 mounting / GPIO connection | Do not draw motor current from the Pi header. |
| I²C device interfaces ×2 | Additional sensors | Source identifies 3.3 V logic; verify voltage compatibility and use an appropriate level shifter where required. |
| Bus-servo control interfaces | Pan-tilt or future manipulator component | Confirm supported servo protocol, voltage, and current. |
| Motor-control interfaces, 4 × drive motors | Chassis motor control | Motors are driven by the chassis electronics, not directly by Raspberry Pi GPIO. |
| ICM20948 IMU and INA219 | Orientation and battery telemetry | Proposed ROS publication includes IMU and battery-state data; confirm driver availability and calibration. |
| 12 V switches on IO4 / IO5 | Auxiliary 12 V loads | Source proposes one for the Pi converter and one spare; verify switch ratings and chassis wiring. |

## 7. Integration Risks and Procurement Checks

| Risk / issue | Planning action |
|---|---|
| ROS 2 distribution and operating-system compatibility | Confirm the current official support matrix and test the selected OS/distribution before procurement. The supplied source mentions Jazzy on Ubuntu 24.04 and Lyrical on Ubuntu 26.04; validate these details against current official ROS documentation. |
| Chassis interfaces and stated specifications | Check the current UGV02 manual and product page for payload, power outputs, battery bay, port map, driver software, and supported firmware. |
| Battery safety and charging | Select cells and a charger designed to work together; verify protection, charging procedure, storage, and supervision requirements. |
| Power brownouts | Measure Pi and sensor voltage/current during startup, turns, and peak workload. Test the complete power system before autonomy trials. |
| Camera cabling | Confirm connector type, pin count, orientation, cable length, and compatibility before ordering. |
| Networking and DDS | Test the actual access point, Wi-Fi adapter drivers, network isolation, discovery, reliability, and latency with multiple robots. |
| Fleet costs | Separate per-robot costs from shared tools and spares. Reconcile all-in, minimum viable, wave, and fleet totals before purchase approval. |
| Mission safety | Document supervision, emergency stop, safe charging, recovery, and terrain-operation procedures before tests. |

## 8. Price Sources and Provenance

The supplied BOM describes prices as US retail estimates researched on **10 November 2026**, before tax and shipping. Prices, stock, product specifications, and software support can change. The following source names were supplied with the estimate; they are listed for provenance and have not been independently validated here.

| Source named in supplied material | Use in estimate |
|---|---|
| waveshare.com/ugv02.htm | UGV02 chassis, stated configuration, and port information |
| pishop.us | Raspberry Pi, camera, PCIe-to-M.2 HAT, and WAVE ROVER price references |
| linuxvox.com and thepricer.org | Raspberry Pi price estimates |
| aifitlab.com and t-firefly.com | RPLIDAR C1 and A2 price references |
| esp32s.com and reichelt.com | RPLIDAR A1M8 price reference |
| makerspet.com | LiDAR comparison information |
| shop.luxonis.com | OAK-D Lite product and price reference |
| myzhar.tech and robotsatlas.com | ROS 2 distribution and platform support information |

## Summary

The proposed Scout is a Raspberry Pi 5-based, six-wheeled sensing rover intended to map and survey terrain for the four-robot Mission 12 team. Its core concept combines a UGV02 chassis, LiDAR, camera, ROS 2 compute, Wi-Fi coordination, and a protected power system. Optional depth sensing, NVMe storage, and camera pan-tilt can be added after the basic computer, camera, mobility, and mapping functions are proven.

The supplied estimates are **$968.99 for an all-in Scout** and **$625.99 for a minimum-viable Scout**. The listed **$2,304 four-robot estimate requires reconciliation** because it does not equal four units at either per-robot price. Before ordering, confirm current prices and hardware specifications, resolve ROS 2 and operating-system compatibility, test the power and communications systems, and separate shared fleet tools from per-robot costs. Build in waves so each stage is tested before the next set of optional hardware is purchased.

## to do list= find specs of components listed here.
