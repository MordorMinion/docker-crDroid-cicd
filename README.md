# docker-crdroid-cicd

Docker image to generate builds of crDroid. 

This is current NOT WORKING

How to use:
1. docker pull https://github.com/MordorMinion/docker-crDroid-cicd
2. cd to directory
3. docker xbuild build .
4. docker image ls to get docker image name
5. docker compose:
```
services:
    docker-crdroid-cicd:
        container_name: build-crd
        environment:
            - BRANCH_NAME=16.0
            - DEVICE_LIST=pdx234
            - WITH_GMS=true
            - INCLUDE_PROPRIETARY=true
        volumes:
            - /mnt/ssd-downloads/WD/build/crDroid/lineage/:/srv/src
            - /mnt/backup/NAS/android-builds/crDroid/zips:/srv/zips
            - /mnt/ssd-downloads/WD/build/crDroid/logs:/srv/logs
            - /mnt/ssd-downloads/WD/build/crDroid/cache:/srv/ccache
        image: "image name from docker image ls"
```
7. docker compose up -d

Thanks to:
- crDroid team
- LineageOS team
- blackshibe
- lineageos4microg/docker-lineage-cicd project


Ignore below
See [the wiki in this repo](https://github.com/lineageos4microg/docker-lineage-cicd/wiki) for updated documentation on this Docker image.

See the [LineageOS for microG project wiki](https://github.com/lineageos4microg/l4m-wiki/wiki) for information about the LineageOS for microG project 



