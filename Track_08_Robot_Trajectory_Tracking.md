# Vision-Based Trajectory Tracking Control for Wheeled Mobile Robots

## Background

Tracking and controlling the movement path of a wheeled mobile robot in video footage is important for understanding behavior, analyzing performance, and enabling precise trajectory following. Whether it is a delivery robot in a warehouse, an autonomous vehicle, or a mobile robot in a controlled environment, being able to track and control its trajectory provides valuable insights for navigation and path following.

Traditional tracking methods rely on GPS or wheel encoders, but these can be inaccurate or unavailable in indoor environments. Vision-based tracking uses cameras that are already common in many environments and can provide rich information about robot movement without requiring additional sensors. For trajectory tracking control, the system needs to not only estimate the robot's position but also provide control signals to follow desired trajectories.

The challenge is processing visual information to accurately track the robot's position and path over time, even when the robot is partially occluded or when lighting conditions change, and using this information for trajectory tracking control.

## Objective

Develop a vision-based trajectory tracking control system that can follow a wheeled mobile robot and control it to follow desired trajectories. The system should:

1. Detect and track the robot in video frames
2. Estimate the robot's position and orientation in each frame
3. Use robust state estimation methods for tracking (consider how Kalman filtering could be enhanced or adapted)
4. Implement trajectory tracking control using control theory methods
5. Handle temporary occlusions or detection failures
6. Visualize the tracked trajectory and control performance

## Expected Work

Students should work on:

1. Detect the robot/vehicle in video frames using object detection or template matching methods
2. Estimate the robot's position (center point or bounding box) in each frame
3. Track the robot across frames and maintain its trajectory even during temporary occlusions
4. Visualize the tracked path overlaid on the video or as a separate plot

You should think about:
- Object detection methods (like YOLO, SSD, or template matching) to find the robot in frames
- **Enhanced state estimation**: Consider how Kalman filtering could be improved for this application. Can filter parameters be learned or adapted from data rather than being fixed? How might this improve state estimation compared to traditional Kalman filters?
- **Control methods for trajectory tracking**: Think about control theory approaches for making the robot follow desired trajectories. What control methods provide good tracking performance? Consider approaches that ensure finite-time convergence and avoid control singularities that could cause problems.
- Kalman filtering for tracking and prediction: Kalman filters can maintain smooth estimates of robot position, velocity, and orientation by combining noisy position measurements with motion predictions. They are particularly useful for tracking because they can predict where the robot will be even when detections are temporarily unavailable, and they provide filtered estimates that are robust to detection noise.
- Python libraries: OpenCV for image processing, NumPy for numerical operations, Matplotlib for visualization, control libraries for implementing control algorithms

You should:
1. Implement robot detection in video frames
2. Track the robot across frames using appropriate filtering methods
3. Implement trajectory tracking control using suitable control theory approaches
4. Reconstruct and visualize the trajectory and control performance
5. Handle cases where the robot is temporarily occluded or not detected
6. Document your approach and results, including control performance metrics

## Datasets

You can use the following datasets:

- **KITTI Dataset**: Comprehensive autonomous vehicle dataset with GPS/IMU data, visual tracking, stereo pairs, and traffic scenes (also used in Track 06 and Track 07)
- **Waymo Open Dataset**: Large-scale autonomous driving dataset with high-quality sensor data and trajectory annotations
- **TUM RGB-D Dataset**: Technical University of Munich dataset with RGB-D sequences and ground truth trajectories
- **EuRoC MAV Dataset**: European Robotics Challenge dataset with visual-inertial sequences and ground truth trajectories
- **Oxford RobotCar Dataset**: Large-scale dataset with repeated traversals of the same route, useful for trajectory analysis
- **Custom or Simulated Data**: You can create your own videos by recording robot movement, use publicly available robot footage, or create simple 2D simulations using Python (Matplotlib animations)

Make sure to document which dataset you use and any preprocessing steps.

## Deliverables

1.  Working Python implementation that processes video and tracks robot trajectory
2.  Videos or images showing the tracked robot with trajectory overlaid
3.  Plots showing the reconstructed trajectory path
4. **Report**: Brief report (10-15 pages) explaining:
   - Your detection and tracking approach
   - How you handle occlusions and missed detections
   - How you reconstruct and visualize the trajectory
   - Results showing tracking accuracy
   - Analysis of tracking errors and when they occur
   - Discussion of limitations and improvements
5.  Video showing the tracking system in action with trajectory visualization

**Note:** It is not required or expected that you complete all aspects of the project. Evaluation is done based on how much percentage of the criteria is fulfilled. Focus on demonstrating understanding and implementing a working solution for the core aspects of your assigned problem.

## Evaluation

Your work will be evaluated based on:

- How accurately you track the robot's position and orientation over time
- How well the robot follows desired trajectories (tracking error, convergence time)
- How well you maintain tracking even during occlusions
- How well you explain your tracking and control approach
- Whether the code is well-structured and documented
- How clearly the trajectory and control performance are visualized

You should measure and report:

- How far off your position estimates are from ground truth (if available)
- How accurately the robot follows desired trajectories (position error, orientation error)
- Convergence time, steady-state error, control effort
- What percentage of frames the robot is successfully tracked
- How similar your reconstructed trajectory is to the actual/desired path
- How well you maintain tracking during occlusions
- Quality of trajectory and control performance visualization

## Future Extensions (Optional)

If you want to extend the project, you could:

- Predict future robot positions based on trajectory history
- Analyze trajectory patterns (speed, acceleration, turning behavior)
- Handle multiple robots simultaneously
- Use multiple camera views for better tracking
- Detect unusual movement patterns or anomalies

---

**Supervision:** All projects are evaluated by Dr. Upendra Kumar Sahoo and coordinated by TA Kannuru Srinadh,Yerram Deekshith Kumar,Debapriya Das Gupta ADSP Lab, NIT Rourkela.
