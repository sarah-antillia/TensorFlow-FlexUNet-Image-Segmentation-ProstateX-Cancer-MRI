<h2>TensorFlow-FlexUNet-Image-Segmentation-ProstateX-Cancer-MRI (2026/11/22)</h2>
Toshiyuki Arai<br>
Software Laboratory antillia.com<br><br>
This is the first experiment of Image Segmentation for <b>ProstateX-Cancer-MRI </b>
 based on
our <a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">TensorFlowFlexUNet Model</a>
 (<b>TensorFlow Flexible UNet Image Segmentation Model for Multiclass</b>) and a 384x384-pixel PNG
<a href="https://drive.google.com/file/d/1BoqKwdXhHow6FIdyhlWcGKSs3xYQP3Zs/view?usp=sharing">
<b>ProstateX-Cancer-MRI-ImageMask-Datasaet.zip</b></a>
 (<a href="https://www.mit.edu/~amini/LICENSE.md">MIT</a>
) derived  by us from the Kaggle
<br><br>
<a href="https://www.kaggle.com/datasets/ajithdari/prostatex-mri-image-and-mask-dataset">
<b>ProstateX MRI Image and Mask Dataset
</b>
</a> by Mukesh Dilip .
<br><br>
<hr>
<b>Actual Image Segmentation for ProstateX-Cancer-MRI Images of 384x384 pixels</b><br>
As shown below, the inferred masks resemble the ground-truth masks. <br>
<br>
<br>
<table>
<tr>
<th width="320" height="auto">Input: image</th>
<th width="320" height="auto">Mask (ground_truth)</th>
<th width="320" height="auto">Prediction: inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/images/10001_30.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/masks/10001_30.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_output/10001_30.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/images/10038_114.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/masks/10038_114.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_output/10038_114.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/images/10051_75.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/masks/10051_75.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_output/10051_75.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>1. Dataset Citation</h3>
The dataset used here was derived from the following Kaggle:<br><br>

<a href="https://www.kaggle.com/datasets/ajithdari/prostatex-mri-image-and-mask-dataset">
<b>ProstateX MRI Image and Mask Dataset
</b>
</a> <br>
<b>3D Prostate MRI Images & Segmentation Masks in NIfTI Format</b>
<br>by Mukesh Dilip .

<br><br>
The following explanation was taken from the website above. 
<br><br>
<b>About Dataset</b><br>
This dataset contains 3D prostate MRI images and their corresponding segmentation masks 
in NIfTI (.nii) format. It is organized at the patient level, with each MRI image paired 
with its respective mask.
<br><br>
A CSV metadata file is included with information such as Patient ID, image and mask 
filenames, image/mask shapes, voxel spacing, shape matching status, image intensity 
statistics, mask voxel count, and processing status.
<br><br>

<b>License</b><br>
Unknown
<br>
<br>
<h3>
2. ProstateX-Cancer-MRI ImageMask Dataset
</h3>
<h3>2.1 Download ImageMask Dataset</h3>
 If you would like to train this ProstateX-Cancer-MRI Segmentation model,
 please download the dataset from the Google Drive 
<a href="https://drive.google.com/file/d/1BoqKwdXhHow6FIdyhlWcGKSs3xYQP3Zs/view?usp=sharing">
<b>ProstateX-Cancer-MRI-ImageMask-Datasaet.zip</b>.
</a> 
Expand the downloaded and put it under the <b>./dataset</b> folder.
<br>
<pre>
./dataset
└─ProstateX-Cancer-MRI
    ├─test
    │   ├─images
    │   └─masks
    ├─train
    │   ├─images
    │   └─masks
    └─valid
         ├─images
         └─masks
</pre>
<br>
<b>ProstateX-Cancer-MRI Statistics</b><br>
<img src ="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/ProstateX-Cancer-MRI_Statistics.png" width="512" height="auto"><br>
<br>
As shown above, the number of images in the training and valid datasets is large enough to use for the
 training set of our segmentation model.
