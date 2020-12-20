# LigEGFR prediciton based-on Anaconda installation

This method supports for Linux and macOS operating systems.

## Prerequisites:

### Linux with GPU

1. Download Miniconda3-py37_4.8.3
```
wget -c https://repo.anaconda.com/miniconda/Miniconda3-py37_4.8.3-Linux-x86_64.sh -O Miniconda3-py37_4.8.3.sh
```

or
```
curl https://repo.anaconda.com/miniconda/Miniconda3-py37_4.8.3-Linux-x86_64.sh -o Miniconda3-py37_4.8.3.sh
```

2. Install Miniconda 3 and package dependencies
```
chmod +x Miniconda3-py37_4.8.3.sh
./Miniconda3-py37_4.8.3.sh -b -f -p ./conda
source ./conda/bin/activate

pip install scikit-learn==0.22
conda install -y -c rdkit rdkit
pip install joblib pandas tensorflow==1.15 pillow deepchem
conda install -y -c pytorch pytorch==1.5.1 
conda install -y -c conda-forge jpype1=0.7.5
conda install -y -c openbabel openbabel=2.4.1
```

3. Download a `LigEGFR_source.tar.gz` file from https://zenodo.org/record/4361642 and then decompress file
```
tar -xzvf LigEGFR_source.tar.gz
```

### Linux without GPU (CPU only)

1. Download Miniconda3-py37_4.8.3
```
wget -c https://repo.anaconda.com/miniconda/Miniconda3-py37_4.8.3-Linux-x86_64.sh -O Miniconda3-py37_4.8.3.sh
```

or
```
curl https://repo.anaconda.com/miniconda/Miniconda3-py37_4.8.3-Linux-x86_64.sh -o Miniconda3-py37_4.8.3.sh
```

2. Install Miniconda 3 and package dependencies
```
chmod +x Miniconda3-py37_4.8.3.sh
./Miniconda3-py37_4.8.3.sh -b -f -p ./conda
source ./conda/bin/activate

pip install scikit-learn==0.22
conda install -y -c rdkit rdkit
pip install joblib pandas tensorflow==1.15 pillow deepchem
conda install -y -c pytorch pytorch==1.5.1 cpuonly
conda install -y -c conda-forge jpype1=0.7.5
conda install -y -c openbabel openbabel=2.4.1
```

3. Download a `LigEGFR_source.tar.gz` file from https://zenodo.org/record/4361642 and then decompress file
```
tar -xzvf LigEGFR_source.tar.gz
```

### macOS

1. Download Miniconda3-py37_4.8.3
```
wget -c https://repo.anaconda.com/miniconda/Miniconda3-py37_4.8.3-MacOSX-x86_64.sh -O Miniconda3-py37_4.8.3.sh
```

or
```
curl https://repo.anaconda.com/miniconda/Miniconda3-py37_4.8.3-MacOSX-x86_64.sh -o Miniconda3-py37_4.8.3.sh
```

2. Install Miniconda 3 and package dependencies
```
chmod +x Miniconda3-py37_4.8.3.sh
./Miniconda3-py37_4.8.3.sh -b -f -p ./conda
source ./conda/bin/activate

pip install scikit-learn==0.22
conda install -y -c rdkit rdkit
pip install joblib pandas tensorflow==1.15 pillow deepchem
conda install -y -c pytorch pytorch==1.5.1 
conda install -y -c conda-forge jpype1=0.7.5
conda install -y -c openbabel openbabel=2.4.1
```

3. Download a `LigEGFR_source.tar.gz` file from https://zenodo.org/record/4361642 and then decompress file
```
tar -xzvf LigEGFR_source.tar.gz
```

## How to run:

Basically, all files and folders in `LigEGFR_source` folder should be under the same folder that contains `conda` directory. The organization of folders and files is shown below.

A valid directory organization:

```bash
├── cdk-2.3.jar
├── conda
│   ├── *.*
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

To getting started, the conda environment requires to activate by

```
source conda/bin/activate
```

For prediction, please run `run_predict.py` and subsequent `qeury.sdf`, this file consists of multi-compounds in sdf format.

```
python3 run_predict.py query.sdf
```

## Examples:

### Run structure10.sdf file, this file contains 10 small molecules.

```
source conda/bin/activate
python3 run_predict.py examples/structure10.sdf
```

### Run structure250.sdf file, this file contains 250 small molecules.

```
source conda/bin/activate
python3 run_predict.py examples/structure250.sdf
```
