# RML_technical_assignment
Study of the biases of a generative model through the example of a face inpainting model

Panel_utkface: folder containing 120 photos manually selected from UTKFace dataset

reshape_images.ipynb: if you run this notebook, it will create in panel_utkface a new reshaped version of each image contained in Panel_utkface. This new version has its facial landmarks at the same position as the images of CelebA-HQ dataset (each facial landmark has a fixed position). The functions involved in reshape_images.ipynb rely on facial landmarks detection using MTCNN and geometric transformations (rotations...). Each reshaped version of an image called 'example.jpg' will be called 'reshaped_example.jpg'

inpainting_results/gt: contains the Ground Truth images that is to say the complete (ie non-masked) images we ask RePaint to inpaint. These are exactly the same as the images created by reshape_images.ipynb (the images that now appear in Panel_utkface with a name starting with 'reshaped' if you've already run the notebook reshape_images.ipynb

inpainting_results/inpainted: contains the output of RePaint that is to say the inpainting of the images. Here we don't provide the code used to generate these images since we didn't code it by ourselves but used a model named RePaint. If you want to generate yourself the images, you can use RePaint too. The code is available on the followingGitHub repository: https://github.com/andreas128/RePaint

statistical_analysis.ipynb: computes the LPIPS and SSIM metrics over ground truth and inpainted images (so all the images of inpainting_results folder) and performs the statistical analysis described in sections 4.2 and 4.3 of the report (linear regressions and regression with binary variable)
