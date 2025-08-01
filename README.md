## 1. Point Cloud Registration Using ICP
Import Dataset
The KITTI dataset is loaded, specifically a series of LiDAR .bin files containing 3D point clouds for registration tasks.

Show Lidar Points
The first scan is converted into an Open3D point cloud and visualized to inspect the spatial distribution of raw LiDAR data.
![ICP Result](images/1.PNG)

Show Lidar Points Intensity
Intensity values from the LiDAR scans are used to color the point cloud, providing richer visual information for interpretation.

(a) Select Two Point Clouds:
Two consecutive frames from the dataset are selected to demonstrate pairwise registration using the ICP algorithm.

(b) Visualize Unregistered Point Clouds:
The source and target point clouds are displayed together in their original (unregistered) coordinate frames to show initial misalignment.
![ICP Result](images/2.PNG)

(c) Apply ICP Algorithm:
The Iterative Closest Point (ICP) algorithm is applied to align the source point cloud with the target. The transformation matrix is printed.

(d) Visualize Aligned Point Clouds:
Both the original and aligned point clouds are visualized together to qualitatively assess the success of registration.
![ICP Result](images/3.PNG)

Animation
A rotating animation is generated to better visualize the 3D alignment result from multiple viewpoints.

## 2. Incremental Registration of Multiple Point Clouds Using ICP
(a, b) Use the Result from Previous Part: Visualize the Final Map
ICP is extended to incrementally register a sequence of point clouds. Each new scan is aligned with the accumulated map, building a global model.
![ICP Result](images/4.PNG)

Map and Trajectory
The final map and estimated trajectory are plotted alongside the ground-truth poses. A comparison is made and the Average Displacement Error (ADE) is computed.
![ICP Result](images/5.PNG)


## Technical Notes
Open3D Rendering Limitation: This notebook uses the Open3D visualizer, which does not support rendering inside Google Colab. For best results, run it locally in Jupyter Notebook or any desktop Python environment.

Dataset Path Adjustment: Make sure to update dataset paths (e.g., kitti_sample/00/) according to the location of your KITTI data on your local system.

Redundant Imports for Modularity: Some import statements are intentionally repeated across cells to allow section-wise execution, enabling you to run individual parts of the notebook independently.

In the first part of the notebook, the KITTI dataset is accessed directly from a ZIP file, while in the second part, it is used from the extracted folder. Make sure both formats are available or adjust the loading logic accordingly.

