# Impact of social media filters in Biometrics 

This is the official repository of "Facial Biometrics in the Social Media Era: An in-Depth Analysis of the Challenge Posed by Beautification Filters" submitted to IEEE Transactions on Biometrics, Behavior, and Identity Science.

Automatic beautification through social media filters has gained popularity in recent years. Users apply face filters to adhere to beauty standards, posing challenges to the reliability of facial images and complicating tasks like automatic face recognition. In this repository, we present the results of our work, where the impact of digital beautification is assessed, focusing on the most popular social media filters from three different platforms, on a range of AI-based face analysis technologies: face recognition, gender classification, apparent age estimation, weight estimation, and heart rate assessment.

# FFMF database

The FFMF dataset is composed of 24312 images and 260 videos belonging to the three categories, original, uploaded, and beautified. In the results presented in this repository, according to their source database, the images and videos of the FFMF are referred to as 1) FFMF-VIP, 2) FFMF-CALFW and 3) FFMF-COHFACE. 

In the following diagram, we present the pipeline for the FFMF dataset creation. The upload of content and application of filters on social networks has some requirements: filters have to be applied online, manually, and to one image or video at a time, with a maximum number of seconds (s) and a restriction of 30 frames per second (fps) for an uploaded video. Following all these prerequisites and to ease the process of manually applying the filters, we created 15s videos with the images originally in CALFW and VIP\_attribute, with each image displayed for 0,3 seconds (i.e. 10 frames). The videos are then passed through the different social networks to be filtered. Similarly, the videos from the COHFACE dataset are beautified with Instagram filters. 

When content is uploaded to SNs, it goes through operations such as compression, resizing, and cropping. The original images were uploaded to and downloaded from the different social media platforms obtaining the "uploaded" category in the database. In our experiments, we consider "uploaded" as a baseline to isolate the impact that filters have on the different tasks studied, excluding all other factors listed above. By comparing the performance of the models on the original and uploaded sets, we ensure that any increase or decrease in performance displayed is solely due to the beautification filters. 

![ffmf_dataset_creation](https://github.com/nmirabeth/filters_biometrics/assets/48354399/b9fa6714-e750-4df5-a6b9-31f70f7eea40)

More information on how to obtain the FFMF database can be found at: https://ffmf.eurecom.fr/

# Technologies evaluated

### Face verification

- ArcFace [1] (Implementation: https://github.com/deepinsight/insightface)
- MagFace [2] (Implementation: https://github.com/IrvingMeng/MagFace)

### Gender classification

- Deepface [3]
- cvlib [4]

### Apparent age estimaiton

- DEX [5] (Implementation: https://github.com/siriusdemon/pytorch-DEX)

### Weight estimation

- ResNet50 [6]

### Heart Rate estimation

- 3DCNN [7]

# Citing

-- Coming soon --

# Acknowledgement

This work has been partially supported by the European CHIST-ERA program (grant agreement CHIST-ERA-19-XAI-011).

# References
[1] Deng, J., Guo, J., Xue, N., & Zafeiriou, S. (2019). Arcface: Additive angular margin loss for deep face recognition. In Proceedings of the IEEE/CVF conference on computer vision and pattern recognition (pp. 4690-4699).

[2] Meng, Q., Zhao, S., Huang, Z., & Zhou, F. (2021). Magface: A universal representation for face recognition and quality assessment. In Proceedings of the IEEE/CVF conference on computer vision and pattern recognition (pp. 14225-14234).

[3] https://github.com/serengil/deepface

[4] https://github.com/arunponnusamy/cvlib

[5] Rothe, R., Timofte, R., & Van Gool, L. (2015). Dex: Deep expectation of apparent age from a single image. In Proceedings of the IEEE international conference on computer vision workshops (pp. 10-15).

[6] Mirabet-Herranz, N., Mallat, K., & Dugelay, J. L. (2023, January). New insights on weight estimation from face images. In 2023 IEEE 17th International Conference on Automatic Face and Gesture Recognition (FG) (pp. 1-6). IEEE.

[7] Mirabet-Herranz, N., Mallat, K., & Dugelay, J. L. (2022, August). Deep Learning for Remote Heart Rate Estimation: A Reproducible and Optimal State-of-the-Art Framework. In International Conference on Pattern Recognition (pp. 558-573). Cham: Springer Nature Switzerland.
