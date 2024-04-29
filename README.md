# Impact of social media filters in Biometrics 

This is the official repository of "Facial Biometrics in the Social Media Era: An in-Depth Analysis of the Challenge Posed by Beautification Filters" submitted to IEEE Transactions on Biometrics, Behavior, and Identity Science.

Automatic beautification through social media filters has gained popularity in recent years. Users apply face filters to adhere to beauty standards, posing challenges to the reliability of facial images and complicating tasks like automatic face recognition. In this repository, we present the results of our work, where the impact of digital beautification is assessed, focusing on the most popular social media filters from three different platforms, on a range of AI-based face analysis technologies: face recognition, gender classification, apparent age estimation, weight estimation, and heart rate assessment.

# FFMF database

The FFMF dataset is composed of 24312 images and 260 videos belonging to the three categories, original, uploaded, and beautified. In the results presented in this repository, according to their source database, the images and videos of the FFMF are referred to as 1) FFMF-VIP, 2) FFMF-CALFW and 3) FFMF-COHFACE. 

In the following diagram, we present the pipeline for the FFMF dataset creation. The upload of content and application of filters on social networks has some requirements: filters have to be applied online, manually, and to one image or video at a time, with a maximum number of seconds (s) and a restriction of 30 frames per second (fps) for an uploaded video. Following all these prerequisites and to ease the process of manually applying the filters, we created 15s videos with the images originally in CALFW and VIP\_attribute, with each image displayed for 0,3 seconds (i.e. 10 frames). The videos are then passed through the different social networks to be filtered. Similarly, the videos from the COHFACE dataset are beautified with Instagram filters. 

When content is uploaded to SNs, it goes through operations such as compression, resizing, and cropping. The original images were uploaded to and downloaded from the different social media platforms obtaining the "uploaded" category in the database. In our experiments, we consider "uploaded" as a baseline to isolate the impact that filters have on the different tasks studied, excluding all other factors listed above. By comparing the performance of the models on the original and uploaded sets, we ensure that any increase or decrease in performance displayed is solely due to the beautification filters. 

