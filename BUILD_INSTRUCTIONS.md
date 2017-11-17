# OpenCV

## Mac OS Build Instructions

Install ffmpeg
`brew install ffmpeg`

Build OpenCV
```
cd opencv
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=~/Desktop/opencv3 -D INSTALL_C_EXAMPLES=OFF \
    -D INSTALL_PYTHON_EXAMPLES=OFF -D BUILD_EXAMPLES=OFF -D OPENCV_EXTRA_MODULES_PATH=<path_to_opencv_contrib>/modules/ \
    -D BUILD_SHARED_LIBS=OFF -D WITH_IPP=OFF -D WITH_OPENCL=OFF -D WITH_GSTREAMER=OFF -D WITH_AVFOUNDATION=OFF -D WITH_FFMPEG=ON -D WITH_WEBP=OFF ..
make -j8
make install
```

## Ubuntu Build Instructions

Install ffmpeg
`sudo apt-get install ffmpeg`

Build OpenCV
```
cd opencv
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=~/Desktop/opencv3 -D INSTALL_C_EXAMPLES=OFF \
    -D INSTALL_PYTHON_EXAMPLES=OFF -D BUILD_EXAMPLES=OFF -D OPENCV_EXTRA_MODULES_PATH=<path_to_opencv_contrib>/modules/ \
    -D BUILD_SHARED_LIBS=OFF -D WITH_IPP=OFF -D WITH_OPENCL=OFF -D WITH_GSTREAMER=OFF -D WITH_AVFOUNDATION=OFF -D WITH_FFMPEG=ON -D WITH_WEBP=OFF ..
make -j8
make install
```

## iOS Build Instructions

```
python opencv/platforms/ios/build_framework.py ios --contrib <path_to_opencv_contrib>/
```
