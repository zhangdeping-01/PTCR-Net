
Hybrid Deep Learning for Predicting Postoperative Recurrence in Papillary Thyroid Carcinoma(PTCR-Net)
=============
Introduction
----
Postoperative recurrence prediction in papillary thyroid carcinoma (PTC) remains a significant challenge for clinical management, primarily due to the highly overlapping imaging features between recurrent lesions and postoperative inflammatory changes, as well as the extreme scarcity of positive samples. These limitations often lead to detection delays with conventional approaches. To address this, we introduce PTCR-Net, a hybrid deep learning framework designed to enhance early recurrence prediction. The framework innovatively integrates a Coordinate Attention Residual Network (CAR-Net) for precise lesion localization and a Progressive Efficient Network (PE-Net) to ensure robust performance with limited samples. Experimental results demonstrate that PTCR-Net achieves an accuracy of 93.33% and an AUC of 96.10%, significantly outperforming traditional methods. By providing both high accuracy and interpretable decision support, this framework establishes a novel paradigm for personalized postoperative follow-up in PTC management.<br>  

Environment

1：Create a new conda environment with python version 3.8<br>  
```
conda create -n "PTCR-Net" python=3.8.18
conda activate PTCR-Net
```
2：Install PyTorch and torchvision.<br>  
```
We recommend an evironment with pytorch==2.0.0+cu118, torchvision==0.15.1+cu118, torchaudio==2.0.1+cu118
```
3：Install MMCV using MIM.<br>  
```
pip install -U openmim
mim install mmcv-full
```
4：Install MMClassification.<br>  
According to your needs, we support two install modes:<br>  

Install from source (Recommended): You want to develop your own image classification task or new features based on MMClassification framework. For example, you want to add new dataset or new models. And you can use all tools we provided.<br>  

Install as a Python package: You just want to call MMClassification’s APIs or import MMClassification’s modules in your project.<br>  
The specific installation process can be referred to：MMClassification （https://mmcls-test.readthedocs.io/en/latest/install.html#install-from-source）<br>  
5：Other packages can be found in the requirements.txt file.

dataset:
-----
The dataset format can refer to the format of MMClassification:CustomDataset (https://mmcls-test.readthedocs.io/zh-cn/latest/tutorials/new_dataset.html),The specific data structure is as follows:


```bash
mmclassification/
├── data/
│   └── my_dataset/
│       ├── meta/
│       │   ├── train.txt     
│       │   ├── val.txt       
│       │   └── test.txt    
│       ├── train/             
│       ├── val/            
│       └── test/             
```
Due to patient privacy protection and ethics committee regulations, the clinical dataset cannot be publicly shared. Researchers can request access through the following process:<br>  
Send an email to: Pangf6@mail.sysu.edu.cn <br>  
Subject line: "TCR-Net Dataset Access Request - [Your Institution Name]"<br>  

train:
-----
1: Go to the /mmclassification/configs directory and make sure that the models in the /mmclassification/mmpretrain/models/ folder are correctly registered.<br>  
2:Go to /mmclassification/tools, and then execute the following command:<br>  
```
python train.py --config your_config --work-dir your_checkpointsavedir
```
test
-----
```
python test.py --config your_config --work-dir your_resultsavedir --checkpoint your_checkpoint
```
> **⚠️ IMPORTANT NOTICE**  
> This repository contains the official implementation of the research paper submitted to **The Visual Computer** journal.  
> If you use this code in your research, please cite our paper:
```bibtex
@article{yuan2024tcrnet,
  title={TCR-Net: A Hybrid Deep Learning Framework for Postoperative Recurrence Risk in Thyroid Cancer},
  author={Yuan, Yuan and Zhang, Deping and Li, Eryong},
  journal={The Visual Computer},
  year={2024},
  note={Under review}
}
```



This repository references MMClassification(https://openmmlab.com/),ResNet(https://arxiv.org/abs/1512.03385), EfficientNetv2(https://arxiv.org/abs/2104.00298). Thanks to them.
