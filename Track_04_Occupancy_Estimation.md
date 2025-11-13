# CCTV-Based Occupancy Estimation on Edge Devices

## Background

Knowing how many people are in a space can help with managing energy use, safety, and space utilization. For example, heating and cooling systems can adjust based on occupancy, or security systems can monitor if areas are too crowded.

Traditional occupancy sensors like motion detectors cannot count people, and they might miss someone who is sitting still. CO2 sensors can estimate occupancy indirectly, but they are slow to respond and not very accurate.

Many buildings already have CCTV surveillance cameras. If we can make those cameras count people, we do not need to install new sensors. The challenge is doing this efficiently on edge devices (small computers, embedded systems, or edge computing devices) typically used in surveillance systems, which have limited computational resources and power constraints.

## Objective

Build a method to estimate how many people are in a room from surveillance camera footage. The system should:

1. Detect people in video frames
2. Count the number of people present
3. Handle cases where people are partially hidden or overlapping
4. Work efficiently enough for real-time or near real-time use
5. Provide reasonably accurate counts (ideally within 1-2 people of the actual count)

## Expected Work

Students should work on:

1. Use object detection methods to find people in video frames
2. Count the detected people, handling overlaps and occlusions
3. Combine information across multiple frames to improve accuracy
4. Test the system and measure counting accuracy

You should think about:
- **Model selection for edge devices**: Consider what makes a model suitable for edge device deployment. How do you balance accuracy with computational efficiency? What characteristics should you look for when selecting or designing models for limited-resource environments?
- Pre-trained person detection models (like YOLO, SSD, or similar) - consider what modifications might make them more suitable for edge deployment
- Counting-specific methods that estimate density maps
- Temporal filtering to smooth counts over time: Kalman filtering can be used to maintain smooth estimates of occupancy counts by combining predictions based on previous counts with new detection measurements. Kalman filters work by maintaining an estimate of the occupancy state and updating it with each new frame, providing filtered counts that are less sensitive to temporary detection errors or occlusions.
- Region-of-interest processing to focus on relevant areas
- **Model optimization strategies**: Think about techniques that could reduce model size, memory usage, or computational requirements while maintaining acceptable accuracy. What approaches could make models more efficient for edge deployment?

You should:
1. Implement a counting method
2. Test it on video sequences with known occupancy counts
3. Evaluate accuracy and processing speed
4. Document your approach and results

## Datasets

You can use the following datasets:

- **ShanghaiTech Dataset**: Large-scale crowd counting dataset with Part A (482 images) and Part B (716 images)
- **UCF-CC-50 Dataset**: Challenging crowd counting dataset with 50 images of varying densities
- **WorldExpo'10 Dataset**: Dataset with 3,980 frames from 108 cameras with head annotations
- **Mall Dataset**: Indoor surveillance dataset with 2,000 frames and pedestrian annotations
- **UCSD Pedestrian Dataset**: Dataset with 2,000 frames from surveillance cameras
- **COCO Dataset**: Contains person detection annotations (subset for people) - useful for person detection
- **Custom Data**: You can collect your own data in controlled environments (with proper permissions) or use public surveillance footage datasets with annotations

Make sure to document which dataset you use and any preprocessing steps.

## Deliverables

1.  Working implementation that processes video and outputs occupancy counts
2. **Results**: Occupancy count results for test videos with ground truth comparisons
3. **Report**: Brief report (10-15 pages) explaining:
   - Your detection and counting approach
   - How you handle overlaps and occlusions
   - Results showing counting accuracy
   - Analysis of errors and when they occur
   - Discussion of computational efficiency
4.  Videos or images showing detected people with count overlays

**Note:** It is not required or expected that you complete all aspects of the project. Evaluation is done based on how much percentage of the criteria is fulfilled. Focus on demonstrating understanding and implementing a working solution for the core aspects of your assigned problem.

## Evaluation

Your work will be evaluated based on:

- How close your counts are to the actual number of people
- How fast the system processes video (frames per second) on edge devices
- Model size, memory usage, and computational requirements suitable for edge deployment
- How well it works with different room sizes, camera angles, and lighting
- How clearly you explain your method and model selection rationale

You should measure and report:

- Average difference between your count and actual count
- Percentage of frames where your count is within 1 of the actual
- Percentage of frames where your count is within 2 of the actual
- Frames per second (FPS) that you can process
- When and why counting errors occur

## Future Extensions (Optional)

If you want to extend the project, you could:

- Show where people are located in the room (spatial map)
- Distinguish between different activities (meeting, individual work)
- Predict future occupancy based on patterns
- Integrate with building management systems
- Handle multiple camera views

---

**Supervision:** All projects are evaluated by Dr. Upendra Kumar Sahoo and coordinated by TA Kannuru Srinadh,Yerram Deekshith Kumar,Debapriya Das Gupta ADSP Lab, NIT Rourkela.
