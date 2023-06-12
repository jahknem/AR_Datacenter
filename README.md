# AR Datacenter

This program recognizes racks and devices within a rack which are marked with ficudical markers. By usign the link encoded in a QR Code it will get additional data from a netbox database. The program will load images which will be laid over the stream. These images are an overley into which information about the individual interfaces can be written and graphs can be shown.

For this to happen we need multiple functionalities:
 - QR Code Recognition
 - Pose Estimation with Ficudical Markers
 - Image Overlay
    - Graphs
    - Text
- Netbox API
    - Get Device Information
    - Get Interface Information
    - Get Graphs
- Stream from Camera

Steps: 
1. Calibrate Camera
1. Read Camera Stream and Display it
2. Read Fiducial Markers and Display them
3. Estimate the Pose of Device on which the Fiducial Markers are
5. Recognize and Read QR Code, estimate which device it belongs to
6. Get Information about Device from Netbox
7. Display Information on Overlay

cmake commands for building opencv:
```
cmake `
-D WITH_TBB=ON `
-D WITH_OPENMP=ON `
<# CUDA #> `
-D WITH_NVCUVID=ON `
-D WITH_CUDA=ON `
-D CUDA_ARCH_BIN=6.1 `
-D ARCH=sm_61 `
-D gencode=arch=compute_61,code=sm_61 `
-D CUDA_FAST_MATH=ON `
-D WITH_CUBLAS=ON `
-D WITH_CUFFT=ON `
-D OPENCV_DNN_CUDA=ON `
<# CUDA Modules #> `
-D WITH_IPP=ON `
-D WITH_CSTRIPES=ON `
-D WITH_OPENCL=ON `
-D ENABLE_PROFILING=ON `
-D OPENCV_ENABLE_NONFREE=ON `
-D CMAKE_BUILD_TYPE=Debug `
-D BUILD_SHARED_LIBS=OFF `
-D BUILD_EXAMPLES=ON `
-D DBUILD_opencv_world=ON `
-D OPENCV_EXTRA_MODULES_PATH=C:\Users\jan\Projects\OpenCV_Build\opencv_contrib\modules `
-D BUILD_NEW_PYTHON_SUPPORT=ON `
-D BUILD_opencv_python3=ON `
-D HAVE_opencv_python3=ON `
-D PYTHON_DEFAULT_EXECUTABLE=C:\Users\jan\AppData\Local\Programs\Python\Python310\python.exe `
-D PYTHON3_INCLUDE_DIR=C:\Users\jan\AppData\Local\Programs\Python\Python310\include `
-D PYTHON3_LIBRARY=C:\Users\jan\AppData\Local\Programs\Python\Python310\libs\python310.lib `
-D PYTHON3_NUMPY_INCLUDE_DIRS=C:\Users\jan\AppData\Local\Programs\Python\Python310\Lib\site-packages\numpy\core\include `
-D CMAKE_INSTALL_PREFIX=C:/OpenCV ..

```
