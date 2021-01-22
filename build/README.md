# Instructions

## Requirements

* NVIDIA GPU with the latest driver installed
* docker / nvidia-docker

## Build
Build the image with:
```
docker build -t project-dev -f Dockerfile.gpu .
```

Create a container with:
```
docker run -v <PATH TO LOCAL PROJECT FOLDER>:/app/project/ -ti project-dev bash
```
and any other flag you find useful to your system (eg, `--shm-size`).
**NOTE:** I needed to add the follwoing to flags in order to make ```Ray``` working:``` --network host --shm-size=256m```
```
nd013-c1-vision-refresh-project/starter:/app/project/ --network host --shm-size=256m -ti project-dev bash
```
## Set up

Once in container, you will need to install gsutil, which you can easily do by running:
```
curl https://sdk.cloud.google.com | bash
```

Once gsutil is installed and added to your path, you can auth using:
```
gcloud auth login
```

## Debug
* Follow this [tutorial](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/install.html#tensorflow-object-detection-api-installation) if you run into any issue with the installation of the
tf object detection api
