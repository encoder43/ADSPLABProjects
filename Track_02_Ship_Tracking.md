# Tracking Vessels in Inland Waterways Using Visual and Location Data

## Background

Ship movement in rivers and canals can be monitored using camera footage and navigation data. Unlike open ocean tracking where radar works well, inland waterways present challenges: bridges, shorelines, and many small vessels moving in close quarters.

Traditional radar systems struggle in these environments because signals bounce off bridges and buildings, creating confusing reflections. Video cameras can see vessels clearly, but they cannot always tell exactly where something is in real-world coordinates. GPS and AIS (Automatic Identification System) data provide precise positions, but they can fail or be unavailable.

This project asks you to combine both types of data – video and location information – to create a more reliable tracking system.

## Objective

Create a tracking process that uses both video input and positional data (like GPS or AIS) to identify and track ships in inland waterways. The system should:

1. Synchronize data from cameras and GPS/AIS systems
2. Match video detections with GPS tracks (figure out which boat in the video corresponds to which GPS signal)
3. Keep tracking even when one sensor temporarily fails
4. Provide accurate position and movement information for each vessel
5. Handle multiple vessels at the same time without mixing up their identities

## Expected Work

Students should work on:

1. **Data Synchronization**: Align video frames with GPS/AIS timestamps, accounting for different update rates
2. **Visual Detection**: Detect ships in video frames using object detection methods
3. **Data Association**: Match video detections to GPS tracks using spatial and temporal information
4. **Tracking**: Maintain vessel identities across frames, even when temporarily hidden
5. **Fusion**: Combine information from both sources to get better position estimates

You can use:
- Object detection libraries (like YOLO or similar) for finding ships in video
- Kalman filtering or similar methods for tracking and prediction: Kalman filters are recursive algorithms that estimate the state of a dynamic system (like vessel position and velocity) by combining noisy measurements with predictions based on a motion model. They are particularly useful for tracking because they can predict where an object will be even when measurements are temporarily unavailable, and they provide smooth, filtered estimates by weighting predictions and observations.
- Data association algorithms to match detections with tracks
- Coordinate transformation to align video coordinates with GPS coordinates

## Datasets

You can use the following datasets:

- **SeaShips Dataset**: Large-scale dataset with 31,000+ ship images and annotations, commonly used for ship detection and tracking
- **ShipRSImageNet**: Comprehensive ship dataset with various ship types and annotations
- **MARVEL Dataset**: Maritime video dataset with vessel tracking annotations
- **AIS Data**: Public Automatic Identification System data from marine traffic websites (MarineTraffic, AISHub)
- **Inland Waterway Datasets**: Custom datasets from research papers on inland waterway tracking
- **Custom or Simulated Data**: If you have access to cameras near waterways, you can collect your own data or create synthetic scenarios by combining video footage with simulated GPS tracks

Make sure to document your dataset sources and any preprocessing you do.

## Deliverables

1. **Tracking Code**: Working implementation that processes video and GPS data to produce tracking results
2. **Tracking Output**: Visualizations showing tracked vessels with plotted trajectories
3. **Report**: Brief report (10-15 pages) explaining:
   - How you synchronize the data
   - Your detection and tracking approach
   - How you match video to GPS data
   - Results showing tracking accuracy
   - Discussion of challenges and solutions
4. **Demo Video**: Video showing the tracking system in action with overlaid trajectories

**Note:** It is not required or expected that you complete all aspects of the project. Evaluation is done based on how much percentage of the criteria is fulfilled. Focus on demonstrating understanding and implementing a working solution for the core aspects of your assigned problem.

## Evaluation

Your work will be evaluated based on:

- **Tracking Accuracy**: How accurately you estimate vessel positions
- **Smoothness**: How consistent and smooth the tracking is (no sudden jumps)
- **Identity Preservation**: Whether you maintain correct vessel identities
- **Robustness**: How well it handles sensor failures or occlusions
- **Clarity of Explanation**: How well you explain your approach

You should measure and report:

- **Position Error**: How far off your position estimates are from ground truth
- **ID Switches**: How often you mix up which vessel is which
- **Track Fragmentation**: How often you lose and reacquire tracks
- **Tracking Duration**: What percentage of time each vessel is successfully tracked

## Future Extensions (Optional)

If you want to extend the project, you could:

- Predict future vessel trajectories
- Detect unusual movement patterns
- Use multiple cameras for better coverage
- Integrate weather data to improve predictions

---

**Supervision:** All projects are evaluated by Dr. Upendra Kumar Sahoo and coordinated by TA Kannuru Srinadh,Yerram Deekshith Kumar,Debapriya Das Gupta ADSP Lab, NIT Rourkela.
