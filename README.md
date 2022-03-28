# Kria-HASA
Home Assist Situational Awareness using Kria KV260

For my code, I leveraged the [tfsdd example](https://github.com/Xilinx/Vitis-AI/tree/master/demo/Vitis-AI-Library/samples/tfssd).

File structure:

/home/Vitis-AI/demo/Vitis-AI-Library/samples/tfsdd/
  - process_result.hpp
  - test_video_tfssd.cpp
  - twilio.cc
  - twilio.hh
  - type_conversion.hh

/usr/include/vitis/ai/
  - demo.hpp
  
Model used:
ssd_mobilenet_v2_coco_tf (downloadable from the [Vitis AI Model Zoo](https://github.com/Xilinx/Vitis-AI/tree/master/models/AI-Model-Zoo))

To build:

>  cd /Vitis-AI/demo/Vitis-AI-Library/samples/tfssd/
>  ./build.sh

Note: Ensure that nlp-smartvision is loaded before starting the executable!

>  sudo xlnx-config --xmutil loadapp nlp-smartvision

To execute (running RTSP):

>  ./test_video_tfssd ~/path_to_model/ssd_mobilenet_v2_coco_tf.xmodel rtsp://user:password@ip_address:554/h264Preview_01_main

Where path_to_model is the location of where the ssd_mobilenet_v2_coco_tf model and prototxt are saved, user and password are the username and password for your RTSP camera, and ip_address is the RTSP IP address.
