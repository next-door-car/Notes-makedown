### 图片标注（labelimg）
> images 旁加入labels文件夹放置标签文件

```
1.标记好的文件labels中的名称与images一一对应
2.classes文件中是标注的类别
3.在label中第一个数字表示类别，中两个中心点坐标，后两个w，h
```
----------------------

### train.py中指明两个配置文件（数据集+模型）

>yaml文件

```数据集配置文件
1.训练集配置路径
2.验证集配置路径
3.数据集类别数量
```
python train.py --data mask_data.yaml --cfg mask_yolov5l.yaml --weights pretrained/yolov5l.pt --epoch 100 --batch-size 4
