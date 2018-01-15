# ubuntu16-full

Dockerfile to create an ubuntu 16.04 container for emulate a full OS features on a minimal instalation and
ssh access by password, ideal for testing purposes and considerating the security risks, any purpose.


## requirements

obviously docker engine

## Installation

you can use ansible for create both (image and container)
``` $ ansible-playbook container.yml ```

or using directly docker

``` $ docker build -t ubuntu16-full . ```


## Usage
 You must use the "privileged" option for systemd compatibility
``` docker run -d --name container-name ubuntu16-full --privileged ```
or if you want more precision add particular capabilities and read access to cgroups
``` --cap-add=SYS_ADMIN -v /sys/fs/cgroup:/sys/fs/cgroup:ro ```

See docker run documentation for more details.

then you can access to container by ssh way, the default password is "test" and you can change in Dockerfile

``` ssh root@ipcontainer ```
or docker cli way

```docker exec -it container-name bash ```

## issues

- I detect that if storage driver is AUFS (default in ubuntu) mysql official package fails, overlay2 not tested

## TO DO

- Feature: ssh by private keys, especially for external access

## Credits
Alex left
alejandro.izquierdo.b@gmail.com

## License
GPL V3
