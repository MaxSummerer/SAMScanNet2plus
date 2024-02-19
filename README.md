# ML3D Project: Segment Anything Model (SAM) for 3D point clouds

  Welcome to our ML3D project! Our mission is to make 3D segmentation through the implementation of the SAM Model [1], harnessing the power of 3D point clouds as our input.
  To achieve this, our approach involves the following process:
  First, a 2D projection of the point cloud is performed using a spherical projection technique, followed by the application of SAM. 
  Our method employs multiple centers for the sphere, providing a more comprehensive and detailed understanding of the entire space. Next, we translate these 2D masks into 3D points. 
  Ultimately, we employ kNN to craft a comprehensive 3D segmentation of the space.
  Important: We used ScanNet++ [2] as dataset. The scene scans were in the file format .ply. 
  We changed the .ply files to .las files using the open-source tool Cloud Compare [3].


## ScanNet++ Dataset
If you're interested in setting up your own model, you can apply for the dataset here: https://kaldir.vc.in.tum.de/scannetpp/

## SAM Segmentation and Downloading SAM
For further information check out the respiratory:
https://github.com/facebookresearch/segment-anything

After downloading the respiratory, you can adopot the model and you'll be able to segment the images quite easily following our instructions!

 ![pc_aligned_1_0](https://github.com/MaxSummerer/SAMScanNet2plus/assets/135828831/85804387-6eb6-48c0-bf5c-ce8355b4ae45)
  ![pc_aligned_1_0](https://github.com/MaxSummerer/SAMScanNet2plus/assets/135828831/d3c6903e-87cb-4d82-bd7e-4939b740ac52)

## 2D to 3D Mapping

  After the spherical projection and segmentation, we map our images back to 3Dspace
  Also, export the Colored Point Cloud into a las file
  ![image](https://github.com/MaxSummerer/SAMScanNet2plus/assets/135828831/409fc945-87ca-4a2b-a6fd-7fdd64a65ddf)

  

## k-NN

  Color Assignment Logic: Assign the most frequent (mode) color among the nearest neighbors. 
  This approach is useful to ensure that the assigned color is actually one of the colors present in the neighborhood, 
  rather than a blend that might not exist. This approach should classify unsegmented points based on the colors of their
  nearest segmented neighbors, helping to fill in unsegmented regions of the point cloud with appropriate colors.

https://github.com/MaxSummerer/SAMScanNet2plus/assets/135828831/6272d908-bb6f-40ac-b108-fa26d3fefc51


  

## Bibliography

  [1] Segment Anything Kirillov et al. https://arxiv.org/abs/2304.02643
  
  [2] Dataset: ScanNet++ https://kaldir.vc.in.tum.de/scannetpp/
  
  [3] Cloud Compare: https://www.cloudcompare.org/
