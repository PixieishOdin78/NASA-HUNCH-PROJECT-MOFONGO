# NASA HERA Requirements
## Moonscape and Robots Planning Phase v1.01

### 1. Executive Summary
The NASA HERA Moonscape and Robots project aims to enhance the realism and engagement of the Human Exploration Research Analog (HERA) program by incorporating a remotely operated robotic lunar exploration component. This project will develop an 8ft × 8ft portable lunar landscape model or a VR model with accompanying robotic systems that HERA participants (HERAnauts) can operate during their 45-day isolation missions. The project leverages NASA HUNCH program capabilities for development and implementation, ensuring educational value while meeting mission requirements. This may be an actual model or a VR model.

This initiative will enhance the psychological fidelity of HERA missions by providing participants with realistic lunar exploration activities while maintaining mission protocols and communication delays.

### 2. Table of Contents
1. Executive Summary
2. Table of Contents
3. Planning Stage
4. Project Overview
5. Scope
5.1 Planning Timeline
5.2 Lunar Landscape Requirements
5.2.1 Physical Specifications
5.2.2 Environmental Features
5.3 Robotic System Requirements
5.3.1 General Specifications
5.3.2 Robot Types and Functions
   1. Transportation Robot
   2. Manipulation Robot
   3. Support Robots
   4. Communication and Control Systems
6. Goal for Requirements of Student Prototype Development (2025-2026 School Year)
6.1 Scaled Model Development
6.2 Robot Prototype Development
6.3 Outline Mission Scenario Testing
Requirements Checklist
NASA HERA Lunar Landscape Data Collection Checklist
A. Lunar Surface Specifications
B. Physical Structure Requirements
C. Lighting System Requirements
D. Robot Specifications
E. CubeSat - ArduSat Integration
F. Control Systems
G. Safety and Maintenance
H. Constraints and Critical Requirements
Special Issues
A. Project Summary
B. Problem Statement
C. Objectives
D. Constraints
E. Deliverables

### 3. Planning Stage
The planning stage is crucial as it establishes the foundational requirements for both the lunar landscape and robotic systems. The lunar landscape specifications detail the exact dimensions (8ft × 8ft) and construction requirements, including portability considerations and the need for visual barriers to maintain mission immersion. The robotic system requirements outline the need for four specialized robots with specific capabilities in transportation and manipulation, all controlled via Bluetooth within a 100-meter range. This phase ensures that all technical specifications, from camera systems to power requirements, are thoroughly defined before moving to implementation.

### 4. Project Overview
The project overview section establishes the fundamental framework for the entire initiative. Its purpose is to enhance HERA missions by providing participants with realistic lunar exploration activities that maintain their psychological immersion in the space environment. The scope encompasses not just the physical construction of the moonscape and robots but also the entire ecosystem of control systems, protocols, and integration requirements necessary for successful implementation.

### 5. Scope
The project encompasses:
- Development of an 8ft × 8ft portable lunar landscape
- Creation of four specialized robotic units
- Implementation of remote control systems
- Development of mission scenarios and testing procedures

#### 1.3 Planning Timeline
- Planning Phase Start: May 15, 2025
- Requirements Document Completion: July 31, 2025
- Project Presentation Website Launch: August 8, 2025

### 5. Lunar Landscape Requirements

#### 5.1 Physical Specifications
- Dimensions: 8ft × 8ft (2.44m × 2.44m)
- Height of Side Walls: Minimum 3ft (0.91m)
- Design Concept: Foldable into 4ft × 4ft sections for portability
- Surface Features: If possible, based on actual lunar south pole crater formations
- Lighting: Integrated system for both day and night operations

#### 5.2 Environmental Features
- Crater-within-crater design based on South Pole region topology
- Integration of 3D printed rocks and surface features
- Scaled representation of actual lunar surface materials
- Visual barriers to prevent external world visibility
- Portable design for easy assembly/disassembly

### 5.3 Robotic System Requirements

