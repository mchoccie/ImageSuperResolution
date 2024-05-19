# ImageSuperResolution
An experiment to test different state of the art image super resolution models using computer vision techniques

# Important references
## Datasets
- 91 Image Dataset Decomposed: https://github.com/yjn870/SRCNN-pytorch
- 91 Image Dataset Raw: https://www.kaggle.com/datasets/ll01dm/t91-image-dataset
- 91 Image Dataset Decomposed (FSRCNN): https://github.com/yjn870/FSRCNN-pytorch
## Cited Code Repositories:
- https://github.com/yjn870/SRCNN-pytorch
- https://github.com/yjn870/FSRCNN-pytorch
- https://github.com/Lornatang/VDSR-PyTorch/blob/master/model.py
- https://github.com/NielsRogge/Transformers-Tutorials/blob/master/Swin2SR/Perform_image_super_resolution_with_Swin2SR.ipynb
- https://goodboychan.github.io/python/deep_learning/vision/tensorflow-keras/2020/10/13/01-Super-Resolution-CNN.html#Build-SR-CNN-Model

# Contributions
This repository contains a set of files which represents our attempt at testing and experimenting with image super
resolution models. In this repository we have 7 notebooks in total and we wish to outline what each of the notebooks
represent. The raw 91 image dataset lives in a folder called train in this repository.

## Our Contribution
The notebooks FR, SRCNN and VDSR all represent state of the art models which have trained on the 91 Image Dataset Raw.
In these notebooks we manually created a data set where we reduced the resolution of all images to create our low resolution training set. We also scaled all images to be of consistent 400x400 size so the train loader works effectively.
In these notebooks we also created our own metric called an average psnr. Essentially, the average psnr represents the overall quality improvement of the generated image when compared with a low resolution one. The higher the average psnr improvement, the better the model has performed

## Comparing with Existing Set Ups
The notebooks FR2, SRCNN2 and VDSR2 all represent models which have trained on the 91 Image Dataset decomposed. In these notebooks, we effectively copy the entire structure that we see in the following repository: https://github.com/yjn870/SRCNN-pytorch. The purpose of this is to compare how our data preparation process compares with the way the authors have conducted this data preparation process. The decomposed dataset comes from the 91 image data set, except all 91 images have been split into patches of size 33x33. This has resulted in approximately 33,000 images which have been stored in h5 files. These images have also been preprocessed to contain 1 channel in the YCrCb color scheme whereas our implementation is tested on 3 channels in the RGB color scheme. 

# Sections
Each section in the notebook has clearly been delineated with whether it falls under "DATA ACQUISITION AND PREPROCESSING", "STATE OF THE ART MODEL", "MODEL ARCHITECTURE AND FINETUNING", "MODEL EVALUATION" and "INFERENCE OPTIMIZATION AND REAL TIME TEST". For our optimization step used torch script in order to restructure the model architecture to conduct model processes more efficiently. We noticed definite speed improvements in this process.


