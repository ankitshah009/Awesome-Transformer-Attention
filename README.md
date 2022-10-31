# Ultimate-Awesome-Transformer-Attention [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

This repo contains a comprehensive paper list of **Vision Transformer & Attention**, including papers, codes, and related websites. <br>
This list is maintained by [Min-Hung Chen](https://minhungchen.netlify.app/). (*Actively* keep updating)

If you find some ignored papers, **feel free to [*create pull requests*](https://github.com/cmhungsteve/Awesome-Transformer-Attention/blob/main/How-to-PR.md), [*open issues*](https://github.com/cmhungsteve/Awesome-Transformer-Attention/issues/new), or [*email* me](mailto:vitec6@gmail.com)**. <br> 
Contributions in any form to make this list more comprehensive are welcome.

If you find this repository useful, please consider **[citing](#citation)** and **★STARing** this list. <br>
Feel free to share this list with others! 

**[Update: October, 2022]** Split the 2nd half of the paper list to [README_2.md](README_2.md) <br>
**[Update: October, 2022]** Added all the related papers from *ECCV 2022*! <br>
**[Update: September, 2022]** Added the [Transformer tutorial slides](http://lucasb.eyer.be/transformer) made by [Lucas Beyer](https://twitter.com/giffmana)! <br>
**[Update: July, 2022]** Added all the related papers from *ICML 2022*! <br>
**[Update: June, 2022]** Added all the related papers from *CVPR 2022*!

---
## Overview

- [Survey](#survey)
- [Image Classification / Backbone](#image-classification--backbone)
    - [Replace Conv w/ Attention](#replace-conv-w-attention)
        - [Pure Attention](#pure-attention)
        - [Conv-stem + Attention](#conv-stem--attention)
        - [Conv + Attention](#conv--attention)
    - [Vision Transformer](#vision-transformer)
        - [General Vision Transformer](#general-vision-transformer)
        - [Efficient Vision Transformer](#efficient-vision-transformer)
        - [Conv + Transformer](#conv--transformer)
        - [Training + Transformer](#training--transformer)
        - [Robustness + Transformer](#robustness--transformer)
        - [Model Compression + Transformer](#model-compression--transformer)
    - [Attention-Free](#attention-free)
        - [MLP-Series](#mlp-series)
        - [Other Attention-Free](#other-attention-free)
    - [Analysis for Transformer](#analysis-for-transformer)
- [Detection](#detection)
    - [Object Detection](#object-detection)
    - [3D Object Detection](#3d-object-detection)
    - [Multi-Modal Detection](#multi-modal-detection)
    - [HOI Detection](#hoi-detection)
    - [Salient Object Detection](#salient-object-detection)
    - [Other Detection Tasks](#other-detection-tasks)
- [Segmentation](#segmentation)
    - [Semantic Segmentation](#semantic-segmentation)
    - [Depth Estimation](#depth-estimation)
    - [Object Segmentation](#object-segmentation)
    - [Other Segmentation Tasks](#other-segmentation-tasks)
- [Video (High-level)](#video-high-level)
    - [Action Recognition](#action-recognition)
    - [Action Detection/Localization](#action-detectionlocalization)
    - [Action Prediction/Anticipation](#action-predictionanticipation)
    - [Video Object Segmentation](#video-object-segmentation)
    - [Video Instance Segmentation](#video-instance-segmentation)
    - [Other Video Tasks](#other-video-tasks)
- [Multi-Modality](#multi-modality)
    - [Visual Captioning](#visual-captioning)
    - [Visual Question Answering](#visual-question-answering)
    - [Visual Grounding](#visual-grounding)
    - [Multi-Modal Representation Learning](#multi-modal-representation-learning)
    - [Multi-Modal Retrieval](#multi-modal-retrieval)
    - [Multi-Modal Generation](#multi-modal-generation)
    - [Visual Document Understanding](#visual-document-understanding)
    - [Scene Graph](#scene-graph)
    - [Other Multi-Modal Tasks](#other-multi-modal-tasks)
- [Citation](#citation)
- [References](#references)

------ (The following papers are move to [README_2.md](README_2.md)) ------

- [Other High-level Vision Tasks](README_2.md#other-high-level-vision-tasks)
    - [Point Cloud / 3D](README_2.md#point-cloud--3d)
    - [Pose Estimation](README_2.md#pose-estimation)
    - [Tracking](README_2.md#tracking)
    - [Re-ID](README_2.md#re-id)
    - [Face](README_2.md#face)
    - [Neural Architecture Search](README_2.md#neural-architecture-search)
- [Transfer / X-Supervised / X-Shot / Continual Learning](README_2.md#transfer--x-supervised--x-shot--continual-learning)
- [Low-level Vision Tasks](README_2.md#low-level-vision-tasks)
    - [Image Restoration](README_2.md#image-restoration)
    - [Video Restoration](README_2.md#video-restoration)
    - [Inpainting / Completion / Outpainting](README_2.md#inpainting--completion--outpainting)
    - [Image Generation](README_2.md#image-generation)
    - [Video Generation](README_2.md#video-generation)
    - [Transfer / Translation / Manipulation](README_2.md#transfer--translation--manipulation)
    - [Other Low-Level Tasks](README_2.md#other-low-level-tasks)
- [Reinforcement Learning](README_2.md#reinforcement-learning)
    - [Navigation](README_2.md#navigation)
    - [Other RL Tasks](README_2.md#other-rl-tasks)
- [Medical](README_2.md#medical)
    - [Medical Segmentation](README_2.md#medical-segmentation)
    - [Medical Classification](README_2.md#medical-classification)
    - [Medical Detection](README_2.md#medical-detection)
    - [Medical Reconstruction](README_2.md#medical-detection)
    - [Medical Low-Level Vision](README_2.md#medical-low-level-vision)
    - [Medical Vision-Language](README_2.md#medical-vision-language)
    - [Medical Others](README_2.md#medical-others)
- [Other Tasks](README_2.md#other-tasks)
- [Attention Mechanisms in Vision/NLP](README_2.md#attention-mechanisms-in-visionnlp)
    - [Attention for Vision](README_2.md#attention-for-vision)
    - [NLP](README_2.md#attention-for-nlp)
    - [Both](README_2.md#attention-for-both)
    - [Others](README_2.md#attention-for-others)

---

## Survey
* "A Survey on Visual Transformer", TPAMI, 2022 (*Huawei*). [[Paper](https://arxiv.org/abs/2012.12556)] 
* "A Comprehensive Study of Vision Transformers on Dense Prediction Tasks", VISAP, 2022 (*NavInfo Europe, Netherlands*). [[Paper](https://arxiv.org/abs/2201.08683)]
* "Vision-and-Language Pretrained Models: A Survey", IJCAI, 2022 (*The University of Sydney*). [[Paper](https://arxiv.org/abs/2204.07356)]
* "Vision-Language Pre-training: Basics, Recent Advances, and Future Trends", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2210.09263)]
* "Vision+X: A Survey on Multimodal Learning in the Light of Data", arXiv, 2022 (*Illinois Institute of Technology, Chicago*). [[Paper](https://arxiv.org/abs/2210.02884)]
* "Vision Transformers for Action Recognition: A Survey", arXiv, 2022 (*Charles Sturt University, Australia*). [[Paper](https://arxiv.org/abs/2209.05700)]
* "VLP: A Survey on Vision-Language Pre-training", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2202.09061)]
* "Transformers in Remote Sensing: A Survey", arXiv, 2022 (*MBZUAI*). [[Paper](https://arxiv.org/abs/2209.01206)][[Github](https://github.com/VIROBO-15/Transformer-in-Remote-Sensing)]
* "Medical image analysis based on transformer: A Review", arXiv, 2022 (*NUS, Singapore*). [[Paper](https://arxiv.org/abs/2208.06643)]
* "3D Vision with Transformers: A Survey", arXiv, 2022 (*MBZUAI*). [[Paper](https://arxiv.org/abs/2208.04309)][[GitHub](https://github.com/lahoud/3d-vision-transformers)]
* "Vision Transformers: State of the Art and Research Challenges", arXiv, 2022 (*NYCU*). [[Paper](https://arxiv.org/abs/2207.03041)]
* "Transformers in Medical Imaging: A Survey", arXiv, 2022 (*MBZUAI*). [[Paper](https://arxiv.org/abs/2201.09873)][[GitHub](https://github.com/fahadshamshad/awesome-transformers-in-medical-imaging)]
* "Multimodal Learning with Transformers: A Survey", arXiv, 2022 (*Oxford*). [[Paper](https://arxiv.org/abs/2206.06488)]
* "Transforming medical imaging with Transformers? A comparative review of key properties, current progresses, and future perspectives", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2206.01136)]
* "Transformers in 3D Point Clouds: A Survey", arXiv, 2022 (*University of Waterloo*). [[Paper](https://arxiv.org/abs/2205.07417)]
* "A survey on attention mechanisms for medical applications: are we moving towards better algorithms?", arXiv, 2022 (*INESC TEC and University of Porto, Portugal*). [[Paper](https://arxiv.org/abs/2204.12406)]
* "Efficient Transformers: A Survey", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2009.06732)]
* "Are we ready for a new paradigm shift? A Survey on Visual Deep MLP", arXiv, 2022 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2111.04060)]
* "Vision Transformers in Medical Computer Vision - A Contemplative Retrospection", arXiv, 2022 (*National University of Sciences and Technology (NUST), Pakistan*). [[Paper](https://arxiv.org/abs/2203.15269)]
* "Video Transformers: A Survey", arXiv, 2022 (*Universitat de Barcelona, Spain*). [[Paper](https://arxiv.org/abs/2201.05991)] 
* "Transformers in Medical Image Analysis: A Review", arXiv, 2022 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2202.12165)]
* "Recent Advances in Vision Transformer: A Survey and Outlook of Recent Work", arXiv, 2022 (*?*). [[Paper](https://arxiv.org/abs/2203.01536)]
* "Transformers Meet Visual Learning Understanding: A Comprehensive Review", arXiv, 2022 (*Xidian University*). [[Paper](https://arxiv.org/abs/2203.12944)]
* "Image Captioning In the Transformer Age", arXiv, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2204.07374)][[GitHub](https://github.com/SjokerLily/awesome-image-captioning)]
* "Visual Attention Methods in Deep Learning: An In-Depth Survey", arXiv, 2022 (*Fayoum University, Egypt*). [[Paper](https://arxiv.org/abs/2204.07756)]
* "Transformers in Vision: A Survey", ACM Computing Surveys, 2021 (*MBZUAI*). [[Paper](https://arxiv.org/abs/2101.01169)]
* "Survey: Transformer based Video-Language Pre-training", arXiv, 2021 (*Renmin University of China*). [[Paper](https://arxiv.org/abs/2109.09920)]
* "A Survey of Transformers", arXiv, 2021 (*Fudan*). [[Paper](https://arxiv.org/abs/2106.04554)]
* "A Survey of Visual Transformers", arXiv, 2021 (*CAS*). [[Paper](https://arxiv.org/abs/2111.06091)]
* "Attention mechanisms and deep learning for machine vision: A survey of the state of the art", arXiv, 2021 (*University of Kashmir, India*). [[Paper](https://arxiv.org/abs/2106.07550)]

[[Back to Overview](#overview)]


## Image Classification / Backbone
### Replace Conv w/ Attention
#### Pure Attention
* **LR-Net**: "Local Relation Networks for Image Recognition", ICCV, 2019 (*Microsoft*). [[Paper](https://arxiv.org/abs/1904.11491)][[PyTorch (gan3sh500)](https://github.com/gan3sh500/local-relational-nets)]
* **SASA**: "Stand-Alone Self-Attention in Vision Models", NeurIPS, 2019 (*Google*). [[Paper](https://arxiv.org/abs/1906.05909)][[PyTorch-1 (leaderj1001)](https://github.com/leaderj1001/Stand-Alone-Self-Attention)][[PyTorch-2 (MerHS)](https://github.com/MerHS/SASA-pytorch)]
* **Axial-Transformer**: "Axial Attention in Multidimensional Transformers", arXiv, 2019 (*Google*). [[Paper](https://openreview.net/forum?id=H1e5GJBtDr)][[PyTorch (lucidrains)](https://github.com/lucidrains/axial-attention)]
* **SAN**: "Exploring Self-attention for Image Recognition", CVPR, 2020 (*CUHK + Intel*). [[Paper](https://arxiv.org/abs/2004.13621)][[PyTorch](https://github.com/hszhao/SAN)]
* **Axial-DeepLab**: "Axial-DeepLab: Stand-Alone Axial-Attention for Panoptic Segmentation", ECCV, 2020 (*Google*). [[Paper](https://arxiv.org/abs/2003.07853)][[PyTorch](https://github.com/csrhddlam/axial-deeplab)]
#### Conv-stem + Attention
* **GSA-Net**: "Global Self-Attention Networks for Image Recognition", arXiv, 2020 (*Google*). [[Paper](https://arxiv.org/abs/2010.03019)][[PyTorch (lucidrains)](https://github.com/lucidrains/global-self-attention-network)]
* **HaloNet**: "Scaling Local Self-Attention For Parameter Efficient Visual Backbones", CVPR, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2103.12731)][[PyTorch (lucidrains)](https://github.com/lucidrains/halonet-pytorch)]
* **CoTNet**: "Contextual Transformer Networks for Visual Recognition", CVPRW, 2021 (*JD*). [[Paper](https://arxiv.org/abs/2107.12292)][[PyTorch](https://github.com/JDAI-CV/CoTNet)]
* **HAT-Net**: "Vision Transformers with Hierarchical Attention", arXiv, 2022 (*ETHZ*). [[Paper](https://arxiv.org/abs/2106.03180)][[PyTorch (in construction)](https://github.com/yun-liu/HAT-Net)]
#### Conv + Attention
* **AA**: "Attention Augmented Convolutional Networks", ICCV, 2019 (*Google*). [[Paper](https://arxiv.org/abs/1904.09925)][[PyTorch (leaderj1001)](https://github.com/leaderj1001/Attention-Augmented-Conv2d)][[Tensorflow (titu1994)](https://github.com/titu1994/keras-attention-augmented-convs)]
* **GCNet**: "Global Context Networks", ICCVW, 2019 (& TPAMI 2020) (*Microsoft*). [[Paper](https://arxiv.org/abs/2012.13375)][[PyTorch](https://github.com/xvjiarui/GCNet)]
* **LambdaNetworks**: "LambdaNetworks: Modeling long-range Interactions without Attention", ICLR, 2021 (*Google*). [[Paper](https://openreview.net/forum?id=xTJEN-ggl1b)][[PyTorch-1 (lucidrains)](https://github.com/lucidrains/lambda-networks)][[PyTorch-2 (leaderj1001)](https://github.com/leaderj1001/LambdaNetworks)]
* **BoTNet**: "Bottleneck Transformers for Visual Recognition", CVPR, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2101.11605)][[PyTorch-1 (lucidrains)](https://github.com/lucidrains/bottleneck-transformer-pytorch)][[PyTorch-2 (leaderj1001)](https://github.com/leaderj1001/BottleneckTransformers)]
* **GCT**: "Gaussian Context Transformer", CVPR, 2021 (*Zhejiang University*). [[Paper](https://openaccess.thecvf.com/content/CVPR2021/html/Ruan_Gaussian_Context_Transformer_CVPR_2021_paper.html)]
* **CoAtNet**: "CoAtNet: Marrying Convolution and Attention for All Data Sizes", NeurIPS, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2106.04803)]
* **ACmix**: "On the Integration of Self-Attention and Convolution", CVPR, 2022 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2111.14556)][[PyTorch](https://github.com/LeapLabTHU/ACmix)]

[[Back to Overview](#overview)]

### Vision Transformer
#### General Vision Transformer
* **ViT**: "An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale", ICLR, 2021 (*Google*). [[Paper](https://openreview.net/forum?id=YicbFdNTTy)][[Tensorflow](https://github.com/google-research/vision_transformer)][[PyTorch (lucidrains)](https://github.com/lucidrains/vit-pytorch)]
* **Perceiver**: "Perceiver: General Perception with Iterative Attention", ICML, 2021 (*DeepMind*). [[Paper](https://arxiv.org/abs/2103.03206)][[PyTorch (lucidrains)](https://github.com/lucidrains/perceiver-pytorch)]
* **PiT**: "Rethinking Spatial Dimensions of Vision Transformers", ICCV, 2021 (*NAVER*). [[Paper](https://arxiv.org/abs/2103.16302)][[PyTorch](https://github.com/naver-ai/pit)]
* **VT**: "Visual Transformers: Where Do Transformers Really Belong in Vision Models?", ICCV, 2021 (*Facebook*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021/html/Wu_Visual_Transformers_Where_Do_Transformers_Really_Belong_in_Vision_Models_ICCV_2021_paper.html)][[PyTorch (tahmid0007)](https://github.com/tahmid0007/VisualTransformers)] 
* **PVT**: "Pyramid Vision Transformer: A Versatile Backbone for Dense Prediction without Convolutions", ICCV, 2021 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2102.12122)][[PyTorch](https://github.com/whai362/PVT)] 
* **iRPE**: "Rethinking and Improving Relative Position Encoding for Vision Transformer", ICCV, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2107.14222)][[PyTorch](https://github.com/microsoft/Cream/tree/main/iRPE)]
* **CaiT**: "Going deeper with Image Transformers", ICCV, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2103.17239)][[PyTorch](https://github.com/facebookresearch/deit)]
* **Swin-Transformer**: "Swin Transformer: Hierarchical Vision Transformer using Shifted Windows", ICCV, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2103.14030)][[PyTorch](https://github.com/microsoft/Swin-Transformer)][[PyTorch (berniwal)](https://github.com/berniwal/swin-transformer-pytorch)]
* **T2T-ViT**: "Tokens-to-Token ViT: Training Vision Transformers from Scratch on ImageNet", ICCV, 2021 (*Yitu*). [[Paper](https://arxiv.org/abs/2101.11986)][[PyTorch](https://github.com/yitu-opensource/T2T-ViT)]
* **FFNBN**: "Leveraging Batch Normalization for Vision Transformers", ICCVW, 2021 (*Microsoft*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021W/NeurArch/html/Yao_Leveraging_Batch_Normalization_for_Vision_Transformers_ICCVW_2021_paper.html)]
* **DPT**: "DPT: Deformable Patch-based Transformer for Visual Recognition", ACMMM, 2021 (*CAS*). [[Paper](https://arxiv.org/abs/2107.14467)][[PyTorch](https://github.com/CASIA-IVA-Lab/DPT)]
* **Focal**: "Focal Attention for Long-Range Interactions in Vision Transformers", NeurIPS, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2107.00641)][[PyTorch](https://github.com/microsoft/Focal-Transformer)]
* **XCiT**: "XCiT: Cross-Covariance Image Transformers", NeurIPS, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2106.09681)]
* **Twins**: "Twins: Revisiting Spatial Attention Design in Vision Transformers", NeurIPS, 2021 (*Meituan*). [[Paper](https://arxiv.org/abs/2104.13840)][[PyTorch)](https://github.com/Meituan-AutoML/Twins)]
* **ARM**: "Blending Anti-Aliasing into Vision Transformer", NeurIPS, 2021 (*Amazon*). [[Paper](https://arxiv.org/abs/2110.15156)][[GitHub (in construction)](https://github.com/amazon-research/anti-aliasing-transformer)]
* **DVT**: "Not All Images are Worth 16x16 Words: Dynamic Vision Transformers with Adaptive Sequence Length", NeurIPS, 2021 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2105.15075)][[PyTorch](https://github.com/blackfeather-wang/Dynamic-Vision-Transformer)]
* **Aug-S**: "Augmented Shortcuts for Vision Transformers", NeurIPS, 2021 (*Huawei*). [[Paper](https://arxiv.org/abs/2106.15941)]
* **TNT**: "Transformer in Transformer", NeurIPS, 2021 (*Huawei*). [[Paper](https://arxiv.org/abs/2103.00112)][[PyTorch](https://github.com/huawei-noah/CV-Backbones/tree/master/tnt_pytorch)][[PyTorch (lucidrains)](https://github.com/lucidrains/transformer-in-transformer)]
* **ViTAE**: "ViTAE: Vision Transformer Advanced by Exploring Intrinsic Inductive Bias", NeurIPS, 2021 (*The University of Sydney*). [[Paper](https://arxiv.org/abs/2106.03348)][[PyTorch](https://github.com/Annbless/ViTAE)]
* **DeepViT**: "DeepViT: Towards Deeper Vision Transformer", arXiv, 2021 (*NUS + ByteDance*). [[Paper](https://arxiv.org/abs/2103.11886)][[Code](https://github.com/zhoudaquan/dvit_repo)]
* **So-ViT**: "So-ViT: Mind Visual Tokens for Vision Transformer", arXiv, 2021 (*Dalian University of Technology*). [[Paper](https://arxiv.org/abs/2104.10935)][[PyTorch](https://github.com/jiangtaoxie/So-ViT)]
* **LV-ViT**: "All Tokens Matter: Token Labeling for Training Better Vision Transformers", NeurIPS, 2021 (*ByteDance*). [[Paper](https://arxiv.org/abs/2104.10858)][[PyTorch](https://github.com/zihangJiang/TokenLabeling)]
* **NesT**: "Aggregating Nested Transformers", arXiv, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2105.12723)][[Tensorflow](https://github.com/google-research/nested-transformer)]
* **KVT**: "KVT: k-NN Attention for Boosting Vision Transformers", arXiv, 2021 (*Alibaba*). [[Paper](https://arxiv.org/abs/2106.00515)]
* **Refined-ViT**: "Refiner: Refining Self-attention for Vision Transformers", arXiv, 2021 (*NUS, Singapore*). [[Paper](https://arxiv.org/abs/2106.03714)][[PyTorch](https://github.com/zhoudaquan/Refiner_ViT)]
* **Shuffle-Transformer**: "Shuffle Transformer: Rethinking Spatial Shuffle for Vision Transformer", arXiv, 2021 (*Tencent*). [[Paper](https://arxiv.org/abs/2106.03650)]
* **CAT**: "CAT: Cross Attention in Vision Transformer", arXiv, 2021 (*KuaiShou*). [[Paper](https://arxiv.org/abs/2106.05786)][[PyTorch](https://github.com/linhezheng19/CAT)]
* **V-MoE**: "Scaling Vision with Sparse Mixture of Experts", arXiv, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2106.05974)]
* **P2T**: "P2T: Pyramid Pooling Transformer for Scene Understanding", arXiv, 2021 (*Nankai University*). [[Paper](https://arxiv.org/abs/2106.12011)]
* **PvTv2**: "PVTv2: Improved Baselines with Pyramid Vision Transformer", arXiv, 2021 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2106.13797)][[PyTorch](https://github.com/whai362/PVT)]
* **LG-Transformer**: "Local-to-Global Self-Attention in Vision Transformers", arXiv, 2021 (*IIAI, UAE*). [[Paper](https://arxiv.org/abs/2107.04735)]
* **ViP**: "Visual Parser: Representing Part-whole Hierarchies with Transformers", arXiv, 2021 (*Oxford*). [[Paper](https://arxiv.org/abs/2107.05790)]
* **Scaled-ReLU**: "Scaled ReLU Matters for Training Vision Transformers", AAAI, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2109.03810)]
* **LIT**: "Less is More: Pay Less Attention in Vision Transformers", AAAI, 2022 (*Monash University*). [[Paper](https://arxiv.org/abs/2105.14217)][[PyTorch](https://github.com/zip-group/LIT)]
* **DTN**: "Dynamic Token Normalization Improves Vision Transformer", ICLR, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2112.02624)][[PyTorch (in construction)](https://github.com/wqshao126/DTN)]
* **RegionViT**: "RegionViT: Regional-to-Local Attention for Vision Transformers", ICLR, 2022 (*MIT-IBM Watson*). [[Paper](https://arxiv.org/abs/2106.02689)][[PyTorch](https://github.com/ibm/regionvit)]
* **CrossFormer**: "CrossFormer: A Versatile Vision Transformer Based on Cross-scale Attention", ICLR, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2108.00154)][[PyTorch](https://github.com/cheerss/CrossFormer)]
* **?**: "Scaling the Depth of Vision Transformers via the Fourier Domain Analysis", ICLR, 2022 (*UT Austin*). [[Paper](https://openreview.net/forum?id=O476oWmiNNp)]
* **ViT-G**: "Scaling Vision Transformers", CVPR, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2106.04560)]
* **CSWin**: "CSWin Transformer: A General Vision Transformer Backbone with Cross-Shaped Windows", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2107.00652)][[PyTorch](https://github.com/microsoft/CSWin-Transformer)]
* **MPViT**: "MPViT: Multi-Path Vision Transformer for Dense Prediction", CVPR, 2022 (*KAIST*). [[Paper](https://arxiv.org/abs/2112.11010)][[PyTorch](https://github.com/youngwanLEE/MPViT)]
* **Diverse-ViT**: "The Principle of Diversity: Training Stronger Vision Transformers Calls for Reducing All Levels of Redundancy", CVPR, 2022 (*UT Austin*). [[Paper](https://arxiv.org/abs/2203.06345)][[PyTorch](https://github.com/VITA-Group/Diverse-ViT)]
* **DW-ViT**: "Beyond Fixation: Dynamic Window Visual Transformer", CVPR, 2022 (*Dark Matter AI, China*). [[Paper](https://arxiv.org/abs/2203.12856)][[PyTorch (in construction)](https://github.com/pzhren/DW-ViT)]
* **MixFormer**: "MixFormer: Mixing Features across Windows and Dimensions", CVPR, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2204.02557)][[Paddle](https://github.com/PaddlePaddle/PaddleClas)]
* **DAT**: "Vision Transformer with Deformable Attention", CVPR, 2022 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2201.00520)][[PyTorch](https://github.com/LeapLabTHU/DAT)]
* **Swin-Transformer-V2**: "Swin Transformer V2: Scaling Up Capacity and Resolution", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.09883)][[PyTorch](https://github.com/microsoft/Swin-Transformer)]
* **MSG-Transformer**: "MSG-Transformer: Exchanging Local Spatial Information by Manipulating Messenger Tokens", CVPR, 2022 (*Huazhong University of Science & Technology*). [[Paper](https://arxiv.org/abs/2105.15168)][[PyTorch](https://github.com/hustvl/MSG-Transformer)]
* **NomMer**: "NomMer: Nominate Synergistic Context in Vision Transformer for Visual Recognition", CVPR, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2111.12994)][[PyTorch](https://github.com/TencentYoutuResearch/VisualRecognition-NomMer)]
* **Shunted**: "Shunted Self-Attention via Multi-Scale Token Aggregation", CVPR, 2022 (*NUS*). [[Paper](https://arxiv.org/abs/2111.15193)][[PyTorch](https://github.com/OliverRensu/Shunted-Transformer)]
* **PyramidTNT**: "PyramidTNT: Improved Transformer-in-Transformer Baselines with Pyramid Architecture", CVPRW, 2022 (*Huawei*). [[Paper](https://arxiv.org/abs/2201.00978)][[PyTorch](https://github.com/huawei-noah/CV-Backbones/tree/master/tnt_pytorch)]
* **X-ViT**: "X-ViT: High Performance Linear Vision Transformer without Softmax", CVPRW, 2022 (*Kakao*). [[Paper](https://arxiv.org/abs/2205.13805)]
* **ReMixer**: "ReMixer: Object-aware Mixing Layer for Vision Transformers", CVPRW, 2022 (*KAIST*). [[Paper](https://drive.google.com/file/d/1E6rXtj5h6tXiJR8Ae8u1vQcwyNyTZSVc/view)][[PyTorch](https://github.com/alinlab/remixer)]
* **UN**: "Unified Normalization for Accelerating and Stabilizing Transformers", ACMMM, 2022 (*Hikvision*). [[Paper](https://arxiv.org/abs/2208.01313)][[Code (in construction)](https://github.com/hikvision-research/Unified-Normalization)]
* **Wave-ViT**: "Wave-ViT: Unifying Wavelet and Transformers for Visual Representation Learning", ECCV, 2022 (*JD*). [[Paper](https://arxiv.org/abs/2207.04978)][[PyTorch](https://github.com/YehLi/ImageNetModel)]
* **DaViT**: "DaViT: Dual Attention Vision Transformers", ECCV, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2204.03645)][[PyTorch](https://github.com/dingmyu/davit)]
* **ScalableViT**: "ScalableViT: Rethinking the Context-oriented Generalization of Vision Transformer", ECCV, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2203.10790)]
* **MaxViT**: "MaxViT: Multi-Axis Vision Transformer", ECCV, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2204.01697)][[Tensorflow](https://github.com/google-research/maxvit)]
* **VSA**: "VSA: Learning Varied-Size Window Attention in Vision Transformers", ECCV, 2022 (*The University of Sydney*). [[Paper](https://arxiv.org/abs/2204.08446)][[PyTorch](https://github.com/ViTAE-Transformer/ViTAE-VSA)]
* **?**: "Expediting Large-Scale Vision Transformer for Dense Prediction without Fine-tuning", NeurIPS (*Microsoft*). [[Paper](https://arxiv.org/abs/2210.01035)]
* **BViT**: "BViT: Broad Attention based Vision Transformer", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2202.06268)]
* **O-ViT**: "O-ViT: Orthogonal Vision Transformer", arXiv, 2022 (*East China Normal University*). [[Paper](https://arxiv.org/abs/2201.12133)]
* **MOA-Transformer**: "Aggregating Global Features into Local Vision Transformer", arXiv, 2022 (*University of Kansas*). [[Paper](https://arxiv.org/abs/2201.12903)][[PyTorch](https://github.com/krushi1992/MOA-transformer)]
* **BOAT**: "BOAT: Bilateral Local Attention Vision Transformer", arXiv, 2022 (*Baidu + HKU*). [[Paper](https://arxiv.org/abs/2201.13027)]
* **ViTAEv2**: "ViTAEv2: Vision Transformer Advanced by Exploring Inductive Bias for Image Recognition and Beyond", arXiv, 2022 (*The University of Sydney*). [[Paper](https://arxiv.org/abs/2202.10108)]
* **VAN**: "Visual Attention Network", arXiv, 2022 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2202.09741)][[PyTorch](https://github.com/Visual-Attention-Network)]
* **HiP**: "Hierarchical Perceiver", arXiv, 2022 (*DeepMind*). [[Paper](https://arxiv.org/abs/2202.10890)]
* **PatchMerger**: "Learning to Merge Tokens in Vision Transformers", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2202.12015)]
* **DGT**: "Dynamic Group Transformer: A General Vision Transformer Backbone with Dynamic Group Attention", arXiv, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2203.03937)]
* **NAT**: "Neighborhood Attention Transformer", arXiv, 2022 (*Oregon*). [[Paper](https://arxiv.org/abs/2204.07143)][[PyTorch](https://github.com/SHI-Labs/Neighborhood-Attention-Transformer)]
* **ASF-former**: "Adaptive Split-Fusion Transformer", arXiv, 2022 (*Fudan*). [[Paper](https://arxiv.org/abs/2204.12196)][[PyTorch (in construction)](https://github.com/szx503045266/ASF-former)]
* **LITv2**: "Fast Vision Transformers with HiLo Attention", arXiv, 2022 (*Monash University*). [[Paper](https://arxiv.org/abs/2205.13213)][[Code (in construction)](https://github.com/zip-group/LITv2)]
* **PerViT**: "Peripheral Vision Transformer", arXiv, 2022 (*POSTECH*). [[Paper](https://arxiv.org/abs/2206.06801)]
* **SP-ViT**: "SP-ViT: Learning 2D Spatial Priors for Vision Transformers", arXiv, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2206.07662)]
* **EATFormer**: "EATFormer: Improving Vision Transformer Inspired by Evolutionary Algorithm", arXiv, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2206.09325)]
* **GC-ViT**: "Global Context Vision Transformers", arXiv, 2022 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2206.09959)][[PyTorch](https://github.com/NVlabs/GCViT)]
* **LinGlo**: "Rethinking Query-Key Pairwise Interactions in Vision Transformers", arXiv, 2022 (*TCL Research Wuhan*). [[Paper](https://arxiv.org/abs/2207.00188)]
* **Dual-ViT**: "Dual Vision Transformer", arXiv, 2022 (*JD*). [[Paper](https://arxiv.org/abs/2207.04976)][[PyTorch](https://github.com/YehLi/ImageNetModel)]
* **MMA**: "Multi-manifold Attention for Vision Transformers", arXiv, 2022 (*Centre for Research and Technology Hellas, Greece*). [[Paper](https://arxiv.org/abs/2207.08569)]
* **MAFormer**: "MAFormer: A Transformer Network with Multi-scale Attention Fusion for Visual Recognition", arXiv, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2209.01620)]
* **AEWin**: "Axially Expanded Windows for Local-Global Interaction in Vision Transformers", arXiv, 2022 (*Southwest Jiaotong University*). [[Paper](https://arxiv.org/abs/2209.08726)]
* **MAGNETO**: "Foundation Transformers", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2210.06423)]
* **GrafT**: "Grafting Vision Transformers", arXiv, 2022 (*Stony Brook*). [[Paper](https://arxiv.org/abs/2210.15943)]
#### Efficient Vision Transformer
* **DeiT**: "Training data-efficient image transformers & distillation through attention", ICML, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2012.12877)][[PyTorch](https://github.com/facebookresearch/deit)]
* **ConViT**: "ConViT: Improving Vision Transformers with Soft Convolutional Inductive Biases", ICML, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2103.10697)][[Code](https://github.com/facebookresearch/convit)]
* **?**: "Improving the Efficiency of Transformers for Resource-Constrained Devices", DSD, 2021 (*NavInfo Europe, Netherlands*). [[Paper](https://arxiv.org/abs/2106.16006)]
* **PS-ViT**: "Vision Transformer with Progressive Sampling", ICCV, 2021 (*CPII*). [[Paper](https://arxiv.org/abs/2108.01684)]
* **HVT**: "Scalable Visual Transformers with Hierarchical Pooling", ICCV, 2021 (*Monash University*). [[Paper](https://arxiv.org/abs/2103.10619)][[PyTorch](https://github.com/MonashAI/HVT)]
* **CrossViT**: "CrossViT: Cross-Attention Multi-Scale Vision Transformer for Image Classification", ICCV, 2021 (*MIT-IBM*). [[Paper](https://arxiv.org/abs/2103.14899)][[PyTorch](https://github.com/IBM/CrossViT)]
* **ViL**: "Multi-Scale Vision Longformer: A New Vision Transformer for High-Resolution Image Encoding", ICCV, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2103.15358)][[PyTorch](https://github.com/microsoft/vision-longformer)]
* **Visformer**: "Visformer: The Vision-friendly Transformer", ICCV, 2021 (*Beihang University*). [[Paper](https://arxiv.org/abs/2104.12533)][[PyTorch](https://github.com/danczs/Visformer)]
* **MultiExitViT**: "Multi-Exit Vision Transformer for Dynamic Inference", BMVC, 2021 (*Aarhus University, Denmark*). [[Paper](https://arxiv.org/abs/2106.15183)][[Tensorflow](https://gitlab.au.dk/maleci/multiexitvit)]
* **SViTE**: "Chasing Sparsity in Vision Transformers: An End-to-End Exploration", NeurIPS, 2021 (*UT Austin*). [[Paper](https://arxiv.org/abs/2106.04533)][[PyTorch](https://github.com/VITA-Group/SViTE)]
* **DGE**: "Dynamic Grained Encoder for Vision Transformers", NeurIPS, 2021 (*Megvii*). [[Paper](https://papers.nips.cc/paper/2021/hash/2d969e2cee8cfa07ce7ca0bb13c7a36d-Abstract.html)][[PyTorch](https://github.com/StevenGrove/vtpack)]
* **GG-Transformer**: "Glance-and-Gaze Vision Transformer", NeurIPS, 2021 (*JHU*). [[Paper](https://arxiv.org/abs/2106.02277)][[Code (in construction)](https://github.com/yucornetto/GG-Transformer)]
* **DynamicViT**: "DynamicViT: Efficient Vision Transformers with Dynamic Token Sparsification", NeurIPS, 2021 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2106.02034)][[PyTorch](https://github.com/raoyongming/DynamicViT)][[Website](https://dynamicvit.ivg-research.xyz/)]
* **ResT**: "ResT: An Efficient Transformer for Visual Recognition", NeurIPS, 2021 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2105.13677)][[PyTorch](https://github.com/wofmanaf/ResT)]
* **Adder-Transformer**: "Adder Attention for Vision Transformer", NeurIPS, 2021 (*Huawei*). [[Paper](https://proceedings.neurips.cc/paper/2021/hash/a57e8915461b83adefb011530b711704-Abstract.html)]
* **SOFT**: "SOFT: Softmax-free Transformer with Linear Complexity", NeurIPS, 2021 (*Fudan*). [[Paper](https://arxiv.org/abs/2110.11945)][[PyTorch](https://github.com/fudan-zvg/SOFT)][[Website](https://fudan-zvg.github.io/SOFT/)]
* **IA-RED<sup>2</sup>**: "IA-RED<sup>2</sup>: Interpretability-Aware Redundancy Reduction for Vision Transformers", NeurIPS, 2021 (*MIT-IBM*). [[Paper](https://arxiv.org/abs/2106.12620)][[Website](http://people.csail.mit.edu/bpan/ia-red/)]
* **LocalViT**: "LocalViT: Bringing Locality to Vision Transformers", arXiv, 2021 (*ETHZ*). [[Paper](https://arxiv.org/abs/2104.05707)][[PyTorch](https://github.com/ofsoundof/LocalViT)]
* **CCT**: "Escaping the Big Data Paradigm with Compact Transformers", arXiv, 2021 (*University of Oregon*). [[Paper](https://arxiv.org/abs/2104.05704)][[PyTorch](https://github.com/SHI-Labs/Compact-Transformers)]
* **DiversePatch**: "Vision Transformers with Patch Diversification", arXiv, 2021 (*UT Austin + Facebook*). [[Paper](https://arxiv.org/abs/2104.12753)][[PyTorch](https://github.com/ChengyueGongR/PatchVisionTransformer)] 
* **SL-ViT**: "Single-Layer Vision Transformers for More Accurate Early Exits with Less Overhead", arXiv, 2021 (*Aarhus University*). [[Paper](https://arxiv.org/abs/2105.09121)]
* **?**: "Multi-Exit Vision Transformer for Dynamic Inference", arXiv, 2021 (*Aarhus University, Denmark*). [[Paper](https://arxiv.org/abs/2106.15183)]
* **DeiT-Manifold**: "Efficient Vision Transformers via Fine-Grained Manifold Distillation", arXiv, 2021 (*Huawei*). [[Paper](https://arxiv.org/abs/2107.01378)]
* **ViX**: "Vision Xformers: Efficient Attention for Image Classification", arXiv, 2021 (*Indian Institute of Technology Bombay*). [[Paper](https://arxiv.org/abs/2107.02239)]
* **Transformer-LS**: "Long-Short Transformer: Efficient Transformers for Language and Vision", NeurIPS, 2021 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2107.02192)][[PyTorch](https://github.com/NVIDIA/transformer-ls)]
* **WideNet**: "Go Wider Instead of Deeper", arXiv, 2021 (*NUS*). [[Paper](https://arxiv.org/abs/2107.11817)]
* **Armour**: "Armour: Generalizable Compact Self-Attention for Vision Transformers", arXiv, 2021 (*Arm*). [[Paper](https://arxiv.org/abs/2108.01778)]
* **IPE**: "Exploring and Improving Mobile Level Vision Transformers", arXiv, 2021 (*CUHK*). [[Paper](https://arxiv.org/abs/2108.13015)]
* **DS-Net++**: "DS-Net++: Dynamic Weight Slicing for Efficient Inference in CNNs and Transformers", arXiv, 2021 (*Monash University*). [[Paper](https://arxiv.org/abs/2109.10060)][[PyTorch](https://github.com/changlin31/DS-Net)]
* **UFO-ViT**: "UFO-ViT: High Performance Linear Vision Transformer without Softmax", arXiv, 2021 (*Kakao*). [[Paper](https://arxiv.org/abs/2109.14382)]
* **Token-Pooling**: "Token Pooling in Visual Transformers", arXiv, 2021 (*Apple*). [[Paper](https://arxiv.org/abs/2110.03860)]
* **Evo-ViT**: "Evo-ViT: Slow-Fast Token Evolution for Dynamic Vision Transformer", AAAI, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2108.01390)][[PyTorch](https://github.com/YifanXu74/Evo-ViT)]
* **PS-Attention**: "Pale Transformer: A General Vision Transformer Backbone with Pale-Shaped Attention", AAAI, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2112.14000)][[Paddle](https://github.com/BR-IDL/PaddleViT)]
* **ShiftViT**: "When Shift Operation Meets Vision Transformer: An Extremely Simple Alternative to Attention Mechanism", AAAI, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2201.10801)][[PyTorch](https://github.com/microsoft/SPACH)]
* **EViT**: "Not All Patches are What You Need: Expediting Vision Transformers via Token Reorganizations", ICLR, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2202.07800)][[PyTorch](https://github.com/youweiliang/evit)]
* **QuadTree**: "QuadTree Attention for Vision Transformers", ICLR, 2022 (*Simon Fraser + Alibaba*). [[Paper](https://arxiv.org/abs/2201.02767)][[PyTorch](https://github.com/Tangshitao/QuadtreeAttention)]
* **Anti-Oversmoothing**: "Anti-Oversmoothing in Deep Vision Transformers via the Fourier Domain Analysis: From Theory to Practice", ICLR, 2022 (*UT Austin*). [[Paper](https://arxiv.org/abs/2203.05962)][[PyTorch](https://github.com/VITA-Group/ViT-Anti-Oversmoothing)]
* **QnA**: "Learned Queries for Efficient Local Attention", CVPR, 2022 (*Tel-Aviv*). [[Paper](https://arxiv.org/abs/2112.11435)][[Jax](https://github.com/moabarar/qna)]
* **LVT**: "Lite Vision Transformer with Enhanced Self-Attention", CVPR, 2022 (*Adobe*). [[Paper](https://arxiv.org/abs/2112.10809)][[PyTorch](https://github.com/Chenglin-Yang/LVT)]
* **A-ViT**: "A-ViT: Adaptive Tokens for Efficient Vision Transformer", CVPR, 2022 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2112.07658)][[Website](https://a-vit.github.io/)]
* **PS-ViT**: "Patch Slimming for Efficient Vision Transformers", CVPR, 2022 (*Huawei*). [[Paper](https://arxiv.org/abs/2106.02852)]
* **Rev-MViT**: "Reversible Vision Transformers", CVPR, 2022 (*Meta*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Mangalam_Reversible_Vision_Transformers_CVPR_2022_paper.html)][[PyTorch](https://github.com/facebookresearch/mvit)]
* **AdaViT**: "AdaViT: Adaptive Vision Transformers for Efficient Image Recognition", CVPR, 2022 (*Fudan*). [[Paper](https://arxiv.org/abs/2111.15668)]
* **DQS**: "Dynamic Query Selection for Fast Visual Perceiver", CVPRW, 2022 (*Sorbonne Universite', France*). [[Paper](https://arxiv.org/abs/2205.10873)]
* **ATS**: "Adaptive Token Sampling For Efficient Vision Transformers", ECCV, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.15667)][[Website](https://adaptivetokensampling.github.io/)]
* **EdgeViT**: "EdgeViTs: Competing Light-weight CNNs on Mobile Devices with Vision Transformers", ECCV, 2022 (*Samsung*). [[Paper](https://arxiv.org/abs/2205.03436)][[PyTorch](https://github.com/saic-fi/edgevit)]
* **SReT**: "Sliced Recursive Transformer", ECCV, 2022 (*CMU + MBZUAI*). [[Paper](https://arxiv.org/abs/2111.05297)][[PyTorch](https://github.com/szq0214/SReT)]
* **SiT**: "Self-slimmed Vision Transformer", ECCV, 2022 (*SenseTime*). [[Paper](https://arxiv.org/abs/2111.12624)][[PyTorch](https://github.com/Sense-X/SiT)]
* **DFvT**: "Doubly-Fused ViT: Fuse Information from Vision Transformer Doubly with Local Representation", ECCV, 2022 (*Alibaba*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/322_ECCV_2022_paper.php)]
* **M<sup>3</sup>ViT**: "M<sup>3</sup>ViT: Mixture-of-Experts Vision Transformer for Efficient Multi-task Learning with Model-Accelerator Co-design", NeurIPS, 2022 (*UT Austin*). [[Paper](https://arxiv.org/abs/2210.14793)][[PyTorch](https://github.com/VITA-Group/M3ViT)]
* **TerViT**: "TerViT: An Efficient Ternary Vision Transformer", arXiv, 2022 (*Beihang University*). [[Paper](https://arxiv.org/abs/2201.08050)]
* **MT-ViT**: "Multi-Tailed Vision Transformer for Efficient Inference", arXiv, 2022 (*Wuhan University*). [[Paper](https://arxiv.org/abs/2203.01587)]
* **ViT-P**: "ViT-P: Rethinking Data-efficient Vision Transformers from Locality", arXiv, 2022 (*Chongqing University of Technology*). [[Paper](https://arxiv.org/abs/2203.02358)]
* **CF-ViT**: "Coarse-to-Fine Vision Transformer", arXiv, 2022 (*Xiamen University + Tencent*). [[Paper](https://arxiv.org/abs/2203.03821)][[PyTorch](https://github.com/ChenMnZ/CF-ViT)]
* **EIT**: "EIT: Efficiently Lead Inductive Biases to ViT", arXiv, 2022 (*Academy of Military Sciences, China*). [[Paper](https://arxiv.org/abs/2203.07116)]
* **SepViT**: "SepViT: Separable Vision Transformer", arXiv, 2022 (*University of Electronic Science and Technology of China*). [[Paper](https://arxiv.org/abs/2203.15380)]
* **ResT-V2**: "ResT V2: Simpler, Faster and Stronger", arXiv, 2022 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2204.07366)][[PyTorch](https://github.com/wofmanaf/ResT)]
* **TRT-ViT**: "TRT-ViT: TensorRT-oriented Vision Transformer", arXiv, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2205.09579)]
* **SuperViT**: "Super Vision Transformer", arXiv, 2022 (*Xiamen University*). [[Paper](https://arxiv.org/abs/2205.11397)][[PyTorch](https://github.com/lmbxmu/SuperViT)]
* **EfficientViT**: "EfficientViT: Enhanced Linear Attention for High-Resolution Low-Computation Visual Recognition", arXiv, 2022 (*MIT*). [[Paper](https://arxiv.org/abs/2205.14756)]
* **EfficientFormer**: "EfficientFormer: Vision Transformers at MobileNet Speed", arXiv, 2022 (*Snap*). [[Paper](https://arxiv.org/abs/2206.01191)][[Code (in construction)](https://github.com/snap-research/EfficientFormer)]
* **Tutel**: "Tutel: Adaptive Mixture-of-Experts at Scale", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.03382)][[PyTorch](https://github.com/microsoft/tutel)]
* **SimA**: "SimA: Simple Softmax-free Attention for Vision Transformers", arXiv, 2022 (*Maryland + UC Davis*). [[Paper](https://arxiv.org/abs/2206.08898)][[PyTorch](https://github.com/UCDvision/sima)]
* **EdgeNeXt**: "EdgeNeXt: Efficiently Amalgamated CNN-Transformer Architecture for Mobile Vision Applications", arXiv, 2022 (*MBZUAI*). [[Paper](https://arxiv.org/abs/2206.10589)][[PyTorch](https://github.com/mmaaz60/EdgeNeXt)]
* **VVT**: "Vicinity Vision Transformer", arXiv, 2022 (*Australian National University*). [[Paper](https://arxiv.org/abs/2206.10552)][[Code (in construction)](https://github.com/OpenNLPLab/Vicinity-Vision-Transformer)]
* **SOFT**: "Softmax-free Linear Transformers", arXiv, 2022 (*Fudan*). [[Paper](https://arxiv.org/abs/2207.03341)][[PyTorch](https://github.com/fudan-zvg/SOFT)]
* **MaiT**: "MaiT: Leverage Attention Masks for More Efficient Image Transformers", arXiv, 2022 (*Samsung*). [[Paper](https://arxiv.org/abs/2207.03006)]
* **LightViT**: "LightViT: Towards Light-Weight Convolution-Free Vision Transformers", arXiv, 2022 (*SenseTime*). [[Paper](https://arxiv.org/abs/2207.05557)][[Code (in construction)](https://github.com/hunto/LightViT)]
* **Next-ViT**: "Next-ViT: Next Generation Vision Transformer for Efficient Deployment in Realistic Industrial Scenarios", arXiv, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2207.05501)]
* **XFormer**: "Lightweight Vision Transformer with Cross Feature Attention", arXiv, 2022 (*Samsung*). [[Paper](https://arxiv.org/pdf/2207.07268.pdf)]
* **PatchDropout**: "PatchDropout: Economizing Vision Transformers Using Patch Dropout", arXiv, 2022 (*KTH, Sweden*). [[Paper](https://arxiv.org/abs/2208.07220)]
* **ClusTR**: "ClusTR: Exploring Efficient Self-attention via Clustering for Vision Transformers", arXiv, 2022 (*The University of Adelaide, Australia*). [[Paper](https://arxiv.org/abs/2208.13138)]
* **DiNAT**: "Dilated Neighborhood Attention Transformer", arXiv, 2022 (*University of Oregon*). [[Paper](https://arxiv.org/abs/2209.15001)][[PyTorch](https://github.com/SHI-Labs/Neighborhood-Attention-Transformer)]
* **MobileViTv3**: "MobileViTv3: Mobile-Friendly Vision Transformer with Simple and Effective Fusion of Local, Global and Input Features", arXiv, 2022 (*Micron*). [[Paper](https://arxiv.org/abs/2209.15159)][[PyTorch](https://github.com/micronDLA/MobileViTv3)]
* **ToMe**: "Token Merging: Your ViT But Faster", arXiv, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2210.09461)][[PyTorch](https://github.com/facebookresearch/ToMe)]
* **ViTCoD**: "ViTCoD: Vision Transformer Acceleration via Dedicated Algorithm and Accelerator Co-Design", IEEE International Symposium on High-Performance Computer Architecture (HPCA), 2023 (*Georgia Tech*). [[Paper](https://arxiv.org/abs/2210.09573)]
#### Conv + Transformer
* **LeViT**: "LeViT: a Vision Transformer in ConvNet's Clothing for Faster Inference", ICCV, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2104.01136)][[PyTorch](https://github.com/facebookresearch/LeViT)]
* **CeiT**: "Incorporating Convolution Designs into Visual Transformers", ICCV, 2021 (*SenseTime*). [[Paper](https://arxiv.org/abs/2103.11816)][[PyTorch (rishikksh20)](https://github.com/rishikksh20/CeiT)]
* **Conformer**: "Conformer: Local Features Coupling Global Representations for Visual Recognition", ICCV, 2021 (*CAS*). [[Paper](https://arxiv.org/abs/2105.03889)][[PyTorch](https://github.com/pengzhiliang/Conformer)]
* **CoaT**: "Co-Scale Conv-Attentional Image Transformers", ICCV, 2021 (*UCSD*). [[Paper](https://arxiv.org/abs/2104.06399)][[PyTorch](https://github.com/mlpc-ucsd/CoaT)]
* **CvT**: "CvT: Introducing Convolutions to Vision Transformers", ICCV, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2103.15808)][[Code](https://github.com/leoxiaobin/CvT)]
* **ViTc**: "Early Convolutions Help Transformers See Better", NeurIPS, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2106.14881)]
* **ConTNet**: "ConTNet: Why not use convolution and transformer at the same time?", arXiv, 2021 (*ByteDance*). [[Paper](https://arxiv.org/abs/2104.13497)][[PyTorch](https://github.com/yan-hao-tian/ConTNet)]
* **SPACH**: "A Battle of Network Structures: An Empirical Study of CNN, Transformer, and MLP", arXiv, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2108.13002)]
* **MobileViT**: "MobileViT: Light-weight, General-purpose, and Mobile-friendly Vision Transformer", ICLR, 2022 (*Apple*). [[Paper](https://arxiv.org/abs/2110.02178)][[PyTorch](https://github.com/apple/ml-cvnets)]
* **CMT**: "CMT: Convolutional Neural Networks Meet Vision Transformers", CVPR, 2022 (*Huawei*). [[Paper](https://arxiv.org/abs/2107.06263)]
* **Mobile-Former**: "Mobile-Former: Bridging MobileNet and Transformer", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2108.05895)][[PyTorch (in construction)](https://github.com/aaboys/mobileformer)]
* **TinyViT**: "TinyViT: Fast Pretraining Distillation for Small Vision Transformers", ECCV, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2207.10666)][[PyTorch](https://github.com/microsoft/Cream/tree/main/TinyViT)]
* **CETNet**: "Convolutional Embedding Makes Hierarchical Vision Transformer Stronger", ECCV, 2022 (*OPPO*). [[Paper](https://arxiv.org/abs/2207.13317)]
* **ParC-Net**: "ParC-Net: Position Aware Circular Convolution with Merits from ConvNets and Transformer", ECCV, 2022 (*Intellifusion, China*). [[Paper](https://arxiv.org/abs/2203.03952)][[PyTorch](https://github.com/hkzhang91/ParC-Net)]
* **?**: "How to Train Vision Transformer on Small-scale Datasets?", BMVC, 2022 (*MBZUAI*). [[Paper](https://arxiv.org/abs/2210.07240)][[PyTorch](https://github.com/hananshafi/vits-for-small-scale-datasets)]
* **DHVT**: "Bridging the Gap Between Vision Transformers and Convolutional Neural Networks on Small Datasets", NeurIPS, 2022 (*USTC*). [[Paper](https://arxiv.org/abs/2210.05958)][[Code (in construction)](https://github.com/ArieSeirack/DHVT)]
* **DenseDCT**: "Explicitly Increasing Input Information Density for Vision Transformers on Small Datasets", NeurIPSW, 2022 (*University of Kansas*). [[Paper](https://arxiv.org/abs/2210.14319)]
* **CXV**: "Convolutional Xformers for Vision", arXiv, 2022 (*IIT Bombay*). [[Paper](https://arxiv.org/abs/2201.10271)][[PyTorch](https://github.com/pranavphoenix/CXV)]
* **ConvMixer**: "Patches Are All You Need?", arXiv, 2022 (*CMU*). [[Paper](https://arxiv.org/abs/2201.09792)][[PyTorch](https://github.com/locuslab/convmixer)]
* **MobileViTv2**: "Separable Self-attention for Mobile Vision Transformers", arXiv, 2022 (*Apple*). [[Paper](https://arxiv.org/abs/2206.02680)][[PyTorch](https://github.com/apple/ml-cvnets)]
* **UniFormer**: "UniFormer: Unifying Convolution and Self-attention for Visual Recognition", arXiv, 2022 (*SenseTime*). [[Paper](https://arxiv.org/abs/2201.09450)][[PyTorch](https://github.com/Sense-X/UniFormer)]
* **EdgeFormer**: "EdgeFormer: Improving Light-weight ConvNets by Learning from Vision Transformers", arXiv, 2022 (*?*). [[Paper](https://arxiv.org/abs/2203.03952)]
* **iFormer**: "Inception Transformer", arXiv, 2022 (*Sea AI Lab*). [[Paper](https://arxiv.org/abs/2205.12956)][[PyTorch](https://github.com/sail-sg/iFormer)]
* **MoCoViT**: "MoCoViT: Mobile Convolutional Vision Transformer", arXiv, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2205.12635)]
* **DynamicViT**: "Dynamic Spatial Sparsification for Efficient Vision Transformers and Convolutional Neural Networks", arXiv, 2022 (*Tsinghua University*). [[Paper](https://arxiv.org/abs/2207.01580)][[PyTorch](https://github.com/raoyongming/DynamicViT)]
* **ConvFormer**: "ConvFormer: Closing the Gap Between CNN and Vision Transformers", arXiv, 2022 (*National University of Defense Technology, China*). [[Paper](https://arxiv.org/abs/2209.07738)]
* **Fast-ParC**: "Fast-ParC: Position Aware Global Kernel for ConvNets and ViTs", arXiv, 2022 (*Intellifusion, China*). [[Paper](https://arxiv.org/abs/2210.04020)]
* **MetaFormer**: "MetaFormer Baselines for Vision", arXiv, 2022 (*Sea AI Lab*). [[Paper](https://arxiv.org/abs/2210.13452)][[PyTorch](https://github.com/sail-sg/metaformer)]
* **SATA**: "Accumulated Trivial Attention Matters in Vision Transformers on Small Datasets", WACV, 2023 (*University of Kansas*). [[Paper](https://arxiv.org/abs/2210.12333)][[PyTorch (in construction)](https://github.com/xiangyu8/SATA)]
#### Training + Transformer
* **iGPT**: "Generative Pretraining From Pixels", ICML, 2020 (*OpenAI*). [[Paper](http://proceedings.mlr.press/v119/chen20s.html)][[Tensorflow](https://github.com/openai/image-gpt)]
* **MoCo-V3**: "An Empirical Study of Training Self-Supervised Vision Transformers", ICCV, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2104.02057)]
* **DINO**: "Emerging Properties in Self-Supervised Vision Transformers", ICCV, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2104.14294)][[PyTorch](https://github.com/facebookresearch/dino)]
* **drloc**: "Efficient Training of Visual Transformers with Small Datasets", NeurIPS, 2021 (*University of Trento*). [[Paper](https://arxiv.org/abs/2106.03746)][[PyTorch](https://github.com/yhlleo/VTs-Drloc)]
* **CARE**: "Revitalizing CNN Attentions via Transformers in Self-Supervised Visual Representation Learning", NeurIPS, 2021 (*Tencent*). [[Paper](https://arxiv.org/abs/2110.05340)][[PyTorch](https://github.com/ChongjianGE/CARE)]
* **MST**: "MST: Masked Self-Supervised Transformer for Visual Representation", NeurIPS, 2021 (*SenseTime*). [[Paper](https://arxiv.org/abs/2106.05656)]
* **SiT**: "SiT: Self-supervised Vision Transformer", arXiv, 2021 (*University of Surrey*). [[Paper](https://arxiv.org/abs/2104.03602)][[PyTorch](https://github.com/Sara-Ahmed/SiT)]
* **MoBY**: "Self-Supervised Learning with Swin Transformers", arXiv, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2105.04553)][[PyTorch](https://github.com/SwinTransformer/Transformer-SSL)]
* **?**: "Investigating Transfer Learning Capabilities of Vision Transformers and CNNs by Fine-Tuning a Single Trainable Block", arXiv, 2021 (*Pune Institute of Computer Technology, India*). [[Paper](https://arxiv.org/abs/2110.05270)]
* **Annotations-1.3B**: "Billion-Scale Pretraining with Vision Transformers for Multi-Task Visual Representations", WACV, 2022 (*Pinterest*). [[Paper](https://arxiv.org/abs/2108.05887)]
* **BEiT**: "BEiT: BERT Pre-Training of Image Transformers", ICLR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2106.08254)][[PyTorch](https://github.com/microsoft/unilm/tree/master/beit)]
* **EsViT**: "Efficient Self-supervised Vision Transformers for Representation Learning", ICLR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2106.09785)]
* **iBOT**: "Image BERT Pre-training with Online Tokenizer", ICLR, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2111.07832)][[PyTorch](https://github.com/bytedance/ibot)]
* **MaskFeat**: "Masked Feature Prediction for Self-Supervised Visual Pre-Training", CVPR, 2022 (*Facebook*). [[Paper](https://arxiv.org/abs/2112.09133)]
* **AutoProg**: "Automated Progressive Learning for Efficient Training of Vision Transformers", CVPR, 2022 (*Monash University, Australia*). [[Paper](https://arxiv.org/abs/2203.14509)][[Code (in construction)](https://github.com/changlin31/AutoProg)]
* **MAE**: "Masked Autoencoders Are Scalable Vision Learners", CVPR, 2022 (*Facebook*). [[Paper](https://arxiv.org/abs/2111.06377)][[PyTorch](https://github.com/facebookresearch/mae)][[PyTorch (pengzhiliang)](https://github.com/pengzhiliang/MAE-pytorch)]
* **SimMIM**: "SimMIM: A Simple Framework for Masked Image Modeling", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.09886)][[PyTorch](https://github.com/microsoft/SimMIM)]
* **SelfPatch**: "Patch-Level Representation Learning for Self-Supervised Vision Transformers", CVPR, 2022 (*KAIST*). [[Paper](https://arxiv.org/abs/2206.07990)][[PyTorch](https://github.com/alinlab/SelfPatch)]
* **Bootstrapping-ViTs**: "Bootstrapping ViTs: Towards Liberating Vision Transformers from Pre-training", CVPR, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2112.03552)][[PyTorch](https://github.com/zhfeing/Bootstrapping-ViTs-pytorch)]
* **TransMix**: "TransMix: Attend to Mix for Vision Transformers", CVPR, 2022 (*JHU*). [[Paper](https://arxiv.org/abs/2111.09833)][[PyTorch](https://github.com/Beckschen/TransMix)]
* **PatchRot**: "PatchRot: A Self-Supervised Technique for Training Vision Transformers", CVPRW, 2022 (*Arizona State*). [[Paper](https://drive.google.com/file/d/1ZHdBMa-MCx05Y0teqb0vmgiiYj8t5xBB/view)]
* **SplitMask**: "Are Large-scale Datasets Necessary for Self-Supervised Pre-training?", CVPRW, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2112.10740)]
* **MC-SSL**: "MC-SSL: Towards Multi-Concept Self-Supervised Learning", CVPRW, 2022 (*University of Surrey, UK*). [[Paper](https://arxiv.org/abs/2111.15340)]
* **RelViT**: "Where are my Neighbors? Exploiting Patches Relations in Self-Supervised Vision Transformer", CVPRW, 2022 (*University of Padova, Italy*). [[Paper](https://arxiv.org/abs/2206.00481?context=cs)]
* **data2vec**: "data2vec: A General Framework for Self-supervised Learning in Speech, Vision and Language", ICML, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2202.03555)][[PyTorch](https://github.com/facebookresearch/fairseq/tree/main/examples/data2vec)]
* **SSTA**: "Self-supervised Models are Good Teaching Assistants for Vision Transformers", ICML, 2022 (*Tencent*). [[Paper](https://proceedings.mlr.press/v162/wu22c.html)][[Code (in construction)](https://github.com/GlassyWu/SSTA)]
* **MP3**: "Position Prediction as an Effective Pretraining Strategy", ICML, 2022 (*Apple*). [[Paper](https://arxiv.org/abs/2207.07611)]
* **CutMixSL**: "Visual Transformer Meets CutMix for Improved Accuracy, Communication Efficiency, and Data Privacy in Split Learning", IJCAI, 2022 (*Yonsei University, Korea*). [[Paper](https://arxiv.org/abs/2207.00234)]
* **BootMAE**: "Bootstrapped Masked Autoencoders for Vision BERT Pretraining", ECCV, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2207.07116)][[PyTorch](https://github.com/LightDXY/BootMAE)]
* **TokenMix**: "TokenMix: Rethinking Image Mixing for Data Augmentation in Vision Transformers", ECCV, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2207.08409)][[PyTorch](https://github.com/Sense-X/TokenMix)]
* **?**: "Locality Guidance for Improving Vision Transformers on Tiny Datasets", ECCV, 2022 (*Peking University*). [[Paper](https://arxiv.org/abs/2207.10026)][[PyTorch](https://github.com/lkhl/tiny-transformers)]
* **HAT**: "Improving Vision Transformers by Revisiting High-frequency Components", ECCV, 2022 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2204.00993)][[PyTorch](https://github.com/jiawangbai/HAT)]
* **IDMM**: "Training Vision Transformers with Only 2040 Images", ECCV, 2022 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2201.10728)]
* **AttMask**: "What to Hide from Your Students: Attention-Guided Masked Image Modeling", ECCV, 2022 (*National Technical University of Athens*). [[Paper](https://arxiv.org/abs/2203.12719)][[PyTorch](https://github.com/gkakogeorgiou/attmask)]
* **SLIP**: "SLIP: Self-supervision meets Language-Image Pre-training", ECCV, 2022 (*Berkeley + Meta*). [[Paper](https://arxiv.org/abs/2112.12750)][[Pytorch](https://github.com/facebookresearch/SLIP)]
* **mc-BEiT**: "mc-BEiT: Multi-Choice Discretization for Image BERT Pre-training", ECCV, 2022 (*Peking University*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/1197_ECCV_2022_paper.php)]
* **SL2O**: "Scalable Learning to Optimize: A Learned Optimizer Can Train Big Models", ECCV, 2022 (*UT Austin*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/2909_ECCV_2022_paper.php)][[PyTorch](https://github.com/VITA-Group/Scalable-L2O)]
* **TokenMixup**: "TokenMixup: Efficient Attention-guided Token-level Data Augmentation for Transformers", NeurIPS, 2022 (*Korea University*). [[Paper](https://arxiv.org/abs/2210.07562)][[Code (in construction)](https://github.com/mlvlab/TokenMixup)]
* **PatchRot**: "PatchRot: A Self-Supervised Technique for Training Vision Transformers", NeurIPSW, 2022 (*Arizona State University*). [[Paper](https://arxiv.org/abs/2210.15722)]
* **DP-CutMix**: "Differentially Private CutMix for Split Learning with Vision Transformer", NeurIPSW, 2022 (*Yonsei University*). [[Paper](https://arxiv.org/abs/2210.15986)]
* **?**: "How to train your ViT? Data, Augmentation, and Regularization in Vision Transformers", Transactions on Machine Learning Research (TMLR), 2022 (*Google*). [[Paper](https://openreview.net/forum?id=4nPswr1KcP)][[Tensorflow](https://github.com/google-research/vision_transformer)][[PyTorch (rwightman)](https://github.com/rwightman/pytorch-image-models)]
* **PeCo**: "PeCo: Perceptual Codebook for BERT Pre-training of Vision Transformers", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.12710)]
* **RePre**: "RePre: Improving Self-Supervised Vision Transformer with Reconstructive Pre-training", arXiv, 2022 (*Beijing University of Posts and Telecommunications*). [[Paper](https://arxiv.org/abs/2201.06857)]
* **Beyond-Masking**: "Beyond Masking: Demystifying Token-Based Pre-Training for Vision Transformers", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2203.14313)][[Code (in construction)](https://github.com/sunsmarterjie/beyond_masking)]
* **Kronecker-Adaptation**: "Parameter-efficient Fine-tuning for Vision Transformers", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2203.16329)]
* **DILEMMA**: "DILEMMA: Self-Supervised Shape and Texture Learning with Transformers", arXiv, 2022 (*University of Bern, Switzerland*). [[Paper](https://arxiv.org/abs/2204.04788)]
* **DeiT-III**: "DeiT III: Revenge of the ViT", arXiv, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2204.07118)]
* **?**: "Better plain ViT baselines for ImageNet-1k", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2205.01580)][[Tensorflow](https://github.com/google-research/big_vision)]
* **ConvMAE**: "ConvMAE: Masked Convolution Meets Masked Autoencoders", arXiv, 2022 (*Shanghai AI Laboratory*). [[Paper](https://arxiv.org/abs/2205.03892)][[PyTorch (in construction)](https://github.com/Alpha-VL/ConvMAE)]
* **ViT-Adapter**: "Vision Transformer Adapter for Dense Predictions", arXiv, 2022 (*Shanghai AI Lab*). [[Paper](https://arxiv.org/abs/2205.08534)][[Code (in construction)](https://github.com/czczup/ViT-Adapter)]
* **UM-MAE**: "Uniform Masking: Enabling MAE Pre-training for Pyramid-based Vision Transformers with Locality", arXiv, 2022 (*Nanjing University of Science and Technology*). [[Paper](https://arxiv.org/abs/2205.10063)][[PyTorch](https://github.com/implus/UM-MAE)]
* **MixMIM**: "MixMIM: Mixed and Masked Image Modeling for Efficient Visual Representation Learning", arXiv, 2022 (*SenseTime*). [[Paper](https://arxiv.org/abs/2205.13137)][[Code (in construction)](https://github.com/Sense-X/MixMIM)]
* **A<sup>2</sup>MIM**: "Architecture-Agnostic Masked Image Modeling - From ViT back to CNN", arXiv, 2022 (*Westlake University, China*). [[Paper](https://arxiv.org/abs/2205.13943)][[PyTorch](https://github.com/Westlake-AI/openmixup)]
* **GMML**: "GMML is All you Need", arXiv, 2022 (*University of Surrey, UK*). [[Paper](https://arxiv.org/abs/2205.14986)][[PyTorch](https://github.com/Sara-Ahmed/GMML)]
* **HiViT**: "HiViT: Hierarchical Vision Transformer Meets Masked Image Modeling", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2205.14949)]
* **?**: "A Closer Look at Self-supervised Lightweight Vision Transformers", arXiv, 2022 (*Megvii*). [[Paper](https://arxiv.org/abs/2205.14443)]
* **SIM**: "Siamese Image Modeling for Self-Supervised Vision Representation Learning", arXiv, 2022 (*SenseTime*). [[Paper](https://arxiv.org/abs/2206.01204)]
* **SupMAE**: "SupMAE: Supervised Masked Autoencoders Are Efficient Vision Learners", arXiv, 2022 (*UT Austin*). [[Paper](https://arxiv.org/abs/2205.14540)][[PyTorch](https://github.com/cmu-enyac/supmae)]
* **LoMaR**: "Efficient Self-supervised Vision Pretraining with Local Masked Reconstruction", arXiv, 2022 (*KAUST*). [[Paper](https://arxiv.org/abs/2206.00790)]
* **SAR**: "Spatial Entropy Regularization for Vision Transformers", arXiv, 2022 (*University of Trento, Italy*). [[Paper](https://arxiv.org/abs/2206.04636)]
* **ExtreMA**: "Extreme Masking for Learning Instance and Distributed Visual Representations", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.04667)]
* **?**: "Exploring Feature Self-relation for Self-supervised Transformer", arXiv, 2022 (*Nankai University*). [[Paper](https://arxiv.org/abs/2206.05184)]
* **?**: "Position Labels for Self-Supervised Vision Transformer", arXiv, 2022 (*Southwest Jiaotong University*). [[Paper](https://arxiv.org/abs/2206.04981)]
* **Jigsaw-ViT**: "Jigsaw-ViT: Learning Jigsaw Puzzles in Vision Transformer", arXiv, 2022 (*KU Leuven, Belgium*). [[Paper](https://arxiv.org/abs/2207.11971)][[PyTorch](https://github.com/yingyichen-cyy/Nested-Co-teaching)][[Website](https://yingyichen-cyy.github.io/Jigsaw-ViT/)]
* **DropKey**: "DropKey", arXiv, 2022 (*Meitu*). [[Paper](https://arxiv.org/abs/2208.02646)]
* **BEiT-v2**: "BEiT v2: Masked Image Modeling with Vector-Quantized Visual Tokenizers", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2208.06366)][[PyTorch](https://github.com/microsoft/unilm/tree/master/beit)]
* **MILAN**: "MILAN: Masked Image Pretraining on Language Assisted Representation", arXiv, 2022 (*Princeton*). [[Paper](https://arxiv.org/abs/2208.06049)][[PyTorch (in construction)](https://github.com/zejiangh/MILAN)]
* **PSS**: "Accelerating Vision Transformer Training via a Patch Sampling Schedule", arXiv, 2022 (*Franklin and Marshall College, Pennsylvania*). [[Paper](https://arxiv.org/abs/2208.09520)][[PyTorch](https://github.com/BradMcDanel/pss)]
* **MaskCLIP**: "MaskCLIP: Masked Self-Distillation Advances Contrastive Language-Image Pretraining", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2208.12262)]
* **DMAE**: "Masked Autoencoders Enable Efficient Knowledge Distillers", arXiv, 2022 (*JHU + UC Santa Cruz*). [[Paper](https://arxiv.org/abs/2208.12256)][[Code (in construction)](https://github.com/UCSC-VLAA/DMAE)]
* **dBOT**: "Exploring Target Representations for Masked Autoencoders", arXiv, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2209.03917)]
* **PatchErasing**: "Effective Vision Transformer Training: A Data-Centric Perspective", arXiv, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2209.15006)] 
* **Self-Distillation**: "Self-Distillation for Further Pre-training of Transformers", arXiv, 2022 (*KAIST*). [[Paper](https://arxiv.org/abs/2210.02871)]
* **TL-Align**: "Token-Label Alignment for Vision Transformers", arXiv, 2022 (*Tsinghua University*). [[Paper](https://arxiv.org/abs/2210.06455)][[PyTorch](https://github.com/Euphoria16/TL-Align)]
* **AutoView**: "Learning Self-Regularized Adversarial Views for Self-Supervised Vision Transformers", arXiv, 2022 (*Sun Yat-sen University*). [[Paper](https://arxiv.org/abs/2210.08458)][[Code (in construction)](https://github.com/Trent-tangtao/AutoView)]
* **CLIPpy**: "Perceptual Grouping in Vision-Language Models", arXiv, 2022 (*Apple*). [[Paper](https://arxiv.org/abs/2210.09996)]
#### Robustness + Transformer
* **ViT-Robustness**: "Understanding Robustness of Transformers for Image Classification", ICCV, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2103.14586)]
* **SAGA**: "On the Robustness of Vision Transformers to Adversarial Examples", ICCV, 2021 (*University of Connecticut*). [[Paper](https://arxiv.org/abs/2104.02610)]
* **?**: "Adversarial Robustness Comparison of Vision Transformer and MLP-Mixer to CNNs", BMVC, 2021 (*KAIST*). [[Paper](https://arxiv.org/abs/2110.02797)][[PyTorch](https://github.com/phibenz/robustness_comparison_vit_mlp-mixer_cnn)]
* **ViTs-vs-CNNs**: "Are Transformers More Robust Than CNNs?", NeurIPS, 2021 (*JHU + UC Santa Cruz*). [[Paper](https://arxiv.org/abs/2111.05464)][[PyTorch](https://github.com/ytongbai/ViTs-vs-CNNs)]
* **T-CNN**: "Transformed CNNs: recasting pre-trained convolutional layers with self-attention", arXiv, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2106.05795)]
* **Transformer-Attack**: "On the Adversarial Robustness of Visual Transformers", arXiv, 2021 (*Xi'an Jiaotong*). [[Paper](https://arxiv.org/abs/2103.15670)]
* **?**: "Reveal of Vision Transformers Robustness against Adversarial Attacks", arXiv, 2021 (*University of Rennes*). [[Paper](https://arxiv.org/abs/2106.03734)]
* **?**: "On Improving Adversarial Transferability of Vision Transformers", arXiv, 2021 (*ANU*). [[Paper](https://arxiv.org/abs/2106.04169)][[PyTorch](https://github.com/Muzammal-Naseer/Improving-Adversarial-Transferability-of-Vision-Transformers)]
* **?**: "Exploring Corruption Robustness: Inductive Biases in Vision Transformers and MLP-Mixers", arXiv, 2021 (*University of Pittsburgh*). [[Paper](https://arxiv.org/abs/2106.13122)]
* **Token-Attack**: "Adversarial Token Attacks on Vision Transformers", arXiv, 2021 (*New York University*). [[Paper](https://arxiv.org/abs/2110.04337)]
* **?**: "Discrete Representations Strengthen Vision Transformer Robustness", arXiv, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2111.10493)]
* **?**: "Vision Transformers are Robust Learners", AAAI, 2022 (*PyImageSearch + IBM*). [[Paper](https://arxiv.org/abs/2105.07581)][[Tensorflow](https://github.com/sayakpaul/robustness-vit)]
* **PNA**: "Towards Transferable Adversarial Attacks on Vision Transformers", AAAI, 2022 (*Fudan + Maryland*). [[Paper](https://arxiv.org/abs/2109.04176)][[PyTorch](https://github.com/zhipeng-wei/PNA-PatchOut)]
* **MIA-Former**: "MIA-Former: Efficient and Robust Vision Transformers via Multi-grained Input-Adaptation", AAAI, 2022 (*Rice University*). [[Paper](https://arxiv.org/abs/2112.11542)]
* **Patch-Fool**: "Patch-Fool: Are Vision Transformers Always Robust Against Adversarial Perturbations?", ICLR, 2022 (*Rice University*). [[Paper](https://arxiv.org/abs/2203.08392)][[PyTorch](https://github.com/RICE-EIC/Patch-Fool)]
* **Generalization-Enhanced-ViT**: "Delving Deep into the Generalization of Vision Transformers under Distribution Shifts", CVPR, 2022 (*Beihang University + NTU, Singapore*). [[Paper](https://arxiv.org/abs/2106.07617)]
* **ECViT**: "Towards Practical Certifiable Patch Defense with Vision Transformer", CVPR, 2022 (*Tencent*).[[Paper](https://arxiv.org/abs/2203.08519)]
* **Attention-Fool**: "Give Me Your Attention: Dot-Product Attention Considered Harmful for Adversarial Patch Robustness", CVPR, 2022 (*Bosch*). [[Paper](https://arxiv.org/abs/2203.13639)]
* **Memory-Token**: "Fine-tuning Image Transformers using Learnable Memory", CVPR, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2203.15243)]
* **APRIL**: "APRIL: Finding the Achilles' Heel on Privacy for Vision Transformers", CVPR, 2022 (*CAS*). [[Paper]([https://arxiv.org/abs/2112.14087](https://openaccess.thecvf.com/content/CVPR2022/html/Lu_APRIL_Finding_the_Achilles_Heel_on_Privacy_for_Vision_Transformers_CVPR_2022_paper.html))]
* **Smooth-ViT**: "Certified Patch Robustness via Smoothed Vision Transformers", CVPR, 2022 (*MIT*). [[Paper](https://arxiv.org/abs/2110.07719)][[PyTorch](https://github.com/MadryLab/smoothed-vit)]
* **RVT**: "Towards Robust Vision Transformer", CVPR, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2105.07926)][[PyTorch](https://github.com/alibaba/easyrobust)]
* **Pyramid**: "Pyramid Adversarial Training Improves ViT Performance", CVPR, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2111.15121)]
* **VARS**: "Visual Attention Emerges from Recurrent Sparse Reconstruction", ICML, 2022 (*Berkeley + Microsoft*). [[Paper](https://arxiv.org/abs/2204.10962)][[PyTorch](https://github.com/bfshi/VARS)]
* **FAN**: "Understanding The Robustness in Vision Transformers", ICML, 2022 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2204.12451)][[PyTorch](https://github.com/NVlabs/FAN)]
* **CFA**: "Robustifying Vision Transformer without Retraining from Scratch by Test-Time Class-Conditional Feature Alignment", IJCAI, 2022 (*The University of Tokyo*). [[Paper](https://arxiv.org/abs/2206.13951)][[PyTorch](https://github.com/kojima-takeshi188/CFA)]
* **?**: "Understanding Adversarial Robustness of Vision Transformers via Cauchy Problem", ECML-PKDD, 2022 (*University of Exeter, UK*). [[Paper](https://arxiv.org/abs/2208.00906)][[PyTorch](https://github.com/TrustAI/ODE4RobustViT)]
* **?**: "An Impartial Take to the CNN vs Transformer Robustness Contest", ECCV, 2022 (*Oxford*). [[Paper](https://arxiv.org/abs/2207.11347)]
* **AGAT**: "Towards Efficient Adversarial Training on Vision Transformers", ECCV, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2207.10498)]
* **?**: "Are Vision Transformers Robust to Patch Perturbations?", ECCV, 2022 (*TUM*). [[Paper](https://arxiv.org/abs/2111.10659)]
* **ViP**: "ViP: Unified Certified Detection and Recovery for Patch Attack with Vision Transformers", ECCV, 2022 (*UC Santa Cruz*). [[Paper](https://cihangxie.github.io/data/li2022vip.pdf)][[PyTorch](https://github.com/UCSC-VLAA/vit_cert)]
* **?**: "When Adversarial Training Meets Vision Transformers: Recipes from Training to Architecture", NeurIPS, 2022 (*Peking University*). [[Paper](https://arxiv.org/abs/2210.07540)][[Code (in construction)](https://github.com/mo666666/When-Adversarial-Training-Meets-Vision-Transformers)]
* **?**: "Are Vision Transformers Robust to Spurious Correlations?", arXiv, 2022 (*UW-Madison*). [[Paper](https://arxiv.org/abs/2203.09125)]
* **MA**: "Boosting Adversarial Transferability of MLP-Mixer", arXiv, 2022 (*Beijing Institute of Technology*). [[Paper](https://arxiv.org/abs/2204.12204)]
* **?**: "Deeper Insights into ViTs Robustness towards Common Corruptions", arXiv, 2022 (*Fudan + Microsoft*). [[Paper](https://arxiv.org/abs/2204.12143)]
* **?**: "Privacy-Preserving Image Classification Using Vision Transformer", arXiv, 2022 (*Tokyo Metropolitan University*). [[Paper](https://arxiv.org/abs/2205.12041)]
* **RobustViT**: "Optimizing Relevance Maps of Vision Transformers Improves Robustness", arXiv, 2022 (*Tel-Aviv*). [[Paper](https://arxiv.org/abs/2206.01161)][[PyTorch](https://github.com/hila-chefer/RobustViT)]
* **FedWAvg**: "Federated Adversarial Training with Transformers", arXiv, 2022 (*Institute of Electronics and Digital Technologies (IETR), France*). [[Paper](https://arxiv.org/abs/2206.02131)]
* **RobustCNN**: "Can CNNs Be More Robust Than Transformers?", arXiv, 2022 (*UC Santa Cruz + JHU*). [[Paper](https://arxiv.org/abs/2206.03452)][[PyTorch](https://github.com/UCSC-VLAA/RobustCNN)]
* **Backdoor-Transformer**: "Backdoor Attacks on Vision Transformers", arXiv, 2022 (*Maryland + UC Davis*). [[Paper](https://arxiv.org/abs/2206.08477)][[Code (in construction)](https://github.com/UCDvision/backdoor_transformer)]
* **?**: "Defending Backdoor Attacks on Vision Transformer via Patch Processing", arXiv, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2206.12381)]
* **?**: "Image and Model Transformation with Secret Key for Vision Transformer", arXiv, 2022 (*Tokyo Metropolitan University*). [[Paper](https://arxiv.org/abs/2207.05366)]
* **?**: "Analyzing Adversarial Robustness of Vision Transformers against Spatial and Spectral Attacks", arXiv, 2022 (*Yonsei University*). [[Paper](https://arxiv.org/abs/2208.09602)]
* **CLIPping Privacy**: "CLIPping Privacy: Identity Inference Attacks on Multi-Modal Machine Learning Models", arXiv, 2022 (*TUM*). [[Paper](https://arxiv.org/abs/2209.07341)]
* **?**: "A Light Recipe to Train Robust Vision Transformers", arXiv, 2022 (*EPFL*). [[Paper](https://arxiv.org/abs/2209.07399)]
* **?**: "Attacking Compressed Vision Transformers", arXiv, 2022 (*NYU*). [[Paper](https://arxiv.org/abs/2209.13785)]
* **C-AVP**: "Visual Prompting for Adversarial Robustness", arXiv, 2022 (*Michigan State*). [[Paper](https://arxiv.org/abs/2210.06284)]
* **?**: "Curved Representation Space of Vision Transformers", arXiv, 2022 (*Yonsei University*). [[Paper](https://arxiv.org/abs/2210.05742)]
* **RKDE**: "Robustify Transformers with Robust Kernel Density Estimation", arXiv, 2022 (*UT Austin*). [[Paper](https://arxiv.org/abs/2210.05794)]
* **MRAP**: "Pretrained Transformers Do not Always Improve Robustness", arXiv, 2022 (*Arizona State University*). [[Paper](https://arxiv.org/abs/2210.07663)]
#### Model Compression + Transformer
* **ViT-quant**: "Post-Training Quantization for Vision Transformer", NeurIPS, 2021 (*Huawei*). [[Paper](https://arxiv.org/abs/2106.14156)]
* **VTP**: "Visual Transformer Pruning", arXiv, 2021 (*Huawei*). [[Paper](https://arxiv.org/abs/2104.08500)]
* **NViT**: "NViT: Vision Transformer Compression and Parameter Redistribution", arXiv, 2021 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2110.04869)]
* **MD-ViT**: "Multi-Dimensional Model Compression of Vision Transformer", arXiv, 2021 (*Princeton*). [[Paper](https://arxiv.org/abs/2201.00043)]
* **FQ-ViT**: "FQ-ViT: Fully Quantized Vision Transformer without Retraining", arXiv, 2021 (*Megvii*). [[Paper](https://arxiv.org/abs/2111.13824)][[PyTorch](https://github.com/linyang-zhh/FQ-ViT)]
* **UVC**: "Unified Visual Transformer Compression", ICLR, 2022 (*UT Austin*). [[Paper](https://arxiv.org/abs/2203.08243)][[PyTorch](https://github.com/VITA-Group/UVC)]
* **MiniViT**: "MiniViT: Compressing Vision Transformers with Weight Multiplexing", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2204.07154)][[PyTorch](https://github.com/microsoft/Cream/tree/main/MiniViT)]
* **Auto-ViT-Acc**: "Auto-ViT-Acc: An FPGA-Aware Automatic Acceleration Framework for Vision Transformer with Mixed-Scheme Quantization", International Conference on Field Programmable Logic and Applications (FPL), 2022 (*Northeastern University*). [[Paper](https://arxiv.org/abs/2208.05163)]
* **SPViT**: "SPViT: Enabling Faster Vision Transformers via Soft Token Pruning", ECCV, 2022 (*Northeastern University*). [[Paper](https://arxiv.org/abs/2112.13890)][[PyTorch](https://github.com/PeiyanFlying/SPViT)]
* **PSAQ-ViT**: "Patch Similarity Aware Data-Free Quantization for Vision Transformers", ECCV, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2203.02250)][[PyTorch](https://github.com/zkkli/PSAQ-ViT)]
* **PTQ4ViT**: "PTQ4ViT: Post-Training Quantization Framework for Vision Transformers", ECCV, 2022 (*Peking University*). [[Paper](https://arxiv.org/abs/2111.12293)]
* **EAPruning**: "EAPruning: Evolutionary Pruning for Vision Transformers and CNNs", BMVC, 2022 (*Meituan*). [[Paper](https://arxiv.org/abs/2210.00181)]
* **Q-ViT**: "Q-ViT: Accurate and Fully Quantized Low-bit Vision Transformer", NeurIPS, 2022 (*Beihang University*). [[Paper](https://arxiv.org/abs/2210.06707)][[PyTorch](https://github.com/YanjingLi0202/Q-ViT)]
* **Q-ViT**: "Q-ViT: Fully Differentiable Quantization for Vision Transformer", arXiv, 2022 (*Megvii*). [[Paper](https://arxiv.org/abs/2201.07703)]
* **VAQF**: "VAQF: Fully Automatic Software-Hardware Co-Design Framework for Low-Bit Vision Transformer", arXiv, 2022 (*Northeastern University*). [[Paper](https://arxiv.org/abs/2201.06618)]
* **VTP**: "Vision Transformer Compression with Structured Pruning and Low Rank Approximation", arXiv, 2022 (*UCLA*). [[Paper](https://arxiv.org/abs/2203.13444)]
* **SiDT**: "Searching Intrinsic Dimensions of Vision Transformers", arXiv, 2022 (*UC Irvine*). [[Paper](https://arxiv.org/abs/2204.07722)]
* **I-ViT**: "I-ViT: Integer-only Quantization for Efficient Vision Transformer Inference", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2207.01405)]
* **PSAQ-ViT-V2**: "PSAQ-ViT V2: Towards Accurate and General Data-Free Quantization for Vision Transformers", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2209.05687)][[PyTorch](https://github.com/zkkli/PSAQ-ViT)]
* **AS**: "Adaptive Sparse ViT: Towards Learnable Adaptive Token Pruning by Fully Exploiting Self-Attention", arXiv, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2209.13802)]
* **SaiT**: "SaiT: Sparse Vision Transformers through Adaptive Token Pruning", arXiv, 2022 (*Samsung*). [[Paper](https://arxiv.org/abs/2210.05832)]
* **oViT**: "oViT: An Accurate Second-Order Pruning Framework for Vision Transformers", arXiv, 2022 (*IST Austria*). [[Paper](https://arxiv.org/abs/2210.09223)]

[[Back to Overview](#overview)]

### Attention-Free 
#### MLP-Series
* **RepMLP**: "RepMLP: Re-parameterizing Convolutions into Fully-connected Layers for Image Recognition", arXiv, 2021 (*Megvii*). [[Paper](https://arxiv.org/abs/2105.01883)][[PyTorch](https://github.com/DingXiaoH/RepMLP)]
* **EAMLP**: "Beyond Self-attention: External Attention using Two Linear Layers for Visual Tasks", arXiv, 2021 (*Tsinghua University*). [[Paper](https://arxiv.org/abs/2105.02358)]
* **Forward-Only**: "Do You Even Need Attention? A Stack of Feed-Forward Layers Does Surprisingly Well on ImageNet", arXiv, 2021 (*Oxford*). [[Paper](https://arxiv.org/abs/2105.02723)][[PyTorch](https://github.com/lukemelas/do-you-even-need-attention)]
* **ResMLP**: "ResMLP: Feedforward networks for image classification with data-efficient training", arXiv, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2105.03404)]
* **?**: "Can Attention Enable MLPs To Catch Up With CNNs?", arXiv, 2021 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2105.15078)]
* **ViP**: "Vision Permutator: A Permutable MLP-Like Architecture for Visual Recognition", arXiv, 2021 (*NUS, Singapore*). [[Paper](https://arxiv.org/abs/2106.12368)][[PyTorch](https://github.com/Andrew-Qibin/VisionPermutator)]
* **CCS**: "Rethinking Token-Mixing MLP for MLP-based Vision Backbone", arXiv, 2021 (*Baidu*). [[Paper](https://arxiv.org/abs/2106.14882)]
* **S<sup>2</sup>-MLPv2**: "S<sup>2</sup>-MLPv2: Improved Spatial-Shift MLP Architecture for Vision", arXiv, 2021 (*Baidu*). [[Paper](https://arxiv.org/abs/2108.01072)]
* **RaftMLP**: "RaftMLP: Do MLP-based Models Dream of Winning Over Computer Vision?", arXiv, 2021 (*Rikkyo University, Japan*). [[Paper](https://arxiv.org/abs/2108.04384)][[PyTorch](https://github.com/okojoalg/raft-mlp)]
* **Hire-MLP**: "Hire-MLP: Vision MLP via Hierarchical Rearrangement", arXiv, 2021 (*Huawei*). [[Paper](https://arxiv.org/abs/2108.13341)]
* **Sparse-MLP**: "Sparse-MLP: A Fully-MLP Architecture with Conditional Computation", arXiv, 2021 (*NUS*). [[Paper](https://arxiv.org/abs/2109.02008)]
* **ConvMLP**: "ConvMLP: Hierarchical Convolutional MLPs for Vision", arXiv, 2021 (*University of Oregon*). [[Paper](https://arxiv.org/abs/2109.04454)][[PyTorch](https://github.com/SHI-Labs/Convolutional-MLPs)]
* **sMLP**: "Sparse MLP for Image Recognition: Is Self-Attention Really Necessary?", arXiv, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2109.05422)]
* **MLP-Mixer**: "MLP-Mixer: An all-MLP Architecture for Vision", NeurIPS, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2105.01601)][[Tensorflow](https://github.com/google-research/vision_transformer)][[PyTorch-1 (lucidrains)](https://github.com/lucidrains/mlp-mixer-pytorch)][[PyTorch-2 (rishikksh20)](https://github.com/rishikksh20/MLP-Mixer-pytorch)]
* **gMLP**: "Pay Attention to MLPs", NeurIPS, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2105.08050)][[PyTorch (antonyvigouret)](https://github.com/antonyvigouret/Pay-Attention-to-MLPs)]
* **S<sup>2</sup>-MLP**: "S<sup>2</sup>-MLP: Spatial-Shift MLP Architecture for Vision", WACV, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2106.07477)]
* **CycleMLP**: "CycleMLP: A MLP-like Architecture for Dense Prediction", ICLR, 2022 (*HKU*). [[Paper](https://arxiv.org/abs/2107.10224)][[PyTorch](https://github.com/ShoufaChen/CycleMLP)]
* **AS-MLP**: "AS-MLP: An Axial Shifted MLP Architecture for Vision", ICLR, 2022 (*ShanghaiTech University*). [[Paper](https://arxiv.org/abs/2107.08391)][[PyTorch](https://github.com/svip-lab/AS-MLP)]
* **Wave-MLP**: "An Image Patch is a Wave: Quantum Inspired Vision MLP", CVPR, 2022 (*Huawei*). [[Paper](https://arxiv.org/abs/2111.12294)][[PyTorch](https://github.com/huawei-noah/CV-Backbones/tree/master/wavemlp_pytorch)]
* **DynaMixer**: "DynaMixer: A Vision MLP Architecture with Dynamic Mixing", ICML, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2201.12083)][[PyTorch](https://github.com/ziyuwwang/DynaMixer)]
* **STD**: "Spatial-Channel Token Distillation for Vision MLPs", ICML, 2022 (*Huawei*). [[Paper](https://proceedings.mlr.press/v162/li22c.html)]
* **AMixer**: " AMixer: Adaptive Weight Mixing for Self-Attention Free Vision Transformers", ECCV, 2022 (*Tsinghua University*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/4464_ECCV_2022_paper.php)]
* **MS-MLP**: "Mixing and Shifting: Exploiting Global and Local Dependencies in Vision MLPs", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2202.06510)]
* **ActiveMLP**: "ActiveMLP: An MLP-like Architecture with Active Token Mixer", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2203.06108)]
* **MDMLP**: "MDMLP: Image Classification from Scratch on Small Datasets with MLP", arXiv, 2022 (*Jiangsu University*). [[Paper](https://arxiv.org/abs/2205.14477)][[PyTorch](https://github.com/Amoza-Theodore/MDMLP)]
* **PosMLP**: "Parameterization of Cross-Token Relations with Relative Positional Encoding for Vision MLP", arXiv, 2022 (*University of Science and Technology
of China*). [[Paper](https://arxiv.org/abs/2207.07284)][[PyTorch](https://github.com/Zhicaiwww/PosMLP)]
* **SplitMixer**: "SplitMixer: Fat Trimmed From MLP-like Models", arXiv, 2022 (*Quintic AI, California*). [[Paper](https://arxiv.org/abs/2207.10255)][[PyTorch](https://github.com/aliborji/splitmixer)]
* **gSwin**: "gSwin: Gated MLP Vision Model with Hierarchical Structure of Shifted Window", arXiv, 2022 (*PKSHATechnology, Japan*). [[Paper](https://arxiv.org/abs/2208.11718)]
* **?**: "Analysis of Quantization on MLP-based Vision Models", arXiv, 2022 (*Berkeley*). [[Paper](https://arxiv.org/abs/2209.06383)]
#### Other Attention-Free
* **PoolFormer**: "MetaFormer is Actually What You Need for Vision", CVPR, 2022 (*Sea AI Lab*). [[Paper](https://arxiv.org/abs/2111.11418)][[PyTorch](https://github.com/sail-sg/poolformer)]
* **FocalNet**: "Focal Modulation Networks", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2203.11926)][[PyTorch](https://github.com/microsoft/FocalNet)]
* **Sequencer**: "Sequencer: Deep LSTM for Image Classification", arXiv, 2022 (*Rikkyo University, Japan*). [[Paper](https://arxiv.org/abs/2205.01972)]

[[Back to Overview](#overview)]

### Analysis for Transformer 
* **Attention-CNN**: "On the Relationship between Self-Attention and Convolutional Layers", ICLR, 2020 (*EPFL*). [[Paper](https://openreview.net/forum?id=HJlnC1rKPB)][[PyTorch](https://github.com/epfml/attention-cnn)][[Website](https://epfml.github.io/attention-cnn/)]
* **Transformer-Explainability**: "Transformer Interpretability Beyond Attention Visualization", CVPR, 2021 (*Tel Aviv*). [[Paper](https://arxiv.org/abs/2012.09838)][[PyTorch](https://github.com/hila-chefer/Transformer-Explainability)]
* **?**: "Are Convolutional Neural Networks or Transformers more like human vision?", CogSci, 2021 (*Princeton*). [[Paper](https://arxiv.org/abs/2105.07197)]
* **?**: "ConvNets vs. Transformers: Whose Visual Representations are More Transferable?", ICCVW, 2021 (*HKU*). [[Paper](https://arxiv.org/abs/2108.05305)]
* **?**: "Do Vision Transformers See Like Convolutional Neural Networks?", NeurIPS, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2108.08810)]
* **?**: "Intriguing Properties of Vision Transformers", NeurIPS, 2021 (*MBZUAI*). [[Paper](https://arxiv.org/abs/2105.10497)][[PyTorch](https://github.com/Muzammal-Naseer/Intriguing-Properties-of-Vision-Transformers)]
* **FoveaTer**: "FoveaTer: Foveated Transformer for Image Classification", arXiv, 2021 (*UCSB*). [[Paper](https://arxiv.org/abs/2105.14173)]
* **?**: "Demystifying Local Vision Transformer: Sparse Connectivity, Weight Sharing, and Dynamic Weight", arXiv, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2106.04263)]
* **?**: "Revisiting the Calibration of Modern Neural Networks", arXiv, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2106.07998)]
* **?**: "What Makes for Hierarchical Vision Transformer?", arXiv, 2021 (*Horizon Robotic*). [[Paper](https://arxiv.org/abs/2107.02174)]
* **?**: "Visualizing Paired Image Similarity in Transformer Networks", WACV, 2022 (*Temple University*). [[Paper](https://openaccess.thecvf.com/content/WACV2022/html/Black_Visualizing_Paired_Image_Similarity_in_Transformer_Networks_WACV_2022_paper.html)][[PyTorch](https://github.com/vidarlab/xformer-paired-viz)]
* **FDSL**: "Can Vision Transformers Learn without Natural Images?", AAAI, 2022 (*AIST*). [[Paper](https://arxiv.org/abs/2103.13023)][[PyTorch](https://github.com/nakashima-kodai/FractalDB-Pretrained-ViT-PyTorch)][[Website](https://hirokatsukataoka16.github.io/Vision-Transformers-without-Natural-Images/)]
* **AlterNet**: "How Do Vision Transformers Work?", ICLR, 2022 (*Yonsei University*). [[Paper](https://arxiv.org/abs/2202.06709)][[PyTorch](https://github.com/xxxnell/how-do-vits-work)]
* **?**: "When Vision Transformers Outperform ResNets without Pretraining or Strong Data Augmentations", ICLR, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2106.01548)][[Tensorflow](https://github.com/google-research/vision_transformer)]
* **?**: "On the Connection between Local Attention and Dynamic Depth-wise Convolution", ICLR, 2022 (*Microsoft*). [[Paper](https://openreview.net/forum?id=L3_SsSNMmy)]
* **?**: "Unraveling Attention via Convex Duality: Analysis and Interpretations of Vision Transformers", ICML, 2022 (*Stanford*). [[Paper](https://arxiv.org/abs/2205.08078)]
* **?**: "Three things everyone should know about Vision Transformers", ECCV, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2203.09795)]
* **?**: "Vision Transformers learn patch association", NeurIPS, 2022 (*Princeton*). [[Paper](https://arxiv.org/abs/2210.09221)]
* **AWD-ViT**: "Visualizing and Understanding Patch Interactions in Vision Transformer", arXiv, 2022 (*JD*). [[Paper](https://arxiv.org/abs/2203.05922)]
* **?**: "CNNs and Transformers Perceive Hybrid Images Similar to Humans", arXiv, 2022 (*Quintic AI, CA*). [[Paper](https://arxiv.org/abs/2203.11678)][[Code](https://github.com/aliborji/hybrid_images)]
* **MJP**: "Breaking the Chain of Gradient Leakage in Vision Transformers", arXiv, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2205.12551)]
* **ViT-Shapley**: "Learning to Estimate Shapley Values with Vision Transformers", arXiv, 2022 (*UW*). [[Paper](https://arxiv.org/abs/2206.05282)][[PyTorch](https://github.com/suinleelab/vit-shapley)]
* **?**: "A Unified and Biologically-Plausible Relational Graph Representation of Vision Transformers", arXiv, 2022 (*University of Electronic Science and Technology of China*). [[Paper](https://arxiv.org/abs/2206.11073)]
* **?**: "How Well Do Vision Transformers (VTs) Transfer To The Non-Natural Image Domain? An Empirical Study Involving Art Classification", arXiv, 2022 (*University of Groningen, The Netherlands*). [[Paper](https://arxiv.org/abs/2208.04693)]
* **?**: "Transformer Vs. MLP-Mixer Exponential Expressive Gap For NLP Problems", arXiv, 2022 (*Technion Israel Institute Of Technology*). [[Paper](https://arxiv.org/abs/2208.08191)]
* **ProtoPFormer**: "ProtoPFormer: Concentrating on Prototypical Parts in Vision Transformers for Interpretable Image Recognition", arXiv, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2208.10431)][[PyTorch](https://github.com/zju-vipa/ProtoPFormer)]
* **ICLIP**: "Exploring Visual Interpretability for Contrastive Language-Image Pre-training", arXiv, 2022 (*HKUST*). [[Paper](https://arxiv.org/abs/2209.07046)][[Code (in construction)](https://github.com/xmed-lab/ICLIP)]
* **?**: "Large Models are Parsimonious Learners: Activation Sparsity in Trained Transformers", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2210.06313)]
* **?**: "Vision Transformer Visualization: What Neurons Tell and How Neurons Behave?", arXiv, 2022 (*Monash University*). [[Paper](https://arxiv.org/abs/2210.07646)][[PyTorch](https://github.com/byM1902/ViT_visualization)]

[[Back to Overview](#overview)]


## Detection
### Object Detection
* CNN-based backbone:
    * **DETR**: "End-to-End Object Detection with Transformers", ECCV, 2020 (*Facebook*). [[Paper](https://arxiv.org/abs/2005.12872)][[PyTorch](https://github.com/facebookresearch/detr)]
    * **Deformable DETR**: "Deformable DETR: Deformable Transformers for End-to-End Object Detection", ICLR, 2021 (*SenseTime*). [[Paper](https://arxiv.org/abs/2010.04159)][[PyTorch](https://github.com/fundamentalvision/Deformable-DETR)]
    * **UP-DETR**: "UP-DETR: Unsupervised Pre-training for Object Detection with Transformers", CVPR, 2021 (*Tencent*). [[Paper](https://arxiv.org/abs/2011.09094)][[PyTorch](https://github.com/dddzg/up-detr)]
    * **SMCA**: "Fast Convergence of DETR with Spatially Modulated Co-Attention", ICCV, 2021 (*CUHK*). [[Paper](https://arxiv.org/abs/2108.02404)][[PyTorch](https://github.com/gaopengcuhk/SMCA-DETR)]
    * **Conditional-DETR**: "Conditional DETR for Fast Training Convergence", ICCV, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2108.06152)]
    * **PnP-DETR**: "PnP-DETR: Towards Efficient Visual Analysis with Transformers", ICCV, 2021 (*Yitu*). [[Paper](https://arxiv.org/abs/2109.07036)][[Code (in construction)](https://github.com/twangnh/pnp-detr)]
    * **TSP**: "Rethinking Transformer-based Set Prediction for Object Detection", ICCV, 2021 (*CMU*). [[Paper](https://arxiv.org/abs/2011.10881)]
    * **Dynamic-DETR**: "Dynamic DETR: End-to-End Object Detection With Dynamic Attention", ICCV, 2021 (*Microsoft*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021/html/Dai_Dynamic_DETR_End-to-End_Object_Detection_With_Dynamic_Attention_ICCV_2021_paper.html)]
    * **ViT-YOLO**: "ViT-YOLO:Transformer-Based YOLO for Object Detection", ICCVW, 2021 (*Xidian University*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021W/VisDrone/html/Zhang_ViT-YOLOTransformer-Based_YOLO_for_Object_Detection_ICCVW_2021_paper.html)]
    * **ACT**: "End-to-End Object Detection with Adaptive Clustering Transformer", BMVC, 2021 (*Peking + CUHK*). [[Paper](https://arxiv.org/abs/2011.09315)][[PyTorch](https://github.com/gaopengcuhk/SMCA-DETR/)]
    * **DIL-ViT**: "Paying Attention to Varying Receptive Fields: Object Detection with Atrous Filters and Vision Transformers", BMVC, 2021 (*Monash University Malaysia*). [[Paper](https://www.bmvc2021-virtualconference.com/assets/papers/0675.pdf)]
    * **Efficient-DETR**: "Efficient DETR: Improving End-to-End Object Detector with Dense Prior", arXiv, 2021 (*Megvii*). [[Paper](https://arxiv.org/abs/2104.01318)]
    * **CA-FPN**: "Content-Augmented Feature Pyramid Network with Light Linear Transformers", arXiv, 2021 (*CAS*). [[Paper](https://arxiv.org/abs/2105.09464)]
    * **DETReg**: "DETReg: Unsupervised Pretraining with Region Priors for Object Detection", arXiv, 2021 (*Tel-Aviv + Berkeley*). [[Paper](https://arxiv.org/abs/2106.04550)][[Website](https://www.amirbar.net/detreg/)]
    * **GQPos**: "Guiding Query Position and Performing Similar Attention for Transformer-Based Detection Heads", arXiv, 2021 (*Megvii*). [[Paper](https://arxiv.org/abs/2108.09691)]
    * **Anchor-DETR**: "Anchor DETR: Query Design for Transformer-Based Detector", AAAI, 2022 (*Megvii*). [[Paper](https://arxiv.org/abs/2109.07107)][[PyTorch](https://github.com/megvii-research/AnchorDETR)]
    * **Sparse-DETR**: "Sparse DETR: Efficient End-to-End Object Detection with Learnable Sparsity", ICLR, 2022 (*Kakao*). [[Paper](https://arxiv.org/abs/2111.14330)][[PyTorch](https://github.com/kakaobrain/sparse-detr)]
    * **DAB-DETR**: "DAB-DETR: Dynamic Anchor Boxes are Better Queries for DETR", ICLR, 2022 (*IDEA, China*). [[Paper](https://arxiv.org/abs/2201.12329)][[PyTorch](https://github.com/SlongLiu/DAB-DETR)]
    * **DN-DETR**: "DN-DETR: Accelerate DETR Training by Introducing Query DeNoising", CVPR, 2022 (*International Digital Economy Academy (IDEA), China*). [[Paper](https://arxiv.org/abs/2203.01305)][[PyTorch](https://github.com/FengLi-ust/DN-DETR)]
    * **SAM-DETR**: "Accelerating DETR Convergence via Semantic-Aligned Matching", CVPR, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2203.06883)][[PyTorch](https://github.com/ZhangGongjie/SAM-DETR)]
    * **AdaMixer**: "AdaMixer: A Fast-Converging Query-Based Object Detector", CVPR, 2022 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2203.16507)][[Code (in construction)](https://github.com/MCG-NJU/AdaMixer)]
    * **DESTR**: "DESTR: Object Detection With Split Transformer", CVPR, 2022 (*Oregon State*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/He_DESTR_Object_Detection_With_Split_Transformer_CVPR_2022_paper.html)]
    * **REGO**: "Recurrent Glimpse-based Decoder for Detection with Transformer", CVPR, 2022 (*The University of Sydney*). [[Paper](https://arxiv.org/abs/2112.04632)][[PyTorch](https://github.com/zhechen/Deformable-DETR-REGO)]
    * **?**: "Training Object Detectors From Scratch: An Empirical Study in the Era of Vision Transformer", CVPR, 2022 (*Ant Group*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Hong_Training_Object_Detectors_From_Scratch_An_Empirical_Study_in_the_CVPR_2022_paper.html)]
    * **DE-DETR**: "Towards Data-Efficient Detection Transformers", ECCV, 2022 (*JD*). [[Paper](https://arxiv.org/abs/2203.09507)][[PyTorch](https://github.com/encounter1997/DE-DETRs)]
    * **DFFT**: "Efficient Decoder-free Object Detection with Transformers", ECCV, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2206.06829)]
    * **Cornerformer**: "Cornerformer: Purifying Instances for Corner-Based Detectors", ECCV, 2022 (*Huawei*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/4286_ECCV_2022_paper.php)]
    * **?**: "A Simple Approach and Benchmark for 21,000-Category Object Detection", ECCV, 2022 (*Microsoft*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/8094_ECCV_2022_paper.php)][[Code (in construction)](https://github.com/SwinTransformer/Simple-21K-Detection)]
    * **KA**: "Knowledge Amalgamation for Object Detection with Transformers", arXiv, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2203.03187)]
    * **MIMDet**: "Unleashing Vanilla Vision Transformer with Masked Image Modeling for Object Detection", arXiv, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2204.02964)][[PyTorch](https://github.com/hustvl/MIMDet)]
    * **imTED**: "Integral Migrating Pre-trained Transformer Encoder-decoders for Visual Object Detection", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2205.09613)]
    * **AO2-DETR**: "AO2-DETR: Arbitrary-Oriented Object Detection Transformer", arXiv, 2022 (*Peking University*). [[Paper](https://arxiv.org/abs/2205.12785)]
    * **MaskDINO**: "Mask DINO: Towards A Unified Transformer-based Framework for Object Detection and Segmentation", arXiv, 2022 (*IDEA, China*). [[Paper](https://arxiv.org/abs/2206.02777)][[Code (in construction)](https://github.com/IDEACVR/MaskDINO)]
    * **TCC**: "Transformer-based Context Condensation for Boosting Feature Pyramids in Object Detection", arXiv, 2022 (*The University of Sydney*). [[Paper](https://arxiv.org/abs/2207.06603)]
    * **Conditional-DETR-V2**: "Conditional DETR V2: Efficient Detection Transformer with Box Queries", arXiv, 2022 (*Peking University*). [[Paper](https://arxiv.org/abs/2207.08914)]
    * **Group-DETR**: "Group DETR: Fast Training Convergence with Decoupled One-to-Many Label Assignment", arXiv, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2207.13085)]
    * **H-DETR**: "DETRs with Hybrid Matching", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2207.13080)]
    * **SAM-DETR++**: "Semantic-Aligned Matching for Enhanced DETR Convergence and Multi-Scale Feature Fusion", arXiv, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2207.14172)][[PyTorch](https://github.com/ZhangGongjie/SAM-DETR)]
    * **IMFA**: "Towards Efficient Use of Multi-Scale Features in Transformer-Based Object Detectors", arXiv, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2208.11356)][[Code (in construction)](https://github.com/ZhangGongjie/IMFA)]
    * **ComplETR**: "ComplETR: Reducing the cost of annotations for object detection in dense scenes with vision transformers", arXiv, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2209.05654)]
    * **Obj2Seq**: "Obj2Seq: Formatting Objects as Sequences with Class Prompt for Visual Tasks", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2209.13948)][[PyTorch](https://github.com/CASIA-IVA-Lab/Obj2Seq)]
* Transformer-based backbone:
    * **ViT-FRCNN**: "Toward Transformer-Based Object Detection", arXiv, 2020 (*Pinterest*). [[Paper](https://arxiv.org/abs/2012.09958)]
    * **WB-DETR**: "WB-DETR: Transformer-Based Detector Without Backbone", ICCV, 2021 (*CAS*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021/html/Liu_WB-DETR_Transformer-Based_Detector_Without_Backbone_ICCV_2021_paper.html)]
    * **YOLOS**: "You Only Look at One Sequence: Rethinking Transformer in Vision through Object Detection", NeurIPS, 2021 (*Horizon Robotics*). [[Paper](https://arxiv.org/abs/2106.00666)][[PyTorch](https://github.com/hustvl/YOLOS)]
    * **?**: "Benchmarking Detection Transfer Learning with Vision Transformers", arXiv, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2111.11429)]
    * **ViDT**: "ViDT: An Efficient and Effective Fully Transformer-based Object Detector", ICLR, 2022 (*NAVER*). [[Paper](https://arxiv.org/abs/2110.03921)][[PyTorch](https://github.com/naver-ai/vidt)]
    * **FP-DETR**: "FP-DETR: Detection Transformer Advanced by Fully Pre-training", ICLR, 2022 (*USTC*). [[Paper](https://openreview.net/forum?id=yjMQuLLcGWK)]
    * **DETR++**: "DETR++: Taming Your Multi-Scale Detection Transformer", CVPRW, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2206.02977)]
    * **ViTDet**: "Exploring Plain Vision Transformer Backbones for Object Detection", ECCV, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2203.16527)]
    * **UViT**: "A Simple Single-Scale Vision Transformer for Object Detection and Instance Segmentation", ECCV, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2112.09747)]
    * **D<sup>2</sup>ETR**: "D<sup>2</sup>ETR: Decoder-Only DETR with Computationally Efficient Cross-Scale Attention", arXiv, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2203.00860)][[PyTorch](https://github.com/alibaba/easyrobust/tree/main/ddetr)]
    * **DINO**: "DINO: DETR with Improved DeNoising Anchor Boxes for End-to-End Object Detection", arXiv, 2022 (*IDEA, China*). [[Paper](https://arxiv.org/abs/2203.03605)][[Code (in construction)](https://github.com/IDEACVR/DINO)]

[[Back to Overview](#overview)]

### 3D Object Detection
* **AST-GRU**: "LiDAR-based Online 3D Video Object Detection with Graph-based Message Passing and Spatiotemporal Transformer Attention", CVPR, 2020 (*Baidu*). [[Paper](https://arxiv.org/abs/2004.01389)][[Code (in construction)](https://github.com/yinjunbo/3DVID)]
* **Pointformer**: "3D Object Detection with Pointformer", arXiv, 2020 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2012.11409)]
* **CT3D**: "Improving 3D Object Detection with Channel-wise Transformer", ICCV, 2021 (*Alibaba*). [[Paper](https://arxiv.org/abs/2108.10723)][[Code (in construction)](https://github.com/hlsheng1/CT3D)]
* **Group-Free-3D**: "Group-Free 3D Object Detection via Transformers", ICCV, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2104.00678)][[PyTorch](https://github.com/zeliu98/Group-Free-3D)]
* **VoTr**: "Voxel Transformer for 3D Object Detection", ICCV, 2021 (*CUHK + NUS*). [[Paper](https://arxiv.org/abs/2109.02497)]
* **3DETR**: "An End-to-End Transformer Model for 3D Object Detection", ICCV, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2109.08141)][[PyTorch](https://github.com/facebookresearch/3detr)][[Website](https://facebookresearch.github.io/3detr/)]
* **DETR3D**: "DETR3D: 3D Object Detection from Multi-view Images via 3D-to-2D Queries", CoRL, 2021 (*MIT*). [[Paper](https://arxiv.org/abs/2110.06922)]
* **M3DETR**: "M3DeTR: Multi-representation, Multi-scale, Mutual-relation 3D Object Detection with Transformers", WACV, 2022 (*University of Maryland*). [[Paper](https://arxiv.org/abs/2104.11896)][[PyTorch](https://github.com/rayguan97/M3DETR)]
* **SST**: "Embracing Single Stride 3D Object Detector with Sparse Transformer", CVPR, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2112.06375)][[PyTorch](https://github.com/TuSimple/SST)]
* **MonoDTR**: "MonoDTR: Monocular 3D Object Detection with Depth-Aware Transformer", CVPR, 2022 (*NTU*). [[Paper](https://arxiv.org/abs/2203.10981)][[Code (in construction)](https://github.com/kuanchihhuang/MonoDTR)]
* **VoxSeT**: "Voxel Set Transformer: A Set-to-Set Approach to 3D Object Detection from Point Clouds", CVPR, 2022 (*The Hong Kong Polytechnic University*). [[Paper](https://arxiv.org/abs/2203.10314)][[PyTorch](https://github.com/skyhehe123/VoxSeT)]
* **TransFusion**: "TransFusion: Robust LiDAR-Camera Fusion for 3D Object Detection with Transformers", CVPR, 2022 (*HKUST*). [[Paper](https://arxiv.org/abs/2203.11496)][[PyTorch](https://github.com/XuyangBai/TransFusion)]
* **CAT-Det**: "CAT-Det: Contrastively Augmented Transformer for Multi-modal 3D Object Detection", CVPR, 2022 (*Beihang University*). [[Paper](https://arxiv.org/abs/2204.00325)]
* **TokenFusion**: "Multimodal Token Fusion for Vision Transformers", CVPR, 2022 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2204.08721)]
* **SST**: "Embracing Single Stride 3D Object Detector with Sparse Transformer", CVPR, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2112.06375)][[PyTorch](https://github.com/TuSimple/SST)]
* **LIFT**: "LIFT: Learning 4D LiDAR Image Fusion Transformer for 3D Object Detection", CVPR, 2022 (*Shanghai Jiao Tong University*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Zeng_LIFT_Learning_4D_LiDAR_Image_Fusion_Transformer_for_3D_Object_CVPR_2022_paper.html)]
* **BoxeR**: "BoxeR: Box-Attention for 2D and 3D Transformers", CVPR, 2022 (*University of Amsterdam*). [[Paper](https://arxiv.org/abs/2111.13087)][[PyTorch](https://github.com/kienduynguyen/BoxeR)]
* **BrT**: "Bridged Transformer for Vision and Point Cloud 3D Object Detection", CVPR, 2022 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2210.01391)]
* **VISTA**: "VISTA: Boosting 3D Object Detection via Dual Cross-VIew SpaTial Attention", CVPR, 2022 (*South China University of Technology*). [[Paper](https://arxiv.org/abs/2203.09704)][[PyTorch](https://github.com/Gorilla-Lab-SCUT/VISTA)]
* **STRL**: "Towards Self-Supervised Pre-Training of 3DETR for Label-Efficient 3D Object Detection", CVPRW, 2022 (*Bosch*). [[Paper](https://drive.google.com/file/d/1_2RedCoqCH4cM6J-TOy18nevVd9RTr8c/view)]
* **MTrans**: "Multimodal Transformer for Automatic 3D Annotation and Object Detection", ECCV, 2022 (*HKU*). [[Paper](https://arxiv.org/abs/2207.09805)][[PyTorch](https://github.com/Cliu2/MTrans)]
* **CenterFormer**: "CenterFormer: Center-based Transformer for 3D Object Detection", ECCV, 2022 (*TuSimple*). [[Paper](https://arxiv.org/abs/2209.05588)][[Code (in construction)](https://github.com/TuSimple/centerformer)]
* **BUTD-DETR**: "Bottom Up Top Down Detection Transformers for Language Grounding in Images and Point Clouds", ECCV, 2022 (*CMU*). [[Paper](https://arxiv.org/abs/2112.08879)][[PyTorch](https://github.com/nickgkan/butd_detr)][[Website](https://butd-detr.github.io/)]
* **SpatialDETR**: "SpatialDETR: Robust Scalable Transformer-Based 3D Object Detection from Multi-View Camera Images with Global Cross-Sensor Attention", ECCV, 2022 (*Mercedes-Benz*). [[Paper](https://markus-enzweiler.de/downloads/publications/ECCV2022-spatial_detr.pdf)][[PyTorch](https://github.com/cgtuebingen/SpatialDETR)]
* **CramNet**: "CramNet: Camera-Radar Fusion with Ray-Constrained Cross-Attention for Robust 3D Object Detection", ECCV, 2022 (*Waymo*). [[Paper](https://arxiv.org/abs/2210.09267)]
* **SWFormer**: "SWFormer: Sparse Window Transformer for 3D Object Detection in Point Clouds", ECCV, 2022 (*Waymo*). [[Paper](https://arxiv.org/abs/2210.07372)]
* **EMMF-Det**: "Enhancing Multi-modal Features Using Local Self-Attention for 3D Object Detection", ECCV, 2022 (*Hikvision*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/6955_ECCV_2022_paper.php)]
* **PETR**: "PETR: Position Embedding Transformation for Multi-View 3D Object Detection", arXiv, 2022 (*Megvii*). [[Paper](https://arxiv.org/abs/2203.05625)]
* **MonoDETR**: "MonoDETR: Depth-aware Transformer for Monocular 3D Object Detection", arXiv, 2022 (*Shanghai AI Laboratory*). [[Paper](https://arxiv.org/abs/2203.13310)][[Code (in construction)](https://github.com/ZrrSkywalker/MonoDETR)]
* **Graph-DETR3D**: "Graph-DETR3D: Rethinking Overlapping Regions for Multi-View 3D Object Detection", arXiv, 2022 (*University of Science and Technology of China*). [[Paper](https://arxiv.org/abs/2204.11582)]
* **UVTR**: "Unifying Voxel-based Representation with Transformer for 3D Object Detection", arXiv, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2206.00630)][[PyTorch](https://github.com/dvlab-research/UVTR)]
* **PETRv2**: "PETRv2: A Unified Framework for 3D Perception from Multi-Camera Images", arXiv, 2022 (*Megvii*). [[Paper](https://arxiv.org/abs/2206.01256)]
* **PolarFormer**: "PolarFormer: Multi-camera 3D Object Detection with Polar Transformer", arXiv, 2022 (*Fudan University*). [[Paper](https://arxiv.org/abs/2206.15398#)][[Code (in construction)](https://github.com/fudan-zvg/PolarFormer)]
* **AST-GRU**: "Graph Neural Network and Spatiotemporal Transformer Attention for 3D Video Object Detection from Point Clouds", arXiv, 2022 (*Beijing Institute of Technology*). [[Paper](https://arxiv.org/abs/2207.12659)]
* **SEFormer**: "SEFormer: Structure Embedding Transformer for 3D Object Detection", arXiv, 2022 (*Tsinghua University*). [[Paper](https://arxiv.org/abs/2209.01745)]
* **CRAFT**: "CRAFT: Camera-Radar 3D Object Detection with Spatio-Contextual Fusion Transformer", arXiv, 2022 (*KAIST*). [[Paper](https://arxiv.org/abs/2209.06535)]
* **CrossDTR**: "CrossDTR: Cross-view and Depth-guided Transformers for 3D Object Detection", arXiv, 2022 (*NTU*). [[Paper](https://arxiv.org/abs/2209.13507)][[Code (in construction)](https://github.com/sty61010/CrossDTR)]
* **Li3DeTr**: "Li3DeTr: A LiDAR based 3D Detection Transformer", WACV, 2023 (*University of Coimbra, Portugal*). [[Paper](https://arxiv.org/abs/2210.15365)]

[[Back to Overview](#overview)]

### Multi-Modal Detection
* **OVR-CNN**: "Open-Vocabulary Object Detection Using Captions", CVPR, 2021 (*Snap*). [[Paper](https://arxiv.org/abs/2011.10678)][[PyTorch](https://github.com/alirezazareian/ovr-cnn)]
* **MDETR**: "MDETR - Modulated Detection for End-to-End Multi-Modal Understanding", ICCV, 2021 (*NYU*). [[Paper](https://arxiv.org/abs/2104.12763)][[PyTorch](https://github.com/ashkamath/mdetr)][[Website](https://ashkamath.github.io/mdetr_page/)]
* **FETNet**: "FETNet: Feature Exchange Transformer Network for RGB-D Object Detection", BMVC, 2021 (*Tsinghua*). [[Paper](https://www.bmvc2021-virtualconference.com/assets/papers/1400.pdf)]
* **MEDUSA**: "Exploiting Scene Depth for Object Detection with Multimodal Transformers", BMVC, 2021 (*Google*). [[Paper](https://www.bmvc2021-virtualconference.com/assets/papers/0568.pdf)][[PyTorch](https://github.com/songhwanjun/MEDUSA)]
* **StrucTexT**: "StrucTexT: Structured Text Understanding with Multi-Modal Transformers", arXiv, 2021 (*Baidu*). [[Paper](https://arxiv.org/abs/2108.02923)]
* **MAVL**: "Class-agnostic Object Detection with Multi-modal Transformer", ECCV, 2022 (*MBZUAI*). [[Paper](https://arxiv.org/abs/2111.11430)][[PyTorch](https://github.com/mmaaz60/mvits_for_class_agnostic_od)]
* **OWL-ViT**: "Simple Open-Vocabulary Object Detection with Vision Transformers", ECCV, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2205.06230)][[JAX](https://github.com/google-research/scenic/tree/main/scenic/projects/owl_vit)][[Hugging Face](https://huggingface.co/docs/transformers/model_doc/owlvit)]
* **X-DETR**: "X-DETR: A Versatile Architecture for Instance-wise Vision-Language Tasks", ECCV, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2204.05626)]
* **simCrossTrans**: "simCrossTrans: A Simple Cross-Modality Transfer Learning for Object Detection with ConvNets or Vision Transformers", arXiv, 2022 (*The City University of New York*). [[Paper](https://arxiv.org/abs/2203.10456)][[PyTorch](https://github.com/liketheflower/simCrossTrans)]
* **?**: "DALL-E for Detection: Language-driven Context Image Synthesis for Object Detection", arXiv, 2022 (*USC*). [[Paper](https://arxiv.org/abs/2206.09592)]
* **YONOD**: "You Only Need One Detector: Unified Object Detector for Different Modalities based on Vision Transformers", arXiv, 2022 (*CUNY*). [[Paper](https://arxiv.org/abs/2207.01071)][[PyTorch](https://github.com/liketheflower/YONOD)]
* **OmDet**: "OmDet: Language-Aware Object Detection with Large-scale Vision-Language Multi-dataset Pre-training", arXiv, 2022 (*Binjiang Institute of Zhejiang University*). [[Paper](https://arxiv.org/abs/2209.05946)]
* **Detection-Hub**: "Detection Hub: Unifying Object Detection Datasets via Query Adaptation on Language Embedding", arXiv, 2022 (*Fudan + Microsoft*). [[Paper](https://arxiv.org/abs/2206.03484)]
* **F-VLM**: "F-VLM: Open-Vocabulary Object Detection upon Frozen Vision and Language Models", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2209.15639)]
* **ContFormer**: "Video Referring Expression Comprehension via Transformer with Content-aware Query", arXiv, 2022 (*Peking University*). [[Paper](https://arxiv.org/abs/2210.02953)]

[[Back to Overview](#overview)]

### HOI Detection
* **HOI-Transformer**: "End-to-End Human Object Interaction Detection with HOI Transformer", CVPR, 2021 (*Megvii*). [[Paper](https://arxiv.org/abs/2103.04503)][[PyTorch](https://github.com/bbepoch/HoiTransformer)]
* **HOTR**: "HOTR: End-to-End Human-Object Interaction Detection with Transformers", CVPR, 2021 (*Kakao + Korea University*). [[Paper](https://arxiv.org/abs/2104.13682)][[PyTorch](https://github.com/kakaobrain/HOTR)]
* **MSTR**: "MSTR: Multi-Scale Transformer for End-to-End Human-Object Interaction Detection", CVPR, 2022 (*Kakao*). [[Paper](https://arxiv.org/abs/2203.14709)]
* **SSRT**: "What to look at and where: Semantic and Spatial Refined Transformer for detecting human-object interactions", CVPR, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2204.00746)]
* **CPC**: "Consistency Learning via Decoding Path Augmentation for Transformers in Human Object Interaction Detection", CVPR, 2022 (*Korea University*). [[Paper](https://arxiv.org/abs/2204.04836)][[PyTorch (in construction)](https://github.com/mlvlab/CPChoi)]
* **DisTR**: "Human-Object Interaction Detection via Disentangled Transformer", CVPR, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2204.09290)]
* **STIP**: "Exploring Structure-Aware Transformer Over Interaction Proposals for Human-Object Interaction Detection", CVPR, 2022 (*JD*). [[Paper](https://arxiv.org/abs/2206.06291)][[PyTorch](https://github.com/zyong812/STIP)]
* **DOQ**: "Distillation Using Oracle Queries for Transformer-Based Human-Object Interaction Detection", CVPR, 2022 (*South China University of Technology*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Qu_Distillation_Using_Oracle_Queries_for_Transformer-Based_Human-Object_Interaction_Detection_CVPR_2022_paper.html)]
* **UPT**: "Efficient Two-Stage Detection of Human-Object Interactions with a Novel Unary-Pairwise Transformer", CVPR, 2022 (*Australian Centre for Robotic Vision*). [[Paper](https://arxiv.org/abs/2112.01838)][[PyTorch](https://github.com/fredzzhang/upt)][[Website](https://fredzzhang.com/unary-pairwise-transformers/)]
* **CATN**: "Category-Aware Transformer Network for Better Human-Object Interaction Detection", CVPR, 2022 (*Huazhong University of Science and Technology*). [[Paper](https://arxiv.org/abs/2204.04911)]
* **HQM**: "Towards Hard-Positive Query Mining for DETR-based Human-Object Interaction Detection", ECCV, 2022 (*South China University of Technology*). [[Paper](https://arxiv.org/abs/2207.05293)][[PyTorch](https://github.com/MuchHair/HQM)]
* **Iwin**: "Iwin: Human-Object Interaction Detection via Transformer with Irregular Windows", ECCV, 2022 (*Shanghai Jiao Tong*). [[Paper](https://arxiv.org/abs/2203.10537)]
* **?**: "Understanding Embodied Reference with Touch-Line Transformer", arXiv, 2022 (*Tsinghua University*). [[Paper](https://arxiv.org/abs/2210.05668)][[PyTorch](https://github.com/Yang-Li-2000/Understanding-Embodied-Reference-with-Touch-Line-Transformer)]

[[Back to Overview](#overview)]

### Salient Object Detection
* **VST**: "Visual Saliency Transformer", ICCV, 2021 (*Northwestern Polytechincal University*). [[Paper](https://arxiv.org/abs/2104.12099)]
* **?**: "Learning Generative Vision Transformer with Energy-Based Latent Space for Saliency Prediction", NeurIPS, 2021 (*Baidu*). [[Paper](https://arxiv.org/abs/2112.13528)]
* **SwinNet**: "SwinNet: Swin Transformer drives edge-aware RGB-D and RGB-T salient object detection", TCSVT, 2021 (*Anhui University*). [[Paper](https://arxiv.org/abs/2204.05585)][[Code](https://github.com/liuzywen/SwinNet)]
* **SOD-Transformer**: "Transformer Transforms Salient Object Detection and Camouflaged Object Detection", arXiv, 2021 (*Northwestern Polytechnical University*). [[Paper](https://arxiv.org/abs/2104.10127)]
* **GLSTR**: "Unifying Global-Local Representations in Salient Object Detection with Transformer", arXiv, 2021 (*South China University of Technology*). [[Paper](https://arxiv.org/abs/2108.02759)]
* **TriTransNet**: "TriTransNet: RGB-D Salient Object Detection with a Triplet Transformer Embedding Network", arXiv, 2021 (*Anhui University*). [[Paper](https://arxiv.org/abs/2108.03990)]
* **AbiU-Net**: "Boosting Salient Object Detection with Transformer-based Asymmetric Bilateral U-Net", arXiv, 2021 (*Nankai University*). [[Paper](https://arxiv.org/abs/2108.07851)]
* **TranSalNet**: "TranSalNet: Visual saliency prediction using transformers", arXiv, 2021 (*Cardiff University, UK*). [[Paper](https://arxiv.org/abs/2110.03593)]
* **DFTR**: "DFTR: Depth-supervised Hierarchical Feature Fusion Transformer for Salient Object Detection", arXiv, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2203.06429)]
* **GroupTransNet**: "GroupTransNet: Group Transformer Network for RGB-D Salient Object Detection", arXiv, 2022 (*Nankai university*). [[Paper](https://arxiv.org/abs/2203.10785)]
* **SelfReformer**: "SelfReformer: Self-Refined Network with Transformer for Salient Object Detection", arXiv, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2205.11283)]
* **DTMINet**: "Dual Swin-Transformer based Mutual Interactive Network for RGB-D Salient Object Detection", arXiv, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2206.03105)]
* **MCNet**: "Mirror Complementary Transformer Network for RGB-thermal Salient Object Detection", arXiv, 2022 (*Beijing University of Posts and Telecommunications*). [[Paper](https://arxiv.org/abs/2207.03558)][[PyTorch](https://github.com/jxr326/SwinMCNet)]
* **SiaTrans**: "SiaTrans: Siamese Transformer Network for RGB-D Salient Object Detection with Depth Image Classification", arXiv, 2022 (*Shandong University of Science and Technology*). [[Paper](https://arxiv.org/abs/2207.04224)]
* **PSFormer**: "PSFormer: Point Transformer for 3D Salient Object Detection", arXiv, 2022 (*Nanjing University of Aeronautics and Astronautics*). [[Paper](https://arxiv.org/abs/2210.15933)]

[[Back to Overview](#overview)]

### Other Detection Tasks
* X-supervised:
    * **LOST**: "Localizing Objects with Self-Supervised Transformers and no Labels", BMVC, 2021 (*Valeo.ai*). [[Paper](https://arxiv.org/abs/2109.14279)][[PyTorch](https://github.com/valeoai/LOST)]
    * **Omni-DETR**: "Omni-DETR: Omni-Supervised Object Detection with Transformers", CVPR, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2203.16089)][[PyTorch](https://github.com/amazon-research/omni-detr)]
    * **TokenCut**: "Self-Supervised Transformers for Unsupervised Object Discovery using Normalized Cut", CVPR, 2022 (*Univ. Grenoble Alpes, France*). [[Paper](https://arxiv.org/abs/2202.11539)][[PyTorch](https://github.com/YangtaoWANG95/TokenCut)][[Website](https://www.m-psi.fr/Papers/TokenCut2022/)]
    * **WS-DETR**: "Scaling Novel Object Detection with Weakly Supervised Detection Transformers", CVPRW, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2207.05205)]
    * **TRT**: "Re-Attention Transformer for Weakly Supervised Object Localization", arXiv, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2208.01838)][[PyTorch](https://github.com/su-hui-zz/ReAttentionTransformer)]
    * **TokenCut**: "TokenCut: Segmenting Objects in Images and Videos with Self-supervised Transformer and Normalized Cut", arXiv, 2022 (*Univ. Grenoble Alpes, France*). [[Paper](https://arxiv.org/abs/2209.00383)][[PyTorch](https://github.com/YangtaoWANG95/TokenCut)][[Website](https://www.m-psi.fr/Papers/TokenCut2022/)]
* X-Shot Object Detection:
    * **AIT**: "Adaptive Image Transformer for One-Shot Object Detection", CVPR, 2021 (*Academia Sinica*). [[Paper](https://openaccess.thecvf.com/content/CVPR2021/html/Chen_Adaptive_Image_Transformer_for_One-Shot_Object_Detection_CVPR_2021_paper.html)]
    * **Meta-DETR**: "Meta-DETR: Few-Shot Object Detection via Unified Image-Level Meta-Learning", arXiv, 2021 (*NTU Singapore*). [[Paper](https://arxiv.org/abs/2103.11731)][[PyTorch](https://github.com/ZhangGongjie/Meta-DETR)]
    * **CAT**: "CAT: Cross-Attention Transformer for One-Shot Object Detection", arXiv, 2021 (*Northwestern Polytechnical University*). [[Paper](https://arxiv.org/abs/2104.14984)]
    * **FCT**: "Few-Shot Object Detection with Fully Cross-Transformer", CVPR, 2022 (*Columbia*). [[Paper](https://arxiv.org/abs/2203.15021)]
    * **SaFT**: "Semantic-aligned Fusion Transformer for One-shot Object Detection", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2203.09093)]
    * **TENET**: "Time-rEversed diffusioN tEnsor Transformer: A New TENET of Few-Shot Object Detection", ECCV, 2022 (*ANU*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/5009_ECCV_2022_paper.php)][[PyTorch](https://github.com/ZS123-lang/TENET)]
    * **Meta-DETR**: "Meta-DETR: Image-Level Few-Shot Detection with Inter-Class Correlation Exploitation", TPAMI, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2208.00219)]
    * **Incremental-DETR**: "Incremental-DETR: Incremental Few-Shot Object Detection via Self-Supervised Learning", arXiv, 2022 (*NUS*). [[Paper](https://arxiv.org/abs/2205.04042)]
    * **FS-DETR**: "FS-DETR: Few-Shot DEtection TRansformer with prompting and without re-training", arXiv, 2022 (*Samsung*). [[Paper](https://arxiv.org/abs/2210.04845)]
* Open-World/Vocabulary:
    * **OW-DETR**: "OW-DETR: Open-world Detection Transformer", CVPR, 2022 (*IIAI*). [[Paper](https://arxiv.org/abs/2112.01513)][[PyTorch](https://github.com/akshitac8/OW-DETR)]
    * **DetPro**: "Learning to Prompt for Open-Vocabulary Object Detection with Vision-Language Model", CVPR, 2022 (*Tsinghua University*). [[Paper](https://arxiv.org/abs/2203.14940)][[PyTorch](https://github.com/dyabel/detpro)]
    * **PromptDet**: "PromptDet: Towards Open-vocabulary Detection using Uncurated Images", ECCV, 2022 (*Meituan*). [[Paper](https://arxiv.org/abs/2203.16513)][[PyTorch](https://github.com/fcjian/PromptDet)][[Website](https://fcjian.github.io/promptdet/)]
    * **OV-DETR**: "Open-Vocabulary DETR with Conditional Matching", ECCV, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2203.11876)]
    * **VL-PLM**: "Exploiting Unlabeled Data with Vision and Language Models for Object Detection", ECCV, 2022 (*Rutgers University*). [[Paper](https://arxiv.org/abs/2207.08954)][[PyTorch](https://github.com/xiaofeng94/VL-PLM)][[Website](https://www.nec-labs.com/~mas/VL-PLM/)]
    * **DetCLIP**: "DetCLIP: Dictionary-Enriched Visual-Concept Paralleled Pre-training for Open-world Detection", NeurIPS, 2022 (*HKUST*). [[Paper](https://arxiv.org/abs/2209.09407)]
* Pedestrian Detection:
    * **PED**: "DETR for Crowd Pedestrian Detection", arXiv, 2020 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2012.06785)][[PyTorch](https://github.com/Hatmm/PED-DETR-for-Pedestrian-Detection)]
    * **Pedestron**: "Pedestrian Detection: Domain Generalization, CNNs, Transformers and Beyond", arXiv, 2022 (*IIAI*). [[Paper](https://arxiv.org/abs/2201.03176)][[PyTorch](https://github.com/hasanirtiza/Pedestron)]
* Lane Detection:
    * **LSTR**: "End-to-end Lane Shape Prediction with Transformers", WACV, 2021 (*Xi'an Jiaotong*). [[Paper](https://arxiv.org/abs/2011.04233)][[PyTorch](https://github.com/liuruijin17/LSTR)]
    * **LETR**: "Line Segment Detection Using Transformers without Edges", CVPR, 2021 (*UCSD*). [[Paper](https://arxiv.org/abs/2101.01909)][[PyTorch](https://github.com/mlpc-ucsd/LETR)]
    * **Laneformer**: "Laneformer: Object-aware Row-Column Transformers for Lane Detection", AAAI, 2022 (*Huawei*). [[Paper](https://arxiv.org/abs/2203.09830)]
    * **TLC**: "Transformer Based Line Segment Classifier With Image Context for Real-Time Vanishing Point Detection in Manhattan World", CVPR, 2022 (*Peking University*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Tong_Transformer_Based_Line_Segment_Classifier_With_Image_Context_for_Real-Time_CVPR_2022_paper.html)]
    * **PersFormer**: "PersFormer: 3D Lane Detection via Perspective Transformer and the OpenLane Benchmark", ECCV, 2022 (*Shanghai AI Laboratory*). [[Paper](https://arxiv.org/abs/2203.11089)][[PyTorch](https://github.com/OpenPerceptionX/OpenLane)]
    * **MHVA**: "Lane Detection Transformer Based on Multi-Frame Horizontal and Vertical Attention and Visual Transformer Module", ECCV, 2022 (*Beihang University*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/3918_ECCV_2022_paper.php)]
    * **PriorLane**: "PriorLane: A Prior Knowledge Enhanced Lane Detection Approach Based on Transformer", arXiv, 2022 (*Zhejiang Lab*). [[Paper](https://arxiv.org/abs/2209.06994)][[PyTorch](https://github.com/vincentqqb/priorlane)]
    * **CurveFormer**: "CurveFormer: 3D Lane Detection by Curve Propagation with Curve Queries and Attention", arXiv, 2022 (*NullMax, China*). [[Paper](https://arxiv.org/abs/2209.07989)]
* Object Localization:
    * **TS-CAM**: "TS-CAM: Token Semantic Coupled Attention Map for Weakly Supervised Object Localization", arXiv, 2021 (*CAS*). [[Paper](https://arxiv.org/abs/2103.14862)]
    * **LCTR**: "LCTR: On Awakening the Local Continuity of Transformer for Weakly Supervised Object Localization", AAAI, 2022 (*Xiamen University*). [[Paper](https://arxiv.org/abs/2112.05291)]
    * **ViTOL**: "ViTOL: Vision Transformer for Weakly Supervised Object Localization", CVPRW, 2022 (*Mercedes-Benz*). [[Paper](https://arxiv.org/abs/2204.06772)][[PyTorch](https://github.com/Saurav-31/ViTOL)]
    * **SCM**: "Weakly Supervised Object Localization via Transformer with Implicit Spatial Calibration", ECCV, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2207.10447)][[PyTorch](https://github.com/164140757/SCM)]
    * **CaFT**: "CaFT: Clustering and Filter on Tokens of Transformer for Weakly Supervised Object Localization", arXiv, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2201.00475)]
* Relation Detection:
    * **PST**: "Visual Relationship Detection Using Part-and-Sum Transformers with Composite Queries", ICCV, 2021 (*Amazon*). [[Paper](https://arxiv.org/abs/2105.02170)]
    * **PST**: "Visual Composite Set Detection Using Part-and-Sum Transformers", arXiv, 2021 (*Amazon*). [[Paper](https://arxiv.org/abs/2105.02170)]
    * **TROI**: "Transformed ROIs for Capturing Visual Transformations in Videos", arXiv, 2021 (*NUS, Singapore*). [[Paper](https://arxiv.org/abs/2106.03162)]
    * **RelTransformer**: "RelTransformer: A Transformer-Based Long-Tail Visual Relationship Recognition", CVPR, 2022 (*KAUST*). [[Paper](https://arxiv.org/abs/2104.11934)][[PyTorch](https://github.com/Vision-CAIR/RelTransformer)]
    * **VReBERT**: "VReBERT: A Simple and Flexible Transformer for Visual Relationship Detection", ICPR, 2022 (*ANU*). [[Paper](https://arxiv.org/abs/2206.09111)]
* Anomaly Detection:
    * **VT-ADL**: "VT-ADL: A Vision Transformer Network for Image Anomaly Detection and Localization", ISIE, 2021 (*University of Udine, Italy*). [[Paper](https://arxiv.org/abs/2104.10036)]
    * **InTra**: "Inpainting Transformer for Anomaly Detection", arXiv, 2021 (*Fujitsu*). [[Paper](https://arxiv.org/abs/2104.13897)]
    * **AnoViT**: "AnoViT: Unsupervised Anomaly Detection and Localization with Vision Transformer-based Encoder-Decoder", arXiv, 2022 (*Korea University*). [[Paper](https://arxiv.org/abs/2203.10808)]
    * **?**: "Multi-Contextual Predictions with Vision Transformer for Video Anomaly Detection", arXiv, 2022 (*Korea University*). [[Paper](https://arxiv.org/abs/2206.08568)]
* Cross-Domain:
    * **SSTN**: "SSTN: Self-Supervised Domain Adaptation Thermal Object Detection for Autonomous Driving", arXiv, 2021 (*Gwangju Institute of Science and Technology*). [[Paper](https://arxiv.org/abs/2103.03150)]
    * **DA-DETR**: "DA-DETR: Domain Adaptive Detection Transformer by Hybrid Attention", arXiv, 2021 (*NTU Singapore*). [[Paper](https://arxiv.org/abs/2103.17084)]
    * **MTTrans**: "MTTrans: Cross-Domain Object Detection with Mean-Teacher Transformer", ECCV, 2022 (*Beihang University*). [[Paper](https://arxiv.org/abs/2205.01643)]
    * **OAA-OTA**: "Improving Transferability for Domain Adaptive Detection Transformers", arXiv, 2022 (*Beijing Institute of Technology*). [[Paper](https://arxiv.org/abs/2204.14195)]
    * **SSTA**: "Cross-domain Detection Transformer based on Spatial-aware and Semantic-aware Token Alignment", arXiv, 2022 (*University of Electronic Science and Technology of China*). [[Paper](https://arxiv.org/abs/2206.00222)]
* Co-Salient Object Detection:
    * **CoSformer**: "CoSformer: Detecting Co-Salient Object with Transformers", arXiv, 2021 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2104.14729)]
* Oriented Object Detection:
    * **O<sup>2</sup>DETR**: "Oriented Object Detection with Transformer", arXiv, 2021 (*Baidu*). [[Paper](https://arxiv.org/abs/2106.03146)]
* Multiview Detection:
    * **MVDeTr**: "Multiview Detection with Shadow Transformer (and View-Coherent Data Augmentation)", ACMMM, 2021 (*ANU*). [[Paper](https://arxiv.org/abs/2108.05888)]
* Polygon Detection:
    * **?**: "Investigating transformers in the decomposition of polygonal shapes as point collections", ICCVW, 2021 (*Delft University of Technology, Netherlands*). [[Paper](https://arxiv.org/abs/2108.07533)]
* Drone-view:
    * **TPH**: "TPH-YOLOv5: Improved YOLOv5 Based on Transformer Prediction Head for Object Detection on Drone-captured Scenarios", ICCVW, 2021 (*Beihang University*). [[Paper](https://arxiv.org/abs/2108.11539)]
    * **TransVisDrone**: "TransVisDrone: Spatio-Temporal Transformer for Vision-based Drone-to-Drone Detection in Aerial Videos", arXiv, 2022 (*UCF*). [[Paper](https://arxiv.org/abs/2210.08423)][[Code (in construction)](https://github.com/tusharsangam/TransVisDrone)]
* Infrared:
    * **?**: "Infrared Small-Dim Target Detection with Transformer under Complex Backgrounds", arXiv, 2021 (*Chongqing University of Posts and Telecommunications*). [[Paper](https://arxiv.org/abs/2109.14379)]
* Text:
    * **SwinTextSpotter**: "SwinTextSpotter: Scene Text Spotting via Better Synergy between Text Detection and Text Recognition", CVPR, 2022 (*South China University of Technology*). [[Paper](https://arxiv.org/abs/2203.10209)][[PyTorch](https://github.com/mxin262/SwinTextSpotter)]
    * **TESTR**: "Text Spotting Transformers", CVPR, 2022 (*UCSD*). [[Paper](https://arxiv.org/abs/2204.01918)][[PyTorch](https://github.com/mlpc-ucsd/TESTR)]
    * **TTS**: "Towards Weakly-Supervised Text Spotting using a Multi-Task Transformer", CVPR, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2202.05508)]
    * **oCLIP**: "Language Matters: A Weakly Supervised Vision-Language Pre-training Approach for Scene Text Detection and Spotting", ECCV, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2203.03911)]
    * **TransDETR**: "End-to-End Video Text Spotting with Transformer", arXiv, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2203.10539)][[PyTorch](https://github.com/weijiawu/TransDETR)]
    * **?**: "Arbitrary Shape Text Detection using Transformers", arXiv, 2022 (*University of Waterloo, Canada*). [[Paper](https://arxiv.org/abs/2202.11221)]
    * **?**: "Arbitrary Shape Text Detection via Boundary Transformer", arXiv, 2022 (*University of Science and Technology Beijing*). [[Paper](https://arxiv.org/abs/2205.05320)][[Code (in construction)](https://github.com/GXYM/TextBPN-Plus-Plus)]
    * **DPText-DETR**: "DPText-DETR: Towards Better Scene Text Detection with Dynamic Points in Transformer", arXiv, 2022 (*JD*). [[Paper](https://arxiv.org/abs/2207.04491)][[Code (in construction)](https://github.com/ymy-k/DPText-DETR)]
    * **DPTNet**: "DPTNet: A Dual-Path Transformer Architecture for Scene Text Detection", arXiv, 2022 (*Xiamen University*). [[Paper](https://arxiv.org/abs/2208.09878)]
* Change Detection:
    * **ChangeFormer**: "A Transformer-Based Siamese Network for Change Detection", arXiv, 2022 (*JHU*). [[Paper](https://arxiv.org/abs/2201.01293)][[PyTorch](https://github.com/wgcban/ChangeFormer)]
    * **IDET**: "IDET: Iterative Difference-Enhanced Transformers for High-Quality Change Detection", arXiv, 2022 (*Civil Aviation University of China*). [[Paper](https://arxiv.org/abs/2207.09240)]
* Edge Detection:
    * **EDTER**: "EDTER: Edge Detection with Transformer", CVPR, 2022 (*Beijing Jiaotong University*). [[Paper](https://arxiv.org/abs/2203.08566)][[Code (in construction)](https://github.com/MengyangPu/EDTER)]
    * **HEAT**: "HEAT: Holistic Edge Attention Transformer for Structured Reconstruction", CVPR, 2022 (*Simon Fraser*). [[Paper](https://arxiv.org/abs/2111.15143)][[PyTorch](https://github.com/woodfrog/heat)][[Website](https://heat-structured-reconstruction.github.io/)]
* Person Search:
    * **COAT**: "Cascade Transformers for End-to-End Person Search", CVPR, 2022 (*Kitware*). [[Paper](https://arxiv.org/abs/2203.09642)][[PyTorch](https://github.com/Kitware/COAT)]
    * **PSTR**: "PSTR: End-to-End One-Step Person Search With Transformers", CVPR, 2022 (*Tianjin University*). [[Paper](https://arxiv.org/abs/2204.03340)][[PyTorch](https://github.com/JialeCao001/PSTR)]
* Manipulation Detection:
    * **ObjectFormer**: "ObjectFormer for Image Manipulation Detection and Localization", CVPR, 2022 (*Fudan University*). [[Paper](https://arxiv.org/abs/2203.14681)]
* Grounded Situation Recognition:
    * **CoFormer**: "Collaborative Transformers for Grounded Situation Recognition", CVPR, 2022 (*POSTECH*). [[Paper](https://arxiv.org/abs/2203.16518)][[PyTorch](https://github.com/jhcho99/CoFormer)]
* Mirror Detection:
    * **SATNet**: "Symmetry-Aware Transformer-based Mirror Detection", arXiv, 2022 (*Harbin Institute of Technology*). [[Paper](https://arxiv.org/abs/2207.06332)][[PyTorch](https://github.com/tyhuang0428/SATNet)]

[[Back to Overview](#overview)]


## Segmentation
### Semantic Segmentation
* **SETR**: "Rethinking Semantic Segmentation from a Sequence-to-Sequence Perspective with Transformers", CVPR, 2021 (*Tencent*). [[Paper](https://arxiv.org/abs/2012.15840)][[PyTorch](https://github.com/fudan-zvg/SETR)][[Website](https://fudan-zvg.github.io/SETR/)]
* **TrSeg**: "TrSeg: Transformer for semantic segmentation", PRL, 2021 (*Korea University*). [[Paper](https://www.sciencedirect.com/science/article/abs/pii/S016786552100163X)][[PyTorch](https://github.com/youngsjjn/TrSeg)]
* **CWT**: "Simpler is Better: Few-shot Semantic Segmentation with Classifier Weight Transformer", ICCV, 2021 (*University of Surrey, UK*). [[Paper](https://arxiv.org/abs/2108.03032)][[PyTorch](https://github.com/zhiheLu/CWT-for-FSS)]
* **Segmenter**: "Segmenter: Transformer for Semantic Segmentation", ICCV, 2021 (*INRIA*). [[Paper](https://arxiv.org/abs/2105.05633)][[PyTorch](https://github.com/rstrudel/segmenter)]
* **UN-EPT**: "A Unified Efficient Pyramid Transformer for Semantic Segmentation", ICCVW, 2021 (*Amazon*). [[Paper](https://arxiv.org/abs/2107.14209)][[PyTorch](https://github.com/amazon-research/unified-ept)]
* **SegFormer**: "SegFormer: Simple and Efficient Design for Semantic Segmentation with Transformers", NeurIPS, 2021 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2105.15203)][[PyTorch](https://github.com/NVlabs/SegFormer)]
* **FTN**: "Fully Transformer Networks for Semantic Image Segmentation", arXiv, 2021 (*Baidu*). [[Paper](https://arxiv.org/abs/2106.04108)]
* **OffRoadTranSeg**: "OffRoadTranSeg: Semi-Supervised Segmentation using Transformers on OffRoad environments", arXiv, 2021 (*IISER. India*). [[Paper](https://arxiv.org/abs/2106.13963)]
* **MaskFormer**: "Per-Pixel Classification is Not All You Need for Semantic Segmentation", arXiv, 2021 (*UIUC + Facebook*). [[Paper](https://arxiv.org/abs/2107.06278)][[Website](https://bowenc0221.github.io/maskformer/)]
* **TRFS**: "Boosting Few-shot Semantic Segmentation with Transformers", arXiv, 2021 (*ETHZ*). [[Paper](https://arxiv.org/abs/2108.02266)]
* **Flying-Guide-Dog**: "Flying Guide Dog: Walkable Path Discovery for the Visually Impaired Utilizing Drones and Transformer-based Semantic Segmentation", arXiv, 2021 (*KIT, Germany*). [[Paper](https://arxiv.org/abs/2108.07007)][[Code (in construction)](https://github.com/EckoTan0804/flying-guide-dog)]
* **VSPW**: "Semantic Segmentation on VSPW Dataset through Aggregation of Transformer Models", arXiv, 2021 (*Xiaomi*). [[Paper](https://arxiv.org/abs/2109.01316)]
* **SDTP**: "SDTP: Semantic-aware Decoupled Transformer Pyramid for Dense Image Prediction", arXiv, 2021 (*?*). [[Paper](https://arxiv.org/abs/2109.08963)]
* **TopFormer**: "TopFormer: Token Pyramid Transformer for Mobile Semantic Segmentation", CVPR, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2204.05525)][[PyTorch](https://github.com/hustvl/TopFormer)]
* **GroupViT**: "GroupViT: Semantic Segmentation Emerges from Text Supervision", CVPR, 2022 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2202.11094)][[Website](https://jerryxu.net/GroupViT/)][[PyTorch](https://github.com/NVlabs/GroupViT)]
* **HRViT**: "Multi-Scale High-Resolution Vision Transformer for Semantic Segmentation", CVPR, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2111.01236)][[PyTorch](https://github.com/facebookresearch/HRViT)]
* **GReaT**: "Graph Reasoning Transformer for Image Parsing", ACMMM, 2022 (*HKUST*). [[Paper](https://arxiv.org/abs/2209.09545)]
* **SegDeformer**: "A Transformer-Based Decoder for Semantic Segmentation with Multi-level Context Mining", ECCV, 2022 (*Shanghai Jiao Tong + Huawei*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/383_ECCV_2022_paper.php)][[PyTorch](https://github.com/lygsbw/segdeformer)]
* **SegViT**: "SegViT: Semantic Segmentation with Plain Vision Transformers", NeurIPS, 2022 (*The University of Adelaide, Australia*). [[Paper](https://arxiv.org/abs/2210.05844)]
* **RTFormer**: "RTFormer: Efficient Design for Real-Time Semantic Segmentation with Transformer", NeurIPS, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2210.07124)][[Paddle](https://github.com/PaddlePaddle/PaddleSeg)]
* **Lawin**: "Lawin Transformer: Improving Semantic Segmentation Transformer with Multi-Scale Representations via Large Window Attention", arXiv, 2022 (*Beijing University of Posts and Telecommunications*). [[Paper](https://arxiv.org/abs/2201.01615)][[PyTorch](https://github.com/yan-hao-tian/lawin)]
* **PFT**: "Pyramid Fusion Transformer for Semantic Segmentation", arXiv, 2022 (*CUHK + SenseTime*). [[Paper](https://arxiv.org/abs/2201.04019)]
* **DFlatFormer**: "Dual-Flattening Transformers through Decomposed Row and Column Queries for Semantic Segmentation", arXiv, 2022 (*OPPO*). [[Paper](https://arxiv.org/abs/2201.09139)]
* **FeSeFormer**: "Feature Selective Transformer for Semantic Image Segmentation", arXiv, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2203.14124)]
* **StructToken**: "StructToken : Rethinking Semantic Segmentation with Structural Prior", arXiv, 2022 (*Shanghai AI Lab*). [[Paper](https://arxiv.org/abs/2203.12612)]
* **TSG**: "Transformer Scale Gate for Semantic Segmentation", arXiv, 2022 (*Monash University, Australia*). [[Paper](https://arxiv.org/abs/2205.07056)]
* **HILA**: "Improving Semantic Segmentation in Transformers using Hierarchical Inter-Level Attention", arXiv, 2022 (*University of Toronto*). [[Paper](https://arxiv.org/abs/2207.02126)][[Website](https://www.cs.toronto.edu/~garyleung/hila/)][[PyTorch](https://github.com/fidler-lab/hila)]
* **HLG**: "Visual Representation Learning with Transformer: A Sequence-to-Sequence Perspective", arXiv, 2022 (*Fudan University*). [[Paper](https://arxiv.org/abs/2207.09339)][[PyTorch](https://github.com/fudan-zvg/SETR)]
* **SSformer**: "SSformer: A Lightweight Transformer for Semantic Segmentation", arXiv, 2022 (*Nanjing University of Aeronautics and Astronautics*). [[Paper](https://arxiv.org/abs/2208.02034)][[PyTorch](https://github.com/shiwt03/SSformer)]
* **NamedMask**: "NamedMask: Distilling Segmenters from Complementary Foundation Models", arXiv, 2022 (*Oxford*). [[Paper](https://arxiv.org/abs/2209.11228)][[PyTorch](https://github.com/NoelShin/namedmask)][[Website](https://www.robots.ox.ac.uk/~vgg/research/namedmask/)]

[[Back to Overview](#overview)]

### Depth Estimation
* **DPT**: "Vision Transformers for Dense Prediction", ICCV, 2021 (*Intel*). [[Paper](https://arxiv.org/abs/2103.13413)][[PyTorch](https://github.com/intel-isl/DPT)]
* **TransDepth**: "Transformer-Based Attention Networks for Continuous Pixel-Wise Prediction", ICCV, 2021 (*Haerbin Institute of Technology + University of Trento*). [[Paper](https://arxiv.org/abs/2103.12091)][[PyTorch](https://github.com/ygjwd12345/TransDepth)]
* **ASTransformer**: "Transformer-based Monocular Depth Estimation with Attention Supervision", BMVC, 2021 (*USTC*). [[Paper](https://www.bmvc2021-virtualconference.com/assets/papers/0244.pdf)][[PyTorch](https://github.com/WJ-Chang-42/ASTransformer)]
* **MT-SfMLearner**: "Transformers in Self-Supervised Monocular Depth Estimation with Unknown Camera Intrinsics", VISAP, 2022 (*NavInfo Europe, Netherlands*). [[Paper](https://arxiv.org/abs/2202.03131)]
* **DepthFormer**: "Multi-Frame Self-Supervised Depth with Transformers", CVPR, 2022 (*Toyota*). [[Paper](https://arxiv.org/abs/2204.07616)]
* **GuideFormer**: "GuideFormer: Transformers for Image Guided Depth Completion", CVPR, 2022 (*Agency for Defense Development, Korea*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Rho_GuideFormer_Transformers_for_Image_Guided_Depth_Completion_CVPR_2022_paper.html)]
* **SparseFormer**: "SparseFormer: Attention-based Depth Completion Network", CVPRW, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2206.04557)]
* **DEST**: "Depth Estimation with Simplified Transformer", CVPRW, 2022 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2204.13791)]
* **MonoViT**: "MonoViT: Self-Supervised Monocular Depth Estimation with a Vision Transformer", 3DV, 2022 (*University of Bologna, Italy*). [[Paper](https://arxiv.org/abs/2208.03543)][[PyTorch](https://github.com/zxcqlf/MonoViT)]
* **Spike-Transformer**: "Spike Transformer: Monocular Depth Estimation for Spiking Camera", ECCV, 2022 (*Peking University*). [[Paper]()][[PyTorch](https://github.com/Leozhangjiyuan/MDE-SpikingCamera)]
* **GLPanoDepth**: "GLPanoDepth: Global-to-Local Panoramic Depth Estimation", arXiv, 2022 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2202.02796)]
* **DepthFormer**: "DepthFormer: Exploiting Long-Range Correlation and Local Information for Accurate Monocular Depth Estimation", arXiv, 2022 (*Harbin Institute of Technology*). [[Paper](https://arxiv.org/abs/2203.14211)][[PyTorch](https://github.com/zhyever/Monocular-Depth-Estimation-Toolbox)]
* **BinsFormer**: "BinsFormer: Revisiting Adaptive Bins for Monocular Depth Estimation", arXiv, 2022 (*Harbin Institute of Technology*). [[Paper](https://arxiv.org/abs/2204.00987)][[PyTorch](https://github.com/zhyever/Monocular-Depth-Estimation-Toolbox)]
* **SideRT**: "SideRT: A Real-time Pure Transformer Architecture for Single Image Depth Estimation", arXiv, 2022 (*Meituan*). [[Paper](https://arxiv.org/abs/2204.13892)]
* **MonoFormer**: "MonoFormer: Towards Generalization of self-supervised monocular depth estimation with Transformers", arXiv, 2022 (*DGIST, Korea*). [[Paper](https://arxiv.org/abs/2205.11083)]
* **Depthformer**: "Depthformer : Multiscale Vision Transformer For Monocular Depth Estimation With Local Global Information Fusion", arXiv, 2022 (*Indian Institute of Technology Delhi*). [[Paper](https://arxiv.org/abs/2207.04535)]
* **TODE-Trans**: "TODE-Trans: Transparent Object Depth Estimation with Transformer", arXiv, 2022 (*USTC*). [[Paper](https://arxiv.org/abs/2209.08455)][[Code (in construction)](https://github.com/yuchendoudou/TODE)]

[[Back to Overview](#overview)]

### Object Segmentation
* **SOTR**: "SOTR: Segmenting Objects with Transformers", ICCV, 2021 (*China Agricultural University*). [[Paper](https://arxiv.org/abs/2108.06747)][[PyTorch](https://github.com/easton-cau/SOTR)]
* **Trans4Trans**: "Trans4Trans: Efficient Transformer for Transparent Object Segmentation to Help Visually Impaired People Navigate in the Real World", ICCVW, 2021 (*Karlsruhe Institute of Technology, Germany*). [[Paper](https://arxiv.org/abs/2107.03172)][[Code (in construction)](https://github.com/jamycheung/Trans4Trans)]
* **Trans2Seg**: "Segmenting Transparent Object in the Wild with Transformer", arXiv, 2021 (*HKU + SenseTime*). [[Paper](https://arxiv.org/abs/2101.08461)][[PyTorch](https://github.com/xieenze/Trans2Seg)]
* **SOIT**: "SOIT: Segmenting Objects with Instance-Aware Transformers", AAAI, 2022 (*Hikvision*). [[Paper](https://arxiv.org/abs/2112.11037)][[PyTorch](https://github.com/hikvision-research/opera)]
* **CAST**: "Concurrent Recognition and Segmentation with Adaptive Segment Tokens", arXiv, 2022 (*Berkeley*). [[Paper](https://arxiv.org/abs/2210.00314)]
* **?**: "Learning Explicit Object-Centric Representations with Vision Transformers", arXiv, 2022 (*Aalto University, Finland*). [[Paper](https://arxiv.org/abs/2210.14139)]

[[Back to Overview](#overview)]

### Other Segmentation Tasks
* Vision-Language:
    * **LSeg**: "Language-driven Semantic Segmentation", ICLR, 2022 (*Cornell*). [[Paper](https://arxiv.org/abs/2201.03546)][[PyTorch](https://github.com/isl-org/lang-seg)]
    * **ZegFormer**: "Decoupling Zero-Shot Semantic Segmentation", CVPR, 2022 (*Wuhan University*). [[Paper](https://arxiv.org/abs/2112.07910)][[PyTorch](https://github.com/dingjiansw101/ZegFormer)]
    * **CLIPSeg**: "Image Segmentation Using Text and Image Prompts", CVPR, 2022 (*University of Göttingen, Germany*). [[Paper](https://arxiv.org/abs/2112.10003)][[PyTorch](https://github.com/timojl/clipseg)]
    * **DenseCLIP**: "DenseCLIP: Language-Guided Dense Prediction with Context-Aware Prompting", CVPR, 2022 (*Tsinghua University*). [[Paper](https://arxiv.org/abs/2112.01518)][[PyTorch](https://github.com/raoyongming/DenseCLIP)][[Website](https://denseclip.ivg-research.xyz/)]
    * **MaskCLIP**: "Extract Free Dense Labels from CLIP", ECCV, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2112.01071)][[PyTorch](https://github.com/chongzhou96/MaskCLIP)][[Website](https://www.mmlab-ntu.com/project/maskclip/)]
    * **?**: "A Simple Baseline for Open Vocabulary Semantic Segmentation with Pre-trained Vision-language Model", ECCV, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2112.14757)][[PyTorch](https://github.com/MendelXu/zsseg.baseline)]
* Multi-Modal:
    * **UCTNet**: "UCTNet: Uncertainty-Aware Cross-Modal Transformer Network for Indoor RGB-D Semantic Segmentation", ECCV, 2022 (*Lehigh University, Pennsylvania*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/7082_ECCV_2022_paper.php)]
    * **CMX**: "CMX: Cross-Modal Fusion for RGB-X Semantic Segmentation with Transformers", arXiv, 2022 (*Karlsruhe Institute of Technology, Germany*). [[Paper](https://arxiv.org/abs/2203.04838)][[PyTorch](https://github.com/huaaaliu/RGBX_Semantic_Segmentation)]
* Panoptic Segmentation:
    * **MaX-DeepLab**: "MaX-DeepLab: End-to-End Panoptic Segmentation with Mask Transformers", CVPR, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2012.00759)][[PyTorch (conradry)](https://github.com/conradry/max-deeplab)]
    * **SIAin**: "An End-to-End Trainable Video Panoptic Segmentation Method usingTransformers", arXiv, 2021 (*SI Analytics, South Korea*). [[Paper](https://arxiv.org/abs/2110.04009)]
    * **VPS-Transformer**: "Time-Space Transformers for Video Panoptic Segmentation", WACV, 2022 (*Technical University of Cluj-Napoca, Romania*). [[Paper](https://openaccess.thecvf.com/content/WACV2022/html/Petrovai_Time-Space_Transformers_for_Video_Panoptic_Segmentation_WACV_2022_paper.html)]
    * **CMT-DeepLab**: "CMT-DeepLab: Clustering Mask Transformers for Panoptic Segmentation", CVPR, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2206.08948)]
    * **Panoptic-SegFormer**: "Panoptic SegFormer", CVPR, 2022 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2109.03814)][[PyTorch](https://github.com/zhiqi-li/Panoptic-SegFormer)]
    * **Mask2Former**: "Masked-attention Mask Transformer for Universal Image Segmentation", CVPR, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2112.01527)][[PyTorch](https://github.com/facebookresearch/Mask2Former)][[Website](https://bowenc0221.github.io/mask2former/)]
    * **kMaX-DeepLab**: "k-means Mask Transformer", ECCV, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2207.04044)][[Tensorflow](https://github.com/google-research/deeplab2)]
    * **Panoptic-PartFormer**: "Panoptic-PartFormer: Learning a Unified Model for Panoptic Part Segmentation", ECCV, 2022 (*Peking*). [[Paper](https://arxiv.org/abs/2204.04655)][[PyTorch](https://github.com/lxtGH/Panoptic-PartFormer)]
* Instance Segmentation:
    * **ISTR**: "ISTR: End-to-End Instance Segmentation with Transformers", arXiv, 2021 (*Xiamen University*). [[Paper](https://arxiv.org/abs/2105.00637)][[PyTorch](https://github.com/hujiecpp/ISTR)]
    * **Mask-Transfiner**: "Mask Transfiner for High-Quality Instance Segmentation", CVPR, 2022 (*ETHZ*). [[Paper](https://arxiv.org/abs/2111.13673)][[PyTorch](https://github.com/SysCV/transfiner)][[Website](https://www.vis.xyz/pub/transfiner/)]
    * **BoundaryFormer**: "Instance Segmentation With Mask-Supervised Polygonal Boundary Transformers", CVPR, 2022 (*UCSD*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Lazarow_Instance_Segmentation_With_Mask-Supervised_Polygonal_Boundary_Transformers_CVPR_2022_paper.html)]
    * **PPT**: "Parallel Pre-trained Transformers (PPT) for Synthetic Data-based Instance Segmentation", CVPRW, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2206.10845)]
    * **OSFormer**: "OSFormer: One-Stage Camouflaged Instance Segmentation with Transformers", ECCV, 2022 (*Huazhong University of Science and Technology*). [[Paper](https://arxiv.org/abs/2207.02255)][[PyTorch](https://github.com/PJLallen/OSFormer)]
    * **AISFormer**: "AISFormer: Amodal Instance Segmentation with Transformer", BMVC, 2022 (*University of Arkansas, Arkansas*). [[Paper](https://arxiv.org/abs/2210.06323)][[Code (in construction)](https://github.com/UARK-AICV/AISFormer)]
    * **TOIST**: "TOIST: Task Oriented Instance Segmentation Transformer with Noun-Pronoun Distillation", NeurIPS, 2022 (*Tsinghua University*). [[Paper](https://arxiv.org/abs/2210.10775)][[PyTorch](https://github.com/AIR-DISCOVER/TOIST)]
* Optical Flow:
    * **CRAFT**: "CRAFT: Cross-Attentional Flow Transformer for Robust Optical Flow", CVPR, 2022 (*A\*STAR, Singapore*). [[Paper](https://arxiv.org/abs/2203.16896)][[PyTorch](https://github.com/askerlee/craft)]
    * **KPA-Flow**: "Learning Optical Flow With Kernel Patch Attention", CVPR, 2022 (*Megvii*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Luo_Learning_Optical_Flow_With_Kernel_Patch_Attention_CVPR_2022_paper.html)][[PyTorch (in construction)](https://github.com/megvii-research/KPAFlow)]
    * **GMFlowNet**: "Global Matching with Overlapping Attention for Optical Flow Estimation", CVPR, 2022 (*Rutgers*). [[Paper](https://arxiv.org/abs/2203.11335)][[PyTorch](https://github.com/xiaofeng94/GMFlowNet)]
    * **FlowFormer**: "FlowFormer: A Transformer Architecture for Optical Flow", ECCV, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2203.16194)][[Website](https://drinkingcoder.github.io/publication/flowformer/)]
* Panoramic Semantic Segmentation:
    * **Trans4PASS**: "Bending Reality: Distortion-aware Transformers for Adapting to Panoramic Semantic Segmentation", CVPR, 2022 (*Karlsruhe Institute of Technology, Germany*). [[Paper](https://arxiv.org/abs/2203.01452)][[PyTorch](https://github.com/jamycheung/Trans4PASS)]
* X-Shot:
    * **CyCTR**: "Few-Shot Segmentation via Cycle-Consistent Transformer", NeurIPS, 2021 (*University of Technology Sydney*). [[Paper](https://arxiv.org/abs/2106.02320)]
    * **CATrans**: "CATrans: Context and Affinity Transformer for Few-Shot Segmentation", IJCAI, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2204.12817)]
    * **VAT**: "Cost Aggregation with 4D Convolutional Swin Transformer for Few-Shot Segmentation", ECCV, 2022 (*Korea University*). [[Paper](https://arxiv.org/abs/2207.10866)][[PyTorch](https://github.com/Seokju-Cho/Volumetric-Aggregation-Transformer)][[Website](https://seokju-cho.github.io/VAT/)]
    * **DCAMA**: "Dense Cross-Query-and-Support Attention Weighted Mask Aggregation for Few-Shot Segmentation", ECCV, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2207.08549)]
    * **AAFormer**: "Adaptive Agent Transformer for Few-Shot Segmentation", ECCV, 2022 (*USTC*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/1397_ECCV_2022_paper.php)]
    * **IPMT**: "Intermediate Prototype Mining Transformer for Few-Shot Semantic Segmentation", NeurIPS, 2022 (*Northwestern Polytechnical University*). [[Paper](https://arxiv.org/abs/2210.06780)][[PyTorch](https://github.com/LIUYUANWEI98/IPMT)]
    * **TAFT**: "Task-Adaptive Feature Transformer with Semantic Enrichment for Few-Shot Segmentation", arXiv, 2022 (*KAIST*). [[Paper](https://arxiv.org/abs/2202.06498)]
    * **MSANet**: "MSANet: Multi-Similarity and Attention Guidance for Boosting Few-Shot Segmentation", arXiv, 2022 (*AiV Research Group, Korea*). [[Paper](https://arxiv.org/abs/2206.09667)][[PyTorch](https://github.com/AIVResearch/MSANet)]
* X-Supervised:
    * **MCTformer**: "Multi-class Token Transformer for Weakly Supervised Semantic Segmentation", CVPR, 2022 (*The University of Western Australia*). [[Paper](https://arxiv.org/abs/2203.02891)][[Code (in construction)](https://github.com/xulianuwa/MCTformer)]
    * **AFA**: "Learning Affinity from Attention: End-to-End Weakly-Supervised Semantic Segmentation with Transformers", CVPR, 2022 (*Wuhan University*). [[Paper](https://arxiv.org/abs/2203.02664)][[PyTorch](https://github.com/rulixiang/afa)]
    * **HSG**: "Unsupervised Hierarchical Semantic Segmentation with Multiview Cosegmentation and Clustering Transformers", CVPR, 2022 (*Berkeley*). [[Paper](https://arxiv.org/abs/2204.11432)][[PyTorch](https://github.com/twke18/HSG)]
    * **?**: "Self-Supervised Pre-training of Vision Transformers for Dense Prediction Tasks", CVPRW, 2022 (*Université Paris-Saclay, France*). [[Paper](https://arxiv.org/abs/2205.15173)]
    * **SegSwap**: "Learning Co-segmentation by Segment Swapping for Retrieval and Discovery", CVPRW, 2022 (*École des Ponts ParisTech*). [[Paper](https://arxiv.org/abs/2110.15904)][[PyTorch](https://github.com/XiSHEN0220/SegSwap)][[Website](http://imagine.enpc.fr/~shenx/SegSwap/)]
    * **ViT-PCM**: "Max Pooling with Vision Transformers Reconciles Class and Shape in Weakly Supervised Semantic Segmentation", ECCV, 2022 (*Sapienza University, Italy*). [[Paper]()][[Tensorflow](https://github.com/deepplants/ViT-PCM)]
    * **TransFGU**: "TransFGU: A Top-down Approach to Fine-Grained Unsupervised Semantic Segmentation", ECCV, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2112.01515)][[PyTorch](https://github.com/damo-cv/TransFGU)]
    * **TransCAM**: "TransCAM: Transformer Attention-based CAM Refinement for Weakly Supervised Semantic Segmentation", arXiv, 2022 (*University of Toronto*). [[Paper](https://arxiv.org/abs/2203.07239)][[PyTorch](https://github.com/liruiwen/TransCAM)]
    * **WegFormer**: "WegFormer: Transformers for Weakly Supervised Semantic Segmentation", arXiv, 2022 (*Tongji University, China*). [[Paper](https://arxiv.org/abs/2203.08421)]
    * **MaskDistill**: "Discovering Object Masks with Transformers for Unsupervised Semantic Segmentation", arXiv, 2022 (*KU Leuven*). [[Paper](https://arxiv.org/abs/2206.06363)][[PyTorch](https://github.com/wvangansbeke/MaskDistill)]
    * **eX-ViT**: "eX-ViT: A Novel eXplainable Vision Transformer for Weakly Supervised Semantic Segmentation", arXiv, 2022 (*La Trobe University, Australia*). [[Paper](https://arxiv.org/abs/2207.05358)]
    * **TCC**: "Transformer-CNN Cohort: Semi-supervised Semantic Segmentation by the Best of Both Students", arXiv, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2209.02178)]
    * **SemFormer**: "SemFormer: Semantic Guided Activation Transformer for Weakly Supervised Semantic Segmentation", arXiv, 2022 (*Shenzhen University*). [[Paper](https://arxiv.org/abs/2210.14618)][[PyTorch](https://github.com/JLChen-C/SemFormer)]
* Cross-Domain:
    * **DAFormer**: "DAFormer: Improving Network Architectures and Training Strategies for Domain-Adaptive Semantic Segmentation", CVPR, 2022 (*ETHZ*). [[Paper](https://arxiv.org/abs/2111.14887)][[PyTorch](https://github.com/lhoyer/DAFormer)]
* Crack Detection:
    * **CrackFormer**: "CrackFormer: Transformer Network for Fine-Grained Crack Detection", ICCV, 2021 (*Nanjing University of Science and Technology*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021/html/Liu_CrackFormer_Transformer_Network_for_Fine-Grained_Crack_Detection_ICCV_2021_paper.html)]
* Camouflaged Object Detection:
    * **UGTR**: "Uncertainty-Guided Transformer Reasoning for Camouflaged Object Detection", ICCV, 2021 (*Group42, Abu Dhabi*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021/html/Yang_Uncertainty-Guided_Transformer_Reasoning_for_Camouflaged_Object_Detection_ICCV_2021_paper.html)][[PyTorch](https://github.com/fanyang587/UGTR)]
    * **COD**: "Boosting Camouflaged Object Detection with Dual-Task Interactive Transformer", ICPR, 2022 (*Anhui University, China*). [[Paper](https://arxiv.org/abs/2205.10579)][[Code (in construction)](https://github.com/liuzywen/COD)]
* Background Separation:
    * **TransBlast**: "TransBlast: Self-Supervised Learning Using Augmented Subspace With Transformer for Background/Foreground Separation", ICCVW, 2021 (*University of British Columbia*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021W/RSLCV/html/Osman_TransBlast_Self-Supervised_Learning_Using_Augmented_Subspace_With_Transformer_for_BackgroundForeground_ICCVW_2021_paper.html)]
* Scene Understanding:
    * **BANet**: "Transformer Meets Convolution: A Bilateral Awareness Net-work for Semantic Segmentation of Very Fine Resolution Urban Scene Images", arXiv, 2021 (*Wuhan University*). [[Paper](https://arxiv.org/abs/2106.12413)]
    * **Cerberus-Transformer**: "Cerberus Transformer: Joint Semantic, Affordance and Attribute Parsing", CVPR, 2022 (*Tsinghua University*). [[Paper](https://arxiv.org/abs/2111.12608)][[PyTorch](https://github.com/OPEN-AIR-SUN/Cerberus)]
    * **IRISformer**: "IRISformer: Dense Vision Transformers for Single-Image Inverse Rendering in Indoor Scenes", CVPR, 2022 (*UCSD*). [[Paper](https://arxiv.org/abs/2206.08423)][[Code (in construction)](https://github.com/ViLab-UCSD/IRISformer)]
    * **InvPT**: "Inverted Pyramid Multi-task Transformer for Dense Scene Understanding", ECCV, 2022 (*HKUST*). [[Paper](https://arxiv.org/abs/2203.07997)][[PyTorch](https://github.com/prismformore/InvPT)]
* 3D Segmentation:
    * **Stratified-Transformer**: "Stratified Transformer for 3D Point Cloud Segmentation", CVPR, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2203.14508)][[PyTorch](https://github.com/dvlab-research/Stratified-Transformer)]
    * **CodedVTR**: "CodedVTR: Codebook-based Sparse Voxel Transformer with Geometric Guidance", CVPR, 2022 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2203.09887)]
    * **M2F3D**: "M2F3D: Mask2Former for 3D Instance Segmentation", CVPRW, 2022 (*RWTH Aachen University, Germany*). [[Paper](https://jonasschult.github.io/Mask3D/assets/workshop_paper.pdf)][[Website](https://jonasschult.github.io/Mask3D/)]
* Multi-Task:
    * **MTFormer**: "MTFormer: Multi-task Learning via Transformer and Cross-Task Reasoning", ECCV, 2022 (*CUHK*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/1353_ECCV_2022_paper.php)]
    * **MQTransformer**: "Multi-Task Learning with Multi-Query Transformer for Dense Prediction", arXiv, 2022 (*Wuhan University*). [[Paper](https://arxiv.org/abs/2205.14354)]
* Forcasting:
    * **DiffAttn**: "Joint Forecasting of Panoptic Segmentations with Difference Attention", CVPR, 2022 (*UIUC*). [[Paper](https://arxiv.org/abs/2204.07157)][[Code (in construction)](https://github.com/cgraber/psf-diffattn)]
* LiDAR:
    * **HelixNet**: "Online Segmentation of LiDAR Sequences: Dataset and Algorithm", CVPRW, 2022 (*CNRS, France*). [[Paper](https://arxiv.org/abs/2206.08194)][[Website](https://romainloiseau.fr/helixnet/)][[PyTorch](https://github.com/romainloiseau/Helix4D)]
* Co-Segmentation:
    * **DINO-ViT-feature**: "Deep ViT Features as Dense Visual Descriptors", arXiv, 2022 (*Weizmann Institute of Science, Israel*). [[Paper](https://arxiv.org/abs/2112.05814)][[PyTorch](https://github.com/ShirAmir/dino-vit-features)][[Website](https://dino-vit-features.github.io/)]
* Top-Down Semantic Segmentation:
    * **Trans4Map**: "Trans4Map: Revisiting Holistic Top-down Mapping from Egocentric Images to Allocentric Semantics with Vision Transformers", arXiv, 2022 (*Karlsruhe Institute of Technology, Germany*). [[Paper](https://arxiv.org/abs/2207.06205)]
* Open-World/Vocabulary:
    * **ViL-Seg**: "Open-world Semantic Segmentation via Contrasting and Clustering Vision-Language Embedding", ECCV, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2207.08455)]
    * **Fusioner**: "Open-vocabulary Semantic Segmentation with Frozen Vision-Language Models", BMVC, 2022 (*Shanghai Jiao Tong University*). [[Paper](https://arxiv.org/abs/2210.15138)][[Website](https://yyh-rain-song.github.io/Fusioner_webpage/)]
    * **OVSeg**: "Open-Vocabulary Semantic Segmentation with Mask-adapted CLIP", arXiv, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2210.04150)][[Website](https://jeff-liangf.github.io/projects/ovseg/)]
* Applications:
    * **FloodTransformer**: "Transformer-based Flood Scene Segmentation for Developing Countries", NeurIPSW, 2022 (*BITS Pilani, India*). [[Paper](https://arxiv.org/abs/2210.04218)]

[[Back to Overview](#overview)]


## Video (High-level)
### Action Recognition
* RGB mainly
    * **Action Transformer**: "Video Action Transformer Network", CVPR, 2019 (*DeepMind*). [[Paper](https://arxiv.org/abs/1812.02707)][[Code (ppriyank)](https://github.com/ppriyank/Video-Action-Transformer-Network-Pytorch-)]
    * **ViViT-Ensemble**: "Towards Training Stronger Video Vision Transformers for EPIC-KITCHENS-100 Action Recognition", CVPRW, 2021 (*Alibaba*). [[Paper](https://arxiv.org/abs/2106.05058)]
    * **TimeSformer**: "Is Space-Time Attention All You Need for Video Understanding?", ICML, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2102.05095)][[PyTorch (lucidrains)](https://github.com/lucidrains/TimeSformer-pytorch)]
    * **MViT**: "Multiscale Vision Transformers", ICCV, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2104.11227)][[PyTorch](https://github.com/facebookresearch/SlowFast)]
    * **VidTr**: "VidTr: Video Transformer Without Convolutions", ICCV, 2021 (*Amazon*). [[Paper](https://arxiv.org/abs/2104.11746)][[PyTorch](https://github.com/amazon-research/gluonmm)]
    * **ViViT**: "ViViT: A Video Vision Transformer", ICCV, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2103.15691)][[PyTorch (rishikksh20)](https://github.com/rishikksh20/ViViT-pytorch)]
    * **VTN**: "Video Transformer Network", ICCVW, 2021 (*Theator*). [[Paper](https://arxiv.org/abs/2102.00719)][[PyTorch](https://github.com/bomri/SlowFast/tree/master/projects/vtn)]
    * **TokShift**: "Token Shift Transformer for Video Classification", ACMMM, 2021 (*CUHK*). [[Paper](https://arxiv.org/abs/2108.02432)][[PyTorch](https://github.com/VideoNetworks/TokShift-Transformer)]
    * **Motionformer**: "Keeping Your Eye on the Ball: Trajectory Attention in Video Transformers", NeurIPS, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2106.05392)][[PyTorch](https://github.com/facebookresearch/Motionformer)][[Website](https://facebookresearch.github.io/Motionformer/)]
    * **X-ViT**: "Space-time Mixing Attention for Video Transformer", NeurIPS, 2021 (*Samsung*). [[Paper](https://arxiv.org/abs/2106.05968)][[PyTorch](https://github.com/1adrianb/video-transformers)]
    * **SCT**: "Shifted Chunk Transformer for Spatio-Temporal Representational Learning", NeurIPS, 2021 (*Kuaishou*). [[Paper](https://arxiv.org/abs/2108.11575)]
    * **RSANet**: "Relational Self-Attention: What's Missing in Attention for Video Understanding", NeurIPS, 2021 (*POSTECH*). [[Paper](https://arxiv.org/abs/2111.01673)][[PyTorch](https://github.com/KimManjin/RSA)][[Website](http://cvlab.postech.ac.kr/research/RSA/)]
    * **STAM**: "An Image is Worth 16x16 Words, What is a Video Worth?", arXiv, 2021 (*Alibaba*). [[Paper](https://arxiv.org/abs/2103.13915)][[Code](https://github.com/Alibaba-MIIL/STAM)]
    * **GAT**: "Enhancing Transformer for Video Understanding Using Gated Multi-Level Attention and Temporal Adversarial Training", arXiv, 2021 (*Samsung*). [[Paper](https://arxiv.org/abs/2103.10043)]
    * **TokenLearner**: "TokenLearner: What Can 8 Learned Tokens Do for Images and Videos?", arXiv, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2106.11297)]
    * **VLF**: "VideoLightFormer: Lightweight Action Recognition using Transformers", arXiv, 2021 (*The University of Sheffield*). [[Paper](https://arxiv.org/abs/2107.00451)]
    * **UniFormer**: "UniFormer: Unified Transformer for Efficient Spatiotemporal Representation Learning", ICLR, 2022 (*CAS + SenstTime*). [[Paper](https://arxiv.org/abs/2201.04676)][[PyTorch](https://github.com/Sense-X/UniFormer)]
    * **Video-Swin**: "Video Swin Transformer", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2106.13230)][[PyTorch](https://github.com/SwinTransformer/Video-Swin-Transformer)]
    * **DirecFormer**: "DirecFormer: A Directed Attention in Transformer Approach to Robust Action Recognition", CVPR, 2022 (*University of Arkansas*). [[Paper](https://arxiv.org/abs/2203.10233)][[Code (in construction)](https://github.com/uark-cviu/DirecFormer)]
    * **DVT**: "Deformable Video Transformer", CVPR, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2203.16795)]
    * **MeMViT**: "MeMViT: Memory-Augmented Multiscale Vision Transformer for Efficient Long-Term Video Recognition", CVPR, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2201.08383)]
    * **MLP-3D**: "MLP-3D: A MLP-like 3D Architecture with Grouped Time Mixing", CVPR, 2022 (*JD*). [[Paper](https://arxiv.org/abs/2206.06292)][[PyTorch (in construction)](https://github.com/ZhaofanQiu/MLP-3D)]
    * **RViT**: "Recurring the Transformer for Video Action Recognition", CVPR, 2022 (*TCL Corporate Research, HK*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Yang_Recurring_the_Transformer_for_Video_Action_Recognition_CVPR_2022_paper.html)]
    * **SIFA**: "Stand-Alone Inter-Frame Attention in Video Models", CVPR, 2022 (*JD*). [[Paper](https://arxiv.org/abs/2206.06931)][[PyTorch](https://github.com/FuchenUSTC/SIFA)]
    * **MViTv2**: "MViTv2: Improved Multiscale Vision Transformers for Classification and Detection", CVPR, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2112.01526)][[PyTorch](https://github.com/facebookresearch/mvit)]
    * **MTV**: "Multiview Transformers for Video Recognition", CVPR, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2201.04288)][[Tensorflow](https://github.com/google-research/scenic/tree/main/scenic/projects/mtv)]
    * **ORViT**: "Object-Region Video Transformers", CVPR, 2022 (*Tel Aviv*). [[Paper](https://arxiv.org/abs/2110.06915)][[Website](https://roeiherz.github.io/ORViT/)]
    * **TIME**: "Time Is MattEr: Temporal Self-supervision for Video Transformers", ICML, 2022 (*KAIST*). [[Paper](https://arxiv.org/abs/2207.09067)][[PyTorch](https://github.com/alinlab/temporal-selfsupervision)]
    * **TPS**: "Spatiotemporal Self-attention Modeling with Temporal Patch Shift for Action Recognition", ECCV, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2207.13259)][[PyTorch](https://github.com/MartinXM/TPS)]
    * **DualFormer**: "DualFormer: Local-Global Stratified Transformer for Efficient Video Recognition", ECCV, 2022 (*Sea AI Lab*). [[Paper](https://arxiv.org/abs/2112.04674)][[PyTorch](https://github.com/sail-sg/dualformer)]
    * **STTS**: "Efficient Video Transformers with Spatial-Temporal Token Selection", ECCV, 2022 (*Fudan University*). [[Paper](https://arxiv.org/abs/2111.11591)][[PyTorch](https://github.com/wangjk666/STTS)]
    * **Turbo**: "Turbo Training with Token Dropout", BMVC, 2022 (*Oxford*). [[Paper](https://arxiv.org/abs/2210.04889)]
    * **MultiTrain**: "Multi-dataset Training of Transformers for Robust Action Recognition", NeurIPS, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2209.12362)][[Code (in construction)](https://github.com/JunweiLiang/MultiTrain)]
    * **AIA**: "Attention in Attention: Modeling Context Correlation for Efficient Video Classification", TCSVT, 2022 (*University of Science and Technology of China*). [[Paper](https://arxiv.org/abs/2204.09303)][[PyTorch](https://github.com/haoyanbin918/Attention-in-Attention)]
    * **MSCA**: "Vision Transformer with Cross-attention by Temporal Shift for Efficient Action Recognition", arXiv, 2022 (*Nagoya Institute of Technology*). [[Paper](https://arxiv.org/abs/2204.00452)]
    * **SViT**: "Bringing Image Scene Structure to Video via Frame-Clip Consistency of Object Tokens", arXiv, 2022 (*Tel Aviv*). [[Paper](https://arxiv.org/abs/2206.06346)][[Website](https://eladb3.github.io/SViT/)]
    * **VAST**: "Efficient Attention-free Video Shift Transformers", arXiv, 2022 (*Samsung*). [[Paper](https://arxiv.org/abs/2208.11108)]
    * **Video-MobileFormer**: "Video Mobile-Former: Video Recognition with Efficient Global Spatial-temporal Modeling", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2208.12257)]
    * **MAM<sup>2</sup>**: "It Takes Two: Masked Appearance-Motion Modeling for Self-supervised Video Transformer Pre-training", arXiv, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2210.05234)]
    * **?**: "Linear Video Transformer with Feature Fixation", arXiv, 2022 (*SenseTime*). [[Paper](https://arxiv.org/abs/2210.08164)]
* Depth:
    * **Trear**: "Trear: Transformer-based RGB-D Egocentric Action Recognition",  IEEE Transactions on Cognitive and Developmental Systems, 2021 (*Tianjing University*). [[Paper](https://ieeexplore.ieee.org/document/9312201)]
* Pose:
    * **ST-TR**: "Spatial Temporal Transformer Network for Skeleton-based Action Recognition", ICPRW, 2020 (*Polytechnic University of Milan*). [[Paper](https://arxiv.org/abs/2012.06399)]
    * **AcT**: "Action Transformer: A Self-Attention Model for Short-Time Human Action Recognition", arXiv, 2021 (*Politecnico di Torino, Italy*). [[Paper](https://arxiv.org/abs/2107.00606)][[Code (in construction)](https://github.com/FedericoAngelini/MPOSE2021_Dataset)]
    * **STAR**: "STAR: Sparse Transformer-based Action Recognition", arXiv, 2021 (*UCLA*). [[Paper](https://arxiv.org/abs/2107.07089)]
    * **GCsT**: "GCsT: Graph Convolutional Skeleton Transformer for Action Recognition", arXiv, 2021 (*CAS*). [[Paper](https://arxiv.org/abs/2109.02860)]
    * **GL-Transformer**: "Global-local Motion Transformer for Unsupervised Skeleton-based Action Learning", ECCV, 2022 (*Seoul National University*). [[Paper](https://arxiv.org/abs/2207.06101)][[PyTorch](https://github.com/Boeun-Kim/GL-Transformer)]
    * **?**: "Pose Uncertainty Aware Movement Synchrony Estimation via Spatial-Temporal Graph Transformer", International Conference on Multimodal Interaction (ICMI), 2022 (*University of Delaware*). [[Paper](https://arxiv.org/abs/2208.01161)]
    * **FG-STFormer**: "Focal and Global Spatial-Temporal Transformer for Skeleton-based Action Recognition", ACCV, 2022 (*Zhengzhou University*). [[Paper](https://arxiv.org/abs/2210.02693)]
    * **STTFormer**: "Spatio-Temporal Tuples Transformer for Skeleton-Based Action Recognition", arXiv, 2022 (*Xidian University*). [[Paper](https://arxiv.org/abs/2201.02849)][[Code (in construction)](https://github.com/heleiqiu/STTFormer)]
    * **ProFormer**: "ProFormer: Learning Data-efficient Representations of Body Movement with Prototype-based Feature Augmentation and Visual Transformers", arXiv, 2022 (*Karlsruhe Institute of Technology, Germany*). [[Paper](https://arxiv.org/abs/2202.11423)][[PyTorch](https://github.com/KPeng9510/ProFormer)]
    * **?**: "Spatial Transformer Network with Transfer Learning for Small-scale Fine-grained Skeleton-based Tai Chi Action Recognition", arXiv, 2022 (*Harbin Institute of Technology*). [[Paper](https://arxiv.org/abs/2206.15002)]
    * **STAN**: "Two-Stream Transformer Architecture for Long Video Understanding", arXiv, 2022 (*The University of Surrey, UK*). [[Paper](https://arxiv.org/abs/2208.01753)]
    * **STAR-Transformer**: "STAR-Transformer: A Spatio-temporal Cross Attention Transformer for Human Action Recognition", WACV, 2023 (*Keimyung University, Korea*). [[Paper](https://arxiv.org/abs/2210.07503)]
* Multi-modal:
    * **MBT**: "Attention Bottlenecks for Multimodal Fusion", NeurIPS, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2107.00135)]
    * **MM-ViT**: "MM-ViT: Multi-Modal Video Transformer for Compressed Video Action Recognition", WACV, 2022 (*OPPO*). [[Paper](https://arxiv.org/abs/2108.09322)]
    * **MMT-NCRC**: "Multimodal Transformer for Nursing Activity Recognition", CVPRW, 2022 (*UCF*). [[Paper](https://arxiv.org/abs/2204.04564)][[Code (in construction)](https://github.com/Momilijaz96/MMT_for_NCRC)]
    * **M&M**: "M&M Mix: A Multimodal Multiview Transformer Ensemble", CVPRW, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2206.09852)]
    * **VT-CE**: "Combined CNN Transformer Encoder for Enhanced Fine-grained Human Action Recognition", CVPRW, 2022 (*A\*STAR*). [[Paper](https://arxiv.org/abs/2208.01897)]
    * **Hi-TRS**: "Hierarchically Self-Supervised Transformer for Human Skeleton Representation Learning", ECCV, 2022 (*Rutgers*). [[Paper](https://arxiv.org/abs/2207.09644)][[PyTorch](https://github.com/yuxiaochen1103/Hi-TRS)]
    * **MVFT**: "Multi-View Fusion Transformer for Sensor-Based Human Activity Recognition", arXiv, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2202.12949)]
    * **MOV**: "Multimodal Open-Vocabulary Video Classification via Pre-Trained Vision and Language Models", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2207.07646)]
    * **MotionBERT**: "MotionBERT: Unified Pretraining for Human Motion Analysis", arXiv, 2022 (*Peking University*). [[Paper](https://arxiv.org/abs/2210.06551)][[Code (in construction)](https://github.com/Walter0807/MotionBERT)][[Website](https://motionbert.github.io/)]
    * **HIT**: "Holistic Interaction Transformer Network for Action Detection", WACV, 2023 (*NTHU*). [[Paper](https://arxiv.org/abs/2210.12686)][[Code (in construction)](https://github.com/joslefaure/HIT)]
* Group Activity:
    * **GroupFormer**: "GroupFormer: Group Activity Recognition with Clustered Spatial-Temporal Transformer", ICCV, 2021 (*Sensetime*). [[Paper](https://arxiv.org/abs/2108.12630)]
    * **?**: "Hunting Group Clues with Transformers for Social Group Activity Recognition", ECCV, 2022 (*Hitachi*). [[Paper](https://arxiv.org/abs/2207.05254)]

[[Back to Overview](#overview)]

### Action Detection/Localization
* **OadTR**: "OadTR: Online Action Detection with Transformers", ICCV, 2021 (*Huazhong University of Science and Technology*). [[Paper](https://arxiv.org/abs/2106.11149)][[PyTorch](https://github.com/wangxiang1230/OadTR)]
* **RTD-Net**: "Relaxed Transformer Decoders for Direct Action Proposal Generation", ICCV, 2021 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2102.01894)][[PyTorch](https://github.com/MCG-NJU/RTD-Action)]
* **FS-TAL**: "Few-Shot Temporal Action Localization with Query Adaptive Transformer", BMVC, 2021 (*University of Surrey, UK*). [[Paper](https://arxiv.org/abs/2110.10552)][[PyTorch](https://github.com/sauradip/fewshotQAT)]
* **LSTR**: "Long Short-Term Transformer for Online Action Detection", NeurIPS, 2021 (*Amazon*). [[Paper](https://arxiv.org/abs/2107.03377)][[PyTorch](https://github.com/amazon-research/long-short-term-transformer)][[Website](https://xumingze0308.github.io/projects/lstr/)]
* **ATAG**: "Augmented Transformer with Adaptive Graph for Temporal Action Proposal Generation", arXiv, 2021 (*Alibaba*). [[Paper](https://arxiv.org/abs/2103.16024)]
* **TAPG-Transformer**: "Temporal Action Proposal Generation with Transformers", arXiv, 2021 (*Harbin Institute of Technology*). [[Paper](https://arxiv.org/abs/2105.12043)]
* **TadTR**: "End-to-end Temporal Action Detection with Transformer", arXiv, 2021 (*Alibaba*). [[Paper](https://arxiv.org/abs/2106.10271)][[Code (in construction)](https://github.com/xlliu7/TadTR)]
* **Vidpress-Soccer**: "Feature Combination Meets Attention: Baidu Soccer Embeddings and Transformer based Temporal Detection", arXiv, 2021 (*Baidu*). [[Paper](https://arxiv.org/abs/2106.14447)][[GitHub](https://github.com/baidu-research/vidpress-sports)]
* **MS-TCT**: "MS-TCT: Multi-Scale Temporal ConvTransformer for Action Detection", CVPR, 2022 (*INRIA*). [[Paper](https://arxiv.org/abs/2112.03902)][[PyTorch](https://github.com/dairui01/MS-TCT)]
* **UGPT**: "Uncertainty-Guided Probabilistic Transformer for Complex Action Recognition", CVPR, 2022 (*Rensselaer Polytechnic Institute, NY*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Guo_Uncertainty-Guided_Probabilistic_Transformer_for_Complex_Action_Recognition_CVPR_2022_paper.html)]
* **TubeR**: "TubeR: Tube-Transformer for Action Detection", CVPR, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2104.00969)]
* **DDM-Net**: "Progressive Attention on Multi-Level Dense Difference Maps for Generic Event Boundary Detection", CVPR, 2022 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2112.04771)][[PyTorch](https://github.com/MCG-NJU/DDM)]
* **?**: "Dual-Stream Transformer for Generic Event Boundary Captioning", CVPRW, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2207.03038)][[PyTorch](https://github.com/GX77/Dual-Stream-Transformer-for-Generic-Event-Boundary-Captioning)]
* **?**: "Exploring Anchor-based Detection for Ego4D Natural Language Query", arXiv, 2022 (*Renmin University of China*). [[Paper](https://arxiv.org/abs/2208.05375)]
* **EAMAT**: "Entity-aware and Motion-aware Transformers for Language-driven Action Localization in Videos", IJCAI, 2022 (*Beijing Institute of Technology*). [[Paper](https://arxiv.org/abs/2205.05854)][[Code (in construction)](https://github.com/shuoyang129/EAMAT)]
* **STPT**: "An Efficient Spatio-Temporal Pyramid Transformer for Action Detection", ECCV, 2022 (*Monash University, Australia*). [[Paper](https://arxiv.org/abs/2207.10448)]
* **TeSTra**: "Real-time Online Video Detection with Temporal Smoothing Transformers", ECCV, 2022 (*UT Austin*). [[Paper](https://arxiv.org/abs/2209.09236)][[PyTorch](https://github.com/zhaoyue-zephyrus/TeSTra)]
* **TALLFormer**: "TALLFormer: Temporal Action Localization with Long-memory Transformer", ECCV, 2022 (*UNC*). [[Paper](https://arxiv.org/abs/2204.01680)][[PyTorch](https://github.com/klauscc/TALLFormer)]
* **?**: "Uncertainty-Based Spatial-Temporal Attention for Online Action Detection", ECCV, 2022 (*Rensselaer Polytechnic Institute, NY*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/2138_ECCV_2022_paper.php)]
* **ActionFormer**: "ActionFormer: Localizing Moments of Actions with Transformers", ECCV, 2022 (*UW-Madison*). [[Paper](https://arxiv.org/abs/2202.07925)][[PyTorch](https://github.com/happyharrycn/actionformer_release)]
* **CoOadTR**: "Continual Transformers: Redundancy-Free Attention for Online Inference", arXiv, 2022 (*Aarhus University, Denmark*). [[Paper](https://arxiv.org/abs/2201.06268)][[PyTorch](https://github.com/LukasHedegaard/continual-transformers)]
* **Temporal-Perceiver**: "Temporal Perceiver: A General Architecture for Arbitrary Boundary Detection", arXiv, 2022 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2203.00307)]
* **LocATe**: "LocATe: End-to-end Localization of Actions in 3D with Transformers", arXiv, 2022 (*Stanford*). [[Paper](https://arxiv.org/abs/2203.10719)]
* **HTNet**: "HTNet: Anchor-free Temporal Action Localization with Hierarchical Transformers", arXiv, 2022 (*Korea University*). [[Paper](https://arxiv.org/abs/2207.09662)]
* **AdaPerFormer**: "Adaptive Perception Transformer for Temporal Action Localization", arXiv, 2022 (*Tianjin University*). [[Paper](https://arxiv.org/abs/2208.11908)][[PyTorch](https://github.com/SouperO/AdaPerFormer)]
* **CWC-Trans**: "A Circular Window-based Cascade Transformer for Online Action Detection", arXiv, 2022 (*Meituan*). [[Paper](https://arxiv.org/abs/2208.14209)]

[[Back to Overview](#overview)]

### Action Prediction/Anticipation
* **AVT**: "Anticipative Video Transformer", ICCV, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2106.02036)][[PyTorch](https://github.com/facebookresearch/AVT)][[Website](https://facebookresearch.github.io/AVT/)]
* **HORST**: "Higher Order Recurrent Space-Time Transformer", arXiv, 2021 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2104.08665)][[PyTorch](https://github.com/CorcovadoMing/HORST)]
* **?**: "Action Forecasting with Feature-wise Self-Attention", arXiv, 2021 (*A\*STAR*). [[Paper](https://arxiv.org/abs/2107.08579)]
* **FUTR**: "Future Transformer for Long-term Action Anticipation", CVPR, 2022 (*POSTECH*). [[Paper](https://arxiv.org/abs/2205.14022)]
* **TTPP**: "TTPP: Temporal Transformer with Progressive Prediction for Efficient Action Anticipation", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2003.03530)]
* **VPTR**: "VPTR: Efficient Transformers for Video Prediction", ICPR, 2022 (*Polytechnique Montreal, Canada*). [[Paper](https://arxiv.org/abs/2203.15836)][[PyTorch](https://github.com/XiYe20/VPTR)]
* **Earthformer**: "Earthformer: Exploring Space-Time Transformers for Earth System Forecasting", arXiv, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2207.05833)]
* **AFFT**: "Anticipative Feature Fusion Transformer for Multi-Modal Action Anticipation", WACV, 2023 (*Karlsruhe Institute of Technology, Germany*). [[Paper](https://arxiv.org/abs/2210.12649)][[Code (in construction)](https://github.com/zeyun-zhong/AFFT)]
* **GliTr**: "GliTr: Glimpse Transformers with Spatiotemporal Consistency for Online Action Prediction", WACV, 2023 (*McGill University, Canada*). [[Paper](https://arxiv.org/abs/2210.13605)]

[[Back to Overview](#overview)]

### Video Object Segmentation
* **GC**: "Fast Video Object Segmentation using the Global Context Module", ECCV, 2020 (*Tencent*). [[Paper](https://arxiv.org/abs/2001.11243)]
* **SSTVOS**: "SSTVOS: Sparse Spatiotemporal Transformers for Video Object Segmentation", CVPR, 2021 (*Modiface*). [[Paper](https://arxiv.org/abs/2101.08833)][[Code (in construction)](https://github.com/dukebw/SSTVOS)]
* **JOINT**: "Joint Inductive and Transductive Learning for Video Object Segmentation", ICCV, 2021 (*University of Science and Technology of China*). [[Paper](https://arxiv.org/abs/2108.03679)][[PyTorch](https://github.com/maoyunyao/JOINT)]
* **AOT**: "Associating Objects with Transformers for Video Object Segmentation", NeurIPS, 2021 (*University of Technology Sydney*). [[Paper](https://arxiv.org/abs/2106.02638)][[PyTorch (yoxu515)](https://github.com/yoxu515/aot-benchmark)][[Code (in construction)](https://github.com/z-x-yang/AOT)]
* **TransVOS**: "TransVOS: Video Object Segmentation with Transformers", arXiv, 2021 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2106.00588)]
* **SITVOS**: "Siamese Network with Interactive Transformer for Video Object Segmentation", AAAI, 2022 (*JD*). [[Paper](https://arxiv.org/abs/2112.13983)] 
* **MTTR**: "End-to-End Referring Video Object Segmentation with Multimodal Transformers", CVPR, 2022 (*Technion - Israel Institute of Technology*). [[Paper](https://arxiv.org/abs/2111.14821)][[PyTorch](https://github.com/mttr2021/MTTR)]
* **HODOR**: "Differentiable Soft-Masked Attention", CVPRW, 2022 (*RWTH Aachen University, Germany*). [[Paper](https://arxiv.org/abs/2206.00182)]
* **BATMAN**: "BATMAN: Bilateral Attention Transformer in Motion-Appearance Neighboring Space for Video Object Segmentation", ECCV, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2208.01159)]
* **AOT**: "Associating Objects with Scalable Transformers for Video Object Segmentation", arXiv, 2022 (*University of Technology Sydney*). [[Paper](https://arxiv.org/abs/2203.11442)][[Code (in construction)](https://github.com/z-x-yang/AOT)]

[[Back to Overview](#overview)]

### Video Instance Segmentation
* **VisTR**: "End-to-End Video Instance Segmentation with Transformers", CVPR, 2021 (*Meituan*). [[Paper](https://arxiv.org/abs/2011.14503)][[PyTorch](https://github.com/Epiphqny/VisTR)]
* **IFC**: "Video Instance Segmentation using Inter-Frame Communication Transformers", NeurIPS, 2021 (*Yonsei University*). [[Paper](https://arxiv.org/abs/2106.03299)][[PyTorch](https://github.com/sukjunhwang/IFC)]
* **Deformable-VisTR**: "Deformable VisTR: Spatio temporal deformable attention for video instance segmentation", ICASSP, 2022 (*University at Buffalo*). [[Paper](https://arxiv.org/abs/2203.06318)][[Code (in construction)](https://github.com/skrya/DefVIS)]
* **TeViT**: "Temporally Efficient Vision Transformer for Video Instance Segmentation", CVPR, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2204.08412)][[PyTorch](https://github.com/hustvl/TeViT)]
* **GMP-VIS**: "A Graph Matching Perspective With Transformers on Video Instance Segmentation", CVPR, 2022 (*Shandong University*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Qin_A_Graph_Matching_Perspective_With_Transformers_on_Video_Instance_Segmentation_CVPR_2022_paper.html)]
* **VMT**: "Video Mask Transfiner for High-Quality Video Instance Segmentation", ECCV, 2022 (*ETHZ*). [[Paper](https://arxiv.org/abs/2207.14012)][[GitHub](https://github.com/SysCV/vmt)][[Website](https://www.vis.xyz/pub/vmt/)]
* **SeqFormer**: "SeqFormer: Sequential Transformer for Video Instance Segmentation", ECCV, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2112.08275)][[PyTorch](https://github.com/wjf5203/SeqFormer)]
* **MS-STS**: "Video Instance Segmentation via Multi-scale Spatio-temporal Split Attention Transformer", ECCV, 2022 (*MBZUAI*). [[Paper](https://arxiv.org/abs/2203.13253)][[PyTorch](https://github.com/OmkarThawakar/MSSTS-VIS)]
* **VITA**: "VITA: Video Instance Segmentation via Object Token Association", arXiv, 2022 (*Yonsei University*). [[Paper](https://arxiv.org/abs/2206.04403)][[Code (in construction)](https://github.com/sukjunhwang/VITA)]
* **IFR**: "Consistent Video Instance Segmentation with Inter-Frame Recurrent Attention", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.07011)]
* **DeVIS**: "DeVIS: Making Deformable Transformers Work for Video Instance Segmentation", arXiv, 2022 (*TUM*). [[Paper](https://arxiv.org/abs/2207.11103)][[PyTorch](https://github.com/acaelles97/DeVIS)]
* **MinVIS**: "MinVIS: A Minimal Video Instance Segmentation Framework without Video-based Training", arXiv, 2022 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2208.02245)][[PyTorch](https://github.com/NVlabs/MinVIS)]
* **InstanceFormer**: "InstanceFormer: An Online Video Instance Segmentation Framework", arXiv, 2022 (*Ludwig Maximilian University of Munich*). [[Paper](https://arxiv.org/abs/2208.10547)][[Code (in construction)](https://github.com/rajatkoner08/InstanceFormer)]

[[Back to Overview](#overview)]

### Other Video Tasks
* Action Segmentation
    * **ASFormer**: "ASFormer: Transformer for Action Segmentation", BMVC, 2021 (*Peking University*). [[Paper](https://arxiv.org/abs/2110.08568)][[PyTorch](https://github.com/ChinaYi/ASFormer)]
    * **Bridge-Prompt**: "Bridge-Prompt: Towards Ordinal Action Understanding in Instructional Videos", CVPR, 2022 (*Tsinghua University*). [[Paper](https://arxiv.org/abs/2203.14104)][[PyTorch](https://github.com/ttlmh/Bridge-Prompt)]
    * **SC-Transformer++**: "SC-Transformer++: Structured Context Transformer for Generic Event Boundary Detection", CVPRW, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2206.12634)][[Code (in construction)](https://github.com/lufficc/SC-Transformer)]
    * **LocVTP**: "LocVTP: Video-Text Pre-training for Temporal Localization", ECCV, 2022 (*Peking University*). [[Paper](https://arxiv.org/abs/2207.10362)][[PyTorch](https://github.com/mengcaopku/LocVTP)]
    * **UVAST**: "Unified Fully and Timestamp Supervised Temporal Action Segmentation via Sequence to Sequence Translation", ECCV, 2022 (*Bosch*). [[Paper](https://arxiv.org/abs/2209.00638)][[PyTorch](https://github.com/boschresearch/UVAST)]
    * **?**: "Transformers in Action: Weakly Supervised Action Segmentation", arXiv, 2022 (*TUM*). [[Paper](https://arxiv.org/abs/2201.05675)]
    * **CETNet**: "Cross-Enhancement Transformer for Action Segmentation", arXiv, 2022 (*Shijiazhuang Tiedao University*). [[Paper](https://arxiv.org/abs/2205.09445)]
    * **EUT**: "Efficient U-Transformer with Boundary-Aware Loss for Action Segmentation", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2205.13425)]
    * **SC-Transformer**: "Structured Context Transformer for Generic Event Boundary Detection", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2206.02985)]
* Video X Segmentation:
    * **STT**: "Video Semantic Segmentation via Sparse Temporal Transformer", MM, 2021 (*Shanghai Jiao Tong*). [[Paper](https://dl.acm.org/doi/abs/10.1145/3474085.3475409)]
    * **CFFM**: "Coarse-to-Fine Feature Mining for Video Semantic Segmentation", CVPR, 2022 (*ETH Zurich*). [[Paper](https://arxiv.org/abs/2204.03330)][[PyTorch](https://github.com/GuoleiSun/VSS-CFFM)]
    * **TF-DL**: "TubeFormer-DeepLab: Video Mask Transformer", CVPR, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2205.15361)]
    * **MRCFA**: "Mining Relations among Cross-Frame Affinities for Video Semantic Segmentation", ECCV, 2022 (*ETH Zurich*). [[Paper](https://arxiv.org/pdf/2207.10436)][[PyTorch](https://github.com/GuoleiSun/VSS-MRCFA)]   
    * **PolyphonicFormer**: "PolyphonicFormer: Unified Query Learning for Depth-aware Video Panoptic Segmentation, ECCV, 2022 (*Wuhan University*). [[Paper](https://arxiv.org/abs/2112.02582)][[Code (in construction)](https://github.com/HarborYuan/PolyphonicFormer)]
    * **?**: "Time-Space Transformers for Video Panoptic Segmentation", arXiv, 2022 (*Technical University of Cluj-Napoca, Romania*). [[Paper](https://arxiv.org/abs/2210.03546)]
* Video Object Detection:
    * **TransVOD**: "End-to-End Video Object Detection with Spatial-Temporal Transformers", arXiv, 2021 (*Shanghai Jiao Tong + SenseTime*). [[Paper](https://arxiv.org/abs/2105.10920)][[Code (in construction)](https://github.com/SJTU-LuHe/TransVOD)]
    * **MODETR**: "MODETR: Moving Object Detection with Transformers", arXiv, 2021 (*Valeo, Egypt*). [[Paper](https://arxiv.org/abs/2106.11422)]
    * **ST-MTL**: "Spatio-Temporal Multi-Task Learning Transformer for Joint Moving Object Detection and Segmentation", arXiv, 2021 (*Valeo, Egypt*). [[Paper](https://arxiv.org/abs/2106.11401)]
    * **ST-DETR**: "ST-DETR: Spatio-Temporal Object Traces Attention Detection Transformer", arXiv, 2021 (*Valeo, Egypt*). [[Paper](https://arxiv.org/abs/2107.05887)]
    * **PTSEFormer**: "PTSEFormer: Progressive Temporal-Spatial Enhanced TransFormer Towards Video Object Detection", ECCV, 2022 (*Shanghai Jiao Tong University*). [[Paper](https://arxiv.org/abs/2209.02242)][[PyTorch](https://github.com/Hon-Wong/PTSEFormer)]
    * **TransVOD**: "TransVOD: End-to-end Video Object Detection with Spatial-Temporal Transformers", arXiv, 2022 (*Shanghai Jiao Tong + SenseTime*). [[Paper](https://arxiv.org/abs/2201.05047)]
    * **?**: "Learning Future Object Prediction with a Spatiotemporal Detection Transformer", arXiv, 2022 (*Zenseact, Sweden*). [[Paper](https://arxiv.org/abs/2204.10321)]
* Dense Video Tasks (Detection + Segmentation):
    * **TDViT**: "TDViT: Temporal Dilated Video Transformer for Dense Video Tasks", ECCV, 2022 (*Queen's University Belfast, UK*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/5559_ECCV_2022_paper.php)][[Code (in construction)](https://github.com/guanxiongsun/TDViT)]
* Video Retrieval
    * **SVRTN**: "Self-supervised Video Retrieval Transformer Network", arXiv, 2021 (*Alibaba*). [[Paper](https://arxiv.org/abs/2104.07993)]
* Video Hashing
    * **BTH**: "Self-Supervised Video Hashing via Bidirectional Transformers", CVPR, 2021 (*Tsinghua*). [[Paper](https://openaccess.thecvf.com/content/CVPR2021/html/Li_Self-Supervised_Video_Hashing_via_Bidirectional_Transformers_CVPR_2021_paper.html)][[PyTorch](https://github.com/Lily1994/BTH)]
* Video-Language:
    * **ActionCLIP**: "ActionCLIP: A New Paradigm for Video Action Recognition", arXiv, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2109.08472)][[PyTorch](https://github.com/sallymmx/ActionCLIP)]
    * **?**: "Prompting Visual-Language Models for Efficient Video Understanding", ECCV, 2022 (*Shanghai Jiao Tong + Oxford*). [[Paper](https://arxiv.org/abs/2112.04478)][[PyTorch](https://github.com/ju-chen/Efficient-Prompt)][[Website](https://ju-chen.github.io/efficient-prompt/)]
    * **X-CLIP**: "Expanding Language-Image Pretrained Models for General Video Recognition", ECCV, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2208.02816)][[PyTorch](https://github.com/microsoft/VideoX/tree/master/X-CLIP)]
    * **EVL**: "Frozen CLIP Models are Efficient Video Learners", ECCV, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2208.03550)][[PyTorch (in construction)](https://github.com/OpenGVLab/efficient-video-recognition)]
    * **STALE**: "Zero-Shot Temporal Action Detection via Vision-Language Prompting", ECCV, 2022 (*University of Surrey, UK*). [[Paper](https://arxiv.org/abs/2207.08184)][[Code (in construction)](https://github.com/sauradip/STALE)]
    * **FineCo**: "Contrastive Video-Language Learning with Fine-grained Frame Sampling", AACL, 2022 (*ICL, UK*). [[Paper](https://arxiv.org/abs/2210.05039)]
    * **MovieCLIP**: "MovieCLIP: Visual Scene Recognition in Movies", WACV, 2023 (*USC*). [[Paper](https://arxiv.org/abs/2210.11065)][[Website](https://sail.usc.edu/~mica/MovieCLIP/)]
* X-supervised Learning:
    * **LSTCL**: "Long-Short Temporal Contrastive Learning of Video Transformers", CVPR, 2022 (*Facebook*). [[Paper](https://arxiv.org/abs/2106.09212)]
    * **SVT**: "Self-supervised Video Transformer", CVPR, 2022 (*Stony Brook*). [[Paper](https://arxiv.org/abs/2112.01514)][[PyTorch](https://github.com/kahnchana/svt)][[Website](https://kahnchana.github.io/svt/)]
    * **BEVT**: "BEVT: BERT Pretraining of Video Transformers", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2112.01529)][[PyTorch](https://github.com/xyzforever/BEVT)]
    * **SCVRL**: "SCVRL: Shuffled Contrastive Video Representation Learning", CVPRW, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2205.11710)]
    * **VideoMAE**: "VideoMAE: Masked Autoencoders are Data-Efficient Learners for Self-Supervised Video Pre-Training", CVPRW, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2203.12602)][[Code (in construction)](https://github.com/MCG-NJU/VideoMAE)]
    * **VIMPAC**: "VIMPAC: Video Pre-Training via Masked Token Prediction and Contrastive Learning", CVPRW, 2022 (*UNC*). [[Paper](https://arxiv.org/abs/2106.11250)][[PyTorch](https://github.com/airsplay/vimpac)]
    * **?**: "Static and Dynamic Concepts for Self-supervised Video Representation Learning", ECCV, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2207.12795)]
    * **MAE**: "Masked Autoencoders As Spatiotemporal Learners", arXiv, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2205.09113)]
    * **OmniMAE**: "OmniMAE: Single Model Masked Pretraining on Images and Videos", arXiv, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2206.08356)][[PyTorch](https://github.com/facebookresearch/omnivore)]
    * **MaskViT**: "MaskViT: Masked Visual Pre-Training for Video Prediction", arXiv, 2022 (*Stanford*). [[Paper](https://arxiv.org/abs/2206.11894)][[Website](https://maskedvit.github.io/)]
    * **?**: "On the Surprising Effectiveness of Transformers in Low-Labeled Video Recognition", arXiv, 2022 (*Georgia Tech*). [[Paper](https://arxiv.org/abs/2209.07474)]
* X-shot:
    * **ResT**: "Cross-modal Representation Learning for Zero-shot Action Recognition", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2205.01657)]
    * **ViSET**: "Zero-Shot Action Recognition with Transformer-based Video Semantic Embedding", arXiv, 2022 (*University of South FLorida*). [[Paper](https://arxiv.org/abs/2203.05156)]
    * **REST**: "REST: REtrieve & Self-Train for generative action recognition", arXiv, 2022 (*Samsung*). [[Paper](https://arxiv.org/abs/2209.15000)]
* Anomaly Detection:
    * **CT-D2GAN**: "Convolutional Transformer based Dual Discriminator Generative Adversarial Networks for Video Anomaly Detection", ACMMM, 2021 (*NEC*). [[Paper](https://arxiv.org/abs/2107.13720)]
    * **ADTR**: "ADTR: Anomaly Detection Transformer with Feature Reconstruction", International Conference on Neural Information Processing (ICONIP), 2022 (*Shanghai Jiao Tong University*). [[Paper](https://arxiv.org/abs/2209.01816)]
    * **SSMCTB**: "Self-Supervised Masked Convolutional Transformer Block for Anomaly Detection", arXiv, 2022 (*UCF*). [[Paper](https://arxiv.org/abs/2209.12148)][[Code (in construction)](https://github.com/ristea/ssmctb)]
* Relation Detection:
    * **VidVRD**: "Video Relation Detection via Tracklet based Visual Transformer", ACMMMW, 2021 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2108.08669)][[PyTorch](https://github.com/Dawn-LX/VidVRD-tracklets)]
    * **VRDFormer**: "VRDFormer: End-to-End Video Visual Relation Detection With Transformers", CVPR, 2022 (*Renmin University of China*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Zheng_VRDFormer_End-to-End_Video_Visual_Relation_Detection_With_Transformers_CVPR_2022_paper.html)][[Code (in construction)](https://github.com/zhengsipeng/VRDFormer_VRD)]
    * **VidSGG-BIG**: "Classification-Then-Grounding: Reformulating Video Scene Graphs as Temporal Bipartite Graphs", CVPR, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2112.04222)][[PyTorch](https://github.com/Dawn-LX/VidSGG-BIG)]
* Saliency Prediction:
    * **STSANet**: "Spatio-Temporal Self-Attention Network for Video Saliency Prediction", arXiv, 2021 (*Shanghai University*). [[Paper](https://arxiv.org/abs/2108.10696)]
    * **UFO**: "A Unified Transformer Framework for Group-based Segmentation: Co-Segmentation, Co-Saliency Detection and Video Salient Object Detection", arXiv, 2022 (*South China University of Technology*). [[Paper](https://arxiv.org/abs/2203.04708)][[PyTorch](https://github.com/suyukun666/UFO)]
* Video Inpainting Detection:
    * **FAST**: "Frequency-Aware Spatiotemporal Transformers for Video Inpainting Detection", ICCV, 2021 (*Tsinghua University*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021/html/Yu_Frequency-Aware_Spatiotemporal_Transformers_for_Video_Inpainting_Detection_ICCV_2021_paper.html)]
* Driver Activity:
    * **TransDARC**: "TransDARC: Transformer-based Driver Activity Recognition with Latent Space Feature Calibration", arXiv, 2022 (*Karlsruhe Institute of Technology, Germany*). [[Paper](https://arxiv.org/abs/2203.00927)]
    * **?**: "Applying Spatiotemporal Attention to Identify Distracted and Drowsy Driving with Vision Transformers", arXiv, 2022 (*Jericho High School, NY*). [[Paper](https://arxiv.org/abs/2207.12148)]
    * **ViT-DD**: "Multi-Task Vision Transformer for Semi-Supervised Driver Distraction Detection", arXiv, 2022 (*Purdue*). [[Paper](https://arxiv.org/abs/2209.09178)][[PyTorch (in construction)](https://github.com/PurdueDigitalTwin/ViT-DD)]
* Video Alignment:
    * **DGWT**: "Dynamic Graph Warping Transformer for Video Alignment", BMVC, 2021 (*University of New South Wales, Australia*). [[Paper](https://www.bmvc2021-virtualconference.com/assets/papers/0993.pdf)]
* Sport-related:
    * **Skating-Mixer**: "Skating-Mixer: Multimodal MLP for Scoring Figure Skating", arXiv, 2022 (*Southern University of Science and Technology*). [[Paper](https://arxiv.org/abs/2203.03990)]
* Action Counting:
    * **TransRAC**: "TransRAC: Encoding Multi-scale Temporal Correlation with Transformers for Repetitive Action Counting", CVPR, 2022 (*ShanghaiTech*). [[Paper](https://arxiv.org/abs/2204.01018)][[PyTorch](https://github.com/SvipRepetitionCounting/TransRAC)][[Website](https://svip-lab.github.io/dataset/RepCount_dataset.html)]
* Action Quality Assessment:
    * **?**: "Action Quality Assessment with Temporal Parsing Transformer", ECCV, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2207.09270)]
    * **?**: "Action Quality Assessment using Transformers", arXiv, 2022 (*USC*). [[Paper](https://arxiv.org/abs/2207.12318)]
* Human Interaction:
    * **IGFormer**: "IGFormer: Interaction Graph Transformer for Skeleton-based Human Interaction Recognition", ECCV, 2022 (*The University of Melbourne*). [[Paper](https://arxiv.org/abs/2207.12100)]
* Domain Adaptation:
    * **UDAVT**: "Unsupervised Domain Adaptation for Video Transformers in Action Recognition", ICPR, 2022 (*University of Trento*). [[Paper](https://arxiv.org/abs/2207.12842)][[Code (in construction)](https://github.com/vturrisi/UDAVT)]
* Multi-Camera Editing:
    * **TC-Transformer**: "Temporal and Contextual Transformer for Multi-Camera Editing of TV Shows", ECCVW, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2210.08737)]

[[Back to Overview](#overview)]


## Multi-Modality
### Visual Captioning
* **Masked Transformers**: "End-to-End Dense Video Captioning with Masked Transformer", CVPR, 2018 (*UMich + Salesforce*). [[Paper](https://openaccess.thecvf.com/content_cvpr_2018/html/Zhou_End-to-End_Dense_Video_CVPR_2018_paper.html)][[PyTorch](https://github.com/salesforce/densecap)]
* **ETA-Transformer**: "Entangled Transformer for Image Captioning", ICCV, 2019 (*UTS*). [[Paper](https://openaccess.thecvf.com/content_ICCV_2019/html/Li_Entangled_Transformer_for_Image_Captioning_ICCV_2019_paper.html)]
* **M2-Transformer**: "Meshed-Memory Transformer for Image Captioning", CVPR, 2020 (*UniMoRE*). [[Paper](https://arxiv.org/abs/1912.08226)][[PyTorch](https://github.com/aimagelab/meshed-memory-transformer)] 
* **BMT**: "A Better Use of Audio-Visual Cues: Dense Video Captioning with Bi-modal Transformer", BMVC, 2020 (*Tampere University, Finland*). [[Paper](https://arxiv.org/abs/2005.08271)][[PyTorch](https://github.com/v-iashin/bmt)][[Website](https://iashin.ai/bmt)]
* **?**: "Optimizing Latency for Online Video Captioning Using Audio-Visual Transformers", Interspeech, 2021 (*MERL*). [[Paper](https://arxiv.org/abs/2108.02147)]
* **MCCFormers**: "Describing and Localizing Multiple Changes with Transformers", ICCV, 2021 (*AIST*). [[Paper](https://arxiv.org/abs/2103.14146)][[Website](https://cvpaperchallenge.github.io/Describing-and-Localizing-Multiple-Change-with-Transformers/)]
* **SATIC**: "Semi-Autoregressive Transformer for Image Captioning", ICCVW, 2021 (*Hefei University of Technology*). [[Paper](https://arxiv.org/abs/2106.09436)][[PyTorch](https://github.com/YuanEZhou/satic)]
* **DGCN**: "Dual Graph Convolutional Networks with Transformer and Curriculum Learning for Image Captioning", ACMMM, 2021 (*Wuhan University*). [[Paper](https://arxiv.org/abs/2108.02366)]
* **CPTR**: "CPTR: Full Transformer Network for Image Captioning", arXiv, 2021 (*CAS*). [[Paper](https://arxiv.org/abs/2101.10804)] 
* **ReFormer**: "ReFormer: The Relational Transformer for Image Captioning", arXiv, 2021 (*Stony Brook University*). [[Paper](https://arxiv.org/abs/2107.14178)]
* **LAViTeR**: "LAViTeR: Learning Aligned Visual and Textual Representations Assisted by Image and Caption Generation", arXiv, 2021 (*University at Buffalo*). [[Paper](https://arxiv.org/abs/2109.04993)]
* **LATGeO**: "Label-Attention Transformer with Geometrically Coherent Objects for Image Captioning", arXiv, 2021 (*Gwangju Institute of Science and Technology*). [[Paper](https://arxiv.org/abs/2109.07799)]
* **GEVST**: "Geometry-Entangled Visual Semantic Transformer for Image Captioning", arXiv, 2021 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2109.14137)]
* **GAT**: "Geometry Attention Transformer with Position-aware LSTMs for Image Captioning", arXiv, 2021 (*University of Electronic Science and Technology of China*). [[Paper](https://arxiv.org/abs/2110.00335)]
* **PureT**: "End-to-End Transformer Based Model for Image Captioning", AAAI, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2203.15350)]
* **VisualGPT**: "VisualGPT: Data-efficient Adaptation of Pretrained Language Models for Image Captioning", CVPR, 2022 (*KAUST*). [[Paper](https://arxiv.org/abs/2102.10407)][[PyTorch](https://github.com/Vision-CAIR/VisualGPT)]
* **ViTCAP**: "Injecting Semantic Concepts into End-to-End Image Captioning", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2112.05230)]
* **CLIP-Event**: "CLIP-Event: Connecting Text and Images with Event Structures", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2201.05078)][[PyTorch](https://github.com/limanling/clip-event)]
* **CLIP4IDC**: "CLIP4IDC: CLIP for Image Difference Captioning", CVPRW, 2022 (*Aalto University, Finland*). [[Paper](https://arxiv.org/abs/2206.00629)][[Code (in construction)](https://github.com/sushizixin/CLIP4IDC)]
* **?**: "A Dual-Attentive Approach to Style-Based Image Captioning Using a CNN-Transformer Model", CVPRW, 2022 (*The University of the West Indies, Jamaica*). [[Paper](https://drive.google.com/file/d/1QYq69dBFMBKHYDUolZqPaermiFz67k77/view)]
* **SpaCap3D**: "Spatiality-guided Transformer for 3D Dense Captioning on Point Clouds", IJCAI, 2022 (*University of Sydney*). [[Paper](https://arxiv.org/abs/2204.10688)][[Code (in construction)](https://github.com/heng-hw/SpaCap3D)][[Website](https://spacap3d.github.io/)]
* **RA-Transformer**: "Retrieval-Augmented Transformer for Image Captioning", International Conference on Content-based Multimedia Indexing (CMBI), 2022 (*University of Modena and Reggio Emilia, Italy*). [[Paper](https://arxiv.org/abs/2207.13162)]
* **VGCL**: "Video-Guided Curriculum Learning for Spoken Video Grounding", ACMMM, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2209.00277)][[PyTorch](https://github.com/marmot-xy/Spoken-Video-Grounding)]
* **GRIT**: "GRIT: Faster and Better Image captioning Transformer Using Dual Visual Features", ECCV, 2022 (*Tohoku University + RIKEN AIP*). [[Paper](https://arxiv.org/abs/2207.09666)][[PyTorch](https://github.com/davidnvq/grit)]
* **?**: "Object-Centric Unsupervised Image Captioning", ECCV, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2112.00969)][[PyTorch](https://github.com/zihangm/obj-centric-unsup-caption)]
* **UEDVC**: "Unifying Event Detection and Captioning as Sequence Generation via Pre-Training", ECCV, 2022 (*Renmin University of China*). [[Paper](https://arxiv.org/abs/2207.08625)][[PyTorch](https://github.com/QiQAng/UEDVC)]
* **TIger**: "Explicit Image Caption Editing", ECCV, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2207.09625)][[Code](https://github.com/baaaad/ECE)]
* **CVLNM**: "Learning to Collocate Visual-Linguistic Neural Modules for Image Captioning", IJCV, 2022 (*Southeast University, China*). [[Paper](https://arxiv.org/abs/2210.01338)][[PyTorch](https://github.com/GCYZSL/CVLMN)]
* **ViNTER**: "ViNTER: Image Narrative Generation with Emotion-Arc-Aware Transformer", arXiv, 2022 (*The University of Tokyo*). [[Paper](https://arxiv.org/abs/2202.07305)]
* **D2**: "Dual-Level Decoupled Transformer for Video Captioning", arXiv, 2022 (*Northwestern Polytechnical University, China*). [[Paper](https://arxiv.org/abs/2205.03039)]
* **VaT**: "Variational Transformer: A Framework Beyond the Trade-off between Accuracy and Diversity for Image Captioning", arXiv, 2022 (*Tongji University*). [[Paper](https://arxiv.org/abs/2205.14458)]
* **SCST-GEG**: "Distincive Image Captioning via CLIP Guided Group Optimization", arXiv, 2022 (*McGill University*). [[Paper](https://arxiv.org/abs/2208.04254)]
* **VASTA**: "Diverse Video Captioning by Adaptive Spatio-temporal Attention", arXiv, 2022 (*University of Tubingen, Germany*). [[Paper](https://arxiv.org/abs/2208.09266)]
* **?**: "Vision Transformer Based Model for Describing a Set of Images as a Story", arXiv, 2022 (*The University of Western Australia*). [[Paper](https://arxiv.org/abs/2210.02762)]

[[Back to Overview](#overview)]

### Visual Question Answering
* **MCAN**: "Deep Modular Co-Attention Networks for Visual Question Answering", CVPR, 2019 (*Hangzhou Dianzi University*). [[Paper](https://arxiv.org/abs/1906.10770)][[PyTorch](https://github.com/MILVLG/mcan-vqa)]
* **M4C**: "Iterative Answer Prediction with Pointer-Augmented Multimodal Transformers for TextVQA", CVPR, 2020 (*Facebook*). [[Paper](https://arxiv.org/abs/1911.06258)]
* **SA-M4C**: "Spatially Aware Multimodal Transformers for TextVQA", ECCV, 2020 (*Georgia Tech*). [[Paper](https://arxiv.org/abs/2007.12146)][[PyTorch](https://github.com/yashkant/sam-textvqa)][[Website](https://yashkant.github.io/projects/sam-textvqa.html)]
* **ConClaT**: "Contrast and Classify: Training Robust VQA Models", ICCV, 2021 (*Georgia Tech*). [[Paper](https://arxiv.org/abs/2010.06087)]
* **TRAR**: "TRAR: Routing the Attention Spans in Transformer for Visual Question Answering", ICCV, 2021 (*Xiamen University*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021/html/Zhou_TRAR_Routing_the_Attention_Spans_in_Transformer_for_Visual_Question_ICCV_2021_paper.html)]
* **UniQer**: "Unified Questioner Transformer for Descriptive Question Generation in Goal-Oriented Visual Dialogue", ICCV, 2021 (*Keio*). [[Paper](https://arxiv.org/abs/2106.15550)]
* **TxT**: "TxT: Crossmodal End-to-End Learning with Transformers", GCPR, 2021 (*TU Darmstadt*). [[Paper](https://arxiv.org/abs/2109.04422)]
* **ProTo**: "ProTo: Program-Guided Transformer for Program-Guided Tasks", NeurIPS, 2021 (*Georiga Tech*). [[Paper](https://arxiv.org/abs/2110.00804)]
* **VisQA**: "VisQA: X-raying Vision and Language Reasoning in Transformers", arXiv, 2021 (*INSA-Lyon*). [[Paper](https://arxiv.org/abs/2104.00926)][[PyTorch](https://github.com/Theo-Jaunet/VisQA)]
* **?**: "Mounting Video Metadata on Transformer-based Language Model for Open-ended Video Question Answering", arXiv, 2021 (*Seoul National University*). [[Paper](https://arxiv.org/abs/2108.05158)]
* **TPT**: "Temporal Pyramid Transformer with Multimodal Interaction for Video Question Answering", arXiv, 2021 (*CAS*). [[Paper](https://arxiv.org/abs/2109.04735)]
* **Block-Skim**: "Block-Skim: Efficient Question Answering for Transformer", AAAI, 2022 (* Shanghai Jiao Tong*). [[Paper](https://arxiv.org/abs/2112.08560)]
* **RelViT**: "RelViT: Concept-guided Vision Transformer for Visual Relational Reasoning", ICLR, 2022 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2204.11167)] [[PyTorch](https://github.com/NVlabs/RelViT)]
* **Hypergraph-Transformer**: "Hypergraph Transformer: Weakly-supervised Multi-hop Reasoning for Knowledge-based Visual Question Answering", ACL, 2022 (*SNU*). [[Paper](https://arxiv.org/abs/2204.10448)][[Code (in construction)](https://github.com/yujungheo/kbvqa-public)]
* **X-Trans2Cap**: "X-Trans2Cap: Cross-Modal Knowledge Transfer using Transformer for 3D Dense Captioning", CVPR, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2203.00843)]
* **SwinBERT**: "SwinBERT: End-to-End Transformers with Sparse Attention for Video Captioning", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.13196)][[PyTorch](https://github.com/microsoft/SwinBERT)]
* **UTC**: "UTC: A Unified Transformer with Inter-Task Contrastive Learning for Visual Dialog", CVPR, 2022 (*Fudan*). [[Paper](https://arxiv.org/abs/2205.00423)]
* **LaTr**: "LaTr: Layout-Aware Transformer for Scene-Text VQA", CVPR, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2112.12494)]
* **QAA**: "Query and Attention Augmentation for Knowledge-Based Explainable Reasoning", CVPR, 2022 (*University of Minnesota*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Zhang_Query_and_Attention_Augmentation_for_Knowledge-Based_Explainable_Reasoning_CVPR_2022_paper.html)][[PyTorch](https://github.com/SuperJohnZhang/QAA)]
* **WebQA**: "WebQA: Multihop and Multimodal QA", CVPR, 2022 (*CMU + Microsoft*). [[Paper](https://arxiv.org/abs/2109.00590)][[PyTorch](https://github.com/WebQnA/WebQA_Baseline)][[Website](https://webqna.github.io/)]
* **?**: "Efficient Adaptive Image-Language Learning for Visual Question Answering", CVPRW, 2022 (*Google*). [[Paper](https://drive.google.com/file/d/1SPeCqJ_Uzs_jk4yxxcSS8OOUKZmXf_Mt/view)]
* **cViL**: "cViL: Cross-Lingual Training of Vision-Language Models using Knowledge Distillation", ICPR, 2022 (*IIIT, Hyderabad*). [[Paper](https://arxiv.org/abs/2206.03354)]
* **WildQA**: "WildQA: In-the-Wild Video Question Answering", International Conference on Computational Linguistics (COLING), 2022 (*University of Michigan*). [[Paper](https://arxiv.org/abs/2209.06650)][[Website](https://lit.eecs.umich.edu/wildqa/)]
* **Distinguishing-VQA**: "Overcoming Language Priors in Visual Question Answering via Distinguishing Superficially Similar Instances", COLING, 2022 (*Nankai University*). [[Paper](https://arxiv.org/abs/2209.08529)][[Code (in construction)](https://github.com/wyk-nku/Distinguishing-VQA)]
* **?**: "Weakly Supervised Grounding for VQA in Vision-Language Transformers", ECCV, 2022 (*UCF*). [[Paper](https://arxiv.org/abs/2207.02334)][[PyTorch (in construction)](https://github.com/aurooj/WSG-VQA-VLTransformers)]
* **VGT**: "Video Graph Transformer for Video Question Answering", ECCV, 2022 (*Sea AI Lab*). [[Paper](https://arxiv.org/abs/2207.05342)][[PyTorch](https://github.com/sail-sg/VGT)]
* **?**: "Video Question Answering with Iterative Video-Text Co-Tokenization", ECCV, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2208.00934)][[Website (in construction)](https://sites.google.com/view/videoqa-cotokenization)]
* **MUST-VQA**: "MUST-VQA: MUltilingual Scene-text VQA", ECCVW, 2022 (*UAB, Spain*). [[Paper](https://arxiv.org/abs/2209.06730)]
* **DeST**: "Learning Fine-Grained Visual Understanding for Video Question Answering via Decoupling Spatial-Temporal Modeling", BMVC, 2022 (*NTU*). [[Paper](https://arxiv.org/abs/2210.03941)][[PyTorch](https://github.com/shinying/dest)]
* **MuRAG**: "MuRAG: Multimodal Retrieval-Augmented Generator for Open Question Answering over Images and Text", EMNLP, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2210.02928)]
* **MMBS**: "Towards Robust Visual Question Answering: Making the Most of Biased Samples via Contrastive Learning", EMNLP, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2210.04563)][[PyTorch](https://github.com/PhoebusSi/MMBS)]
* **EnFoRe**: "Entity-Focused Dense Passage Retrieval for Outside-Knowledge Visual Question Answering", EMNLP, 2022 (*UT Austin*). [[Paper](https://arxiv.org/abs/2210.10176)]
* **PnP-VQA**: "Plug-and-Play VQA: Zero-shot VQA by Conjoining Large Pretrained Models with Zero Training", EMNLP Findings, 2022 (*Salesforce*). [[Paper](https://arxiv.org/abs/2210.08773)]
* **TMN**: "Transformer Module Networks for Systematic Generalization in Visual Question Answering", arXiv, 2022 (*Fujitsu*). [[Paper](https://arxiv.org/abs/2201.11316)]
* **?**: "On the Efficacy of Co-Attention Transformer Layers in Visual Question Answering", arXiv, 2022 (*Birla Institute of Technology Mesra, India*). [[Paper](https://arxiv.org/abs/2201.03965)]
* **DST**: "Towards Efficient and Elastic Visual Question Answering with Doubly Slimmable Transformer", arXiv, 2022 (*Hangzhou Dianzi University*). [[Paper](https://arxiv.org/abs/2203.12814)]
* **PAVCR**: "Attention Mechanism based Cognition-level Scene Understanding", arXiv, 2022 (*Leibniz University of Hannover, Germany*). [[Paper](https://arxiv.org/abs/2204.08027)]
* **REVIVE**: "REVIVE: Regional Visual Representation Matters in Knowledge-Based Visual Question Answering", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.01201)]
* **TAG**: "TAG: Boosting Text-VQA via Text-aware Visual Question-answer Generation", arXiv, 2022 (*Maryland + Salesforce*). [[Paper](https://arxiv.org/abs/2208.01813)][[PyTorch](https://github.com/HenryJunW/TAG)]
* **UniCon**: "UniCon: Unidirectional Split Learning with Contrastive Loss for Visual Question Answering", arXiv, 2022 (*University of Tokyo*). [[Paper](https://arxiv.org/abs/2208.11435)]
* **CLOVE**: "Symbolic Replay: Scene Graph as Prompt for Continual Learning on VQA Task", arXiv, 2022 (*NUS*). [[Paper](https://arxiv.org/abs/2208.12037)][[Code (in construction)](https://github.com/showlab/CLVQA)]
* **WSQG**: "Frame-Subtitle Self-Supervision for Multi-Modal Video Question Answering", arXiv, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2209.03609)]
* **mVQA**: "Towards Multi-Lingual Visual Question Answering", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2209.05401)]
* **CIB**: "Finetuning Pretrained Vision-Language Models with Correlation Information Bottleneck for Robust Visual Question Answering", arXiv, 2022 (*Xi'an Jiaotong University*). [[Paper](https://arxiv.org/abs/2209.06954)]
* **LocAns**: "Locate before Answering: Answer Guided Question Localization for Video Question Answering", arXiv, 2022 (*Fudan University*). [[Paper](https://arxiv.org/abs/2210.02081)]
* **?**: "Compressing And Debiasing Vision-Language Pre-Trained Models for Visual Question Answering", arXiv, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2210.14558)]
* **VLC-BERT**: "VLC-BERT: Visual Question Answering with Contextualized Commonsense Knowledge", WACV, 2023 (*UBC, Canada*). [[Paper](https://arxiv.org/abs/2210.13626)][[PyTorch](https://github.com/aditya10/VLC-BERT)]

[[Back to Overview](#overview)]

### Visual Grounding
* General:
    * **TransRefer3D**: "TransRefer3D: Entity-and-Relation Aware Transformer for Fine-Grained 3D Visual Grounding", ACMMM, 2021 (*Beihang University*). [[Paper](https://arxiv.org/abs/2108.02388)]
    * **?**: "Vision-and-Language or Vision-for-Language? On Cross-Modal Influence in Multimodal Transformers", EMNLP, 2021 (*University of Trento*). [[Paper](https://arxiv.org/abs/2109.04448)]
    * **MITVG**: "Multimodal Incremental Transformer with Visual Grounding for Visual Dialogue Generation", ACL Findings, 2021 (*Tencent*). [[Paper](https://arxiv.org/abs/2109.08478)]
    * **TransVG**: "TransVG: End-to-End Visual Grounding with Transformers", ICCV, 2021 (*USTC*). [[Paper](https://arxiv.org/abs/2104.08541)]
    * **GSRTR**: "Grounded Situation Recognition with Transformers", BMVC, 2021 (*POSTECH*). [[Paper](https://arxiv.org/abs/2111.10135)][[PyTorch](https://github.com/jhcho99/gsrtr)]
    * **Referring-Transformer**: "Referring Transformer: A One-step Approach to Multi-task Visual Grounding", NeurIPS, 2021 (*UBC*). [[Paper](https://arxiv.org/abs/2106.03089)]
    * **VGTR**: "Visual Grounding with Transformers", arXiv, 2021 (*Beihang University*). [[Paper](https://arxiv.org/abs/2105.04281)]
    * **UNICORN**: "Crossing the Format Boundary of Text and Boxes: Towards Unified Vision-Language Modeling", arXiv, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.12085)]
    * **Word2Pix**: "Word2Pix: Word to Pixel Cross Attention Transformer in Visual Grounding", arXiv, 2021 (*A\*STAR*). [[Paper](https://arxiv.org/abs/2108.00205)]
    * **MVT**: "Multi-View Transformer for 3D Visual Grounding", CVPR, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2204.02174)][[PyTorch](https://github.com/sega-hsj/MVT-3DVG)]
    * **GLIP**: "Grounded Language-Image Pre-training", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2112.03857)][[PyTorch](https://github.com/microsoft/GLIP)]
    * **M-DGT**: "Multi-Modal Dynamic Graph Transformer for Visual Grounding", CVPR, 2022 (*University of Toronto*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Chen_Multi-Modal_Dynamic_Graph_Transformer_for_Visual_Grounding_CVPR_2022_paper.html)][[PyTorch](https://github.com/iQua/M-DGT)]
    * **QRNet**: "Shifting More Attention to Visual Backbone: Query-modulated Refinement Networks for End-to-End Visual Grounding", CVPR, 2022 (*East China Normal University*). [[Paper](https://arxiv.org/abs/2203.15442)][[PyTorch](https://github.com/LukeForeverYoung/QRNet)]
    * **SiRi**: "SiRi: A Simple Selective Retraining Mechanism for Transformer-based Visual Grounding", ECCV, 2022 (*JD*). [[Paper](https://arxiv.org/abs/2207.13325)][[PyTorch](https://github.com/qumengxue/siri-vg)]
    * **UniTAB**: "UniTAB: Unifying Text and Box Outputs for Grounded Vision-Language Modeling", ECCV, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.12085)]
    * **TAP**: "Improving Closed and Open-Vocabulary Attribute Prediction Using Transformers", ECCV, 2022 (*Adobe*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/5247_ECCV_2022_paper.php)][[GitHub](https://github.com/adobe-research/vaw_dataset)][[Website](https://vkhoi.github.io/TAP/)]
    * **?**: "Do Vision-and-Language Transformers Learn Grounded Predicate-Noun Dependencies?", EMNLP, 2022 (*Aix-Marseille University, France*). [[Paper](https://arxiv.org/abs/2210.12079)]
    * **SeqTR**: "SeqTR: A Simple yet Universal Network for Visual Grounding", arXiv, 2022 (*Xiamen University*). [[Paper](https://arxiv.org/abs/2203.16265)][[Code (in construction)](https://github.com/sean-zhuh/SeqTR)]
    * **BEST**: "Visual Clues: Bridging Vision and Language Foundations for Image Paragraph Captioning", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.01843)]
    * **GLIPv2**: "GLIPv2: Unifying Localization and Vision-Language Understanding", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.05836)][[PyTorch](https://github.com/microsoft/GLIP)]
    * **TransVG++**: "TransVG++: End-to-End Visual Grounding with Language Conditioned Vision Transformer", arXiv, 2022 (*USTC*). [[Paper](https://arxiv.org/abs/2206.06619)]
    * **HLGT**: "Hierarchical Local-Global Transformer for Temporal Sentence Grounding", arXiv, 2022 (*Huazhong University of Science and Technology*). [[Paper](https://arxiv.org/abs/2208.14882)]
    * **Dynamic-MDETR**: "Dynamic MDETR: A Dynamic Multimodal Transformer Decoder for Visual Grounding", arXiv, 2022 (*Nanjing University*). [[Paper](https://arxiv.org/abs/2209.13959)]
* Video:
    * **Multi-Stage-Transformer**: "Multi-Stage Aggregated Transformer Network for Temporal Language Localization in Videos", CVPR, 2021 (*University of Electronic Science and Technology of China*). [[Paper](https://openaccess.thecvf.com/content/CVPR2021/html/Zhang_Multi-Stage_Aggregated_Transformer_Network_for_Temporal_Language_Localization_in_Videos_CVPR_2021_paper.html)]
    * **GTR**: "On Pursuit of Designing Multi-modal Transformer for Video Grounding", EMNLP, 2021 (*Peking*). [[Paper](https://arxiv.org/abs/2109.06085)]
    * **STVGBert**: "STVGBert: A Visual-Linguistic Transformer Based Framework for Spatio-Temporal Video Grounding", ICCV, 2021 (*Tencent*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021/html/Su_STVGBert_A_Visual-Linguistic_Transformer_Based_Framework_for_Spatio-Temporal_Video_Grounding_ICCV_2021_paper.html)]
    * **DRFT**: "End-to-end Multi-modal Video Temporal Grounding", NeurIPS, 2021 (*UC Merced*). [[Paper](https://arxiv.org/abs/2107.05624)]
    * **TubeDETR**: "TubeDETR: Spatio-Temporal Video Grounding with Transformers", CVPR, 2022 (*INRIA*). [[Paper](https://arxiv.org/abs/2203.16434)][[Website](https://antoyang.github.io/tubedetr.html)]
    * **STVGFormer**: "STVGFormer: Spatio-Temporal Video Grounding with Static-Dynamic Cross-Modal Understanding", ACMMMW, 2022 (*Sun Yat-sen University*). [[Paper](https://arxiv.org/abs/2207.02756)]
    * **VidGTR**: "Explore and Match: End-to-End Video Grounding with Transformer", arXiv, 2022 (*KAIST*). [[Paper](https://arxiv.org/abs/2201.10168)]
    * **?**: "Language-free Training for Zero-shot Video Grounding", WACV, 2023 (*Yonsei University*). [[Paper](https://arxiv.org/abs/2210.12977)]


[[Back to Overview](#overview)]

### Multi-Modal Representation Learning
* General:
    * **LXMERT**: "LXMERT: Learning Cross-Modality Encoder Representations from Transformers", EMNLP, 2019 (*UNC*). [[Paper](https://arxiv.org/abs/1908.07490)][[PyTorch](https://github.com/airsplay/lxmert)]
    * **ViLBERT**: "ViLBERT: Pretraining Task-Agnostic Visiolinguistic Representations for Vision-and-Language Tasks", NeurIPS, 2019 (*Georgia Tech*). [[Paper](https://papers.nips.cc/paper/2019/hash/c74d97b01eae257e44aa9d5bade97baf-Abstract.html)][[PyTorch](https://github.com/facebookresearch/vilbert-multi-task)]
    * **Unified-VLP**: "Unified Vision-Language Pre-Training for Image Captioning and VQA", AAAI, 2020 (*UMich + Microsoft*). [[Paper](https://arxiv.org/abs/1909.11059)][[PyTorch](https://github.com/LuoweiZhou/VLP)]
    * **UNITER**: "UNITER: UNiversal Image-TExt Representation Learning", ECCV, 2020 (*Microsoft*). [[Paper](https://arxiv.org/abs/1909.11740)][[PyTorch](https://github.com/ChenRocks/UNITER)]
    * **VinVL**: "VinVL: Revisiting Visual Representations in Vision-Language Models", CVPR, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2101.00529)][[Code](https://github.com/pzzhang/VinVL)]
    * **CATT**: "Causal Attention for Vision-Language Tasks", CVPR, 2021 (*NTU Singapore*). [[Paper](https://arxiv.org/abs/2103.03493)][[PyTorch](https://github.com/yangxuntu/lxmertcatt)]
    * **CLIP**: "Learning Transferable Visual Models From Natural Language Supervision", ICML, 2021 (*OpenAI*). [[Paper](https://arxiv.org/abs/2103.00020)][[PyTorch](https://github.com/openai/CLIP)]
    * **ViLT**: "ViLT: Vision-and-Language Transformer Without Convolution or Region Supervision", ICML, 2021 (*Kakao*). [[Paper](https://arxiv.org/abs/2102.03334)][[PyTorch](https://github.com/dandelin/vilt)]
    * **SVO-Probes**: "Probing Image-Language Transformers for Verb Understanding", arXiv, 2021 (*DeepMind*). [[Paper](https://arxiv.org/abs/2106.09141)]
    * **CLIP-ViL**: "How Much Can CLIP Benefit Vision-and-Language Tasks?", arXiv, 2021 (*Berkeley + UCLA*). [[Paper](https://arxiv.org/abs/2107.06383)][[PyTorch](https://github.com/clip-vil/CLIP-ViL)]
    * **Florence**: "Florence: A New Foundation Model for Computer Vision", arXiv, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.11432)]
    * **UFO**: "UFO: A UniFied TransfOrmer for Vision-Language Representation Learning", arXiv, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.10023)]
    * **LiT**: "LiT: Zero-Shot Transfer with Locked-image text Tuning", CVPR, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2111.07991)]
    * **UniCL**: "Unified Contrastive Learning in Image-Text-Label Space", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2204.03610)][[PyTorch](https://github.com/microsoft/UniCL)]
    * **FLAVA**: "FLAVA: A Foundational Language And Vision Alignment Model", CVPR, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2112.04482)][[Pretrained Model](https://huggingface.co/facebook/flava-full)][[Code](https://github.com/facebookresearch/multimodal/tree/main/examples/flava)][[Dataset](https://huggingface.co/datasets/facebook/pmd)][[Website](https://flava-model.github.io/)][[Demos](https://huggingface.co/flava)]
    * **LEMON**: "Scaling Up Vision-Language Pre-training for Image Captioning", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.12233)]
    * **METER**: "An Empirical Study of Training End-to-End Vision-and-Language Transformers", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.02387)][[PyTorch](https://github.com/zdou0830/METER)]
    * **CM-mix**: "Pre-training image-language transformers for open-vocabulary tasks", CVPRW, 2022 (*Google*). [[Paper](https://drive.google.com/file/d/1dYM4g42rptj647v1EfNARmnCt3HdPpNR/view)]
    * **VLMixer**: "VLMixer: Unpaired Vision-Language Pre-training via Cross-Modal CutMix", ICML, 2022 (*Southern University of Science and Technology*). [[Paper](https://arxiv.org/abs/2206.08919)][[Code (in construction)](https://github.com/ttengwang/VLMixer)]
    * **VLUE**: "VLUE: A Multi-Task Benchmark for Evaluating Vision-Language Models", ICML, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2205.15237)][[Website](https://vlue-benchmark.github.io/)][[PyTorch](https://github.com/MichaelZhouwang/VLUE)]
    * **X-VLM**: "Multi-Grained Vision Language Pre-Training: Aligning Texts with Visual Concepts", ICML, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2111.08276)][[PyTorch](https://github.com/zengyan-97/X-VLM)]
    * **BLIP**: "BLIP: Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation", ICML, 2022 (*Salesforce*). [[Paper](https://arxiv.org/abs/2201.12086)][[PyTorch](https://github.com/salesforce/BLIP)]
    * **MS-CLIP**: "Learning Visual Representation from Modality-Shared Contrastive Language-Image Pre-training", ECCV, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2207.12661)][[PyTorch](https://github.com/Hxyou/MSCLIP)]
    * **GRIT-VLP**: "GRIT-VLP: Grouped Mini-batch Sampling for Efficient Vision and Language Pre-training", ECCV, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2208.04060)][[PyTorch](https://github.com/jaeseokbyun/GRIT-VLP)]
    * **SIMLA**: "Single-Stream Multi-Level Alignment for Vision-Language Pretraining", ECCV, 2022 (*Northeastern University*). [[Paper](https://arxiv.org/abs/2203.14395)][[PyTorch](https://github.com/codezakh/SIMLA)][[Website](http://zaidkhan.me/SIMLA/)]
    * **Switch-BERT**: "Switch-BERT: Learning to Model Multimodal Interactions by Switching Attention and Input", ECCV, 2022 (*Ant Group*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/3834_ECCV_2022_paper.php)]
    * **OmniVL**: "OmniVL: One Foundation Model for Image-Language and Video-Language Tasks", NeurIPS, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2209.07526)]
    * **UniCLIP**: "UniCLIP: Unified Framework for Contrastive Language-Image Pre-training", NeurIPS, 2022 (*LG*). [[Paper](https://arxiv.org/abs/2209.13430)]
    * **TVLT**: "TVLT: Textless Vision-Language Transformer", NeurIPS, 2022 (*UNC*). [[Paper](https://arxiv.org/abs/2209.14156)][[PyTorch](https://github.com/zinengtang/TVLT)]
    * **FaD-VLP**: "FaD-VLP: Fashion Vision-and-Language Pre-training towards Unified Retrieval and Captioning", EMNLP, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2210.15028)]
    * **VLMo**: "VLMo: Unified Vision-Language Pre-Training with Mixture-of-Modality-Experts", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.02358)][[PyTorch (in construction)](https://github.com/microsoft/unilm/tree/master/vlmo)]
    * **Omnivore**: "Omnivore: A Single Model for Many Visual Modalities", arXiv, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2201.08377)][[PyTorch](https://github.com/facebookresearch/omnivore)]
    * **MultiMAE**: "MultiMAE: Multi-modal Multi-task Masked Autoencoders", arXiv, 2022 (*EPFL*). [[Paper](https://arxiv.org/abs/2204.01678)][[PyTorch](https://github.com/EPFL-VILAB/MultiMAE)][[Website](https://multimae.epfl.ch/)]
    * **Flamingo**: "Flamingo: a Visual Language Model for Few-Shot Learning", arXiv, 2022 (*DeepMind*). [[Paper](https://arxiv.org/abs/2204.14198)]
    * **PyramidCLIP**: "PyramidCLIP: Hierarchical Feature Alignment for Vision-language Model Pretraining", arXiv, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2204.14095)]
    * **CoCa**: "CoCa: Contrastive Captioners are Image-Text Foundation Models", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2205.01917)]
    * **VLC**: "Training Vision-Language Transformers from Captions Alone", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2205.09256)][[Code (in construction)](https://github.com/guilk/VLC)]
    * **UViM**: "UViM: A Unified Modeling Approach for Vision with Learned Guiding Codes", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2205.10337)]
    * **GIT**: "GIT: A Generative Image-to-text Transformer for Vision and Language", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2205.14100)]
    * **CyCLIP**: "CyCLIP: Cyclic Contrastive Language-Image Pretraining", arXiv, 2022 (*UCLA*). [[Paper](https://arxiv.org/abs/2205.14459)]
    * **CCLM**: "Cross-View Language Modeling: Towards Unified Cross-Lingual Cross-Modal Pre-training", arXiv, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2206.00621)]
    * **VL-BEiT**: "VL-BEiT: Generative Vision-Language Pretraining", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.01127)]
    * **Uni-Perceiver-MoE**: "Uni-Perceiver-MoE: Learning Sparse Generalist Models with Conditional MoEs", arXiv, 2022 (*SenseTime*). [[Paper](https://arxiv.org/abs/2206.04674)]
    * **MetaLM**: "Language Models are General-Purpose Interfaces", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.06336)][[PyTorch](https://github.com/microsoft/unilm)]
    * **DaVinci**: "Prefix Language Models are Unified Modal Learners", arXiv, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2206.07699)]
    * **FIBER**: "Coarse-to-Fine Vision-Language Pre-training with Fusion in the Backbone", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.07643)][[PyTorch](https://github.com/microsoft/FIBER)]
    * **Bridge-Tower**: "Bridge-Tower: Building Bridges Between Encoders in Vision-Language Representation Learning", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.08657)][[Code (in construction)](https://github.com/microsoft/BridgeTower)]
    * **e-CLIP**: "e-CLIP: Large-Scale Vision-Language Representation Learning in E-commerce", arXiv, 2022 (*NAVER*). [[Paper](https://arxiv.org/abs/2207.00208)]
    * **LW-Transformer**: "Towards Lightweight Transformer via Group-wise Transformation for Vision-and-Language Tasks", arXiv, 2022 (*Xiamen University*). [[Paper](https://arxiv.org/abs/2204.07780)][[PyTorch](https://github.com/luogen1996/LWTransformer)]
    * **UCM**: "Self-Training Vision Language BERTs with a Unified Conditional Model", arXiv, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2201.02010)]
    * **MaskVLM**: "Masked Vision and Language Modeling for Multi-modal Representation Learning", arXiv, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2208.02131)]
    * **LOUPE**: "Fine-Grained Semantically Aligned Vision-Language Pre-Training", arXiv, 2022 (*Huawei*). [[Paper](https://arxiv.org/abs/2208.02515)]
    * **Prefix-conditioning**: "Prefix Conditioning Unifies Language and Label Supervision", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2206.01125)]
    * **VLMAE**: "VLMAE: Vision-Language Masked Autoencoder", arXiv, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2208.09374)]
    * **BEiT-3**: "Image as a Foreign Language: BEiT Pretraining for All Vision and Vision-Language Tasks", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2208.10442)][[PyTorch](https://github.com/microsoft/unilm/tree/master/beit)]
    * **ViCHA**: "Efficient Vision-Language Pretraining with Visual Concepts and Hierarchical Alignment", arXiv, 2022 (*Sorbonne University, France*). [[Paper](https://arxiv.org/abs/2208.13628)][[Code (in construction)](https://github.com/mshukor/ViCHA)]
    * **DetailCLIP**: "Injecting Image Details into CLIP's Feature Space", arXiv, 2022 (*Megvii*). [[Paper](https://arxiv.org/abs/2208.14649)]
    * **?**: "Pre-training image-language transformers for open-vocabulary tasks", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2209.04372)]
    * **PaLI**: "PaLI: A Jointly-Scaled Multilingual Language-Image Model", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2209.06794)]
    * **ERNIE**: "ERNIE-ViL 2.0: Multi-view Contrastive Learning for Image-Text Pre-training", arXiv, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2209.15270)][[Paddle](https://github.com/PaddlePaddle/ERNIE)]
    * **Pix2Struct**: "Pix2Struct: Screenshot Parsing as Pretraining for Visual Language Understanding", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2210.03347)]
    * **VoLTA**: "VoLTA: Vision-Language Transformer with Weakly-Supervised Local-Feature Alignment", arXiv, 2022 (*JHU*). [[Paper](https://arxiv.org/abs/2210.04135)]
    * **MAP**: "MAP: Modality-Agnostic Uncertainty-Aware Vision-Language Pre-training Model", arXiv, 2022 (*Tsinghua + Waseda*). [[Paper](https://arxiv.org/abs/2210.05335)][[PyTorch](https://github.com/IIGROUP/MAP)]
    * **?**: "One does not fit all! On the Complementarity of Vision Encoders for Vision and Language Tasks", arXiv, 2022 (*Technical University of Darmstadt, Germany*). [[Paper](https://arxiv.org/abs/2210.06379)]
    * **MAPL**: "MAPL: Parameter-Efficient Adaptation of Unimodal Pre-Trained Models for Vision-Language Few-Shot Prompting", arXiv, 2022 (*Mila*). [[Paper](https://arxiv.org/abs/2210.07179)]
    * **EfficientVLM**: "EfficientVLM: Fast and Accurate Vision-Language Models via Knowledge Distillation and Modal-adaptive Pruning", arXiv, 2022 (*Bytedance*). [[Paper](https://arxiv.org/abs/2210.07795)][[PyTorch (in construction)](https://github.com/swaggy-TN/EfficientVLM)]
    * **xCLIP**: "Non-Contrastive Learning Meets Language-Image Pre-Training", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2210.09304)]
    * **WFH**: "Learning by Hallucinating: Vision-Language Pre-training with Weak Supervision", WACV, 2023 (*Aalto University, Finland*). [[Paper](https://arxiv.org/abs/2210.13591)]
* Video:
    * **COOT**: "COOT: Cooperative Hierarchical Transformer for Video-Text Representation Learning", NeurIPS, 2020 (*University of Freiburg*). [[Paper](https://arxiv.org/abs/2011.00597)][[PyTorch](https://github.com/gingsi/coot-videotext)]
    * **Parameter-Reduction**: "Parameter Efficient Multimodal Transformers for Video Representation Learning", ICLR, 2021 (*Seoul National University*). [[Paper](https://openreview.net/forum?id=6UdQLhqJyFD)]
    * **VML**: "VLM: Task-agnostic Video-Language Model Pre-training for Video Understanding", ACL Findings, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2105.09996)]
    * **VATT**: "VATT: Transformers for Multimodal Self-Supervised Learning from Raw Video, Audio and Text", NeurIPS, 2021 (*Google*). [[Paper](https://arxiv.org/abs/2104.11178)][[Tensorflow](https://github.com/google-research/google-research/tree/master/vatt)]
    * **TAN**: "Temporal Alignment Networks for Long-term Video", CVPR, 2022 (*Oxford*). [[Paper](https://arxiv.org/abs/2204.02968)][[Code (in construction)](https://github.com/TengdaHan/TemporalAlignNet)][[Website](https://www.robots.ox.ac.uk/~vgg/research/tan/)]
    * **HD-VILA**: "Advancing High-Resolution Video-Language Representation with Large-Scale Video Transcriptions", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.10337)][[GitHub](https://github.com/microsoft/XPretrain)]
    * **ATP**: "Revisiting the "Video" in Video-Language Understanding", CVPR, 2022 (*Stanford*). [[Paper](https://arxiv.org/abs/2206.01720)][[Website](https://stanfordvl.github.io/atp-revisit-video-lang/)]
    * **ALPRO**: "Align and Prompt: Video-and-Language Pre-training with Entity Prompts", CVPR, 2022 (*Salesforce*). [[Paper](https://arxiv.org/abs/2112.09583)][[PyTorch](https://github.com/salesforce/ALPRO)]
    * **?**: "Learning Audio-Video Modalities from Image Captions", ECCV, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2204.00679)]
    * **MUGEN**: "MUGEN: A Playground for Video-Audio-Text Multimodal Understanding and GENeration", ECCV, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2204.08058)][[Website](https://mugen-org.github.io/)]
    * **LiteVL**: "LiteVL: Efficient Video-Language Learning with Enhanced Spatial-Temporal Modeling", EMNLP, 2022 (*Peking University*). [[Paper](https://arxiv.org/abs/2210.11929)]
    * **EgoVLP**: "Egocentric Video-Language Pretraining", arXiv, 2022 (*NUS*). [[Paper](https://arxiv.org/abs/2206.01670)][[Code (in construction)](https://github.com/showlab/EgoVLP)]
    * **Singularity**: "Revealing Single Frame Bias for Video-and-Language Learning", arXiv, 2022 (*UNC*). [[Paper](https://arxiv.org/abs/2206.03428)]
    * **LAVENDER**: "LAVENDER: Unifying Video-Language Understanding as Masked Language Modeling", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2206.07160)][[Code (in construction)](https://github.com/microsoft/LAVENDER)]
    * **Clover**: "Clover: Towards A Unified Video-Language Alignment and Fusion Model", arXiv, 2022 (*ByteDance*). [[Paper](https://arxiv.org/abs/2207.07885)][[PyTorch (in construction)](https://github.com/LeeYN-43/Clover)]
    * **?**: "An Empirical Study of End-to-End Video-Language Transformers with Masked Visual Modeling", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2209.01540)]
    * **CLIP-ViP**: "CLIP-ViP: Adapting Pre-trained Image-Text Model to Video-Language Representation Alignment", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2209.06430)][[Code (in construction)](https://github.com/microsoft/XPretrain/tree/main/CLIP-ViP)]


[[Back to Overview](#overview)]

### Multi-Modal Retrieval
* General:
    * **Fast-and-Slow**: "Thinking Fast and Slow: Efficient Text-to-Visual Retrieval with Transformers", CVPR, 2021 (*DeepMind*). [[Paper](https://arxiv.org/abs/2103.16553)]
    * **HTR**: "Revamping Cross-Modal Recipe Retrieval with Hierarchical Transformers and Self-supervised Learning", CVPR, 2021 (*Amazon*). [[Paper](https://arxiv.org/abs/2103.13061)][[PyTorch](https://github.com/amzn/image-to-recipe-transformers)]
    * **TERN**: "Towards Efficient Cross-Modal Visual Textual Retrieval using Transformer-Encoder Deep Features", CBMI, 2021 (*National Research Council, Italy*). [[Paper](https://arxiv.org/abs/2106.00358)]
    * **VisualSparta**: "VisualSparta: Sparse Transformer Fragment-level Matching for Large-scale Text-to-Image Search", arXiv, 2021 (*CMU*). [[Paper](https://arxiv.org/abs/2101.00265)]
    * **CCR-CCS**: "More Than Just Attention: Learning Cross-Modal Attentions with Contrastive Constraints", arXiv, 2021 (*Rutgers + Amazon*). [[Paper](https://arxiv.org/abs/2105.09597)]
    * **MCProp**: "Transformer-Based Multi-modal Proposal and Re-Rank for Wikipedia Image-Caption Matching", ICLRW, 2022 (*National Research Council, Italy*). [[Paper](https://arxiv.org/abs/2206.10436)][[PyTorch](https://github.com/mesnico/Wiki-Image-Caption-Matching)]
    * **TASK-former**: "A Sketch Is Worth a Thousand Words: Image Retrieval with Text and Sketch", ECCV, 2022 (*Georgia Tech*). [[Paper](https://arxiv.org/abs/2208.03354)][[Website](https://patsorn.me/projects/tsbir/)]
    * **CODER**: "CODER: Coupled Diversity-Sensitive Momentum Contrastive Learning for Image-Text Retrieval", ECCV, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2208.09843)]
    * **?**: "Most and Least Retrievable Images in Visual-Language Query Systems", ECCV, 2022 (*Old Dominion University, Virginia*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/7050_ECCV_2022_paper.php)]
    * **SpeechCLIP**: "SpeechCLIP: Integrating Speech with Pre-Trained Vision and Language Model", IEEE Workshop on Spoken Language Technology (SLT), 2022 (*NTU*). [[Paper](https://arxiv.org/abs/2210.00705)]
    * **LoopITR**: "LoopITR: Combining Dual and Cross Encoder Architectures for Image-Text Retrieval", arXiv, 2022 (*UNC*). [[Paper](https://arxiv.org/abs/2203.05465)]
    * **TNLBT**: "Transformer-based Cross-Modal Recipe Embeddings with Large Batch Training", arXiv, 2022 (*The University of Electro-Communications, Japan*). [[Paper](https://arxiv.org/abs/2205.04948)]
    * **HiVLP**: "HiVLP: Hierarchical Vision-Language Pre-Training for Fast Image-Text Retrieval", arXiv, 2022 (*Huawei*). [[Paper](https://arxiv.org/abs/2205.12105)]
    * **?**: "Revising Image-Text Retrieval via Multi-Modal Entailment". arXiv, 2022 (*Soochow University, China*). [[Paper](https://arxiv.org/abs/2208.10126)]
    * **TokenFlow**: "TokenFlow: Rethinking Fine-grained Cross-modal Alignment in Vision-Language Retrieval", arXiv, 2022 (*Kuaishou*). [[Paper](https://arxiv.org/abs/2209.13822)]
* Video:
    * **MMT**: "Multi-modal Transformer for Video Retrieval", ECCV, 2020 (*INRIA + Google*). [[Paper](https://arxiv.org/abs/2007.10639)][[Website](http://thoth.inrialpes.fr/research/MMT/)]
    * **ClipBERT**: "Less is More: ClipBERT for Video-and-Language Learning via Sparse Sampling", CVPR, 2021 (*UNC + Microsoft*). [[Paper](https://arxiv.org/abs/2102.06183)][[PyTorch](https://github.com/jayleicn/ClipBERT)]
    * **AYCE**: "All You Can Embed: Natural Language based Vehicle Retrieval with Spatio-Temporal Transformers", CVPRW, 2021 (*University of Modena and Reggio Emilia*). [[Paper](https://arxiv.org/abs/2106.10153)][[PyTorch](https://github.com/cscribano/AYCE_2021)]
    * **HiT**: "HiT: Hierarchical Transformer with Momentum Contrast for Video-Text Retrieval", ICCV, 2021 (*Kuaishou*). [[Paper](https://arxiv.org/abs/2103.15049)]
    * **WebVid-2M**: "Frozen in Time: A Joint Video and Image Encoder for End-to-End Retrieval", ICCV, 2021 (*Oxford*). [[Paper](https://arxiv.org/abs/2104.00650)]
    * **UMT**: "UMT: Unified Multi-modal Transformers for Joint Video Moment Retrieval and Highlight Detection", CVPR, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2203.12745)][[Code (in constrcution)](https://github.com/TencentARC/UMT)]
    * **MMFT**: "Everything at Once - Multi-modal Fusion Transformer for Video Retrieval", CVPR, 2022 (*Goethe University Frankfurt, Germany*). [[Paper](https://arxiv.org/abs/2112.04446)]
    * **X-Pool**: "X-Pool: Cross-Modal Language-Video Attention for Text-Video Retrieval", CVPR, 2022 (*Layer 6 AI, Toronto*). [[Paper](https://arxiv.org/abs/2203.15086)][[PyTorch](https://github.com/layer6ai-labs/xpool)][[Website](https://layer6ai-labs.github.io/xpool/)]
    * **MVPt**: "It's Time for Artistic Correspondence in Music and Video", CVPR, 2022 (*Adobe*). [[Paper](https://arxiv.org/abs/2206.07148)][[Website](https://musicforvideo.cs.columbia.edu/)]
    * **CenterCLIP**: "CenterCLIP: Token Clustering for Efficient Text-Video Retrieval", SIGIR, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2205.00823)]
    * **X-CLIP**: "X-CLIP: End-to-End Multi-grained Contrastive Learning for Video-Text Retrieval", ACMMM, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2207.07285)]
    * **HiSE**: "Boosting Video-Text Retrieval with Explicit High-Level Semantics", ACMMM, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2208.04215)]
    * **TS2-Net**: "TS2-Net: Token Shift and Selection Transformer for Text-Video Retrieval", ECCV, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2207.07852)][[PyTorch](https://github.com/yuqi657/ts2_net)]
    * **LAFF**: "Lightweight Attentional Feature Fusion: A New Baseline for Text-to-Video Retrieval", ECCV, 2022 (*Renmin University of China*). [[Paper](https://arxiv.org/abs/2112.01832)]
    * **ECLIPSE**: "ECLIPSE: Efficient Long-range Video Retrieval using Sight and Sound", ECCV, 2022 (*UNC*). [[Paper](https://arxiv.org/abs/2204.02874)][[PyTorch](https://github.com/GenjiB/ECLIPSE)][[Website](https://yblin.ml/project_page/eclipse/)]
    * **MILES**: "MILES: Visual BERT Pre-training with Injected Language Semantics for Video-text Retrieval", ECCV, 2022 (*HKU*). [[Paper](https://arxiv.org/abs/2204.12408)]
    * **VTC**: "VTC: Improving Video-Text Retrieval with User Comments", ECCV, 2022 (*Unitary, UK*). [[Paper](https://arxiv.org/abs/2210.10820)][[PyTorch](https://github.com/unitaryai/VTC)][[Website](https://unitaryai.github.io/vtc-paper/)]
    * **LINAS**: "Learning Linguistic Association towards Efficient Text-Video Retrieval", ECCV, 2022 (*CAS*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/3305_ECCV_2022_paper.php)][[PyTorch](https://github.com/silenceFS/LINAS)]
    * **?**: "Text-Adaptive Multiple Visual Prototype Matching for Video-Text Retrieval", NeurIPS, 2022 (*Sun Yat-sen University*). [[Paper](https://arxiv.org/abs/2209.13307)]
    * **ConTra**: "ConTra: (Con)text (Tra)nsformer for Cross-Modal Video Retrieval", ACCV, 2022 (*University of Bristol, UK*). [[Paper](https://arxiv.org/abs/2210.04341)]
    * **RaP**: "RaP: Redundancy-aware Video-language Pre-training for Text-Video Retrieval", EMNLP, 2022 (*CAS*). [[Paper](https://arxiv.org/abs/2210.06881)][[PyTorch](https://github.com/caskcsg/VLP/tree/main/RaP)]
    * **BridgeFormer**: "BridgeFormer: Bridging Video-text Retrieval with Multiple Choice Questions", arXiv, 2022 (*HKU*). [[Paper](https://arxiv.org/abs/2201.04850)][[Website](https://geyuying.github.io/MCQ.html)]
    * **MDMMT-2**: "MDMMT-2: Multidomain Multimodal Transformer for Video Retrieval, One More Step Towards Generalization", arXiv, 2022 (*Huawei*). [[Paper](https://arxiv.org/abs/2203.07086)]
    * **M2HF**: "M2HF: Multi-level Multi-modal Hybrid Fusion for Text-Video Retrieval", arXiv, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2208.07664)]
    * **FIRE**: "Fighting FIRe with FIRE: Assessing the Validity of Text-to-Video Retrieval Benchmarks", arXiv, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2210.05038)][[PyTorch](https://github.com/facebookresearch/mm-retrieval-evaluation)]

[[Back to Overview](#overview)]

### Multi-Modal Generation
* General:
    * **AttnGAN**: "AttnGAN: Fine-Grained Text to Image Generation with Attentional Generative Adversarial Networks", CVPR, 2018 (*Microsoft*). [[Paper](https://arxiv.org/abs/1711.10485)][[PyTorch](https://github.com/taoxugit/AttnGAN)]
    * **ControlGAN**: "Controllable Text-to-Image Generation", NeurIPS, 2019 (*Oxford*). [[Paper](https://arxiv.org/abs/1909.07083)][[PyTorch](https://github.com/mrlibw/ControlGAN)]
    * **DALL-E**: "Zero-Shot Text-to-Image Generation", ICML, 2021 (*OpenAI*). [[Paper](https://arxiv.org/abs/2102.12092)][[PyTorch](https://github.com/openai/DALL-E)][[PyTorch (lucidrains)](https://github.com/lucidrains/DALLE-pytorch)]
    * **CogView**: "CogView: Mastering Text-to-Image Generation via Transformers", NeurIPS, 2021 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2105.13290)][[PyTorch](https://github.com/THUDM/CogView)][[Website](https://lab.aminer.cn/cogview/index.html)]
    * **Layout-VQGAN**: "Text-to-Image Synthesis Based on Object-Guided Joint-Decoding Transformer", CVPR, 2022 (*CAS*). [[Paper](https://openaccess.thecvf.com/content/CVPR2022/html/Wu_Text-to-Image_Synthesis_Based_on_Object-Guided_Joint-Decoding_Transformer_CVPR_2022_paper.html)]
    * **Lafite**: "Towards Language-Free Training for Text-to-Image Generation", CVPR, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2111.13792)][[PyTorch](https://github.com/drboog/Lafite)]
    * **AvatarCLIP**: "AvatarCLIP: Zero-Shot Text-Driven Generation and Animation of 3D Avatars", SIGGRAPH, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2205.08535)][[PyTorch](https://github.com/hongfz16/AvatarCLIP)][[Website](https://hongfz16.github.io/projects/AvatarCLIP.html)]
    * **StoryDALL-E**: "StoryDALL-E: Adapting Pretrained Text-to-Image Transformers for Story Continuation", ECCV, 2022 (*UNC*). [[Paper](https://arxiv.org/abs/2209.06192)][[PyTorch](https://github.com/adymaharana/storydalle)]	
    * **Make-A-Scene**: "Make-A-Scene: Scene-Based Text-to-Image Generation with Human Priors", ECCV, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2203.13131)][[Video](https://www.youtube.com/watch?v=QLTyqoJJKTo&ab_channel=OranGafni)]
    * **TCTIG**: "Trace Controlled Text to Image Generation", ECCV, 2022 (*Beihang University*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/1894_ECCV_2022_paper.php)]
    * **DALL-Eval**: "DALL-Eval: Probing the Reasoning Skills and Social Biases of Text-to-Image Generative Transformers", arXiv, 2022 (*UNC*). [[Paper](https://arxiv.org/abs/2202.04053)][[PyTorch](https://github.com/j-min/DallEval)]
    * **DALL-E-2**: "Hierarchical Text-Conditional Image Generation with CLIP Latents", arXiv, 2022 (*OpenAI*). [[Paper](https://arxiv.org/abs/2204.06125)][[Website](https://openai.com/dall-e-2/)]
    * **CogView2**: "CogView2: Faster and Better Text-to-Image Generation via Hierarchical Transformers", arXiv, 2022 (*Tsinghua*). [[Paper](https://arxiv.org/abs/2204.14217)][[PyTorch](https://github.com/THUDM/CogView2)]
    * **?**: "A very preliminary analysis of DALL-E 2", arXiv, 2022 (*NYU*). [[Paper](https://arxiv.org/abs/2204.13807)]
    * **Imagen**: "Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding", arXiv, 2022 (*Google*). [[Paper](https://gweb-research-imagen.appspot.com/paper.pdf)][[Website](https://gweb-research-imagen.appspot.com/)]
    * **GLIDE**: "GLIDE: Towards Photorealistic Image Generation and Editing with Text-Guided Diffusion Models", arXiv, 2022 (*OpenAI*). [[Paper](https://arxiv.org/abs/2112.10741)][[PyTorch](https://github.com/openai/glide-text2im)]
    * **?**: "Discovering the Hidden Vocabulary of DALLE-2", arXiv, 2022 (*UT Austin*). [[Paper](https://arxiv.org/abs/2206.00169)]
    * **Parti**: "Scaling Autoregressive Models for Content-Rich Text-to-Image Generation", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2206.10789)][[GitHub](https://github.com/google-research/parti)][[Website](https://parti.research.google/)]
    * **?**: "Prompt-to-Prompt Image Editing with Cross Attention Control", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2208.01626)]
    * **Textual-Inversion**: "An Image is Worth One Word: Personalizing Text-to-Image Generation using Textual Inversion", arXiv, 2022 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2208.01618)][[Website](https://textual-inversion.github.io/)]
    * **VLMGAN**: "Vision-Language Matching for Text-to-Image Synthesis via Generative Adversarial Networks", arXiv, 2022 (*Fudan University*). [[Paper](https://arxiv.org/abs/2208.09596)]
    * **PDM**: "Progressive Denoising Model for Fine-Grained Text-to-Image Generation", arXiv, 2022 (*Meituan*). [[Paper](https://arxiv.org/abs/2210.02291)]
    * **FS-VQG**: "Few-Shot Visual Question Generation: A Novel Task and Benchmark Datasets", arXiv, 2022 (*IIT Kharagpur*). [[Paper](https://arxiv.org/abs/2210.07076)]
    * **Swinv2-Imagen**: "Swinv2-Imagen: Hierarchical Vision Transformer Diffusion Models for Text-to-Image Generation", arXiv, 2022 (*Auckland University of Technology*). [[Paper](https://arxiv.org/abs/2210.09549)]
    * **UniTune**: "UniTune: Text-Driven Image Editing by Fine Tuning an Image Generation Model on a Single Image", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2210.09477)]
    * **VSD**: "Visual Spatial Description: Controlled Spatial-Oriented Image-to-Text Generation", arXiv, 2022 (*Tianjin University*). [[Paper](https://arxiv.org/abs/2210.11109)][[Code (in construction)](https://github.com/zhaoyucs/VSD)]
    * **Lafite2**: "Lafite2: Few-shot Text-to-Image Generation", arXiv, 2022 (*SUNY, Buffalo*). [[Paper](https://arxiv.org/abs/2210.14124)]
* Video:
    * **CogVideo**: "CogVideo: Large-scale Pretraining for Text-to-Video Generation via Transformers", arXiv, 2022 (*Tsinghua University*) [[Paper](https://arxiv.org/abs/2205.15868)][[GitHub (in construction)](https://github.com/THUDM/CogVideo)]
    * **Make-A-Video**: "Make-A-Video: Text-to-Video Generation without Text-Video Data", arXiv, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2209.14792)]
    * **Imagen-Video**: "Imagen Video: High Definition Video Generation with Diffusion Models", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2210.02303)][[Website](https://imagen.research.google/video/)]
    * **Phenaki**: "Phenaki: Variable Length Video Generation From Open Domain Textual Description", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2210.02399)][[PyTorch (LAION-AI, in construction)](https://github.com/LAION-AI/phenaki)][[Website](https://phenaki.video/)]
    * **?**: "Towards Real-Time Text2Video via CLIP-Guided, Pixel-Level Optimization", arXiv, 2022 (*CMU*). [[Paper](https://arxiv.org/abs/2210.12826)][[PyTorch](https://github.com/pschaldenbrand/Text2Video)][[Website](https://pschaldenbrand.github.io/text2video/)]

[[Back to Overview](#overview)]

### Visual Document Understanding
* **LayoutLMv2**: "LayoutLMv2: Multi-modal Pre-training for Visually-Rich Document Understanding", ACL, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2012.14740)][[PyTorch](https://github.com/microsoft/unilm/tree/master/layoutlmv2)]
* **DocFormer**: "DocFormer: End-to-End Transformer for Document Understanding", ICCV, 2021 (*Amazon*). [[Paper](https://arxiv.org/abs/2106.11539)]
* **LayoutXLM**: "LayoutXLM: Multimodal Pre-training for Multilingual Visually-rich Document Understanding", arXiv, 2021 (*Microsoft*). [[Paper](https://arxiv.org/abs/2104.08836)][[PyTorch](https://github.com/microsoft/unilm/tree/master/layoutxlm)]
* **TableFormer**: "TableFormer: Table Structure Understanding with Transformers", CVPR, 2022 (*IBM*). [[Paper](https://arxiv.org/abs/2203.01017)]
* **TSRFormer**: "TSRFormer: Table Structure Recognition with Transformers", ACMMM, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2208.04921)]
* **ERNIE-mmLayout**: "ERNIE-mmLayout: Multi-grained MultiModal Transformer for Document Understanding", ACMMM, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2209.08569)]
* **Donut**: "Donut: Document Understanding Transformer without OCR", ECCV, 2022 (*NAVER*). [[Paper](https://arxiv.org/abs/2111.15664)][[PyTorch](https://github.com/clovaai/donut)]
* **I2DFormer**: "I2DFormer: Learning Image to Document Attention for Zero-Shot Image Classification", NeurIPS, 2022 (*ETHZ*). [[Paper](https://arxiv.org/abs/2209.10304)]
* **DocEnTr**: "DocEnTr: An End-to-End Document Image Enhancement Transformer", arXiv, 2022 (*UAB, Spain*). [[Paper](https://arxiv.org/abs/2201.10252)][[PyTorch](https://github.com/dali92002/DocEnTR)]
* **DocSegTr**: "DocSegTr: An Instance-Level End-to-End Document Image Segmentation Transformer", arXiv, 2022 (*UAB, Spain*). [[Paper](https://arxiv.org/abs/2201.11438)]
* **DiT**: "DiT: Self-supervised Pre-training for Document Image Transformer", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2203.02378)][[Code (in construction)](https://github.com/microsoft/unilm/tree/master/dit)]
* **LayoutLMv3**: "LayoutLMv3: Pre-training for Document AI with Unified Text and Image Masking", arXiv, 2022 (*Microsoft*). [[Paper](https://arxiv.org/abs/2204.08387)][[PyTorch](https://github.com/microsoft/unilm/tree/master/layoutlmv3)]
* **MATrIX**: "MATrIX - Modality-Aware Transformer for Information eXtraction", arXiv, 2022 (*Amazon*). [[Paper](https://arxiv.org/abs/2205.08094)]
* **VLCDoC**: "VLCDoC: Vision-Language Contrastive Pre-Training Model for Cross-Modal Document Classification", arXiv, 2022 (*La Rochelle University, France*). [[Paper](https://arxiv.org/abs/2205.12029)]
* **Bi-VLDoc**: "Bi-VLDoc: Bidirectional Vision-Language Modeling for Visually-Rich Document Understanding", arXiv, 2022 (*Alibaba*). [[Paper](https://arxiv.org/abs/2206.13155)]
* **TRUST**: "TRUST: An Accurate and End-to-End Table structure Recognizer Using Splitting-based Transformers", arXiv, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2208.14687)]
* **OCR-VQGAN**: "OCR-VQGAN: Taming Text-within-Image Generation", WACV, 2023 (*UAB, Spain*). [[Paper](https://arxiv.org/abs/2210.11248)]

[[Back to Overview](#overview)]

### Scene Graph
* **BGT-Net**: "BGT-Net: Bidirectional GRU Transformer Network for Scene Graph Generation", CVPRW, 2021 (*ETHZ*). [[Paper](https://arxiv.org/abs/2109.05346)]
* **STTran**: "Spatial-Temporal Transformer for Dynamic Scene Graph Generation", ICCV, 2021 (*Leibniz University Hannover, Germany*). [[Paper](https://arxiv.org/abs/2107.12309)][[PyTorch](https://github.com/yrcong/STTran)]
* **SGG-NLS**: "Learning to Generate Scene Graph from Natural Language Supervision", ICCV, 2021 (*University of Wisconsin-Madison*). [[Paper](https://arxiv.org/abs/2109.02227)][[PyTorch](https://github.com/YiwuZhong/SGG_from_NLS)]
* **SGG-Seq2Seq**: "Context-Aware Scene Graph Generation With Seq2Seq Transformers", ICCV, 2021 (*Layer 6 AI, Canada*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021/html/Lu_Context-Aware_Scene_Graph_Generation_With_Seq2Seq_Transformers_ICCV_2021_paper.html)][[PyTorch](https://github.com/layer6ai-labs/SGG-Seq2Seq)]
* **RELAX**: "Image-Text Alignment using Adaptive Cross-attention with Transformer Encoder for Scene Graphs", BMVC, 2021 (*Samsung*). [[Paper](https://www.bmvc2021-virtualconference.com/assets/papers/0117.pdf)]
* **Relation-Transformer**: "Scenes and Surroundings: Scene Graph Generation using Relation Transformer", arXiv, 2021 (*LMU Munich*). [[Paper](https://arxiv.org/abs/2107.05448)]
* **SGTR**: "SGTR: End-to-end Scene Graph Generation with Transformer", CVPR, 2022 (*ShanghaiTech*). [[Paper](https://arxiv.org/abs/2112.12970)][[Code (in construction)](https://github.com/Scarecrow0/SGTR)]
* **GCL**: "Stacked Hybrid-Attention and Group Collaborative Learning for Unbiased Scene Graph Generation", CVPR, 2022 (*Shandong University*). [[Paper](https://arxiv.org/abs/2203.09811)][[PyTorch](https://github.com/dongxingning/SHA-GCL-for-SGG)]
* **Relationformer**: "Relationformer: A Unified Framework for Image-to-Graph Generation", ECCV, 2022 (*TUM*). [[Paper](https://arxiv.org/abs/2203.10202)][[Code (in construction)](https://github.com/suprosanna/relationformer)]
* **SVRP**: "Towards Open-vocabulary Scene Graph Generation with Prompt-based Finetuning", ECCV, 2022 (*Monash University*). [[Paper](https://arxiv.org/abs/2208.08165)]
* **RelTR**: "RelTR: Relation Transformer for Scene Graph Generation", arXiv, 2022 (*Leibniz University Hannover, Germany*). [[Paper](https://arxiv.org/abs/2201.11460)][[PyTorch](https://github.com/yrcong/RelTR)]

[[Back to Overview](#overview)]

### Other Multi-Modal Tasks
* Prompt Learning:
    * **CoCoOp**: "Conditional Prompt Learning for Vision-Language Models", CVPR, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2203.05557)][[PyTorch](https://github.com/KaiyangZhou/CoOp)]
    * **ProDA**: "Prompt Distribution Learning", CVPR, 2022 (*Huawei*). [[Paper](https://arxiv.org/abs/2205.03340)]
    * **VPT**: "Visual Prompt Tuning", ECCV, 2022 (*Cornell*). [[Paper](https://arxiv.org/abs/2203.12119)][[PyTorch](https://github.com/kmnp/vpt)]
    * **PerVL**: ""This is my unicorn, Fluffy": Personalizing frozen vision-language representations", ECCV, 2022 (*NVIDIA*). [[Paper](https://arxiv.org/abs/2204.01694)][[PyTorch](https://github.com/NVlabs/PALAVRA)]
    * **CoOp**: "Learning to Prompt for Vision-Language Models", IJCV, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2109.01134)][[PyTorch](https://github.com/KaiyangZhou/CoOp)]
    * **LASP**: "Language-Aware Soft Prompting for Vision & Language Foundation Models", arXiv, 2022 (*Samsung*). [[Paper](https://arxiv.org/abs/2210.01115)]
    * **PLOT**: "Prompt Learning with Optimal Transport for Vision-Language Models", arXiv, 2022 (*CMU*). [[Paper](https://arxiv.org/abs/2210.01253)]
    * **VPT**: "Variational prompt tuning improves generalization of vision-language models", arXiv, 2022 (*Samsung*). [[Paper](https://arxiv.org/abs/2210.02390)]
    * **MaPLe**: "MaPLe: Multi-modal Prompt Learning", arXiv, 2022 (*MBZUAI*). [[Paper](https://arxiv.org/abs/2210.03117)][[PyTorch](https://github.com/muzairkhattak/multimodal-prompt-learning)]
    * **CAVPT**: "Class-Aware Visual Prompt Tuning for Vision-Language Pre-Trained Model", arXiv, 2022 (*Northwestern Polytechnical University, China*). [[Paper](https://arxiv.org/abs/2208.08340)]
    * **Visual-Prompting**: "Exploring Visual Prompts for Adapting Large-Scale Models", arXiv, 2022 (*MIT*). [[Paper](https://arxiv.org/abs/2203.17274)][[PyTorch](https://github.com/hjbahng/visual_prompting)][[Website](https://hjbahng.github.io/visual_prompting/)]
    * **PGN**: "Prompt Generation Networks for Efficient Adaptation of Frozen Vision Transformers", arXiv, 2022 (*University of Amsterdam*). [[Paper](https://arxiv.org/abs/2210.06466)][[PyTorch](https://github.com/jochemloedeman/PGN)]
    * **UPT**: "Unified Vision and Language Prompt Learning", arXiv, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2210.07225)][[Code (in construction)](https://github.com/yuhangzang/UPT)]
    * **?**: "Visual Classification via Description from Large Language Models", arXiv, 2022 (*Columbia*). [[Paper](https://arxiv.org/abs/2210.07183)]
    * **CPL**: "CPL: Counterfactual Prompt Learning for Vision and Language Models", arXiv, 2022 (*UC Santa Cruz*). [[Paper](https://arxiv.org/abs/2210.10362)]
    * **PTP**: "Prompting through Prototype: A Prototype-based Prompt Learning on Pretrained Vision-Language Models", arXiv, 2022 (*Baidu*). [[Paper](https://arxiv.org/abs/2210.10841)]
* X-Shot:
    * **VidIL**: "Language Models with Image Descriptors are Strong Few-Shot Video-Language Learners", NeurIPS, 2022 (*UIUC*). [[Paper](https://arxiv.org/abs/2205.10747)][[PyTorch](https://github.com/MikeWangWZHL/VidIL)]
    * **LIMoE**: "Multimodal Contrastive Learning with LIMoE: the Language-Image Mixture of Experts", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2206.02770)]
* Segmentation:
    * **VLT**: "Vision-Language Transformer and Query Generation for Referring Segmentation", ICCV, 2021 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2108.05565)][[Tensorflow](https://github.com/henghuiding/Vision-Language-Transformer)]
    * **LAVT**: "LAVT: Language-Aware Vision Transformer for Referring Image Segmentation", CVPR, 2022 (*Oxford*). [[Paper](https://arxiv.org/abs/2112.02244)]
    * **ReSTR**: "ReSTR: Convolution-free Referring Image Segmentation Using Transformers", CVPR, 2022 (*POSTECH*). [[Paper](https://arxiv.org/abs/2203.16768)][[Website](http://cvlab.postech.ac.kr/research/restr/)]
    * **VLT**: "VLT: Vision-Language Transformer and Query Generation for Referring Segmentation", TPAMI, 2022 (*NTU, Singapore*). [[Paper](https://arxiv.org/abs/2210.15871)]
* Tracking:
    * **ModaMixer**: "Divert More Attention to Vision-Language Tracking", arXiv, 2022 (*Beijing Jiaotong University*). [[Paper](https://arxiv.org/abs/2207.01076)][[PyTorch](https://github.com/JudasDie/SOTS)]
* Analysis:
    * **MM-Explainability**: "Generic Attention-model Explainability for Interpreting Bi-Modal and Encoder-Decoder Transformers", ICCV, 2021 (*Tel Aviv*). [[Paper](https://arxiv.org/abs/2103.15679)][[PyTorch](https://github.com/hila-chefer/Transformer-MM-Explainability)]
    * **?**: "Are Multimodal Transformers Robust to Missing Modality?", CVPR, 2022 (*University of Delaware*). [[Paper](https://arxiv.org/abs/2204.05454)]
    * **VL-InterpreT**: "VL-InterpreT: An Interactive Visualization Tool for Interpreting Vision-Language Transformers", CVPR (demo), 2022 (*Intel*). [[Paper](https://arxiv.org/abs/2203.17247)][[Website](http://vlinterpretenv4env-env.eba-vmhhefup.us-east-2.elasticbeanstalk.com/)][[Video](https://www.youtube.com/watch?v=2HZ2IjzG5_4&ab_channel=MengDu)]
    * **?**: "Understanding Attention for Vision-and-Language Tasks", International Conference on Computational Linguistics (COLING), 2022 (*The University of Sydney*). [[Paper](https://arxiv.org/abs/2208.08104)]
    * **VL-CheckList**: "VL-CheckList: Evaluating Pre-trained Vision-Language Models with Objects, Attributes and Relations", arXiv, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2207.00221)][[Code (in construction)](https://github.com/om-ai-lab/VL-CheckList)]
* Speaker Localization:
    * **?**: "The Right to Talk: An Audio-Visual Transformer Approach", ICCV, 2021 (*University of Arkansas*). [[Paper](https://arxiv.org/abs/2108.03256)]
* Multi-task:
    * **UniT**: "Transformer is All You Need: Multimodal Multitask Learning with a Unified Transformer", ICCV, 2021 (*Facebook*). [[Paper](https://arxiv.org/abs/2102.10772)][[PyTorch](https://github.com/facebookresearch/mmf)][[Website](https://mmf.sh/)]
    * **Pix2Seq**: "A Unified Sequence Interface for Vision Tasks", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2206.07669)]
    * **Unified-IO**: "Unified-IO: A Unified Model for Vision, Language, and Multi-Modal Tasks", arXiv, 2022 (*AI2*). [[Paper](https://arxiv.org/abs/2206.08916)][[Website](https://unified-io.allenai.org/)]
    * **LAVIS**: "LAVIS: A Library for Language-Vision Intelligence", arXiv, 2022 (*Salesforce*). [[Paper](https://arxiv.org/abs/2209.09019)][[PyTorch](https://github.com/salesforce/LAVIS)]
* Language-based Video Editing:
    * **M<sup>3</sup>L**: "Language-based Video Editing via Multi-Modal Multi-Level Transformer", CVPR, 2022 (*UCSB*). [[Paper](https://arxiv.org/abs/2104.01122)]
* Video Summarization:
    * **GPT2MVS**: "GPT2MVS: Generative Pre-trained Transformer-2 for Multi-modal Video Summarization", ICMR, 2021 (*BBC*). [[Paper](https://arxiv.org/abs/2104.12465)]
    * **QVHighlights**: "QVHighlights: Detecting Moments and Highlights in Videos via Natural Language Queries", NeurIPS, 2021 (*UNC*). [[Paper](https://arxiv.org/abs/2107.09609)][[PyTorch](https://github.com/jayleicn/moment_detr)]
    * **HMT**: "Hierarchical Multimodal Transformer to Summarize Videos", arXiv, 2021 (*Xidian University*). [[Paper](https://arxiv.org/abs/2109.10559)]
    * **?**: "Show Me What I Like: Detecting User-Specific Video Highlights Using Content-Based Multi-Head Attention", ACMMM, 2022 (*Adobe*). [[Paper](https://arxiv.org/abs/2207.08352)]
    * **IV-Sum**: "TL;DW? Summarizing Instructional Videos with Task Relevance & Cross-Modal Saliency", ECCV, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2208.06773)][[Website](https://medhini.github.io/ivsum/)]
* Robotics:
    * **CRT**: "Case Relation Transformer: A Crossmodal Language Generation Model for Fetching Instructions", IROS, 2021 (*Keio University*). [[Paper](https://arxiv.org/abs/2107.00789)]
    * **TraSeTR**: "TraSeTR: Track-to-Segment Transformer with Contrastive Query for Instance-level Instrument Segmentation in Robotic Surgery", ICRA, 2022 (*CUHK*). [[Paper](https://arxiv.org/abs/2202.08453)]
* Multi-modal Fusion:
    * **MICA**: "Attention Is Not Enough: Mitigating the Distribution Discrepancy in Asynchronous Multimodal Sequence Fusion", ICCV, 2021 (*Southwest Jiaotong University*). [[Paper](https://openaccess.thecvf.com/content/ICCV2021/html/Liang_Attention_Is_Not_Enough_Mitigating_the_Distribution_Discrepancy_in_Asynchronous_ICCV_2021_paper.html)]
    * **IFT**: "Image Fusion Transformer", arXiv, 2021 (*Johns Hopkins*). [[Paper](https://arxiv.org/abs/2107.09011)][[PyTorch](https://github.com/Vibashan/Image-Fusion-Transformer)]
    * **PPT**: "PPT Fusion: Pyramid Patch Transformerfor a Case Study in Image Fusion", arXiv, 2021 (*?*). [[Paper](https://arxiv.org/abs/2107.13967)]
    * **TransFuse**: "TransFuse: A Unified Transformer-based Image Fusion Framework using Self-supervised Learning", arXiv, 2022 (*Fudan University*). [[Paper](https://arxiv.org/abs/2201.07451)]
    * **SwinFuse**: "SwinFuse: A Residual Swin Transformer Fusion Network for Infrared and Visible Images", arXiv, 2022 (*Taiyuan University of Science and Technology*). [[Paper](https://arxiv.org/abs/2204.11436)]
    * **?**: "Array Camera Image Fusion using Physics-Aware Transformers", arXiv, 2022 (*University of Arizona*). [[Paper](https://arxiv.org/abs/2207.02250)]
* Human Interaction:
    * **Dyadformer**: "Dyadformer: A Multi-modal Transformer for Long-Range Modeling of Dyadic Interactions", ICCVW, 2021 (*Universitat de Barcelona*). [[Paper](https://arxiv.org/abs/2109.09487)]
* Sign Language Translation:
    * **LWTA**: "Stochastic Transformer Networks with Linear Competing Units: Application to end-to-end SL Translation", ICCV, 2021 (*Cyprus University of Technology*). [[Paper](https://arxiv.org/abs/2109.13318)]
* 3D:
    * **3DRefTransformer**: "3DRefTransformer: Fine-Grained Object Identification in Real-World Scenes Using Natural Language", WACV, 2022 (*KAUST*). [[Paper](https://openaccess.thecvf.com/content/WACV2022/html/Abdelreheem_3DRefTransformer_Fine-Grained_Object_Identification_in_Real-World_Scenes_Using_Natural_Language_WACV_2022_paper.html)][[Website](https://vision-cair.github.io/3dreftransformer/)]
    * **EDA**: "EDA: Explicit Text-Decoupling and Dense Alignment for 3D Visual and Language Learning", arXiv, 2022 (*Peking University*). [[Paper](https://arxiv.org/abs/2209.14941)]
* Speech Recognition:
    * **AV-HuBERT**: "Robust Self-Supervised Audio-Visual Speech Recognition", arXiv, 2022 (*Meta*). [[Paper](https://arxiv.org/abs/2201.01763)][[PyTorch](https://github.com/facebookresearch/av_hubert)]
    * **?**: "Transformer-Based Video Front-Ends for Audio-Visual Speech Recognition", arXiv, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2201.10439)]
* Emotion Recognition:
    * **?**: "A Pre-trained Audio-Visual Transformer for Emotion Recognition", ICASSP, 2022 (*USC*). [[Paper](https://arxiv.org/abs/2201.09165)]
    * **MDAN**: "MDAN: Multi-level Dependent Attention Network for Visual Emotion Analysis", CVPR, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2203.13443)]
* Voice Separation:
    * **VoViT**: "VoViT: Low Latency Graph-based Audio-Visual Voice Separation Transformer", ECCV, 2022 (*Universitat Pompeu Fabra, Spain*). [[Paper](https://arxiv.org/abs/2203.04099)][[PyTorch](https://github.com/JuanFMontesinos/VoViT)][[Website](https://ipcv.github.io/VoViT/)]
* Language-guided Video Segmentation:
    * **Locater**: "Local-Global Context Aware Transformer for Language-Guided Video Segmentation", arXiv, 2022 (*Zhejiang*). [[Paper](https://arxiv.org/abs/2203.09773)][[PyTorch](https://github.com/leonnnop/Locater)]
* Audio-Visual:
    * **AVCA**: "Audio-visual Generalised Zero-shot Learning with Cross-modal Attention and Language", CVPR, 2022 (*University of Tubingen, Germany*). [[Paper](https://arxiv.org/abs/2203.03598)][[PyTorch](https://github.com/ExplainableML/AVCA-GZSL)]
    * **TCaF**: "Temporal and cross-modal attention for audio-visual zero-shot learning", ECCV, 2022 (*University of Tubingen, Germany*). [[Paper](https://arxiv.org/abs/2207.09966)][[PyTorch](https://github.com/ExplainableML/TCAF-GZSL)]
    * **?**: "Learning Audio-Video Modalities from Image Captions", ECCV, 2022 (*Google*). [[Paper](https://arxiv.org/abs/2204.00679)]
    * **AVSBench**: "Audio-Visual Segmentation", ECCV, 2022 (*SenseTime*). [[Paper](https://arxiv.org/abs/2207.05042)][[PyTorch](https://github.com/OpenNLPLab/AVSBench)][[Website](https://opennlplab.github.io/AVSBench/)]
    * **AVA-Memory**: "Audio-Visual Mismatch-Aware Video Retrieval via Association and Adjustment", ECCV, 2022 (*KAIST*). [[Paper](https://www.ecva.net/papers/eccv_2022/papers_ECCV/html/5034_ECCV_2022_paper.php)]
    * **PC-VAE**: "Multimodal Transformer for Parallel Concatenated Variational Autoencoders", NeurIPSW, 2022 (*USC*). [[Paper](https://arxiv.org/abs/2210.16174)]
    * **MTD**: "Multimodal Transformer Distillation for Audio-Visual Synchronization", arXiv, 2022 (*NTU*). [[Paper](https://arxiv.org/abs/2210.15563)]
    * **AVE-CLIP**: "AVE-CLIP: AudioCLIP-based Multi-window Temporal Transformer for Audio Visual Event Localization", WACV, 2023 (*UT Austin*). [[Paper](https://arxiv.org/abs/2210.05060)]
* Sentiment Analysis:
    * **CubeMLP**: "CubeMLP: A MLP-based Model for Multimodal Sentiment Analysis and Depression Estimation", ACMMM, 2022 (*Zhejiang University*). [[Paper](https://arxiv.org/abs/2207.14087)]
    * **MCMulT**: "Multi-scale Cooperative Multimodal Transformers for Multimodal Sentiment Analysis in Videos", arXiv, 2022 (*Tencent*). [[Paper](https://arxiv.org/abs/2206.07981)]
* Name Entity Recognition:
    * **FMIT**: "Flat Multi-modal Interaction Transformer for Named Entity Recognition", International Conference on Computational Linguistics (COLING), 2022 (*South China University of Technology*). [[Paper](https://arxiv.org/abs/2208.11039)]
* Localization via Embodied Dialog:
    * **LED-Bert**: "Transformer-based Localization from Embodied Dialog with Large-scale Pre-training", arXiv, 2022 (*Georgia Tech*). [[Paper](https://arxiv.org/abs/2210.04864)]

[[Back to Overview](#overview)]



---
## Citation
If you find this repository useful, please consider citing this list:
```
@misc{chen2022transformerpaperlist,
    title = {Ultimate awesome paper list: transformer and attention},
    author = {Chen, Min-Hung},
    journal = {GitHub repository},
    url = {https://github.com/cmhungsteve/Awesome-Transformer-Attention},
    year = {2022},
}
```

---

## References
* Online Resources:
    * [Papers with Code](https://paperswithcode.com/methods/category/vision-transformer)
    * [Transformer tutorial (Lucas Beyer)](http://lucasb.eyer.be/transformer)
    * [CS25: Transformers United (Course @ Stanford)](https://web.stanford.edu/class/cs25/)
    * [The Annotated Transformer (Blog)](http://nlp.seas.harvard.edu/annotated-transformer/)
    * [3D Vision with Transformers (GitHub)](https://github.com/lahoud/3d-vision-transformers)
    * [Practical Introduction to Transformers (GitHub)](https://github.com/IbrahimSobh/Transformers)
    * [Awesome Transformer Architecture Search (GitHub)](https://github.com/automl/awesome-transformer-search)
    * [Transformer-in-Vision (GitHub)](https://github.com/DirtyHarryLYL/Transformer-in-Vision)   
    * [Awesome Visual-Transformer (GitHub)](https://github.com/dk-liang/Awesome-Visual-Transformer)
    * [Awesome Transformer for Vision Resources List (GitHub)](https://github.com/lijiaman/awesome-transformer-for-vision)
    * [Transformer-in-Computer-Vision (GitHub)](https://github.com/Yangzhangcst/Transformer-in-Computer-Vision)