#### 5.3.1 General Specifications
- Quantity: 4 specialized robots
- Control System: Bluetooth-enabled remote control
- Operating Range: 100 meters from the HERA module
- Camera Systems: Standard and infrared options with SD card storage
- Power Requirements: TBD during planning phase

#### 5.3.2 Robot Types and Functions
1. Transportation Robot:
   - Payload capacity: 0.5-1.0 lb
   - Ability to carry 10cm³ cube
   - Mobile platform with a stable base
2. Manipulation Robot:
   - Lifting mechanism/arm
   - Precision placement capabilities
   - Cube transfer functionality
3. Support Robots:
   - Specialized functions TBD during planning
   - Complementary capabilities to primary units
4. Communication and Control Systems:
   - Bluetooth control interface compatible with HERA systems
   - Video feed storage and transmission capabilities
   - Mission control monitoring interface
   - Data logging and analysis capabilities

### 6. Goal for Requirements of: Student Prototype Development (2025-2026 School Year)

#### 6.1 Scaled Model Development
- 2ft × 2ft prototype landscape
- Scale factor: 1:4 of the final design
- Integration with the NASA HUNCH program guidelines
- Student team collaboration framework

#### 6.2 Robot Prototype Development
- Arduino-based control systems
- Scaled robot designs
- Testing and validation protocols
- Documentation requirements

#### 6.3 Outline Mission Scenario Testing
- Day/night operation verification
- Communication system validation
- Emergency procedure testing
- User interface evaluation

### Requirements Checklist

#### NASA HERA Lunar Landscape Data Collection Checklist

##### A. Lunar Surface Specifications
- [ ] Identify a specific South Pole crater to model (e.g., Shackleton Crater)
- [ ] Calculate the scaling factor from the actual 21km crater to 8ft space
- [ ] Document elevation changes and depth requirements
- [ ] Map out crater-within-crater features
- [ ] Identify key surface landmarks for navigation

##### B. Physical Structure Requirements
- [ ] Measure exact dimensions (8ft × 8ft)
- [ ] Calculate load-bearing requirements for surface materials
- [ ] Document folding/portability requirements (4ft sections)
- [ ] Specify assembly/disassembly procedure requirements
- [ ] List structural support specifications

##### C. Lighting System Requirements
- [ ] Document LED specifications for day/night simulation
- [ ] Calculate power requirements for the lighting system
- [ ] Map lighting placement for minimal shadows
- [ ] Specify control system requirements
- [ ] List backup lighting requirements

##### D. Robot Specifications
- [ ] Document maximum dimensions for each robot
- [ ] Specify minimum separation distances between robots
- [ ] List camera system requirements
- [ ] Document Bluetooth range requirements (100m max)
- [ ] Specify battery life requirements

##### E. CubeSat - ArduSat Integration
- [ ] Document exact dimensions (10cm cube)
- [ ] Specify weight requirements (0.5-1.0 lb)
- [ ] List handling procedures
- [ ] Document storage requirements
- [ ] Specify safety protocols

##### F. Control Systems
- [ ] Document Bluetooth specifications
- [ ] List range testing procedures
- [ ] Specify interference prevention measures
- [ ] Document backup communication systems
- [ ] List security requirements

##### G. Safety and Maintenance
- [ ] Document operational safety procedures
- [ ] List emergency shutdown protocols
- [ ] Specify maintenance schedules
- [ ] Document inspection requirements
- [ ] List safety equipment needs

##### H. Constraints and Critical Requirements
- [ ] List of Constraints (Physical, Time, Functionality, etc.)
- [ ] Software
- [ ] Reliability
- [ ] Realism

### Special Issues
One of the additions would be a lunar landscape that allows participants to control robots and potentially place ArduSAT Cube or many on a lunar landscape. The HERAnauts would retrieve the cubes or robots that are exploring on their behalf remotely while they are in their lodging and lab.

The objective of this phase of the project is to gather the requirements and potential requirements, plus scenarios that the HERA facilitators may be interested in setting up for their participants in the simulation. This project will include the following major components.

