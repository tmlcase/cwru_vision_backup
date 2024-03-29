cmake_minimum_required(VERSION 2.8.3)
project(cwru_opencv_common)
find_package(OpenCV REQUIRED)



find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport
  camera_info_manager
  roscpp
  sensor_msgs
  std_msgs
  tf
)

catkin_package(
    INCLUDE_DIRS include
    LIBRARIES opencv_ui_lib circle_detection_lib block_detection_lib grab_cut_lib
    CATKIN_DEPENDS cv_bridge image_transport roscpp sensor_msgs std_msgs
    #   DEPENDS system_lib
)

SET(LIB_TYPE STATIC) 


include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)


add_library(circle_detection_lib
    src/circle_detection.cpp
)

add_library(block_detection_lib
    src/block_detection.cpp
)

add_library(opencv_3d_lib
    src/opencv_geometry_3d.cpp
)

add_library(opencv_2d_lib
    src/opencv_geometry_2d.cpp
)

add_library(opencv_ui_lib
    src/opencv_ui.cpp
)

add_library(opencv_local_lib
    src/opencv_local.cpp
)

add_library(opencv_rot_lib
    src/cv_rotations.cpp
)

add_library(projective_lib
    src/projective_geometry.cpp
)


add_library(grab_cut_lib
    src/grab_cut.cpp
)

add_library(color_model_lib
    src/color_model.cpp
)





#catkin_package(
#    INCLUDE_DIRS include
#    LIBRARIES opencv_ui_lib circle_detection_lib block_detection_lib
#    CATKIN_DEPENDS cv_bridge image_transport roscpp sensor_msgs std_msgs
    #   DEPENDS system_lib
    #)


#SET(CUDA_NVCC_FLAGS "-arch=sm_13" CACHE STRING "nvcc flags" FORCE)
#SET (CUDA_VERBOSE_BUILD ON CACHE BOOL "nvcc verbose" FORCE)
#SET(LIB_TYPE STATIC) 


#include_directories(
#  include
#  ${catkin_INCLUDE_DIRS}
#)


#CUDA_ADD_LIBRARY(vesselness_image_filter_gpu_kernels src/gpu_src/vesselness_image_filter_kernels.cu)
#CUDA_ADD_LIBRARY(vesselness_image_gpu src/gpu_src/vesselness_image_filter_gpu.cu)



#add_library(dummy_lib
#    src/dummylib.cpp
#)

#add_library(catadioptric_calibration_lib
    #   src/catadioptric_calibration.cpp
   # )

#add_library(catheter_driver_lib
    #   src/catheter_driver.cpp
   # )

#add_library(catheter_import_lib
#   src/catheter_image_import.cpp
# )


#cuda_add_library( 

#add_library(vesselness_image_filter
#   src/${PROJECT_NAME}/src/vesselness_image_filter.cpp
# )



#ADD_EXECUTABLE(vesselness_image_filter_cpu_node src/cpu_src/vesselness_image_filter_cpu_node.cpp)

#ADD_EXECUTABLE(catheter_playback_node src/catheter_playback_node.cpp)

#ADD_EXECUTABLE(vesselness_image_filter_gpu_node src/gpu_src/vesselness_image_filter_gpu_node.cpp)

#ADD_EXECUTABLE(vesselness_image_filter_cpu src/cpu_src/vesselness_image_filter_gpu.cpp)
#ADD_DEPENDENCIES(beginner_tutorials_node T)

#TARGET_LINK_LIBRARIES(
#   #vesselness_image_filter
#   ${catkin_LIBRARIES}
#  #${PCL_LIBRARIES}
#)

#target_link_libraries(catheter_import_lib
#    #opencv_imgcodecs
#    ${catkin_LIBRARIES}
#)


#target_link_libraries(vesselness_image_filter_gpu_node
#   vesselness_image_base
#  vesselness_image_gpu
#  vesselness_image_filter_gpu_kernels
#  ${CUDA_LIBRARIES}
#  ${OpenCV_LIBRARIES}
#  ${catkin_LIBRARIES}
# )

#target_link_libraries(vesselness_image_cpu
#  vesselness_image_base
#   ${catkin_LIBRARIES}
# )

#target_link_libraries(vesselness_image_gpu
# vesselness_image_gpu
# vesselness_image_filter_gpu_kernels
#  vesselness_image_base
#   ${CUDA_LIBRARIES}
#   ${catkin_LIBRARIES}
# )

#target_link_libraries(vesselness_image_base
#   ${catkin_LIBRARIES}
# )

#target_link_libraries(vesselness_image_filter_viewer_node
#   ${catkin_LIBRARIES}
# )
