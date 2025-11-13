# Multi-Person Fall Detection in Video Sequences

## Background

Fall detection helps in health monitoring and safety applications, especially for elderly people or those with mobility issues. When someone falls and cannot get up, getting help quickly is important.

Traditional fall detection systems use wearable devices like pendants or wristbands with motion sensors. These work, but people may forget to wear them, or they might not trigger if someone falls in an unusual way. Pressure mats can detect when someone gets up from a bed or chair, but they cannot tell if someone fell elsewhere in the room.

Vision-based fall detection uses cameras that are already common in many care facilities and homes. The challenge is making it work reliably – detecting real falls while avoiding false alarms from people just sitting down, bending over, or crouching.

## Objective

Design a system that detects when one or more people fall by analyzing video footage. The system should:

1. Track multiple people simultaneously in video sequences
2. Identify fall events accurately for each person
3. Distinguish falls from similar activities like sitting or bending
4. Work in real-time or near real-time
5. Minimize false alarms
6. Handle multiple people in the same scene without confusion

## Expected Work

Students should experiment with different approaches to detect falls. Possible methods include:

- **Frame Difference Analysis**: Compare consecutive frames to detect sudden motion changes
- **Bounding Box Analysis**: Track person bounding boxes and detect when aspect ratio changes rapidly (tall when standing, wide when lying)
- **State estimation for multi-person tracking**: Think about how to track multiple people simultaneously. How can you combine observations (detections) with predictions (motion models) to maintain robust state estimates for each person? Kalman filtering can be used here to track person position, velocity, and acceleration over time, providing smooth estimates that help distinguish falls from normal activities. Consider how to maintain separate state estimates for each person in multi-person scenarios.
- **Pose Estimation**: Use pose detection to identify when body orientation changes from vertical to horizontal
- **State Machine Approach**: Model different states (standing, walking, sitting, lying) and detect transitions to "lying" that indicate falls

You should:
1. Implement a fall detection method
2. Test it on video sequences with known fall and non-fall events
3. Evaluate detection accuracy and false alarm rate
4. Document your approach and results

## Datasets

You can use the following datasets:

- **UR Fall Detection Dataset**: Contains fall and non-fall video sequences from multiple camera angles, widely used benchmark
- **UP-Fall Detection Dataset**: University of Patras fall detection dataset with various activities and fall scenarios
- **Multiple Cameras Fall Dataset (MCFD)**: Videos from different camera angles with synchronized multi-view data
- **Fall Detection Dataset (FDD)**: Public dataset with annotated fall events and ADL (Activities of Daily Living)
- **TST Fall Detection Dataset**: Dataset with temporal segmentation for fall detection
- **Custom or Simulated Data**: You can create your own dataset with consent (ethical considerations apply) or use datasets with actors performing simulated falls in controlled environments

Make sure to follow ethical guidelines when working with video data of people, and document your dataset sources.

## Deliverables

1. **Detection Code**: Working implementation that processes video and detects falls
2. **Demo Video**: Video showing the system detecting falls with annotations or alerts
3. **Report**: Brief report (10-15 pages) explaining:
   - Your detection approach and why you chose it
   - How your method distinguishes falls from other activities
   - Results showing detection accuracy
   - Analysis of false alarms and missed detections
   - Discussion of limitations and improvements
4. **Results Summary**: Table or chart showing detection performance metrics

**Note:** It is not required or expected that you complete all aspects of the project. Evaluation is done based on how much percentage of the criteria is fulfilled. Focus on demonstrating understanding and implementing a working solution for the core aspects of your assigned problem.

## Evaluation

Your work will be evaluated based on:

- **Detection Accuracy**: How many real falls you detect (sensitivity/recall)
- **False Alarm Rate**: How often you incorrectly identify non-falls as falls
- **Precision**: When you say there's a fall, how often are you correct?
- **Clarity of Explanation**: How well you explain your detection logic
- **Robustness**: How well it works with different camera angles and lighting

You should measure and report:

- **Sensitivity (Recall)**: Percentage of actual falls that you detect
- **Specificity**: Percentage of non-falls correctly identified as non-falls
- **Precision**: When you detect a fall, how often is it actually a fall?
- **False Positive Rate**: Number of false alarms per hour of video
- **Detection Latency**: How quickly after a fall you generate an alert

## Future Extensions (Optional)

If you want to extend the project, you could:

- Detect multiple people simultaneously
- Assess fall severity based on impact
- Integrate with alert systems (notifications, alarms)
- Process only skeleton data for privacy
- Learn individual movement patterns to reduce false alarms

---

**Supervision:** All projects are evaluated by Dr. Upendra Kumar Sahoo and coordinated by TA Kannuru Srinadh,Yerram Deekshith Kumar,Debapriya Das Gupta ADSP Lab, NIT Rourkela.
