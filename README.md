# Chicken-Embryos-3D-Images-Registration

This is a idea for auto match of chicken embryos 3D images. I do not have the medical knowledge and backgrounds so some parts of it include more details of terms and notions.


## 1.Problem Statements

The research is about to analysis the cardiac development under the influence of different genes. The process from CT to 3D has been done and our task is to rotate or say registrate the images to keep its consistent orentation of the heart so that the pathologists will find it easier to analyze the phenotype of the egg. The challenge is that the embroyo's 3D images are develop with it grows and the embryos can move in the egg so that the 3D match objects are not the same in each stage.

![the development of embryo](https://www.researchgate.net/profile/Maria_Sandoval23/publication/260764808/figure/fig2/AS:669257205571587@1536574760268/Stages-of-mid-stage-embryonic-development-of-Columba-livia-Scale-2-mm.png)


### 1.1 Some explanation of the items

#### (1) long axis of heart

Because the development of the embryos in the 

![long axis of heart](https://image.slidesharecdn.com/cardiacus-090930141613-phpapp02/95/cardiac-us-16-728.jpg?cb=1254320229)


## 1.2. Input data

#### (1) CT images

#### (2) some labeled data 

Some couples of images, one is the original image, and the other is the processed images with correct orientation. So this question can be regarded as the supervised learning problems with input of images and output of transformed matrix or output images.

## 2.Assumptions

#### (1) CT pictures has the enough precision (we use micro-CT) and the 3D reconstruction process is good enough to reduce potential errors. 

#### (2) The impact of motion artifacts and other artifacts has been reduced. 

([[1]](https://www.researchgate.net/publication/44677254_Motion-Artifact-Free_In_Vivo_Imaging_Utilizing_Narcotized_Avian_Embryos_In_Ovo) has demonstrate how the motion artifact influence our images)

#### (3) The chicken embryos are in Ovo and in vivo

according to the question, they need to determine phenotype of each egg

(there are some [experiments](https://abt.ucpress.edu/content/74/9/628) ex ovo and the observation is not quite similar)

#### (4) The labeled data are well distributed and correct.
It means the labeled data cover the whole developmenet process of the embryo. Because the phenotype of chicken embryos changed dramatically if we lost some stages of this development, it may cause error with the use of labeled data. Also, we can consider the labeled data as ground truth (the labeled data has been filtraded).

#### (5) The missing data, error images have been removed. (all data is valid)
Just to make this question more spefific and only focus on the algorithms (in actual industrial field, it is often the case to have error input data). If the data has not been prepocessing, we can just write some scripts to check and select the valid data


 
## 3.Process

### 3.1.Reading 3D Images

There are a lot of types of medical images as dcm，nii.gz，nrrd，mha，mhd.

#### 3.1.1 factors to influence the embryos images.

### 3.2.Filtering

### 3.3.Segementation (only keep the heart part)

### 3.4 Image registration


algorithm ideas:

### 4.Sample analysis



## Reference

[1] [Motion-Artifact-Free In Vivo Imaging Utilizing Narcotized Avian Embryos In Ovo](https://www.researchgate.net/publication/44677254_Motion-Artifact-Free_In_Vivo_Imaging_Utilizing_Narcotized_Avian_Embryos_In_Ovo)

[2] [Quantitative Three-DimensionalAnalysis of Embryonic ChickMorphogenesis Via MicrocomputedTomography](https://anatomypubs.onlinelibrary.wiley.com/doi/pdf/10.1002/ar.21276)


[3] [Automated Segmentation and Object Classification ofCT Images: Application toIn VivoMolecular Imaging ofAvian Embryos](http://downloads.hindawi.com/journals/ijbi/2013/508474.pdf)

