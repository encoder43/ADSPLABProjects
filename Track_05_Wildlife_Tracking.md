# Tracking Animals in Forest Footage Using Simple Prediction Methods

## Background

Monitoring animal movements supports ecological research and wildlife conservation. Scientists need to understand how animals move, where they go, and how they behave to protect species and manage ecosystems.

Traditional methods like radio collars or GPS tags require catching animals and fitting them with devices, which is invasive, expensive, and not suitable for all species. Camera traps and surveillance cameras offer a non-intrusive way to monitor wildlife.

The challenge is that these cameras are often in remote locations, running on batteries or solar power. Animals also get hidden behind trees, move unpredictably, and multiple animals might be present at the same time. The tracking system needs to handle these challenges while using minimal computational resources.

## Objective

Develop a video-based tracking system that can follow animals across frames, even when they are partially hidden or move unpredictably. The system should:

1. Detect animals in video frames
2. Track individual animals across frames
3. Maintain identity when animals temporarily disappear behind vegetation
4. Handle multiple animals without mixing up their identities
5. Work efficiently for field deployment scenarios

## Expected Work

Students should implement a tracker that uses prediction or similarity-based matching. Possible approaches include:

- **Motion Prediction**: Use Kalman filtering or similar methods to predict where an animal will be based on its previous motion. Kalman filters are recursive estimation algorithms that combine noisy position measurements with motion predictions to provide smooth, accurate tracking. They work by maintaining an estimate of the animal's state (position, velocity) and updating it with each new observation, making them robust to temporary occlusions or missed detections.
- **Appearance Matching**: Extract features from detected animals and match them across frames to maintain identity
- **Hybrid Approach**: Combine prediction with appearance matching for better robustness
- **Multi-Object Tracking**: Use data association algorithms to track multiple animals simultaneously

You should:
1. Implement a tracking method
2. Test it on video sequences with known animal tracks
3. Evaluate tracking stability and accuracy
4. Handle cases where animals are occluded or hidden
5. Document your approach and results

## Datasets

You can use the following datasets:

- **Wildlife Datasets**: Public datasets containing animal tracking video with annotations
- **Camera Trap Datasets**: Datasets from wildlife camera trap projects
- **Animal Tracking Datasets**: Datasets like VisDrone, MOTChallenge (if applicable), or wildlife-specific tracking datasets
- **Custom Data**: If you have access to wildlife footage, you can use it (with proper permissions)
- **Simulated Data**: You can create tracking scenarios using available video footage

Make sure to document your dataset sources and any preprocessing.

## Deliverables

1. **Tracking Code**: Working implementation that processes video and tracks animals
2. **Tracking Results**: Visualizations showing tracked animals with trajectories overlaid on video
3. **Report**: Brief report (10-15 pages) explaining:
   - Your tracking approach and why you chose it
   - How you handle occlusions and identity maintenance
   - Results showing tracking performance
   - Analysis of when tracking fails and why
   - Discussion of robustness and efficiency
4. **Performance Summary**: Metrics showing tracking accuracy and stability

## Evaluation Parameters

Your work will be evaluated based on:

- **Tracking Stability**: How consistently you maintain animal tracks without losing them
- **Identity Preservation**: Whether you maintain correct animal identities (no ID switches)
- **Robustness**: How well it handles occlusions, multiple animals, and challenging conditions
- **Clarity of Explanation**: How well you explain your tracking method
- **Efficiency**: Computational requirements (if relevant for your approach)

## Evaluation Metrics

You should measure and report:

- **Tracking Accuracy**: How accurately you estimate animal positions
- **ID Switches**: How often you mix up which animal is which
- **Track Fragmentation**: How often you lose and reacquire tracks
- **Mostly Tracked Ratio**: What percentage of animals are tracked for most of their time in view
- **Occlusion Handling**: How well you maintain tracking during occlusions

## Future Extensions (Optional)

If you want to extend the project, you could:

- Classify different animal species automatically
- Recognize behaviors (grazing, running, resting)
- Estimate population sizes from tracking data
- Use multiple cameras for better coverage
- Predict animal movement patterns

---

**Note:**

*This problem statement is part of the ADSP Lab Final Project Series under the supervision of Dr. Upendra Kumar Sahoo, coordinated by TA Yerram Deekshith Kumar.*
