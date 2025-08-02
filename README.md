# slam-registration-icp
Learning Point Cloud Registration using ICP on KITTI dataset


## Summary – Point Cloud Registration Using ICP
1. Load and Visualize KITTI Point Cloud
This section loads binary LiDAR scans from the KITTI dataset, converts them into Open3D point clouds, and displays the first scan. This gives a visual sense of the raw data before registration.
![ICP Result](images/1.png)

3. Load Ground Truth Poses
Ground-truth camera poses are loaded from the KITTI .txt file. These poses are essential for evaluating the accuracy of the registration results.
![ICP Result](images/2.png)

5. Apply ICP for Frame-to-Frame Registration
Iteratively aligns each point cloud to the previous one using Open3D's ICP algorithm. The result is an estimated trajectory and a map built by accumulating registered scans.
![ICP Result](images/image.png)
6. Transform Ground Truth and Estimated Trajectories
This section extracts and transforms the translation components of ground truth and estimated trajectories, preparing them for 2D visualization.

7. Visualize Robot Trajectory
Plots the estimated and ground-truth robot paths in the 2D plane (X, Y), allowing for a qualitative comparison of trajectory accuracy.

8. Compute Average Displacement Error (ADE)
Calculates the mean Euclidean distance between estimated positions and ground-truth at each time step, giving a quantitative measure of registration accuracy.

9. Visualize Final Registered Map
Displays the full registered point cloud map after applying ICP across all frames. This helps to verify the 
