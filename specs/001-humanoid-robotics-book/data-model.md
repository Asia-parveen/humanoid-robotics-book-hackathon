# Data Model: Physical AI & Humanoid Robotics Textbook

This document outlines the key entities and their relationships within the domain of Physical AI and Humanoid Robotics, as derived from the feature specification. This conceptual data model will guide the content structure and ensure comprehensive coverage of all critical components.

## 1. ROS 2 Components

### Entities:

-   **Node**: An executable process that performs computation. Nodes communicate with each other.
    -   **Properties**: Name, executable, associated topics/services/actions.
    -   **Relationships**: Connects to other Nodes via Topics, Services, and Actions.
-   **Topic**: A named bus over which nodes exchange messages asynchronously. One-to-many communication.
    -   **Properties**: Name, message type, publisher nodes, subscriber nodes.
    -   **Relationships**: Connects publishing Nodes to subscribing Nodes.
-   **Service**: A named RPC (Remote Procedure Call) mechanism for synchronous request/response communication between nodes. One-to-one communication.
    -   **Properties**: Name, request type, response type, service server node, service client node.
    -   **Relationships**: Connects a service client Node to a service server Node.
-   **Action**: A long-running, goal-oriented asynchronous communication mechanism between nodes, offering feedback and the ability to cancel. Similar to services but for long-duration tasks.
    -   **Properties**: Name, goal type, result type, feedback type, action server node, action client node.
    -   **Relationships**: Connects an action client Node to an Baction server Node.
-   **Middleware (DDS - Data Distribution Service)**: The underlying communication layer that enables ROS 2 components to discover and communicate with each other.
    -   **Properties**: Quality of Service (QoS) settings (reliability, durability, liveliness, etc.).
    -   **Relationships**: Provides the communication backbone for all ROS 2 entities.

## 2. Robotics Hardware

### Entities:

-   **Humanoid Robot**: A robot designed to resemble the human body, typically with a torso, head, two arms, and two legs.
    -   **Properties**: Kinematic structure, degrees of freedom (DoF), joint limits, mass, inertia, link geometry, sensor payload.
    -   **Relationships**: Composed of Links and Joints; interacts with the environment via Sensors.
-   **Link**: A rigid body part of the robot (e.g., forearm, upper leg, torso).
    -   **Properties**: Name, geometry (visual/collision), inertial properties.
    -   **Relationships**: Connected by Joints.
-   **Joint**: A mechanism that connects two links, allowing relative motion.
    -   **Properties**: Name, type (revolute, prismatic, fixed), axis, limits (position, velocity, effort).
    -   **Relationships**: Connects a parent Link to a child Link.
-   **Sensor**: Devices that perceive the robot's environment or internal state.
    -   **Types**: LiDAR, IMU (Inertial Measurement Unit), RGB-D Cameras (RGB + Depth).
    -   **Properties**: Field of view, resolution, update rate, noise model, data output type.
    -   **Relationships**: Mounted on Links of a Humanoid Robot; data consumed by AI Models or ROS 2 Nodes.

## 3. Simulation Environments

### Entities:

-   **Gazebo**: A robust 3D physics simulator for robots.
    -   **Properties**: Physics engine (ODE, Bullet, etc.), world files (SDF), plugin support.
    -   **Relationships**: Simulates Humanoid Robots and their interaction with environments; integrates with ROS 2 for control and sensor data.
-   **Unity**: A real-time 3D development platform for high-fidelity visualization and interactive experiences.
    -   **Properties**: Rendering capabilities, asset pipelines, scripting (C#), physics engine (PhysX).
    -   **Relationships**: Can be used for visualizing Gazebo data (digital twin concept) or as a standalone simulation environment; capable of hosting virtual Humanoid Robots.
-   **NVIDIA Isaac Sim**: An extensible robotics simulation application built on NVIDIA Omniverse, offering photorealistic rendering and synthetic data generation.
    -   **Properties**: RTX rendering, PhysX physics, USD (Universal Scene Description) asset format, Python API, Omniverse Kit extensions.
    -   **Relationships**: Simulates Humanoid Robots and their environments; integrates with Isaac ROS for perception and AI workflows; provides synthetic data for AI Model training.

## 4. AI Models

### Entities:

-   **LLM (Large Language Model)**: Used for cognitive planning, interpreting natural language commands, and generating robot action sequences.
    -   **Properties**: Model architecture (e.g., Transformer), training data, prompt engineering techniques.
    -   **Relationships**: Receives input from OpenAI Whisper; generates high-level plans/actions for ROS 2 Nodes to execute on a Humanoid Robot.
-   **OpenAI Whisper**: An Automatic Speech Recognition (ASR) model for converting speech into text.
    -   **Properties**: Language support, accuracy, inference speed.
    -   **Relationships**: Processes human voice input; feeds transcribed text to LLMs for interpretation.
-   **Vision-Language-Action (VLA) Model (Conceptual)**: An overarching concept for models that combine visual perception, language understanding, and action generation.
    -   **Properties**: Integration of vision encoders, language models, and action decoders.
    -   **Relationships**: Utilizes data from RGB-D Cameras and LLM outputs to enable intelligent robot behavior.

## Relationships Summary

-   **ROS 2 Components** facilitate communication and control of **Robotics Hardware** within **Simulation Environments**.
-   **Robotics Hardware** (composed of **Links**, **Joints**) is equipped with **Sensors** that provide data to **AI Models** and **ROS 2 Nodes**.
-   **Simulation Environments** (Gazebo, Unity, Isaac Sim) provide virtual testing grounds for **Robotics Hardware** and **ROS 2** systems, often generating data for **AI Models**.
-   **AI Models** (LLMs, Whisper, VLA) process sensor data, interpret human commands, and generate intelligent behaviors/plans for **Robotics Hardware** via **ROS 2**.

