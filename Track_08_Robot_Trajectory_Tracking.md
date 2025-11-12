# Controlling the Motion Path of a Wheeled Robot Using Visual Feedback

## Background

Mobile robots need to follow specific paths accurately. Whether it is a delivery robot navigating a warehouse, an agricultural robot following crop rows, or a mobile robot in a factory, the ability to track a desired trajectory is essential.

Traditional approaches use wheel encoders to estimate position, but these can be inaccurate due to wheel slip. Inertial measurement units (IMUs) can help, but they accumulate drift over time. GPS works outdoors, but it is not available indoors and can be inaccurate.

Vision-based control uses cameras to understand where the robot is and where it needs to go. Cameras are passive sensors that do not require external infrastructure, are relatively inexpensive, and provide rich information about the environment. The challenge is processing that visual information quickly enough for real-time control and making it robust to lighting changes.

## Objective

Design a control method that allows a robot to track and maintain a planned trajectory using visual feedback. The system should:

1. Estimate the robot's position relative to a desired path using visual information
2. Compute control commands (like linear and angular velocities) to follow the path
3. Achieve accurate tracking with bounded errors
4. Work in real-time suitable for robot control
5. Handle varying lighting conditions

## Expected Work

Students should work on:

1. **Visual Feature Extraction**: Process camera images to find features useful for understanding robot position (like lines, corners, or patterns)
2. **Pose Estimation**: Estimate where the robot is relative to the desired trajectory
3. **Trajectory Representation**: Define or load a desired trajectory (waypoints or a path)
4. **Control Design**: Design a controller that computes velocities to follow the path
5. **Integration**: Combine visual estimation with control to achieve trajectory tracking

You can use:
- Visual feature detection (like corner detection, line detection)
- Pose estimation methods (geometric methods or simple matching): Kalman filtering can be used to maintain smooth estimates of robot pose (position and orientation) by combining visual pose measurements with motion predictions. Kalman filters help filter out noise in visual measurements, predict robot state between measurements, and provide robust pose estimates even when visual features are temporarily lost or occluded.
- Control methods (like proportional control, PID control, or geometric path following)
- Robot simulation environments (like Gazebo, V-REP, or simple 2D simulators)

You should:
1. Implement visual pose estimation
2. Design a control law for trajectory tracking
3. Test in simulation
4. Evaluate tracking accuracy
5. Document your approach and results

## Datasets and Simulation

You can work with:

- **Robot Simulation**: Use simulation environments like Gazebo, V-REP/CoppeliaSim, or PyBullet
- **Trajectory Data**: Define your own desired trajectories or use standard test paths
- **Visual Landmarks**: Use environments with visual features (lines, markers, patterns) for easier tracking

Note: This project should be completed entirely in simulation.

## Deliverables

1. **Control Code**: Working implementation that processes camera images and computes control commands
2. **Simulation Demo**: Demonstration showing the robot following a trajectory
3. **Trajectory Plots**: Plots showing desired vs. actual robot trajectory
4. **Report**: Brief report (10-15 pages) explaining:
   - Your visual pose estimation approach
   - Your control design and why you chose it
   - How you integrate vision with control
   - Results showing tracking accuracy
   - Analysis of tracking errors
   - Discussion of stability and robustness
5. **Video**: Video showing the robot (or simulation) following the trajectory

## Evaluation Parameters

Your work will be evaluated based on:

- **Path Accuracy**: How accurately the robot follows the desired path
  - Metrics: Lateral error, position error, orientation error
- **Control Stability**: Whether the control is smooth and stable (no oscillations)
- **Clarity of Explanation**: How well you explain your control approach
- **Robustness**: How well it handles disturbances or changes in conditions

## Evaluation Metrics

You should measure and report:

- **Lateral Error**: How far the robot deviates sideways from the desired path
- **Position Error**: Overall distance error from desired position
- **Orientation Error**: How much the robot's heading differs from desired heading
- **Root Mean Square Error**: Average tracking error over the entire trajectory
- **Convergence**: How quickly the robot converges to the path if it starts off-path

## Future Extensions (Optional)

If you want to extend the project, you could:

- Add obstacle avoidance while tracking the trajectory
- Handle more complex trajectories (sharp turns, loops)
- Use multiple simulated sensors (combine vision with simulated IMU or encoder data)
- Implement adaptive control that adjusts to different conditions
- Extend to multiple robots following paths

---

**Note:**

*This problem statement is part of the ADSP Lab Final Project Series under the supervision of Dr. Upendra Kumar Sahoo, coordinated by TA Yerram Deekshith Kumar.*
