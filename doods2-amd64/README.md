## DOODS2 - Distributed Open Object Detection Service - V2 - AMD64

AMD64 Version - This is designed for modern x86_64 chipsets that have the AVX instruction set.

See https://github.com/snowzach/doods2 for more documentation.

### Models

This add-on maps the /share directory by default. The default configuration uses the built in model.

Place your custom models in something like /share/doods and you can access them from within the container when you configure it.
(See the `tensorflow` example below)

For example:

```
{
  "logger": {
    "level": "info"
  },
  "server": {
    "port": "8080",
  },
  "doods.detectors": [
    {
      "name": "default",
      "type": "tflite",
      "modelFile": "/opt/doods/models/coco_ssd_mobilenet_v1_1.0_quant.tflite",
      "labelFile": "/opt/doods/models/coco_labels0.txt",
      "hwAccel": false
    },
    {
      "name": "tensorflow",
      "type": "tensorflow",
      "modelFile": "/share/doods/faster_rcnn_inception_v2_coco_2018_01_28.pb",
      "labelFile": "/share/doods/coco_labels1.txt",
      "hwAccel": false
    }
  ]
}
```