1. Testing a single Arduino robot with a Bluetooth remote control and a camera.
2. Define the visual scope that the robots would have that ensures the product will always remain within the scenario. Specifically, when the robots are moving around, they will not see the outside world. Questions we must answer include the impact of the Sun on the facility, both from a scenario perspective and from survivability in the human environment, as well as the outside elements of the project. Additionally, there are concerns about lighting that could take them outside the scenario and whether they have to endure both day and night in a lunar landscape.
3. The initial scenario proposed is for all the robots to work inside a crater, and that would be the physical limitation. Actual size sounds like it could be 8 ft by 8 ft, but actual dimensions must be considered, including when a robot hits a rock or another small divot within the crater or comes out of another smaller crater. The camera may reflect higher and see the Earth’s sky, which would violate the scenario. This project must therefore include a backdrop or barrier that hides the Earth from the view of the HERAnauts. Another aspect is that once the dimensions and the overall scope of the sandbox have been defined, the CAD drawings for the outer frame should be created. Other requirements, such as stones and rocks and positioning of pieces, takeoff zones, and placement zones of the robot, must be defined so we know it will stay within the environment.
4. The final deliverable will be a comprehensive report and drawings of the external aspects. This would be given to the requesters and sent to NASA HUNCH students so they may work on Phase Two during the school year.

### A. Project Summary

### B. PROBLEM STATEMENT
a. The facilitators of the NASA HERA projects, with the mission starting in January 2026, require more activities for the HERAnauts to test challenges that astronauts will encounter in space. This includes navigating to multiple locations on the Moon and requiring a facility where they can drive robots.

b. Therefore, we have two objectives to solve: create the facility and model the lunar environment in which the robots operate.

### C. OBJECTIVES
a. Create an 8 ft by 8 ft collapsible environment used to mimic a small segment of the Moon in the South Pole area at Shackleton Crater. In addition, we would like robots that could carry a CubeSat into this lunar environment. The features for this terrain must also include appropriate boulders, stones, craters, etc.

b. We also need a way to manage some sort of regolith facsimile and keep track of terrain as we move forward with setting up different locations and environments. We must isolate the cameras of the different robots so they do not accidentally see ceilings and walls that would represent the simulation being violated.

c. We would like to enclose it using a tent-like structure as one of the solutions proposed during the summer. The internals would be modified to comply with the 8 ft by 8 ft collapsible environment so the whole thing can be stored inside a cabinet in the HERA facility in Johnson Space Center.

### D. Constraints
a. Some of the key constraints include the ability to collapse the 8 ft by 8 ft terrain or lunar landscape, while keeping track of all the pieces and parts that represent the surface. This includes surfaces where the locations of things like craters or hills might change, along with smaller boulders and stones, and potentially facilities like a mining or water recovery plant at different locations. We also need to consider how light would be managed if we decide to do night options in future missions.

b. The other unique part of this is that the HERAnauts will be going from a virtual reality environment to a facilities environment where they are controlling the robots by computer screens. Optionally, if you had some sort of smart facility in the robots, they might be able to do some scanning or other AI-related smart robot missions. The HERAnauts would watch the results or perhaps have to do a rescue mission if the AI messes up. They will also need to carry a CubeSat.

### E. Deliverables
a. Summary of deliverables includes the lunar moonscape and up to four lunar robots that have different functionality but provide the capability to take a CubeSat from the HERA facility and drive it over the lunar landscape. This requires the CubeSat to be put on top of the robot and removed and placed at the end of the trip.

b. All robots must have some sort of visual control system and the ability to drive the robot using a laptop or computer with multiple display screens, potentially one display screen for each robot.

### Final Summary
This project defines the planning requirements for a realistic lunar landscape and four-robot mission system to support HERA analog activities. The built environment and robots are intended to simulate lunar exploration, robot operation, cube transport, and mission realism in a portable and scalable format.

This phase provides the requirements and scenarios that will guide prototype development during the 2025-2026 school year.