<br>
<br>
<h3>2.2 Train Sample Images and Masks</h3>
<b>Train_sample_images</b><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/asset/train_images_sample.png" width="1024" height="auto">
<br>
<b>Train_sample_masks</b><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/asset/train_masks_sample.png" width="1024" height="auto">
<br>
<h3>
3. Train TensorFlowFlexUNet Model
</h3>
 We trained the ProstateX-Cancer-MRI TensorFlowFlexUNet model using the following
<a href="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/train_eval_infer.config"> <b>train_eval_infer.config</b></a> file. <br>
Please move to ./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI and run the following bat file.<br>
<pre>
>1.train.bat
</pre>
This runs the following command.<br>
<pre>
>python ../../../src/TensorFlowFlexUNetTrainer.py ./train_eval_infer.config
</pre>
<hr>
<b>Model parameters</b><br>
Defined a small <b>base_filters=16 </b> and large <b>base_kernels=(11,11)</b> for the first Conv Layer of Encoder Block of 
<a href="./src/TensorFlowFlexUNet.py">TensorFlowFlexUNet.py</a> 
and a large <b>num_layers=8</b> (including a bridge between Encoder and Decoder Blocks).
<pre>
[model]
; You may specify your own UNet class derived from our TensorFlowFlexModel
model         = "TensorFlowFlexUNet"
generator     =  False
image_width    = 384
image_height   = 384
image_channels = 3
num_classes    = 2
base_filters   = 16
base_kernels   = (11,11)
num_layers     = 8
dropout_rate   = 0.05
dilation       = (1,1)
</pre>
<b>Learning rate</b><br>
Defined a small learning rate.  
<pre>
[model]
learning_rate  = 0.00007
</pre>
<b>Loss and metrics functions</b><br>
Specified "categorical_focal_dice_loss" and <a href="./src/dice_coef_multiclass.py">"dice_coef_hybrid"</a>.<br>
<pre>
[model]
loss           = "categorical_focal_dice_loss"
metrics        = ["dice_coef_hybrid"]
hybrid_alpha   = 1.4
hybrid_beta    = 0.6
</pre>
<b>Dataset class</b><br>
Specified <a href="./src/ImageCategorizedMaskDataset.py">ImageCategorizedMaskDataset</a> class.<br>
<pre>
[dataset]
class_name    = "ImageCategorizedMaskDataset"
</pre>
<br>
<b>Learning rate reducer callback</b><br>
Enabled the learning_rate_reducer callback and a small reducer_patience.
<pre> 
[train]
learning_rate_reducer = True
reducer_factor     = 0.4
reducer_patience   = 4
</pre>
<b>Early stopping callback</b><br>
Enabled early stopping callback with the patience parameter.
<pre>
[train]
patience      = 10
</pre>
<b>RGB Color map</b><br>
Specified RGB color map dict for ProstateX-Cancer-MRI 1+1 classes.<br>
<pre>
[mask]
mask_datatyoe    = "categorized"
mask_file_format = ".png"
;ProstateX-Cancer-MRI RGB color map dict for 1+1 classes.
; Background: black,  Cancer: dark_red
rgb_map = {(0,0,0):0,(210,20,20):1}
</pre>
<b>Epoch change inference callback</b><br>
Enabled <a href="./src/EpochChangeInferencer.py">epoch_change_infer callback</a></b>.<br>
<pre>
[train]
epoch_change_infer       = True
epoch_change_infer_dir   =  "./epoch_change_infer"
num_infer_images         = 6
</pre>
By using this callback, on every epoch change, the inference procedure can be called
 for 6 images in the <b>mini_test</b> folder. This will help you confirm how the predicted mask changes 
 at each epoch during your training process.<br> 
