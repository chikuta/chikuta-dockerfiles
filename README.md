# chikuta-docker-envs

## Environment
以下の環境でテストをしています。

* Hardware
  * gpu - Geformce RTX 2060 super

* Software
  * ubuntu - 20.04.1
  * docker version - 19.03
  * nvidia-driver - 440.100
  * cuda version - 10.2

## Install nvidia container runtime

I refered [nvidia-container-runtime site](https://nvidia.github.io/nvidia-container-runtime/)

```bash
$ curl -s -L https://nvidia.github.io/nvidia-container-runtime/gpgkey | sudo apt-key add -
$ distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
$ curl -s -L https://nvidia.github.io/nvidia-container-runtime/$distribution/nvidia-container-runtime.list | sudo tee /etc/apt/sources.list.d/nvidia-container-runtime.list
$ sudo apt update
$ sudo apt install nvidia-container-runtime
```

After install nvidia container runtime, please restart docker service as follows.

```bash
$ sudo systemctl restart docker.service
```

## How to build docker image

### ros-melodic

```bash
$ ./docker/ros-bionic-melodic/build-docker-image.bash
```

### ros-melodic-unity

```bash
$ ./docker/ros-bionic-melodic-unity/build-docker-image.bash
```

### ros2-foxy

```bash
$ ./docker/ros2-foxy-focal/build-docker-image.bash
```

## How to launch

### ros-melodic

```bash
$ ./docker/ros-bionic-melodic/run-docker-container.bash
```

### ros-melodic-unity

First launch terminator from host console.

```bash
$ ./docker/ros-bionic-melodic-unity/build-docker-image.bash
```

Next launch unity-hub from appimage as folllows.

```bash
$ cd /opt/unity
$ ./UnityHub.AppImage
```

### ros2-foxy

```bash
$ ./docker/ros2-foxy-focal/run-docker-container.bash
```

## References
* https://waldeinsamkeit.hatenablog.jp/entry/2019/08/17/002854
* https://nvidia.github.io/nvidia-container-runtime/
* https://medium.com/@benjamin.botto/opengl-and-cuda-applications-in-docker-af0eece000f1


## LICENSE
MIT