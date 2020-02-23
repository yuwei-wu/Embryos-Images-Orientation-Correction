# Embryos-3D-Images-Transfer

This is a idea for auto match of chicken embryos 3D images. I do not have the medical knowledge and backgrounds so some parts of it include more details of terms and notions.


## 1.Problem Statement

The research is about to analysis the cardiac development under the influence of different genes. The process from CT to 3D has been done and our task is to rotate or say registrate the images to keep its consistent orentation of the heart so that the pathologists will find it easier to analyze the phenotype of the egg. The challenge is that the embroyo's 3D images are develop with it grows and the embryos can move in the egg so that the 3D match objects are not the same in each stage.(more specific details of its movement and development can be seen in <a href="#1" >[1]</a>  )


### 1.1 Some explanation of the items

#### (1) long axis of heart

Because the development of the embryos changes with time, the long axis orientation of heart also varies.

<img width="400" height="300" src="https://image.slidesharecdn.com/cardiacus-090930141613-phpapp02/95/cardiac-us-16-728.jpg?cb=1254320229"/>

## 1.2. Input data

#### (1) CT images

The images from micro CT. 

#### (2) some labeled images from pathologists

Some couples of images, one is the original image, and the other is the processed images with correct orientation. So this question can be regarded as the supervised learning problems with input of images and output of transformed matrix or output images.

## 2.Assumptions

#### (1) CT pictures has the enough precision (we use micro-CT) and the 3D reconstruction process is good enough to reduce potential errors. 

In the problem description, they get the resulting 3d images and then do some rotations. So it's assumed that the 3D reconstruction has been done (or if not, we can use many tools such as the ASTRA Toolbox with a lot of reconstruction algorithms to build the 3D images.)

#### (2) The impact of motion artifacts and other artifacts has been reduced. 

<a href="#2" >[2]</a> has demonstrate how the motion artifact influence our images. It's assumed that some pictures with many artifacts have been remove and the images is not blur to influence the work of pathologists.  

#### (3) The chicken embryos are in Ovo and in vivo

According to the question, they need to determine phenotype of each egg, so it's the case that we observe embryos in the eggshell and in vivo so that they may have movements. There are some [experiments](https://abt.ucpress.edu/content/74/9/628) as ex ovo and the observation is not quite similar.

#### (4) The labeled data are well distributed and correct.

It means the labeled data cover the whole developmenet process of the embryo. Because the phenotype of chicken embryos changed dramatically if we lost some stages of this development, it may cause error with the use of labeled data. Also, we can consider the labeled data as ground truth (the labeled data has been filtraded).

#### (5) The missing data, error images have been removed. (all data is valid)

Just to make this question more spefific and only focus on the algorithms (in actual industrial field, it is often the case to have error input data). If the data has not been prepocessing, we can just write some scripts to check and select the valid data.

#### (6) The movement of heart include non-rigid transformation.

## 2.5 Data prepocessing

If the images are not as perfect as our assumptions, we need to clean and reconstruct the data first. There's something we can do:

- Check the scale, size or other information of the images.
- Remove some images if they do not contain useful info.

## 3. 

If there is no labeled images, there are some steps for developing the rotation of the images. Firstly we can 

### 3.1.Reading 3D Images

There are a lot of types of medical images as dcm，nii.gz，nrrd，mha，mhd. suppose we use dcm  pydicom

### 3.2.Filtering

### 3.3.Segementation and rotation

Because the position of the heart in the embryo can change and not proper to match the whole 3D image of the embryo, therefore it's better to extract or partition the cardiac part and then match it.

algorithm ideas:


## 4.Netrual network






## 5.Sample analysis







## 6.Conclusion








## 7.Other discussion

Last year, kaggle has a competition [RSNA Intracranial Hemorrhage Detection](https://www.kaggle.com/c/rsna-intracranial-hemorrhage-detection/) that use the 3D images to build an algorithm to detect acute intracranial hemorrhage. I do not research more about the types of heart disease and mutation. But maybe the presence and degree of cardiac abnormalities can also be labeled and we can directly use these and machine learning method to process more images.

## 7.Reference

<a id="1"/> 1.[Embryonic development of Columba livia(Aves: Columbiformes) from an altricial-precocial perspective](https://www.researchgate.net/publication/260764808_Embryonic_development_of_Columba_liviaAves_Columbiformes_from_an_altricial-precocial_perspective)

<a id="2"/> 2.[Motion-Artifact-Free In Vivo Imaging Utilizing Narcotized Avian Embryos In Ovo](https://www.researchgate.net/publication/44677254_Motion-Artifact-Free_In_Vivo_Imaging_Utilizing_Narcotized_Avian_Embryos_In_Ovo)


<a id="3"/> 3.[Quantitative Three-DimensionalAnalysis of Embryonic ChickMorphogenesis Via MicrocomputedTomography](https://anatomypubs.onlinelibrary.wiley.com/doi/pdf/10.1002/ar.21276)

<a id="4"/> 4.[Automated Segmentation and Object Classification ofCT Images: Application toIn VivoMolecular Imaging ofAvian Embryos](http://downloads.hindawi.com/journals/ijbi/2013/508474.pdf)
