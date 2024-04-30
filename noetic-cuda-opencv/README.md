# ROS Noetic CUDA OpenCV
## build
### build image `noetic-cuda-ws`
If you already build this image, skip this process.
```
cd ~/dockerfiles/noetic-cuda
docker compose build
```
### build image `noetic-cuda-opencv-ws`
If you already build the image `noetic-cuda-ws`, please execute the following:
```
cd ~/dockerfiles/noetic-cuda-opencv
docker compose build
```
