# Vehicle Detection, Tracking and Counting in Traffic Video Streams

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

1. Use object detection methods to find vehicles in video frames
2. Track detected vehicles across frames to maintain identities
3. Count vehicles passing through defined counting lines or regions
4. Estimate vehicle speeds using pixel-to-meter calibration
5. Generate basic traffic statistics (counts, flow rates, etc.)

You should think about:
- **Vehicle detection models**: Consider using pre-trained vehicle detection models (like YOLO, SSD, or similar). Think about what characteristics make a detection model suitable for traffic scenarios. What are the trade-offs between different model architectures?
- **Multi-object tracking approaches**: Think about how to track multiple vehicles across frames. How can you combine appearance features with motion prediction? Consider tracking algorithms that use Kalman filtering to maintain vehicle position and velocity estimates, combining noisy detections with motion predictions to provide smooth tracking and handle occlusions. What role does appearance matching play in maintaining vehicle identities?
- Counting logic that tracks vehicles crossing lines or entering/exiting regions
- Calibration methods to convert pixel distances to real-world distances

You should:
1. Implement detection and tracking
2. Test on traffic video sequences
3. Evaluate counting accuracy
4. Document your approach and results

## Datasets

You can use the following datasets:

- **UA-DETRAC Dataset**: Large-scale dataset with 10 hours of videos, 140,000 frames, and 8,250 vehicles with tracking annotations
- **KITTI Dataset**: Comprehensive dataset with traffic scenes, vehicle annotations, tracking data, and stereo pairs (also used in Track 06 and Track 08)
- **Cityscapes Dataset**: Large-scale dataset with 5,000 fine-annotated images and 20,000 coarse-annotated images
- **BDD100K Dataset**: Berkeley DeepDrive dataset with 100,000 videos and diverse traffic scenarios
- **nuScenes Dataset**: Large-scale autonomous driving dataset with 3D bounding boxes and tracking
- **Custom or Simulated Data**: You can use publicly available traffic camera footage (with proper attribution) or create test scenarios

Make sure to document which dataset you use and any preprocessing steps.

## Deliverables

1.  Working implementation that processes traffic video and counts vehicles
2.  Results showing vehicle counts for test videos with ground truth comparisons
3. **Report**: Brief report (10-15 pages) explaining:
   - Your detection and tracking approach
   - How you count vehicles (counting lines, regions, etc.)
   - Results showing counting accuracy
   - Analysis of errors and when they occur
   - Discussion of challenges (occlusions, multiple vehicles, etc.)
4.  Videos or images showing detected and tracked vehicles with count overlays

**Note:** It is not required or expected that you complete all aspects of the project. Evaluation is done based on how much percentage of the criteria is fulfilled. Focus on demonstrating understanding and implementing a working solution for the core aspects of your assigned problem.

## Evaluation

Your work will be evaluated based on:

- Count error, mean absolute error, accuracy within ±1 or ±2 vehicles
- ID switches, track fragmentation, how well you maintain vehicle identities
- Frames per second you can process
- How well it handles different traffic densities and conditions
- Quality of visualization, explanation, and error analysis

## Future Extensions (Optional)

If you want to extend the project, you could:

- Classify vehicle types (car, truck, motorcycle, bus)
- Estimate vehicle speeds more accurately
- Analyze traffic flow per lane
- Detect traffic incidents or stopped vehicles
- Generate real-time traffic statistics

---

**Supervision:** All projects are evaluated by Dr. Upendra Kumar Sahoo and coordinated by TA Kannuru Srinadh,Yerram Deekshith Kumar,Debapriya Das Gupta ADSP Lab, NIT Rourkela.
