# Detecting Human Falls in Video Sequences

## Background

Fall detection helps in health monitoring and safety applications, especially for elderly people or those with mobility issues. When someone falls and cannot get up, getting help quickly is important.

Traditional fall detection systems use wearable devices like pendants or wristbands with motion sensors. These work, but people may forget to wear them, or they might not trigger if someone falls in an unusual way. Pressure mats can detect when someone gets up from a bed or chair, but they cannot tell if someone fell elsewhere in the room.

Vision-based fall detection uses cameras that are already common in many care facilities and homes. The challenge is making it work reliably – detecting real falls while avoiding false alarms from people just sitting down, bending over, or crouching.

## Objective

Design a system that detects when a person falls by analyzing video footage. The system should:

1. Track people in video sequences
2. Identify fall events accurately
3. Distinguish falls from similar activities like sitting or bending
4. Work in real-time or near real-time
5. Minimize false alarms

## Expected Work

Students should experiment with different approaches to detect falls. Possible methods include:

- **Frame Difference Analysis**: Compare consecutive frames to detect sudden motion changes
- **Bounding Box Analysis**: Track person bounding boxes and detect when aspect ratio changes rapidly (tall when standing, wide when lying)
- **Motion Pattern Analysis**: Analyze velocity and acceleration patterns to identify sudden downward motion. Kalman filtering can be used here to track person position and velocity over time, providing smooth estimates of motion that help distinguish falls from normal activities. Kalman filters maintain state estimates (position, velocity, acceleration) and update them with noisy measurements, making them robust to detection failures and useful for analyzing motion trajectories.
- **Pose Estimation**: Use pose detection to identify when body orientation changes from vertical to horizontal
- **State Machine Approach**: Model different states (standing, walking, sitting, lying) and detect transitions to "lying" that indicate falls

You should:
1. Implement a fall detection method
2. Test it on video sequences with known fall and non-fall events
3. Evaluate detection accuracy and false alarm rate
4. Document your approach and results

## Datasets

You can use the following datasets:

- **UR Fall Detection Dataset**: Contains fall and non-fall video sequences
- **Multiple Cameras Fall Dataset**: Videos from different camera angles
- **Fall Detection Dataset (FDD)**: Public dataset with annotated fall events
- **Simulated Falls Dataset**: Datasets with actors performing simulated falls
- **Custom Data**: You can create your own dataset with consent (ethical considerations apply)

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

## Evaluation Parameters

Your work will be evaluated based on:

- **Detection Accuracy**: How many real falls you detect (sensitivity/recall)
- **False Alarm Rate**: How often you incorrectly identify non-falls as falls
- **Precision**: When you say there's a fall, how often are you correct?
- **Clarity of Explanation**: How well you explain your detection logic
- **Robustness**: How well it works with different camera angles and lighting

## Evaluation Metrics

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

**Note:**

*This problem statement is part of the ADSP Lab Final Project Series under the supervision of Dr. Upendra Kumar Sahoo, coordinated by TA Yerram Deekshith Kumar.*
