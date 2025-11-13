# Real-Time Hybrid Wildlife Tracking on Edge Networks

## Background

Monitoring animal movements supports ecological research and wildlife conservation. Scientists need to understand how animals move, where they go, and how they behave to protect species and manage ecosystems.

Traditional methods like radio collars or GPS tags require catching animals and fitting them with devices, which is invasive, expensive, and not suitable for all species. Camera traps and surveillance cameras offer a non-intrusive way to monitor wildlife.

The challenge is that these cameras are often in remote locations, running on batteries or solar power, and connected to edge networks with limited bandwidth and computational resources. Animals also get hidden behind trees, move unpredictably, and multiple animals might be present at the same time. The tracking system needs to handle these challenges while operating in real-time on edge devices with minimal computational resources.

## Objective

Develop a video-based tracking system that can follow animals across frames, even when they are partially hidden or move unpredictably. The system should:

1. Detect animals in video frames
2. Track individual animals across frames
3. Maintain identity when animals temporarily disappear behind vegetation
4. Handle multiple animals without mixing up their identities
5. Work efficiently for field deployment scenarios

## Expected Work

Students should think about implementing a real-time hybrid tracker that combines prediction and similarity-based matching. Consider:

- **Hybrid Tracking Approach**: How can you combine motion prediction with appearance matching for robust real-time tracking? What are the advantages of using both approaches together?
- **Kalman Filter for Motion Prediction**: Use Kalman filtering to predict where an animal will be based on its previous motion. Kalman filters are recursive estimation algorithms that combine noisy position measurements with motion predictions to provide smooth, accurate tracking. They work by maintaining an estimate of the animal's state (position, velocity) and updating it with each new observation, making them robust to temporary occlusions or missed detections.
- **Efficient appearance matching**: Think about what kind of features would be efficient for appearance matching on edge devices. What characteristics make features suitable for fast matching while maintaining good tracking performance? Consider local binary patterns or similar computationally efficient feature representations.
- **Multi-Object Tracking**: Use data association algorithms to track multiple animals simultaneously
- **Edge Network Optimization**: Think about how to design the system to work efficiently on edge devices with limited computational resources

You should:
1. Implement a tracking method
2. Test it on video sequences with known animal tracks
3. Evaluate tracking stability and accuracy
4. Handle cases where animals are occluded or hidden
5. Document your approach and results

## Datasets

You can use the following datasets:

- **WILDTRACK Dataset**: Multi-camera dataset for pedestrian tracking, can be adapted for wildlife tracking
- **Caltech Camera Traps Dataset**: Large-scale camera trap dataset with animal annotations
- **Animal-Pose Dataset**: Dataset with animal pose annotations for tracking
- **MOTChallenge Datasets**: Multi-object tracking benchmarks (MOT17, MOT20) that can be adapted
- **VisDrone Dataset**: Aerial tracking dataset that can be used for wildlife monitoring
- **Camera Trap Datasets**: Datasets from wildlife camera trap projects (e.g., Snapshot Serengeti)
- **Custom or Simulated Data**: If you have access to wildlife footage, you can use it (with proper permissions) or create tracking scenarios using available video footage

Make sure to document your dataset sources and any preprocessing.

## Deliverables

1.  Working implementation that processes video and tracks animals
2.  Visualizations showing tracked animals with trajectories overlaid on video
3. **Report**: Brief report (10-15 pages) explaining:
   - Your tracking approach and why you chose it
   - How you handle occlusions and identity maintenance
   - Results showing tracking performance
   - Analysis of when tracking fails and why
   - Discussion of robustness and efficiency
4.  Metrics showing tracking accuracy and stability

**Note:** It is not required or expected that you complete all aspects of the project. Evaluation is done based on how much percentage of the criteria is fulfilled. Focus on demonstrating understanding and implementing a working solution for the core aspects of your assigned problem.

## Evaluation

Your work will be evaluated based on:

- How consistently you maintain animal tracks without losing them
- Whether you maintain correct animal identities (no ID switches)
- How well it handles occlusions, multiple animals, and challenging conditions
- How well you explain your tracking method
- Computational requirements and real-time performance on edge devices

You should measure and report:

- How accurately you estimate animal positions
- How often you mix up which animal is which
- How often you lose and reacquire tracks
- What percentage of animals are tracked for most of their time in view
- How well you maintain tracking during occlusions

## Future Extensions (Optional)

If you want to extend the project, you could:

- Classify different animal species automatically
- Recognize behaviors (grazing, running, resting)
- Estimate population sizes from tracking data
- Use multiple cameras for better coverage
- Predict animal movement patterns

---

**Supervision:** All projects are evaluated by Dr. Upendra Kumar Sahoo and coordinated by TA Kannuru Srinadh,Yerram Deekshith Kumar,Debapriya Das Gupta ADSP Lab, NIT Rourkela.
