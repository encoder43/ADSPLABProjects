# Vehicle Detection and Counting in Traffic Videos

## Background

Traffic management requires understanding traffic flow – how many vehicles, how fast they are moving, where congestion occurs. This information helps optimize signal timing, plan infrastructure, and manage incidents.

Traditional methods like inductive loop detectors embedded in roadways are expensive to install and maintain, and provide limited information. Vision-based traffic monitoring using existing surveillance cameras offers a flexible, cost-effective alternative.

The challenge is that urban traffic scenes are complex: multiple vehicles, varying lighting, occlusions, different vehicle types. We need to not just detect vehicles, but track them across frames to measure speeds, understand trajectories, and maintain accurate counts even when vehicles temporarily disappear behind other vehicles.

## Objective

Design a video processing system that detects and counts vehicles in recorded traffic footage. The system should:

1. Detect vehicles in video frames
2. Track vehicles across frames to maintain identities
3. Count vehicles passing through defined regions or lines
4. Optionally estimate vehicle speeds
5. Generate useful statistics about traffic flow

## Expected Work

Students should implement:

1. **Vehicle Detection**: Use object detection methods to find vehicles in video frames
2. **Vehicle Tracking**: Track detected vehicles across frames to maintain identities
3. **Counting**: Count vehicles passing through defined counting lines or regions
4. **Optional Speed Estimation**: Estimate vehicle speeds using pixel-to-meter calibration
5. **Statistics**: Generate basic traffic statistics (counts, flow rates, etc.)

You can use:
- Pre-trained vehicle detection models (like YOLO, SSD, or similar)
- Tracking algorithms (like DeepSORT, ByteTrack, or simpler methods): Kalman filtering can be used to maintain vehicle position and velocity estimates, combining noisy detections with motion predictions to provide smooth tracking and handle occlusions.
- Counting logic that tracks vehicles crossing lines or entering/exiting regions
- Calibration methods to convert pixel distances to real-world distances

You should:
1. Implement detection and tracking
2. Test on traffic video sequences
3. Evaluate counting accuracy
4. Document your approach and results

## Datasets

You can use the following datasets:

- **Traffic Datasets**: Public datasets like UA-DETRAC, KITTI (traffic scenes), or Cityscapes
- **Vehicle Detection Datasets**: Datasets with vehicle annotations in traffic scenes
- **Traffic Monitoring Datasets**: Datasets specifically designed for traffic analysis
- **Custom Data**: You can use publicly available traffic camera footage (with proper attribution)
- **Simulated Scenarios**: You can create test scenarios using available video footage

Make sure to document which dataset you use and any preprocessing steps.

## Deliverables

1. **Detection and Counting Code**: Working implementation that processes traffic video and counts vehicles
2. **Count Results**: Results showing vehicle counts for test videos with ground truth comparisons
3. **Report**: Brief report (10-15 pages) explaining:
   - Your detection and tracking approach
   - How you count vehicles (counting lines, regions, etc.)
   - Results showing counting accuracy
   - Analysis of errors and when they occur
   - Discussion of challenges (occlusions, multiple vehicles, etc.)
4. **Visual Outputs**: Videos or images showing detected and tracked vehicles with count overlays

## Evaluation

Your work will be evaluated based on:

- **Counting Accuracy**: Count error, mean absolute error, accuracy within ±1 or ±2 vehicles
- **Tracking Quality**: ID switches, track fragmentation, how well you maintain vehicle identities
- **Processing Speed**: Frames per second you can process
- **Robustness**: How well it handles different traffic densities and conditions
- **Clarity**: Quality of visualization, explanation, and error analysis

## Future Extensions (Optional)

If you want to extend the project, you could:

- Classify vehicle types (car, truck, motorcycle, bus)
- Estimate vehicle speeds more accurately
- Analyze traffic flow per lane
- Detect traffic incidents or stopped vehicles
- Generate real-time traffic statistics

---

**Note:**

*This problem statement is part of the ADSP Lab Final Project Series under the supervision of Dr. Upendra Kumar Sahoo, coordinated by TA Yerram Deekshith Kumar.*
