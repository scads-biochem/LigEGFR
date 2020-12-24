# LigEGFR prediciton based-on Docker installation

This method supports for Windows, Linux and macOS operating systems (recommended for Windows).

## Hardware requirements:

CPUs: Minimum 2 cores\
Memory (RAM): Minimum 4GB\
swap (in docker setting): Minimum 8GB

## Prerequisites:

### Download Docker from source and install

For installing the Docker, please follow the instructions from each link depending on your operating system:
- Windows: https://docs.docker.com/docker-for-windows/install/
- macOS: https://docs.docker.com/docker-for-mac/install/
- CentOS: https://docs.docker.com/engine/install/centos/
- Debian: https://docs.docker.com/engine/install/debian/
- Fedora: https://docs.docker.com/engine/install/fedora/
- Ubuntu: https://docs.docker.com/engine/install/ubuntu/

### Download LigEGFR_docker.tar.gz and decompress file

The `LigEGFR_docker.tar.gz` file provides at https://zenodo.org/record/4361642 and then extract file by
```
tar -xzvf LigEGFR_docker.tar.gz
```

## How to run:

Basically, the organization of `LigEGFR_docker` folder contains files and directories as below.

A valid organization of a directory:

```bash
├── cdk-2.3.jar
├── DockerFile
├── examples
│   ├── structure*.sdf
├── models
│   ├── __init__.py
│   ├── applicabilityDomain.py
│   ├── cleanSmiles.py
│   ├── csgen.py
│   ├── fingerprint.py
│   ├── knnpickle_file
│   ├── longlist.py
│   ├── model.py
│   ├── model256.model
│   ├── mydataset.py
│   └── tobject.py
└── run_predict.py
```

### I) Build Docker image from local

This step will build docker image based-on CentOS7, it will be taken time ~6 mins and storage ~5.26GB. 

```
cd LigEGFR_docker
docker build -t ligegfr .
```

### II) Run Docker container from builded image

For prediction, please add input `qeury.sdf` file, this file consists of multi-compounds in sdf format.

#### Windows

```
docker run -it --cpus="2" --memory="4g" --memory-swap="8g" --name lig1 --rm -i --mount type=bind,source=%cd%,target=/ligegfr ligegfr python3 run_predict.py query.sdf
```


#### Linux & macOS

```
docker run -it --cpus="2" --memory="4g" --memory-swap="8g" --name lig1 --rm -i --mount type=bind,source=$(pwd),target=/ligegfr ligegfr python3 run_predict.py query.sdf
```


Hardware specification is depends on your computer performance, it can be adjusted as appropriate. When the script is computed to finish, returning a `LigEGFR_output.csv` file for prediction results. By the way, swap memory is normally adjusted by 2 times of RAM setting *e.g.* RAM = 4GB, swap = 8GB.


## Examples:

### Run structure10.sdf file on Windows, this file contains 10 small molecules.

```
docker run -it --cpus="2" --memory="4g" --memory-swap="8g" --name lig1 --rm -i --mount type=bind,source=%cd%,target=/ligegfr ligegfr python3 run_predict.py examples/structure10.sdf
```

### Run structure250.sdf file on Linux, this file contains 250 small molecules.

```
docker run -it --cpus="2" --memory="4g" --memory-swap="8g" --name lig1 --rm -i --mount type=bind,source=$(pwd),target=/ligegfr ligegfr python run_predict.py examples/structure250.sdf
```
