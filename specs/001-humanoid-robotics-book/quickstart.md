# Quickstart Guide: Physical AI & Humanoid Robotics Textbook Development

This guide provides a rapid setup for the Docusaurus documentation environment and a basic ROS 2 development workspace. This allows authors and contributors to quickly get started with content creation and example development.

## 1. Docusaurus Environment Setup

### Prerequisites

-   Node.js (LTS version, e.g., 18.x or 20.x)
-   npm or Yarn

### Steps

1.  **Clone the Repository (if not already done)**:

    ```bash
    git clone [repository-url]
    cd humanoid-robotics-book
    ```

2.  **Install Dependencies**:

    Navigate to the project root (where `package.json` is located) and install the Docusaurus dependencies.

    ```bash
    npm install
    # or
    yarn install
    ```

3.  **Start Docusaurus Development Server**:

    This will start a local development server and open the site in your browser, with hot-reloading for changes.

    ```bash
    npm start
    # or
    yarn start
    ```

4.  **Build the Static Site (for deployment)**:

    To generate the static HTML, CSS, and JavaScript files for deployment, run:

    ```bash
    npm run build
    # or
    yarn build
    ```

    The output will be in the `build/` directory.

## 2. ROS 2 Development Workspace Setup

ROS 2 (Robot Operating System 2) is the primary framework for robotics development in this textbook. This section guides you through setting up a basic ROS 2 workspace.

### Prerequisites

-   Ubuntu 22.04 LTS (Jammy Jellyfish) recommended.
-   A working ROS 2 installation (e.g., Humble Hawksbill or Iron Irwini).
    -   Refer to the official ROS 2 documentation for installation instructions: [https://docs.ros.org/en/latest/Installation.html](https://docs.ros.org/en/latest/Installation.html)

### Steps

1.  **Source your ROS 2 Installation**:

    Open a new terminal and source your ROS 2 environment. Replace `humble` with your installed distribution if different.

    ```bash
    source /opt/ros/humble/setup.bash
    ```

2.  **Create a ROS 2 Workspace**:

    It's good practice to organize your ROS 2 packages within a dedicated workspace.

    ```bash
    mkdir -p ~/ros2_ws/src
    cd ~/ros2_ws
    ```

3.  **Create a Sample ROS 2 Package (rclpy - Python)**:

    Use `ros2 pkg create` to create a new Python package. This example creates a package named `my_robot_pkg` with a dependency on `rclpy`.

    ```bash
    cd ~/ros2_ws/src
    ros2 pkg create --build-type ament_python my_robot_pkg --dependencies rclpy
    ```

4.  **Build the Workspace**:

    Navigate back to the workspace root and build your packages. The `--symlink-install` flag is useful for Python packages as it allows you to modify Python source files without re-running the build.

    ```bash
    cd ~/ros2_ws
    colcon build --symlink-install
    ```

5.  **Source the Workspace Overlay**:

    After building, you need to source your workspace's `setup.bash` file to make your new package available in the environment. This must be done *after* sourcing the main ROS 2 installation.

    ```bash
    source ~/ros2_ws/install/setup.bash
    ```

6.  **Verify Package (Optional)**:

    You can verify your package was created correctly:

    ```bash
    ros2 pkg list | grep my_robot_pkg
    ```

Now you have both the Docusaurus environment and a basic ROS 2 workspace ready for development.
