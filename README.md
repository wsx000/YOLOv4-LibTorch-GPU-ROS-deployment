# YOLO4-ROS-GPU
this code deploy yolov4 on ROS-Melodic with libtorch1.7.0  


环境配置（不唯一）：  
Ubuntu18.04  
CUDA10.2  
Libtorch1.7.0-cxx11 ABI  
OpenCV3.4.10  
torchvision0.8.0  

需要修改的地方：  
1、在下载好的文件中新建module文件夹，放入你的***.pt模型文件  
2、在cmakelists.txt 文件中修改set(CMAKE_PREFIX_PATH "/path/to/libtorch; /path/to/torchvision")  
3、在yolo.h文件中修改all_anchors、class_name、smodel_image_size参数； 修改utils.h中的num_classes参数，修改方法代码中有注释  
4、修改detect_node.cpp中的modulePath为你的***.pt模型文件路径  

测试结果：
RTX2070下，帧率21FPS  

  
  更新：  
  注意 utils.cpp里第172行代码有问题，我比较懒，就先不改啦，具体怎么改可看 
  https://github.com/wsx000/YOLOv4-LibTorch-GPU-deployment/issues/2




