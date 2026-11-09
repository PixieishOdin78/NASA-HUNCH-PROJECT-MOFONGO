# SFT 2025–2027 HERA Moonscape, Mars-Scape, and Robotics Planning

## Software, Technology, Hardware Engineering, and Robotics

**Document status:** Updated planning draft  
**Version:** Updated #0  
**Program:** NASA HERA / NASA HUNCH  
**Naming note:** Moon-Scape and Mars-Scape terminology is still being reviewed. Until the project team confirms the final environment, this document uses **Mars-Scape** for the updated mission concepts and **Moon-Scape / Mars-Scape** when requirements apply to either environment.

> **Planning note:** Surface terminology, dimensions, robot communication ranges, and storage requirements remain subject to review and testing. Do not treat unresolved items as approved final specifications.

## 1. Executive Summary

The NASA HERA Moonscape, Mars-Scape, and Robotics project aims to improve the realism and educational value of the Human Exploration Research Analog (HERA) program. The project explores a portable exploration landscape, remotely operated robotic systems, and mission scenarios that HERA participants (HERAnauts) can operate during simulated isolation missions.

The current concept includes a landscape approximately 8 ft × 8 ft, or a virtual-reality equivalent, and as many as four specialized robots. The robots would support exploration, payload transportation, manipulation, and other support tasks. A primary objective is to let robots carry, move, place, and retrieve a CubeSat/ArduSat-style payload while sending camera views and mission data to Mission Control.

The project is intended to progress from planning and requirements gathering to student prototypes, testing, and later construction. Basic Operations Missions 1–8 establish foundational capabilities for a Preliminary Design Review (PDR). Innovative Missions 9–14 provide stretch goals for a Critical Design Review (CDR), subject to schedule and prototype readiness.

## 2. Project Status and Decisions to Confirm

The following items remain open and should be confirmed by the project team before detailed design or construction:

| Topic | Current planning direction | Decision or test needed |
|---|---|---|
| Environment name | Moon-Scape, Mars-Scape, or Both-Scape | Confirm final project and mission terminology |
| Environment format | Physical landscape, VR model, or a combination | Select the initial prototype approach |
| Landscape size | Approximately 8 ft × 8 ft | Confirm dimensions, layout, and safe operating area |
| Portability and storage | Foldable sections; storage in a 4 ft-wide cabinet has been proposed | Verify folded dimensions, mass, assembly time, and cabinet fit |
| Robot fleet | Up to four specialized robots | Confirm roles, number of prototypes, and interfaces |
| Communications | Bluetooth, Wi-Fi, IR, or a combination | Test reliable range and operation through the intended facility walls |
| Operating range | Earlier planning described 100 m; the updated concept proposes 50 m through thin metal walls | Resolve the requirement through a site test; do not assume either value is met |
| Payload | CubeSat/ArduSat-style object, approximately 10 cm in size and up to 1 lb | Confirm whether “10 cm³” means a 10 cm cube and verify mass and handling constraints |
| Environment requirements | Lunar and Martian features are both discussed | Select surface materials, terrain references, and lighting scenarios for each version |

## 3. Project Goals

1. Develop a portable, immersive lunar or Martian exploration environment, or a VR equivalent.
2. Develop and test robotic systems that can traverse the terrain and operate remotely.
3. Demonstrate payload loading, transportation, placement, and retrieval.
4. Provide camera views, robot status, mission logs, and other useful data to Mission Control.
5. Create progressively challenging student missions, from basic teleoperation to coordinated autonomy.
6. Document requirements, testing, design decisions, and lessons learned to support later project phases.

## 4. Landscape Planning Requirements

### 4.1 Physical Environment

The current physical concept is an approximately 8 ft × 8 ft portable landscape. Earlier planning proposed folding the structure into 4 ft × 4 ft sections, with a minimum 3 ft side-wall height. These dimensions and the proposed ability to store the folded system in a 4 ft-wide cabinet must be verified during design.

The landscape should be designed for assembly, disassembly, storage, and reconfiguration. It should include terrain features appropriate to the selected mission environment, such as craters, rocks, slopes, narrow passages, and designated science or deployment locations. A crater-within-crater layout based on lunar south-polar terrain was proposed for the Moon-Scape concept. The Mars-Scape terrain layout and reference features remain to be selected.

### 4.2 Immersion and Lighting

Visual barriers should prevent cameras and participants from seeing surroundings that break the simulation. The layout must account for camera angles when a robot climbs, crosses an obstacle, or enters a depression. Lighting should support day and night operations, with control and emergency-lighting requirements established during prototype testing.

### 4.3 Surface Materials and Reconfiguration

Surface materials should provide realistic appearance and sufficient traction for the selected robots. The design should allow terrain features to be repositioned between missions and should provide a way to document or track each configuration. Regolith simulant, surface reflectivity, material containment, cleanup, and safety requirements must be assessed before selecting materials.

## 5. Robotic System Planning Requirements

### 5.1 Fleet and Control

