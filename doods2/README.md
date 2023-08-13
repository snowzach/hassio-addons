## DOODS2 - Distributed Open Object Detection Service - V2

See https://github.com/snowzach/doods2 for more documentation.


### Models

This add-on maps the /share directory by default. The default configuration uses the built in model.

Place your custom models in something like /share/doods and you can access them from within the container when you configure it.
(See the `tensorflow` example below)

For example:

```
logger:
  level: info
server:
  port: '8080'
  auth_key: ''
doods.log: detections
doods.boxes:
  enabled: true
  boxColor: "#00ff00"
  boxThickness: 1
  fontScale: 1.2
  fontColor: "#00ff00"
  fontThickness: 1
doods.regions:
  enabled: true
  boxColor: "#ff00ff"
  boxThickness: 1
  fontScale: 1.2
  fontColor: "#ff00ff"
  fontThickness: 1
doods.globals:
  enabled: true
  fontScale: 1.2
  fontColor: "#ffff00"
  fontThickness: 1
doods.detectors:
  - name: default
    type: tflite
    modelFile: models/coco_ssd_mobilenet_v1_1.0_quant.tflite
    labelFile: models/coco_labels0.txt
  - name: tensorflow
    type: tensorflow
    modelFile: models/faster_rcnn_inception_v2_coco_2018_01_28.pb
    labelFile: models/coco_labels1.txt
  - name: pytorch
    type: pytorch
    modelFile: ultralytics/yolov5,yolov5s
```
