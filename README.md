# MonoDepth_Transfer: Monocular Depth Estimation from Image Using CNNs and Transfer Learning
When an image is captured, the 3-dimensional scene are projected onto a 2D plane which results in the loss of relative distance information for each point. 
The image with those distance information for each pixel point is called depth maps. 
This research is generating or pixel-wise prediction of depth information from 2D single RGB image by creating a CNN utilizing transfer learning.
<br>
Example Input RGB images and Output Depth maps
<p align="center">
  <img style="max-width:500px" src="depth_output_results/results_img.png" width="" alt="RGBD Demo">
</p>

<br>
Depth Estimation from a Video
<p align="center">
  <img style="max-width:500px" src="depth_output_results/video_depth_result.gif" width="" alt="RGBD Demo">
</p>
<br>

The estimated depht values of each pixel are projected in 3D space as 3D points cloud
<p align="center">
  <img style="max-width:500px" src="other_pictures/point_cloud1.png" width="" alt="RGBD Demo">
</p>

<p align="center">
  <img style="max-width:500px" src="other_pictures/point_cloud2.png" width="" alt="RGBD Demo">
</p>

<br><br>



# Example use of monocular depth estimation from single image in real world
<br>
<p align="center">
  <img style="max-width:500px" src="https://github.com/kelvin-kkw/MonoDepth_Transfer/assets/105034699/2be71d1a-363e-4918-856e-e8b62d7b1e3a" width="" alt="RGBD Demo">
</p>
Multi-layered image depth effect in IOS version 16 (Released in September, 2022)
- This feature combined the monocular depth estimation of image with 3D object rendering with depth value to make occlusion aware 3D object rendering

<br><br>
# How depth estimation is used in occlusion aware Augmented Reality 3D object rendering
<br>
<p align="center">
  <img style="max-width:500px" src="other_pictures/cat_occ.png" width="" alt="RGBD Demo">
</p>
ARcore occlusion dense depth AR effect (Released in October, 2020)
- This feature contains the use of Visual Simultaneous Localization and Mapping (vSLAM), the process of calculating the position and orientation of a camera with respect to its surroundings while simultaneously mapping the environment. With the use of vSLAM, the depth of scene is estimated and combine with 3D object rendering.

<br><br>



# Traditional way of depth estimation before
Use triangulation process to get spare depth information. The hardware set up and calculation of these 
approaches are complex and the estimated depth information can be inaccurate due to the ambiguity or occlusion problem in different viewpoints of the cameras. 
<p align="center">
  <img style="max-width:500px" src="other_pictures/stereo_camera.png" width="" alt="RGBD Demo">
</p>

<br><br>



# Depth Estimation using pre-trained CNN, DenseNet-169 as Encoder
The architecutre of base DenseNet model contain 4 Dense blocks
<p align="center">
  <img style="max-width:500px" src="other_pictures/DenseNet_example.png" width="" alt="RGBD Demo">
</p>
<br>


Each Dense block contains certain number of Dense Layers based on the DenseNet model number
<p align="center">
  <img style="max-width:500px" src="other_pictures/Dense_block.png" width="" alt="RGBD Demo">
</p>
<br>


The number of the layers varied based on the variation of pre-trained DenseNet model
<p align="center">
  <img style="max-width:500px" src="other_pictures/densenet_archs.png" width="" alt="RGBD Demo">
</p>
<br>


# Decoder with Upsampling Layers
The decoder contain upsmaling layer to enlarge the downsampled, shrinked in resolution, of input image as feature maps.
<p align="center">
  <img style="max-width:500px" src="other_pictures/bilinear.png" width="" alt="RGBD Demo">
</p>
<br>


# Layers in Encoder-Decoder Architecture
<p align="center">
  <img style="max-width:500px" src="other_pictures/model_layer.png" width="" alt="RGBD Demo">
</p>
<br>