![ffmf_dataset_creation](https://github.com/nmirabeth/filters_biometrics/assets/48354399/b9fa6714-e750-4df5-a6b9-31f70f7eea40)

More information on how to obtain the FFMF database can be found at: https://ffmf.eurecom.fr/

### Image differences

![differences](https://github.com/nmirabeth/filters_biometrics/assets/48354399/06eeb0f4-b5cf-4053-bdbb-b16780575c5a)

From left to right top row: Original image, Thinner_face (Instagram filter), Mellow_glow (Snapchat filter) and Belle (Tiktok filter). 
Differences between original and filtered images are displayed in the bottom row. Changes are not easily noticeable by the naked eye.

# Technologies evaluated

### Face verification

- ArcFace [13] (Implementation: https://github.com/deepinsight/insightface)
- MagFace [14] (Implementation: https://github.com/IrvingMeng/MagFace)

### Gender classification

- Deepface [15]
- cvlib [16]

### Apparent age estimaiton

- DEX [17] (Implementation: https://github.com/siriusdemon/pytorch-DEX)

### Weight estimation

- ResNet50 [18]

### Heart Rate estimation

- 3DCNN [19]

# Results

-- Best performances in green and worst in red --

![table1](https://github.com/nmirabeth/filters_biometrics/assets/48354399/d865bc8a-9368-4a03-8550-66c646d61dc7)


Table 1: Works addressing the impact of beautification in different manners. We select a representative set of papers based on the date of publication and number of citations. We present three pieces of research per beautification type.

![table2](https://github.com/nmirabeth/filters_biometrics/assets/48354399/5abad4e1-411b-4fd0-b45a-69a789fcbdfd)

Table 2: Overview of categories and face features modified by filters from Instagram, Snapchat, and TikTok. All filters except ”Thinner face” include Colour Adjustment (CA).

![table3](https://github.com/nmirabeth/filters_biometrics/assets/48354399/dd9dadad-1838-437b-8449-9864a0954dbf)

Table 3: SSIM coefficient between the original and processed images of the FFMF extended database. Results are apportioned by gender: female (F) and male (M).

![table4](https://github.com/nmirabeth/filters_biometrics/assets/48354399/cfb7e2b4-da5d-43a7-af2c-90979bd4dc13)

Table 4: Assessment of the impact of beautification filters on face verification. Accuracy, corresponding standard deviation (±) and the Area Under the ROC Curve (AUC) are reported. The higher the value, the better.

![table5](https://github.com/nmirabeth/filters_biometrics/assets/48354399/a919eeed-21a4-4e5e-b669-0d47b18719cb)

Table 5: Assessment of the impact of beautification filters on face verification. Performances are reported in terms of FNMR (%) at fixed values of FMR. The lower the value, the better.

![table6](https://github.com/nmirabeth/filters_biometrics/assets/48354399/43c51e7a-d57d-4c8c-9422-016828e66d05)

Table 6: Assessment in terms of classification accuracy of the impact of beautification filters on gender classification. The higher the value, the better.

![table7](https://github.com/nmirabeth/filters_biometrics/assets/48354399/f361ee9f-af1c-4fc0-a29c-b0d7d8d8635f)

Table 7: Assessment of the impact of beautification filters on age estimation. The lower the Mean, SD and MAE, the better. The higher the ρ, the better.

![table8](https://github.com/nmirabeth/filters_biometrics/assets/48354399/be812290-b56b-4d4c-9e53-f2ddd4615222)

Table 8: Assessment of the impact of SN filters on weight estimation on the FFMF-VIP. The lower the Me, SD and MAE, the better. The higher the ρ and PAP, the better.

![weight_apportioned](https://github.com/nmirabeth/filters_biometrics/assets/48354399/d3c9f6cf-c5c9-4770-b919-012c47398a7b)

Table 8b: Assessment of the impact of SN filters on weight estimation on the FFMF-VIP apportioned by gender. The lower the Me, SD and MAE, the better. The higher the ρ and PAP, the better.

![table9](https://github.com/nmirabeth/filters_biometrics/assets/48354399/a89a4edf-05dd-431d-9244-c74e4a6e0ee5)

Table 9: Assessment of the impact of SN filters on HR estimation on FFMF-COHFACE. The lower the SD and MAE, the better. The higher the ρ, the better

![table10](https://github.com/nmirabeth/filters_biometrics/assets/48354399/db239b1a-7b06-421b-b1e3-7946ac94f47d)

Table 10: Impact of each filter on the analyzed facial processing tasks. The filters are ranked from lower to higher aggressivity according to SSIM values and the impact is measured by taking the compressed images as a baseline.


# Citing

-- Coming soon --

# Acknowledgement

This work has been partially supported by the European CHIST-ERA program (grant agreement CHIST-ERA-19-XAI-011).

# References

[1] S. Ueda and T. Koyama, “Influence of make-up on facial recognition,” Perception, vol. 39, no. 2, pp. 260–264, 2010

[2] C. Chen, A. Dantcheva, and A. Ross, “Impact of facial cosmetics on automatic gender and age estimation algorithms,” in 2014 International Conference on Computer Vision Theory and Applications (VISAPP), vol. 2. IEEE, 2014, pp. 182–190

[3] C. Rathgeb, P. Drozdowski, D. Fischer, and C. Busch, “Vulnerability assessment and detection of makeup presentation attacks,” in 2020 8th International Workshop on Biometrics and Forensics (IWBF). IEEE, 2020, pp. 1–6.

[4] C. Rathgeb, D. Dogan, F. Stockhardt, M. De Marsico, and C. Busch, “Plastic surgery: An obstacle for deep face recognition?” in Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops, 2020, pp. 806–807.

[5] S. Suri, A. Sankaran, M. Vatsa, and R. Singh, “On matching faces with alterations due to plastic surgery and disguise,” in 2018 IEEE 9th International Conference on Biometrics Theory, Applications and Systems (BTAS). IEEE, 2018, pp. 1–7.

[6] R. Singh, M. Vatsa, H. S. Bhatt, S. Bharadwaj, A. Noore, and S. S. Nooreyezdan, “Plastic surgery: A new dimension to face recognition,” IEEE Transactions on Information Forensics and Security, vol. 5, no. 3, pp. 441–448, 2010.

[7] C. Rathgeb, A. Dantcheva, and C. Busch, “Impact and detection of facial beautification in face recognition: An overview,” IEEE Access, vol. 7, pp. 152 667–152 678, 2019. 

[8] A. Bharati, M. Vatsa, R. Singh, K. W. Bowyer, and X. Tong, “Demography-based facial retouching detection using subclass supervised sparse autoencoder,” in 2017 IEEE international joint conference on biometrics (IJCB). IEEE, 2017, pp. 474–482.

[9] H. Chen, W. Li, X. Gao, and B. Xiao, “Aep-gan: Aesthetic enhanced perception generative adversarial network for asian facial beauty synthesis,” Applied Intelligence, pp. 1–28, 2023. 

[10] P. Riccio, B. Psomas, F. Galati, F. Escolano, T. Hofmann, and N. M. Oliver, “Openfilter: A framework to democratize research access to social media ar filters,” in Thirty-sixth Conference on Neural Information Processing Systems Datasets and Benchmarks Track, 2022.

[11] P. Hedman, V. Skepetzis, K. Hernandez-Diaz, J. Bigun, and F. Alonso-Fernandez, “On the effect of selfie beautification filters on face detection and recognition,” Pattern Recognition Letters, vol. 163, pp. 104–111, 2022.

[12] N. Mirabet-Herranz, C. Galdi, and J.-L. Dugelay, “Impact of digital face beautification in biometrics,” in EUVIP 2022, 10th European Workshop on Visual Information Processing, 2022. 

[13] Deng, J., Guo, J., Xue, N., & Zafeiriou, S. (2019). Arcface: Additive angular margin loss for deep face recognition. In Proceedings of the IEEE/CVF conference on computer vision and pattern recognition (pp. 4690-4699).

[14] Meng, Q., Zhao, S., Huang, Z., & Zhou, F. (2021). Magface: A universal representation for face recognition and quality assessment. In Proceedings of the IEEE/CVF conference on computer vision and pattern recognition (pp. 14225-14234).

[15] https://github.com/serengil/deepface

[16] https://github.com/arunponnusamy/cvlib

[17] Rothe, R., Timofte, R., & Van Gool, L. (2015). Dex: Deep expectation of apparent age from a single image. In Proceedings of the IEEE international conference on computer vision workshops (pp. 10-15).

[18] Mirabet-Herranz, N., Mallat, K., & Dugelay, J. L. (2023, January). New insights on weight estimation from face images. In 2023 IEEE 17th International Conference on Automatic Face and Gesture Recognition (FG) (pp. 1-6). IEEE.

[19] Mirabet-Herranz, N., Mallat, K., & Dugelay, J. L. (2022, August). Deep Learning for Remote Heart Rate Estimation: A Reproducible and Optimal State-of-the-Art Framework. In International Conference on Pattern Recognition (pp. 558-573). Cham: Springer Nature Switzerland.
