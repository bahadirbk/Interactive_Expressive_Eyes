# Interactive Expressive Eyes

## Requirements of the project (in order)

- Python 3.8+
- numpy
- scipy
- pycozmo (https://github.com/zayfod/pycozmo)
- OpenFace (https://github.com/TadasBaltrusaitis/OpenFace) 
- ROS (noetic)
- openface2_ros (https://github.com/ditoec/openface2_ros)

## Clone

- `git clone https://github.com/bahadirbk/Interactive_Expressive_Eyes.git

## Details

In order to manage to install and run without having an issue, the opencv version 4 and OpenFace version 2.2 need to be installed. Afterwards, the line related to the opencv version of the CMakeLists.txt file in the openface2_ros node needs to be reconfigured as it would work with opencv version 4 as well. Make sure that the following line is in the CMakeLists.txt file 'find_package(OpenCV 4 REQUIRED COMPONENTS core objdetect)'. Also, in openface2_ros.cpp and openface2_ros_single.cpp files, the line 'include <tbb/tbb.h>' needs to be commented out, Lastly, in openface2_ros.cpp file, the line 'vector<tbb::atomic<bool> > face_detections_used(face_detections.size());' needs to be changed as it will be 'vector<bool> face_detections_used(face_detections.size());' as well before catkin_make. 

## Running

Running the code (in order):

- roscore
- rosrun usb_cam usb_cam_node
- roslaunch openface2_ros openface2_ros.launch
- python_subscriber.py



