# label-studio-yolov8-backend

YoloV8 ML backend for label-studio for semi-automatic labeling

## How to use it?
**
Step-0:** install label-studio-ml-backend using pip and if necessary then install label-studio dependencies.
```
 pip install git+https://github.com/heartexlabs/label-studio-ml-backend.git
```

**Step-1:** Copy yolov8 directory to your label-studio project

**Step-2:** Change yolov8/model.py settings if you want to use custom settings. Change following setttings to work with custom model.
```
# COCO pretrained model
self.model = YOLO("yolov8s.pt")

# Custom model
self.model = YOLO("path-to-your-yolov8-model")
```

Do not forget to modify labelmap in model script. Change it to your model labelmaps.

**Step-3:** Initialize model inference server
```
label-studio-ml init yolov8_ml --script yolov8/model.py
```

**Step-4:**  Start model inference server
```
label-studio-ml start ./yolov8_ml
```
Copy inference url for next stop. It will be shown in blue color i.e. http://192.168.0.10:9090/


**Step-5:** Open your label-studio user interface then add model to your settings by

```settings > machine learning > Add model url with model name > save```

**Step-6:** Enjoy Semi-Automatic labeling using YoloV8
