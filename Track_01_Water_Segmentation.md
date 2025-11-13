# Water Body Segmentation in Agricultural Remote Sensing

## Background

In agricultural planning and land monitoring, it is important to identify water bodies from captured images. This information helps with irrigation planning, flood monitoring, and water resource management. Farmers and environmental scientists need accurate maps showing where water is located.

The challenge is that water can look different depending on lighting conditions, weather, and the time of day. Shadows from clouds or trees can be mistaken for water. Dark soil or wet fields in agricultural areas might also look similar to actual water bodies.

This project asks you to develop a method that can reliably separate water regions from other parts of an image, even when conditions vary.

## Objective

Develop an image processing approach that can identify and segment water areas from soil, vegetation, and other land features in aerial or satellite images. The method should:

1. Work with different types of images (satellite imagery, drone footage, or aerial photographs)
2. Handle varying lighting conditions and weather
3. Distinguish water from similar-looking features like shadows or dark soil
4. Produce clear segmentation results that show water regions

## Expected Work

Students should explore different approaches to solve this problem. Consider the following aspects:

- **Efficient network design**: Think about how to design network architectures that are suitable for agricultural remote sensing applications. What makes a network "lightweight" or efficient? How can you balance accuracy with computational constraints?
- **Feature focus mechanisms**: Consider how to make your method focus on the most relevant features for water segmentation. What techniques could help your model pay more attention to water regions while ignoring irrelevant details like shadows or vegetation?
- **Temporal smoothing for video sequences**: If working with video sequences, think about how to smooth segmentation results over time. Kalman filtering can be used here, but consider: can the filter parameters be learned or adapted rather than being fixed? How might this improve performance for agricultural imagery?
- **Threshold-based segmentation**: Using color or intensity thresholds to separate water from other regions
- **Filtering and edge detection**: Applying image filters and detecting edges to identify water boundaries
- **Region-based segmentation**: Grouping similar pixels together to form water regions
- **Hybrid methods**: Combining multiple techniques for better results

You should:
1. Implement at least one segmentation method
2. Test it on sample images with known water regions
3. Evaluate how well it works using appropriate metrics
4. Compare different approaches if you try multiple methods

## Datasets

You can use the following datasets for this project:

- **DeepGlobe Land Cover Classification Challenge**: Large-scale dataset with satellite imagery and land cover annotations including water bodies
- **SpaceNet Building Detection & Segmentation**: Contains satellite imagery with various land cover types including water
- **Sentinel-2 Satellite Imagery**: Free satellite imagery from the European Space Agency (ESA) - available through Copernicus Open Access Hub
- **Landsat Imagery**: Publicly available satellite imagery from USGS EarthExplorer with historical data
- **Water Bodies Dataset (Kaggle)**: Various water segmentation datasets available on Kaggle
- **USGS Water Body Dataset**: Annotated water body datasets from US Geological Survey
- **Custom Data**: You can collect your own images if you have access to drone or aerial photography

Make sure to document which dataset you use and how you obtained it.

## Deliverables

1.  Working code that takes an image as input and produces a segmentation mask showing water regions
2.  Segmentation results for multiple test images, showing before and after comparisons
3.  Brief report (10-15 pages) explaining:
   - The method you chose and why
   - How your implementation works
   - Results on test images
   - Discussion of strengths and limitations
   - Comparison with other methods (if applicable)
4.  Images showing original photos, segmentation masks, and overlays

**Note:** It is not required or expected that you complete all aspects of the project. Evaluation is done based on how much percentage of the criteria is fulfilled. Focus on demonstrating understanding and implementing a working solution for the core aspects of your assigned problem.

## Evaluation

Your work will be evaluated based on:

- How well your method identifies water regions correctly
- How well it handles different lighting conditions and image types
- How clearly you explain your approach and results
- Whether the code is well-structured and documented

You should measure and report:

- Percentage of pixels classified correctly
- Overlap between predicted and actual water regions
- Of the pixels you labeled as water, how many are actually water?
- Of all the actual water pixels, how many did you find?

## Future Extensions (Optional)

If you want to extend the project, you could:

- Handle video sequences instead of single images
- Segment multiple classes (water, vegetation, soil, buildings)
- Optimize the method to run faster on larger images
- Create a simple user interface for the segmentation tool

---

**Supervision:** All projects are evaluated by Dr. Upendra Kumar Sahoo and coordinated by TA Kannuru Srinadh,Yerram Deekshith Kumar,Debapriya Das Gupta ADSP Lab, NIT Rourkela.
