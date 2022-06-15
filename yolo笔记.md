# yolo笔记

## 作者

joseph redmon，觉得这些工作不应该用于人脸检测，退出计算机视觉领域了，看了看推特，还挺关心中国的，觉得中国防疫政策好，个人网站pjreddie.com像邪教组织，左边的简历，很少女心，好家伙，Middlebury College，明德学院，西工大明德学院

30fps  实时检测

Pascal数据集20个类别

上古时期：DPM：Deformable Part Models传统机器学习，计算机视觉特征，滑窗，非常慢 

R-CNN，Region with CNN features，选大约2000个候选框，放缩到一样大，喂到网络里面，

这两个都是基于候选框的，都慢



为什么要两个BBox？



## YOLO V2

为什么BN和Dropout不能一起用？

ANCHOR  ？充电宝？

V1两个BBOX形状是随意的，野蛮生长；V2中有初始参考框，先验的参考框，

<img src="yolo%E7%AC%94%E8%AE%B0.assets/image-20220609110707615.png" alt="image-20220609110707615" style="zoom:50%;" />

天生就一个，矮胖，一个高瘦的，这就是两个ANCHOR

V2中13x13，每个grid cell预测五个anchor，五种长宽大小尺度不同的先验框

<img src="yolo%E7%AC%94%E8%AE%B0.assets/image-20220609110927328.png" alt="image-20220609110927328" style="zoom: 33%;" />

小女孩的中心点落在那个gridcell中，就由中这个grid cell中IOU最大的那个的anchor来预测，

变成了奇数个grid cell，这样有中心了

<img src="yolo%E7%AC%94%E8%AE%B0.assets/image-20220609111754298.png" alt="image-20220609111754298" style="zoom:33%;" />

<img src="yolo%E7%AC%94%E8%AE%B0.assets/image-20220609111919974.png" alt="image-20220609111919974" style="zoom:33%;" />

 聚类kmeans选anchor

<img src="yolo%E7%AC%94%E8%AE%B0.assets/image-20220609115415604.png" alt="image-20220609115415604" style="zoom:33%;" />

<img src="yolo%E7%AC%94%E8%AE%B0.assets/image-20220609115440341.png" alt="image-20220609115440341" style="zoom:33%;" />

bn是对每个神经元（batch个样本）做归一化

anchor输出偏移量