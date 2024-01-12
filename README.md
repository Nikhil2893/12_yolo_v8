# 12_yolo_v8
#create virtual env
pip install ultralytics==8.0.0

# if torch not available
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

# command for image detection/video detection
yolo task=detect mode=predict model=yolov8n.pt source=image1.jpg 
yolo task=detect mode=predict model=yolov8n.pt source=demo.mp4

# command for image detection/video detection with confidence 
yolo task=detect mode=predict model=yolov8n.pt source=image1.jpg conf=0.8
yolo task=detect mode=predict model=yolov8n.pt source=demo.mp4 conf=0.8

# command for image detection/video detection with bounding box 
yolo task=detect mode=predict model=yolov8n.pt source=image1.jpg save_txt=True

# command for image detection/video detection with bounding box and crop the image
yolo task=detect mode=predict model=yolov8n.pt source=image1.jpg save_txt=True save_crop=True


# command for image detection/video detection with to hide labels and confidence score
yolo task=detect mode=predict model=yolov8n.pt source=image1.jpg hide_labels=True hide_conf=True
yolo task=detect mode=predict model=yolov8n.pt source=demo.mp4 hide_labels=True hide_conf=True

# command for image/video--semantic segmentation
yolo task=segment mode=predict model=yolov8n-seg.pt source=image1.jpg 
yolo task=segment mode=predict model=yolov8n-seg.pt source=demo.mp4

# command for image/video detection--semantic segmentation with hide labels and confidence score
yolo task=segment mode=predict model=yolov8n-seg.pt source=image1.jpg hide_labels=True hide_conf=True
yolo task=segment mode=predict model=yolov8n-seg.pt source=demo.mp4 hide_labels=True hide_conf=True

# command for image detection--classification
<!-- yolo task=segment mode=predict model=yolov8n-cls.pt source=image1.jpg  --> not sure

# command for, if you want to show output in real time
yolo task=segment mode=predict model=yolov8n-seg.pt source=image1.jpg show=True

# To convert Yolo-v8 model in onnx format
yolo mode=export task=detect model=yolov8n.pt format=onnx

# yolov8n.pt downloaded and output folder runs created




