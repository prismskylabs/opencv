# OpenCV

## Mac OS Build Instructions

Install ffmpeg, you can do this by running `brew install ffmpeg`. Then run:

```
cd opencv
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=~/Desktop/opencv3 -D INSTALL_C_EXAMPLES=OFF \
    -D INSTALL_PYTHON_EXAMPLES=OFF -D BUILD_EXAMPLES=OFF -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules/ -D BUILD_SHARED_LIBS=OFF \
    -D WITH_TBB=OFF -D WITH_IPP=OFF -D WITH_IPP_A=OFF -D WITH_CUDA=OFF -D WITH_EIGEN=OFF -D WITH_CLP=OFF -D WITH_CSTRIPES=OFF -D WITH_OPENMP=OFF \
    -D WITH_PTHREADS_PF=OFF -D WITH_OPENCL=OFF \
    -D WITH_GSTREAMER=OFF -D WITH_AVFOUNDATION=OFF -D WITH_FFMPEG=ON -D WITH_WEBP=OFF ..
make -j8
make install
```

You will get opencv installed in `~/Desktop/opencv3`, navigate to that folder and create artifact by running:

```
tar -czvf opencv_3.4.0_macos.Release.tar.gz include/ lib/ share/
```

## Ubuntu Build Instructions

Install ffmpeg. Then run:

```
cd opencv
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=~/Desktop/opencv3 -D INSTALL_C_EXAMPLES=OFF \
    -D INSTALL_PYTHON_EXAMPLES=OFF -D BUILD_EXAMPLES=OFF -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules/ -D BUILD_SHARED_LIBS=OFF \
    -D WITH_TBB=OFF -D WITH_IPP=OFF -D WITH_IPP_A=OFF -D WITH_CUDA=OFF -D WITH_EIGEN=OFF -D WITH_CLP=OFF -D WITH_CSTRIPES=OFF -D WITH_OPENMP=OFF \
    -D WITH_PTHREADS_PF=OFF -D WITH_OPENCL=OFF \
    -D WITH_GSTREAMER=OFF -D WITH_FFMPEG=ON -D WITH_WEBP=OFF ..
make -j8
make install
```

## iOS Build Instructions

```
python opencv/platforms/ios/build_framework.py ios --contrib opencv_contrib/
```
