# Detecting and Tracking Flying Drones Using Stereo Vision

## Background

As drones become more common, security systems need ways to detect and track them, especially near critical infrastructure, restricted airspace, or private facilities. Small drones can be difficult to detect with traditional radar because they have low radar cross-sections, fly slowly, and can operate at low altitudes.

Stereo vision uses two cameras (like human eyes) to see depth and estimate 3D positions. It is more cost-effective than LIDAR systems and can provide the 3D information needed to not just detect drones, but also figure out exactly where they are and where they are heading.

The challenge is that drones appear as very small objects in images, especially at security-relevant distances (50-500 meters). They might be just a few pixels across, making them hard to detect. They also move in 3D space, so we need to track not just their 2D position in an image, but their full 3D position and movement.

## Objective

Create a stereo-based detection system that can detect flying drones and estimate their distance and movement. The system should:

1. Detect small drones in stereo image pairs
2. Estimate 3D position using stereo disparity computation
3. Track drone movement over time
4. Estimate distance accurately for security-relevant ranges
5. Work in real-time or near real-time

## Expected Work

Students should work on:

1. **Stereo Calibration**: Calibrate two cameras to understand their relative positions
2. **Drone Detection**: Detect drones in stereo image pairs (can use object detection methods)
3. **Stereo Matching**: Find corresponding points in left and right images to compute depth
4. **3D Localization**: Convert 2D detections to 3D positions using computed depth
5. **Tracking**: Track drones over time and estimate their movement

You can use:
- Stereo calibration tools (OpenCV provides functions for this)
- Object detection methods for finding drones in images
- Stereo matching algorithms to compute disparity and depth
- Tracking methods to follow drones across frames: Kalman filtering is particularly useful for tracking drones in 3D space. Kalman filters can maintain estimates of drone position, velocity, and acceleration in 3D coordinates, combining noisy stereo measurements with motion predictions. This provides smooth tracking even when detections are temporarily lost or when stereo matching produces noisy depth estimates, and enables prediction of future drone positions for better tracking continuity.

You should:
1. Use provided stereo data or simulated stereo pairs
2. Implement drone detection in stereo images
3. Compute 3D positions using stereo vision
4. Track drones and estimate their trajectories
5. Evaluate distance estimation accuracy

## Datasets

You can use the following datasets:

- **Drone Detection Datasets**: Public datasets with drone imagery and annotations
- **Stereo Vision Datasets**: Datasets with stereo image pairs (you can adapt them for drone detection)
- **Aerial Object Datasets**: Datasets containing small flying objects
- **Custom Data**: You can create custom scenarios using available footage
- **Simulated Data**: You can create scenarios using 3D graphics or combine existing footage

Note: You can work with provided stereo datasets or simulate stereo pairs from single camera footage.

## Deliverables

1. **Detection and Tracking Code**: Working implementation that processes stereo images and detects/tracks drones
2. **Demonstration**: Video or images showing detected drones with 3D position estimates and trajectories
3. **Report**: Brief report (10-15 pages) explaining:
   - Your stereo calibration approach
   - How you detect drones in stereo images
   - Your stereo matching and depth estimation method
   - How you compute 3D positions and track movement
   - Results showing detection and distance estimation accuracy
   - Discussion of challenges and limitations
4. **Data Analysis**: Results showing distance estimation accuracy compared to ground truth (if available)

## Evaluation Parameters

Your work will be evaluated based on:

- **Detection Accuracy**: How well you detect drones (precision and recall)
- **Distance Estimation Accuracy**: How accurately you estimate drone distances
- **Tracking Quality**: How well you track drones over time
- **Clarity of Explanation**: How clearly you explain your stereo vision approach
- **Robustness**: How well it works at different distances and conditions

## Evaluation Metrics

You should measure and report:

- **Detection Performance**: Precision, recall, and F1 score for drone detection
- **Distance Error**: How far off your distance estimates are from actual distances
- **Relative Distance Error**: Distance error as a percentage of actual distance
- **Tracking Accuracy**: How well you maintain drone tracks
- **3D Position Error**: Accuracy of 3D position estimates (if ground truth available)

## Future Extensions (Optional)

If you want to extend the project, you could:

- Use multiple stereo pairs for better coverage
- Classify different types of drones
- Predict future drone trajectories
- Integrate with countermeasure systems
- Handle multiple drones simultaneously

---

**Note:**

*This problem statement is part of the ADSP Lab Final Project Series under the supervision of Dr. Upendra Kumar Sahoo, coordinated by TA Yerram Deekshith Kumar.*
