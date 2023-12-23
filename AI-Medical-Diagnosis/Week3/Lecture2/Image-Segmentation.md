# MRI Data and Image Registration

The focus is on training and evaluating segmentation models for tumor identification in MRI data. The UNet architecture is introduced, along with successful training procedures for segmentation models. Dealing with 3D medical data presents challenges, and the session explores creative solutions. The discussion revolves around representing MRI data, which differs from 2D X-rays. MRI sequences are 3D volumes with multiple sequences per example.

To input MRI data into a segmentation model, it's suggested treating different sequences as channels, analogous to the RGB channels in an image. The process involves combining multiple 3D volumes into one, with each sequence represented as a channel. Despite the analogy to RGB, the concept extends to handling more than three sequences. The resulting image is considered an RGB image for visualization, but machines interpret it as channels stacked in the depth dimension.

A challenge arises from the potential misalignment of sequences due to patient movement between acquisitions. To address this, there is a process called image registration, a preprocessing approach that aligns or registers images. Although not delving into the details, the importance of image registration in combining 3D volumes is emphasized. The alignment problem is crucial, as misalignment can lead to discrepancies between corresponding regions in different channels.

## Coronal, Sagittal, and Axial Planes

- Coronal plane: divides the body into anterior and posterior parts
- Sagittal plane: divides the body into left and right parts
- Axial plane: divides the body into superior and inferior parts

# Segmentation

After registering the image sequences, the combined information from different sequences results in a 3D volume with multiple channels. The primary goal is to define the boundaries of tissues, particularly tumors, in this volume. There is two segmentation approaches: a 2D approach and a 3D approach.

In the 2D approach, the 3D MRI volume is divided into 2D slices, each processed individually by a segmentation model. However, this method may lead to a loss of important 3D context, as adjacent slices may contain related information that the model cannot capture.

The 3D approach aims to address this limitation by feeding the entire MRI volume into the segmentation model, producing a 3D segmentation map. Due to memory and computational constraints, the volume is divided into smaller 3D subvolumes. While this approach captures context in the width, height, and depth dimensions, there is still a risk of losing spatial context within subvolumes.

# 2D U-Net and 3D U-Net

There is a popular architecture used for biomedical image segmentation called U-Net. The U-Net comprises two paths: a contracting path, involving repeated down convolutions and pooling operations, and an expanding path, involving up-sampling and up-convolution steps. The architecture, named for its U-like shape, demonstrated success in tasks such as cell tracking. In the 2D approach, the U-Net can be trained on input-output pairs of 2D slices for segmentation.

The 3D U-Net accommodates 3D subvolumes by replacing 2D operations with their 3D counterparts. The 3D convolutions and pooling layers allow the model to process 3D subvolumes, generating outputs for every voxel (3D pixel representation) in the volume and specifying the probability of a tumor. This extension enables the 3D U-Net to be trained on subvolume input and outputs as part of the 3D segmentation approach.

# Data Augmentation for Segmentation

Now the focus is on the technique of data augmentation applied to the training of segmentation models. How, similar to the approach used for chest x-rays, data augmentation can be implemented in segmentation tasks. However, there are key differences, including the presence of segmentation outputs. When transforming input images, such as rotation, corresponding adjustments must be made to the output segmentations. Additionally, since segmentation involves 3D volumes rather than 2D images, transformations need to apply to the entire 3D volume.

With these considerations, it's suggested that the components for training a brain tumor segmentation model are nearly in place. The final aspect to address is the loss function. The need for a loss function that quantifies the error by comparing the model's predictions to the ground truth. A simplified 2D example is presented, demonstrating how the output of the segmentation model (P) is compared to the ground truth (G) at specific pixel locations to assess the accuracy of tumor predictions in the context of brain tumor segmentation.

# Loss Function for Image Segmentation

The representation of prediction (p) and ground truth (g) values in a table, where each row corresponds to a cell location with associated probability and ground truth values. The soft dice loss, a popular loss function for segmentation models, is proposed for optimizing the segmentation model. The soft dice loss is particularly advantageous in handling imbalanced data, crucial in brain tumor segmentation where tumor regions constitute a small fraction of the brain.

The soft dice loss measures the error by assessing the overlap between prediction map (P) and ground truth map (G). The objective is to maximize the overlap, indicated by a large fraction. When G is 1, P should be close to 1, and when G is 0, P should be close to 0. The loss is computed as 1 minus this fraction, where a higher loss corresponds to a small overlap and a low loss to a high overlap.

To illustrate the computation of the loss, an example: multiplying P and G element-wise to obtain pigi, and then calculating the sum of squares of pi and gi for the denominator. The soft dice loss is then computed as 1 minus 2 times the product of P and G divided by the sum of squares of pi and gi. The resulting loss, approximately 0.2, serves as a measure of error for the given prediction and ground truth.