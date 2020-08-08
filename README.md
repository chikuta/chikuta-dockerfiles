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

After install nvidia container runtime, please restart docker service as follows.

```bash
$ sudo systemctl restart docker.service
```

## How to build docker image

```bash
$ ./docker/ros-bionic-melodic/build-docker-image.bash
```

## How to launch

```bash
$ ./docker/ros-bionic-melodic/run-docker-container.bash
```

## References
* https://waldeinsamkeit.hatenablog.jp/entry/2019/08/17/002854
* https://nvidia.github.io/nvidia-container-runtime/
* https://medium.com/@benjamin.botto/opengl-and-cuda-applications-in-docker-af0eece000f1