The planning concept includes up to four specialized robotic units. Candidate control methods include Bluetooth, Wi-Fi, and infrared. The final communication method and operating range must be established through testing in the intended environment, including tests through any relevant walls and in the presence of interference.

Robots should provide remote driving or mission control, camera feedback, and appropriate status or sensor data. The system should support data logging and a way for Mission Control to monitor robots and coordinate assignments. Power, battery life, emergency stop behavior, maintenance, and recovery procedures remain to be specified.

### 5.2 Candidate Robot Roles

| Robot role | Candidate responsibilities |
|---|---|
| Scout | Survey terrain, identify landmarks, and report a safe route |
| Transporter | Carry a CubeSat-style payload or other equipment across the landscape |
| Manipulator | Grasp, lift, transfer, place, or retrieve a payload with controlled positioning |
| Mining / Support | Collect or process simulated regolith, carry sensors, or provide another complementary capability |

The four roles are a planning concept. The team may combine roles on fewer prototypes during early testing.

### 5.3 Payload Handling

The mission concepts use a CubeSat/ArduSat-style payload described as approximately 10 cm in size and weighing up to 1 lb. The exact dimensions, whether the intended item is a 10 cm cube, its allowable mass, grasping features, and safe handling procedure must be confirmed. Robots should be designed to load, transport, place, transfer, and retrieve the payload without dropping or damaging it.

## 6. Development Phases

### 6.1 Planning and Requirements

Confirm the environment name and format, requirements, mission scenarios, facility constraints, safety needs, robot roles, payload dimensions, and communication approach.

### 6.2 Student Prototype Development (2025–2026 School Year)

The initial landscape prototype was proposed at 2 ft × 2 ft, a 1:4 scale of an 8 ft × 8 ft design. The robot prototype concept includes Arduino-based control, scaled robot designs, testing and validation, and documentation. The team should verify what scale is appropriate for both terrain and robot testing.

### 6.3 Testing and Design Refinement

Testing should include basic teleoperation, camera visibility, day/night operation, communications, payload handling, emergency procedures, user-interface evaluation, robot reliability, and repeatability of mission scenarios. Test results should be recorded and used to refine requirements before full-scale construction.

## 7. Mission Progression

The mission sequence is designed to demonstrate increasingly advanced prototype capabilities. Missions 1–8 focus on core operations and PDR readiness. Missions 9–14 are innovative stretch goals intended to inform CDR-level design and testing. The scope of each review should be matched to the schedule and demonstrated prototype capability.

### Basic Operations — Missions 1–8

#### Mission 1 — First Drive on Mars

The robot leaves its designated HERA base, travels across the Mars-Scape to three marked checkpoints, and safely returns to its starting point. The team demonstrates reliable forward and reverse movement, turning, stopping, and remote control without striking walls, rocks, craters, or equipment.

#### Mission 2 — Drive by Camera Only

The operator cannot directly see the Mars-Scape and must navigate using the robot’s onboard camera. The operator locates three designated landmarks and sends images of each to Mission Control. This mission demonstrates remote operations and video feedback.

#### Mission 3 — Crater and Rock Obstacle Course

The robot traverses terrain containing rocks, slopes, crater edges, simulated loose regolith, and narrow passages. The team evaluates traction, stability, maneuverability, communications, and the robot’s ability to reach a designated science location.

#### Mission 4 — Day and Night Exploration

The team repeats an exploration mission under illuminated and simulated nighttime conditions. The robot uses onboard lighting, an infrared camera, or another sensing method to locate designated objects and return safely to base.

#### Mission 5 — Pick Up the CubeSat

A simulated CubeSat/ArduSat payload is placed at a designated location. The robot locates, grasps, lifts, and transports it to a marked deployment zone without dropping or damaging it. Confirm the payload dimensions and mass before testing.

#### Mission 6 — Precision CubeSat Deployment

The robot retrieves the payload, navigates an obstacle course, and places it inside a designated target. The team demonstrates controlled manipulation using an arm, gripper, lift, or another mechanism and verifies placement using camera feedback.

#### Mission 7 — Dig, Mine, and Return

The robot travels to a designated collection zone, gathers a measured quantity of simulated Martian regolith, and transfers it to a sieve or student-designed processing apparatus. It then returns the processed sample to the HERA base. The team defines an allowable sample-loss threshold before testing.

#### Mission 8 — Complete HERA Exploration Mission

Starting at the HERA base, the robot navigates the Mars-Scape, inspects designated landmarks, records imagery, retrieves and deploys a CubeSat-style payload, collects a regolith sample, and returns to base. Mission Control receives available video, robot status, mission events, and a final mission log.

### Innovative / Out-of-the-Box Missions — Missions 9–14

#### Mission 9 — Lost Communications!

Mission Control deliberately interrupts the primary communications link for a predetermined period. The robot follows a student-designed loss-of-communications protocol. Depending on the situation, it may safely halt, retrace its route, proceed to a predefined safe point, or switch to a tested backup communication method. The team documents how the robot detects link loss and how communications are restored.

