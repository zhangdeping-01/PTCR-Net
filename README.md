
# Hybrid Deep Learning for Predicting Postoperative Recurrence in Papillary Thyroid Carcinoma(PTCR-Net)
#Introduction
Postoperative recurrence prediction in papillary thyroid carcinoma (PTC) remains a significant challenge for clinical management, primarily due to the highly overlapping imaging features between recurrent lesions and postoperative inflammatory changes, as well as the extreme scarcity of positive samples. These limitations often lead to detection delays with conventional approaches. To address this, we introduce PTCR-Net, a hybrid deep learning framework designed to enhance early recurrence prediction. The framework innovatively integrates a Coordinate Attention Residual Network (CAR-Net) for precise lesion localization and a Progressive Efficient Network (PE-Net) to ensure robust performance with limited samples. Experimental results demonstrate that PTCR-Net achieves an accuracy of 93.33% and an AUC of 96.10%, significantly outperforming traditional methods. By providing both high accuracy and interpretable decision support, this framework establishes a novel paradigm for personalized postoperative follow-up in PTC management.
#Environment
1：Create a new conda environment with python version 3.8
···
conda create -n "PTCR-Net" python=3.8.18
conda activate PTCR-Net
···
2：Install PyTorch and torchvision.
···
We recommend an evironment with pytorch==2.0.0+cu118, torchvision==0.15.1+cu118, torchaudio==2.0.1+cu118
···
3：Install MMCV using MIM.
···
pip install -U openmim
mim install mmcv-full
···
4：Install MMClassification.
According to your needs, we support two install modes:

Install from source (Recommended): You want to develop your own image classification task or new features based on MMClassification framework. For example, you want to add new dataset or new models. And you can use all tools we provided.

Install as a Python package: You just want to call MMClassification’s APIs or import MMClassification’s modules in your project.
The specific installation process can be referred to：MMClassification （https://mmcls-test.readthedocs.io/en/latest/install.html#install-from-source）
5：Other packages can be found in the requirements.txt file.
#
