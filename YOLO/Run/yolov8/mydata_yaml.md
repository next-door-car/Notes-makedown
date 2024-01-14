# 路径，train and val
train: E:/LK/ultralytics-main/ultralytics/models/yolo/VOC/mydata/dataset/train.txt
val: E:/LK/ultralytics-main/ultralytics/models/yolo/VOC/mydata/dataset/val.txt

# number of classes
nc: 20

# class names
names: [ 'aeroplane', 'bicycle', 'bird', 'boat', 'bottle', 'bus', 'car', 'cat', 'chair', 'cow', 'diningtable', 'dog',
         'horse', 'motorbike', 'person', 'pottedplant', 'sheep', 'sofa', 'train', 'tvmonitor' ]



# YOLOv8 backbone
backbone:
  # [from, number, module, args]
  - [-1, 1, Focus, [64, 3, 2]]  
  - [-1, 1, Conv, [128, 3, 2]]  
  - [-1, 3, C2f, [128, True]]
  - [-1, 1, Conv, [256, 3, 2]]  
  - [-1, 6, c2f, [256,True]]
  - [-1, 1, Conv, [512, 3, 2]]  
  - [-1, 6, c2f, [512, True]]
  - [-1, 1, Conv, [1024, 3, 2]]  
  - [-1, 3, c2f, [1024, True]]
  - [-1, 1, SPPF, [1024, 5]] 


# YOLOv8 head
head:
   - [-1, 1, nn.Upsample, [None, 2, 'nearest']]
   - [[-1, 6], 1, Concat, [1]]  
   - [-1, 3, c2f, [512]]  
   - [-1, 1, nn.Upsample, [None, 2, 'nearest']]
   - [[-1, 4], 1, Concat, [1]]  
   - [-1, 3, c2f, [256]]  

   - [-1, 1, Conv, [256, 3, 2]]
   - [[-1, 12], 1, Concat, [1]]  
   - [-1, 3, c2f, [512]]  

   - [-1, 1, Conv, [512, 3, 2]]
   - [[-1, 9], 1, Concat, [1]]  
   - [-1, 3, c2f, [1024]]  

   - [[15, 18, 21], 1, Segment, [nc,32, 256]]