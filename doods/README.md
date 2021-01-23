## DOODS - Distributed Open Object Detection Service

See https://github.com/snowzach/doods for more documentation.


### Models

This add-on maps the /share directory by default. The default configuration uses the built in model.

Place your custom models in something like /share/doods and you can access them from within the container when you configure it.

For example:

```
{
  "server": {
    "port": "8080"
  },
  "auth_key": "",
  "doods.detectors": [
    {
      "name": "default",
      "type": "tflite",
      "modelFile": "/opt/doods/models/coco_ssd_mobilenet_v1_1.0_quant.tflite",
      "labelFile": "/opt/doods/models/coco_labels0.txt",
      "numThreads": 1,
      "numConcurrent": 1,
      "hwAccel": false
    },
    {
      "name": "tensorflow",
      "type": "tensorflow",
      "modelFile": "/share/doods/faster_rcnn_inception_v2_coco_2018_01_28.pb",
      "labelFile": "/share/doods/coco_labels1.txt",
      "numThreads": 1,
      "numConcurrent": 1,
      "hwAccel": false
    }
  ]
}
```
