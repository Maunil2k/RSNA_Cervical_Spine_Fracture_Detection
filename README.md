# RSNA Cervical Spine Fracture Detection

The goal of this competition was to detect fracture in the specific section of spinal cord known as the cervical spine ranging from C1-C7.
<img src= "https://user-images.githubusercontent.com/51321172/201368336-2f6f0e1b-9733-4da3-89b2-aeeb95ddc80e.png" height="400" width="150" align="left">
The competition was evaluated on weighted log loss as show below.<br />
L<sub>ij</sub>=−w<sub>j</sub>∗[y<sub>ij</sub>∗log(p<sub>ij</sub>)+(1−y<sub>ij</sub>)∗log(1−p<sub>ij</sub>)].<br />
The training dataset consisted of 2019 patient samples with DICOM file slice less than 1mm. Hence, total number of slices added upto 711601 image arrays. Python modules such as GDCM and pylibjpeg like were additionally needed to read the pixel array of these files. It also consisted of 3D segmentations formed using 3D UNet. Due to the availability of huge dataset, I decided to finetune Vision Transformer. The model was originally proposed in the research paper [An Image is worth 16 x 16 words: Transformers for Image Recognition at Scale](https://arxiv.org/pdf/2010.11929v2.pdf) and was an attempt to introduce transformer model to the world of computer vision. One huge downside to the transformer model is that it needs huge dataset to achieve the SOTA CNN results.<br /><br /><br /><br /><br /><br />

# My Approach:
The approach to the problem was very similar to traditional boosting technique. We finetune the model on first batch, say 15000 slices, save the model and again finetune the same saved model on next batch of 15000, eventually repeating the same procedure.
Although after some iterations of the process, the public score saturated at a particular and deteriorated after 4 iterations of the process. The best public score that I received was 0.5955 (based on weighted log loss).


# Winner's solution:
This problem can be best solved using 3D Deep learning techniques. Unfortunately, I haven't explored the field of the 3D CV as of now. The toppers solution lies in the domain of 3D CV and can be found [here](https://www.kaggle.com/competitions/rsna-2022-cervical-spine-fracture-detection/discussion/362787).

# Final word:
The approach I used may not be the smartest one out there, hence, it might be wise to solve this problem using 3D deep learning approaches for better real world applications.

# References:
1) Competition: [RSNA 2022 Cervical Spine Fracture Detection](https://www.kaggle.com/competitions/rsna-2022-cervical-spine-fracture-detection)
2) Spinal Cord Image: https://en.wikipedia.org/wiki/Vertebral_column#/media/File:Gray_111_-_Vertebral_column-coloured.png