<br> 
<!--
As shown below, early in the model training, the predicted masks from our FlexUNet segmentation model showed 
discouraging results.
 However, as training progressed through the epochs, the predictions gradually improved. 
 <br> 
<br>
-->
<b>Epoch_change_inference output at starting (epoch 1,2,3)</b><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/asset/epoch_change_infer_at_start.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at middlepoint (epoch 23,24,25)</b><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/asset/epoch_change_infer_at_middlepoint.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at ending (epoch 48,49,50)</b><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/asset/epoch_change_infer_at_end.png" width="1024" height="auto"><br>
<br>
In this experiment, the training process was terminated at epoch 50.<br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/asset/train_console_output_at_epoch50.png" width="1024" height="auto"><br>
<br>
<a href="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/eval/train_metrics.csv">train_metrics.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/eval/train_metrics.png" width="520" height="auto"><br>
<br>
<a href="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/eval/train_losses.csv">train_losses.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/eval/train_losses.png" width="520" height="auto"><br>
<br>
<h3>
4. Evaluation
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI</b> folder,
and run the following bat file to evaluate the TensorFlowUNet model for ProstateX-Cancer-MRI.<br>
<pre>
>./2.evaluate.bat
</pre>
This runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetEvaluator.py ./train_eval_infer.config
</pre>
Evaluation console output:<br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/asset/evaluate_console_output_at_epoch50.png" width="1024" height="auto">
<br><br>Image-Segmentation-ProstateX-Cancer-MRI

<a href="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/evaluation.csv">evaluation.csv</a><br>
The loss (categorical_focal_dice_loss) on this ProstateX-Cancer-MRI/test was very low, 
and dice_coef_hybrid was very high,
 as shown below.
<br>
<pre>
categorical_focal_dice_loss,0.0042
dice_coef_hybrid,0.9902
</pre>
<br>
<h3>
5. Inference
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI</b> folder
and run the following bat file to infer segmentation regions for images using the trained TensorFlowUNet model for ProstateX-Cancer-MRI.<br>
<pre>
>./3.infer.bat
</pre>
This runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetInferencer.py ./train_eval_infer.config
</pre>
<hr>
<b>mini_test_images</b><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/asset/mini_test_images.png" width="1024" height="auto"><br>
<b>mini_test_mask(ground_truth)</b><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/asset/mini_test_masks.png" width="1024" height="auto"><br>
<hr>
<b>Inferred test masks</b><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/asset/mini_test_output.png" width="1024" height="auto"><br>
<br>
<hr>
<b>Enlarged images and masks for ProstateX-Cancer-MRI Images of 384x384 pixels</b><br>
As shown below, the inferred masks look similar to the ground truth masks.<br>
<br><br>
<table>
<tr>
<th width="320" height="auto">Image</th>
<th width="320" height="auto">Mask (ground_truth)</th>
<th width="320" height="auto">Inferred-mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/images/10003_35.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/masks/10003_35.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_output/10003_35.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/images/10012_61.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/masks/10012_61.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_output/10012_61.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/images/10022_7.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/masks/10022_7.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_output/10022_7.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/images/10038_11.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/masks/10038_11.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_output/10038_11.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/images/10042_26.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/masks/10042_26.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_output/10042_26.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/images/10062_46.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test/masks/10062_46.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_output/10062_46.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>

<h3>
6. 3D Volume Segmentation
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI</b> folder
, and run the following bat file to infer images segmentation for 2D slices of 3D volume NIfTI files
 by the Trained-TensorFlowFlexUNet model for ProstateX-Cancer-MRI.<br>
