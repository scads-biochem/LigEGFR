<img src="logo.svg" align="left" width="300">

# LigEGFR

LigEGFR: Spatial graph embedding and molecular descriptors assisted bioactivity prediction of ligand molecules for epidermal growth factor receptor on a cell line-based dataset

Puri Virakarin<sup>1,#</sup>, Natthakan Saengnil<sup>1,#</sup>, Bundit Boonyarit<sup>2,#</sup>, Jiramet Kinchagawat<sup>2</sup>, Rattasat Laotaew<sup>2</sup>, Treephop Saeteng<sup>2</sup>, Thanasan Nilsu<sup>1</sup>, Naravut Suvannang<sup>2,\*</sup>, Thanyada Rungrotmongkol<sup>3,4,\*</sup>, and Sarana Nutanong<sup>2,\*</sup>

<sup>1</sup> Kamnoetvidya Science Academy (KVIS), Rayong 21210, Thailand\
<sup>2</sup> School of Information Science and Technology, Vidyasirimedhi Institute of Science and Technology (VISTEC), Rayong 21210, Thailand\
<sup>3</sup> Program in Bioinformatics and Computational Biology, Graduate School, Chulalongkorn University, Bangkok 10330, Thailand\
<sup>4</sup> Biocatalyst and Environmental Biotechnology Research Unit, Department of Biochemistry, Faculty of Science, Chulalongkorn University, Bangkok 10330, Thailand

<sup>#</sup> These authors contributed equally to this work.\
<sup>\*</sup> Corresponding author

<img src="ligegfr_workflow.svg" align="center">

## About

LigEGFR is a novel deep learning architecture for pIC<sub>50</sub> prediction of small molecules against human epidermal growth factor receptor (EGFR) tyrosine kinase. The architecture is inspired and adapted from a convolution spatial graph embedding layer (C-SGEL) which is constructed by graph convolutional networks and incorporated especial molecular descriptors. This model outperformed baseline machine learning models for predicting pIC<sub>50</sub> and is a notable for higher performance in hit compound classification, compared to molecular docking and machine learning approaches. Moreover, our work is the first model that employed a large-scale and non-redundant dataset to enhance the diversity of the small molecules. 

We developed a user-friendly online platform with compatibility for all devices and Python executable script to predict pIC<sub>50</sub> and classify the hit compounds. This approach opens a new way for applying the hit and lead compounds discovery via targeted lung cancer therapy, offering a powerful strategy that potentially helps researchers overcome the drawbacks of drug discovery processes, and avoids pitfalls of conventional computation methods.

Herein, we provide LigEGFR web service at https://ligegfr.vistec.ist/, and a Python executable file based-on [Anaconda](https://github.com/scads-biochem/LigEGFR/blob/main/LigEGFR_conda.md) (recommended for Linux and macOS) and [Docker](https://github.com/scads-biochem/LigEGFR/blob/main/LigEGFR_docker.md) (recommended for Windows) installation. 

<img src="c-sgen_propagation.svg" align="center">

For C-SGEL, this layer is a part of the convolution spatial graph embedding network (C-SGEN) architecture. For more information, please visit https://doi.org/10.1021/acs.jcim.9b00410


## Citation

Please cite our paper by:
```

```

## Contact

Bundit Boonyarit

Scalable Data Systems Lab (SCADS)\
School of Information Science and Technology

Vidyasirimedhi Institute of Science and Technology (VISTEC)\
Wangchan Valley, 555 Moo 1, Payupnai, Wangchan, Rayong, 21210 Thailand

Email: bundit.b_s18@vistec.ac.th
