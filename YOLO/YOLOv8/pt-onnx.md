```python
from ultralytics import YOLO
model = YOLO("best.pt")   #pt文件
success = model.export(format="onnx", simplify=True)  # export the model to onnx format
assert success
print("转换成功")
```