#### Mission 10 — AI Mars Navigator

The operator gives the robot a destination but no preset route. Using cameras, ultrasonic sensors, LiDAR, computer vision, or other selected sensors, the robot identifies terrain hazards and blocked paths and determines a safe route. When an unexpected obstacle is introduced, the system detects the change and replans without operator steering.

#### Mission 11 — Search and Rescue on Mars

A simulated astronaut has lost a critical equipment package somewhere in the Mars-Scape. Mission Control knows only its approximate location. The robot searches the area, distinguishes the target from decoys using vision, RFID, thermal/infrared sensing, or another selected technology, retrieves the correct item, and returns it to the HERA base.

#### Mission 12 — Four Robots, One Mission

A team of specialized robots cooperates on a shared objective that no single robot can complete alone. A possible sequence is for the Scout to map a route, the Transporter to carry the payload, the Manipulator to deploy it, and the Mining Robot to collect regolith. Mission Control monitors the fleet and may reassign tasks if a robot becomes unavailable.

#### Mission 13 — Build a Mars Resource Station

Robots identify collection areas, gather material, transport it to a processing station, separate it using a sieve or mining apparatus, measure the processed quantity, and deposit it into labeled storage. Optional extensions include terrain classification, automated weighing, material identification, and a digital inventory. This mission is a small-scale demonstration of in-situ resource utilization concepts.

#### Mission 14 — 45-Day Mars Mission: HERA Grand Challenge

The team simulates an accelerated version of a 45-day HERA isolation mission. The robotic fleet receives changing exploration objectives, payload deployments, science targets, mining assignments, day/night operations, blocked routes, communication failures, equipment problems, and unexpected discoveries. With minimal direct intervention, the system prioritizes tasks, coordinates robots, conserves power, responds to failures, and returns samples and payloads.

At mission completion, the team produces a HERA Mars Exploration Mission Report containing available robot telemetry, maps, imagery, mission results, failures, recovery actions, and lessons learned.

## 8. Testing and Readiness Guidance

The missions are capability goals, not claims that the current prototypes already meet them. For each test, the team should record the setup, objective, success criteria, results, issues, and follow-up actions.

1. Begin with safe, supervised bench and low-speed tests before running missions on complex terrain.
2. Define measurable pass criteria before each mission, including payload retention, navigation accuracy, communication performance, and acceptable sample loss where applicable.
3. Test communication range in the actual operating environment; validate the proposed 50 m or 100 m range rather than assuming it.
4. Confirm emergency stop, safe halt, manual recovery, and battery procedures before autonomous or multi-robot tests.
5. Treat AI navigation, autonomous recovery, and multi-robot coordination as stretch capabilities until validated on the prototype.

## 9. Planning Checklist

### Environment and Terrain

| Status | Requirement |
|---|---|
| [ ] | Confirm Moon-Scape, Mars-Scape, Both-Scape, or VR terminology and scope |
| [ ] | Confirm final footprint, wall height, folding configuration, storage size, and assembly process |
| [ ] | Select terrain references and document craters, rocks, slopes, and landmarks |
| [ ] | Select surface materials and evaluate traction, containment, cleanup, and safety |
| [ ] | Define visual barriers and check camera views throughout the terrain |
| [ ] | Define day/night lighting and emergency-lighting needs |

### Robots, Payload, and Control

| Status | Requirement |
|---|---|
| [ ] | Confirm robot count and roles for the first prototype phase |
| [ ] | Confirm CubeSat/ArduSat payload dimensions, mass, and handling interface |
| [ ] | Select candidate communication methods and test range through facility walls |
| [ ] | Define camera, infrared, storage, telemetry, and Mission Control requirements |
| [ ] | Define power, battery-life, emergency-stop, and recovery requirements |
| [ ] | Define payload placement, retrieval, and transfer success criteria |

### Operations and Documentation

| Status | Requirement |
|---|---|
| [ ] | Define mission procedures and measurable success criteria |
| [ ] | Test day/night operation, communications, user interface, and emergency procedures |
| [ ] | Record prototype configurations, test results, failures, and corrective actions |
| [ ] | Prepare requirements documentation and engineering drawings for the next phase |

## 10. Summary

This updated planning document broadens the HERA robotics concept from a lunar-only landscape to a Moon-Scape, Mars-Scape, or combined environment while recognizing that the final terminology and design are still under review. It proposes a portable exploration landscape, up to four robots, remote camera-enabled operations, and payload transport and manipulation.

The 14-mission progression moves from basic driving, camera use, terrain navigation, payload handling, and sample collection to communications recovery, autonomous navigation, search and rescue, multi-robot cooperation, resource processing, and an accelerated 45-day mission challenge. The immediate priority is to confirm open requirements—especially environment scope, dimensions and storage, payload specifications, and communication range—then validate them with student prototypes and documented tests. The final goal is a safe, immersive, educational system with clear evidence of what each robot and mission can reliably accomplish.
