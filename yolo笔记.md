# yolo笔记

## 作者

joseph redmon，觉得这些工作不应该用于人脸检测，退出计算机视觉领域了，看了看推特，还挺关心中国的，觉得中国防疫政策好，个人网站pjreddie.com像邪教组织，左边的简历，很少女心，好家伙，Middlebury College，明德学院，西工大明德学院

30fps  实时检测

Pascal数据集20个类别

上古时期：DPM：Deformable Part Models传统机器学习，计算机视觉特征，滑窗，非常慢 

R-CNN，Region with CNN features，选大约2000个候选框，放缩到一样大，喂到网络里面，

这两个都是基于候选框的，都慢



为什么要两个BBox？

为什么BN和Dropout不能一起用？