<pre>
>./5.infer3d.bat
</pre>
This simply runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNet3DInferencer.py ./train_eval_infer.config
</pre>
<b>infer3d section </b> in <a href="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/train_eval_infer.config">
train_eval_infer.config
<a></b>
<pre>
[infer3d] 
;Specify an images_dir which contains NIfTI files
images_dir    = "./mini_test_3d/images/"
output_dir    = "./mini_test_3d_output/"
slice_shape_order = "hwd"
slice_normalize = True
slice_resize   = (384,384)
slice_rotation = "cv2.ROTATE_90_CLOCKWISE"
mask_overlay  = True
</pre>
<hr>
<b>Acutual Image Segmentation for 2D Slices of a ProstateX-Cancer-MRI NIfTI</b><br>
Some Slices, Inferred Masks and Mask overlays for a 3D volume <b>ProstateX-0070.nii</b> file in <b>ProstateX/image</b> 
folder.<br>
<br>
<br>
<table>
<tr>
<th>Image</th>
<th>Inferred-mask</th>
<th>Mask overlay</th>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/slices/10007.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/masks/10007.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/overlays/10007.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/slices/10011.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/masks/10011.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/overlays/10011.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/slices/10015.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/masks/10015.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/overlays/10015.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/slices/10020.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/masks/10020.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/overlays/10020.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/slices/10026.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/masks/10026.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/overlays/10026.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/slices/10032.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/masks/10032.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/mini_test_3d_output/ProstateX-0070.nii/overlays/10032.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>
7. MaskOverlay Video of 3D Volume Segmentation
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI</b> folder, and run the following bat file 
to generate <b>overlays.mp4</b> or <b>overlay.gif</b> for MaskOverlays of 3D Volume Segmentation. <br>
<pre>
>./6.video3d.bat
</pre>
This simply runs the following command.
<pre>
>python ../../../src/MaskOverlayVideoGenerator.py ./train_eval_infer.config
</pre>
<br>
<b>infer3d section </b> in <a href="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/train_eval_infer.config">
train_eval_infer.config
<a></b>
<pre>
[infer3d] 
mask_overlay  = True
;Specify ".mp4" or ".gif".
;video_fileformat  = ".mp4"
video_fileformat  = ".gif"
</pre>
<br>
<b>overlays.gif</b><br>
<img src="./projects/TensorFlowFlexUNet/ProstateX-Cancer-MRI/video_3d/overlays.gif">
<br>
<br>
<h3>
References
</h3>
<b>1. Evaluation of prostate segmentation algorithms for MRI: The PROMISE12 challenge</b><br>
Geert Litjens, Robert Toth, Wendy van de Ven, Caroline Hoeks, Sjoerd Kerkstra, Bram van Ginneken,<br>
Graham Vincent, Gwenael Guillard, Neil Birbeck, Jindang Zhang, Robin Strand, Filip Malmberg,<br>
Yangming Ou, Christos Davatzikos, Matthias Kirschner, Florian Jung, Jing Yuan, Wu Qiu, Qinquan Gao,<br>
Philip “Eddie” Edwards, Bianca Maan, Ferdinand van der Heijden, Soumya Ghose, Jhimli Mitra,<br>
Jason Dowling, Dean Barratt, Henkjan Huisman, Anant Madabhushi<br>
<a href="https://www.sciencedirect.com/science/article/abs/pii/S1361841513001734?via%3Dihub">
https://www.sciencedirect.com/science/article/abs/pii/S1361841513001734?via%3Dihub
</a><br><br>
<b>2. TensorFlow-FlexUNet-Image-Segmentation-PROMISE12-Prostate-Cancer</b><br>
Toshiyuki Arai<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-PROMISE12-Prostate-Cancer">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-PROMISE12-Prostate-Cancer
</a>
<br><br>
<b>3. TensorFlow-FlexUNet-Image-Segmentation-Transverse-Plane-Prostate-Cancer-MRI</b><br>
Toshiyuki Arai<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Transverse-Plane-Prostate-Cancer-MRI">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Transverse-Plane-Prostate-Cancer-MRI
</a>
<br><br>
<b>4. TensrFlow-FlexUNet-Image-Segmentation-Model</b><br>
Toshiyuki Arai<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model
</a>
<br><br>
