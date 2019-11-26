# Win-VB-ros-hector_slam
This is a sample project to use a UST-10LX(Hokuyo) and hector_slam on Ubuntu on Windows with VirtualBox.

## Usage

- Make sure Hyper-V is correctly disabled.
- You need to set a PATH to the VirtualBox folder.

### Required softwares
- VirtualBox
- Vagrant
- VcXsrv

### VcXsrv setting
You need to edit C:\Program Files\VcXsrv\X0.hosts .

```
localhost
inet6:localhost
10.0.2.2
```

Using rviz, you have to use -nowgl (Disable native OpenGL) option.

### Run

```
> cd *Win-vagrant-Ubuntu-webcam dir*
> vagrant up
> vagrant reload # only the first time
> vagrant ssh

$ cd share
$ docker-compose up
```