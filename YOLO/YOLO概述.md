# YOLOv1

* 1.多层卷积网络
* 2.池化层+全连接层
* 3.每个单元格：30----5（cell）+5+20（特征数）
* 4.边界框：7+7+2=98个边界框
* 5.分辨率 固定224+224

-----------------------------

# YOLOv2

* *1.加入卷积残差网络
* *2.移除全连接层，加入anchor boxes（锚框）
* *3分辨率：416+416-------受采样步长为32的影响（最大下采样）
* 4.改变YOLOv1两个框的方式，使用不规则的5个框进行检测
* 5.增加了准确率(召回率)，小幅度下降定位率（MAP）
* 6.边界框：13+13+num_anchors
* 7.在3+3卷积后加入1+1卷积来压缩特征图channles以降低模型计算量和参数
* 8.backbone: Darknet-19

-----------------------------
  
# YOLOv3

* 1.删去全连接层
* 2.输出三个特征图：下采样32倍（最大的），下采样16倍，下采样8倍
* 3.借用金字塔思想，不同层之间存在上采样，不同框识别不同大小的物体
* 4.使用固定的9个框进行检测
* 5.最后会得到3个特征图
* 6.backbone: Darknet-53

----------------------------

# YOLOv4

* 1.backbone: CSPDarknet53
* 2.接入下向上传特征的金字塔结构
* 3.调整Anchor模型

---------------------------

# YOLOv5

* 1.backbone: New CSPDarknet53
* 2.引出多层模型的概念（小，中，大）



