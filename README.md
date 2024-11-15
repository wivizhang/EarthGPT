# 🌏 EarthGPT: A Universal Multi-modal Large Language Model for Multi-sensor Image Comprehension in Remote Sensing Domain 

Official repository for [EarthGPT](https://arxiv.org/abs/2401.16822). :smile: 

Authors: Wei Zhang*, Miaoxin Cai*, Tong Zhang, Yin Zhuang, and Xuerui Mao
* The authors contributed equally to this work.
  
## :mega: News
- [2024.10.21]: We open source the dataset MMRS-1M ! :fire::fire::fire:
- [2024.05.25]: EarthGPT has been accepted to IEEE-TGRS 🎉 
- [2024.04.29]: We partially released the data of MMRS-1M ! 
* [2024.01.30]: The paper for EarthGPT is released [arxiv](https://arxiv.org/abs/2401.16822). 

##  :sparkles: Overview
EarthGPT is a universal MLLM tailored for the remote sensing domain, effectively establishing a multi-modal mutual learning framework and seamlessly unifying a wide range of RS tasks and multi-sensor imagery interpretation in multi-turn dialogues. Specifically, EarthGPT is capable of various visual reasoning tasks including scene classification, image captioning, region-level captioning, VQA, visual grounding, object detection, etc. Most importantly, EarthGPT is versatile at multi-sensor imagery comprehension across optical, SAR, and infrared images. 
<div align="center">
  <img src="images/examples.png">
</div>

##  :sparkles: MMRS-1M: Multi-modal Multi-sensor Remote Sensing Instruction Dataset
MMRS-1M is the largest multi-modal multi-sensor RS instruction-following dataset, consisting of over 1M image-text pairs that include optical, SAR, and infrared RS images. 

<u>___The entire data of MMRS-1M is released! 🚀___</u>

Link1: https://pan.baidu.com/s/1sK9I862tuQfiiFbHBvOOpw?pwd=mycu 

PWD：mycu


Link2: https://1drv.ms/f/c/f0f596fd5598cb73/EmsAs3OUbN1Kl-ymejXBN04BpYd_EAR23nigm1_5eghG7A

PWD: 123456789



### Datasets Usage guidelines
1. Each task provides an image file and a corresponding JSON file.
2. The detection and visual grounding data involve coordinate transformation. Taking the horizontal bounding box as an example, assume the horizontal bounding box for the original detection data  is [x0, y0, w, h], and the dimensions of the image are width and height. The coordinate transformation is performed as follows:
   
   First, performing padding：
```Shell
     if height > width:
        pad_x0 = int((height - width) / 2)
        pad_y0 = 0
        width = height
    else:
        pad_x0 = 0
        pad_y0 = int((width - height) / 2)
        height = width
```
   Then, performing normalization：
```Shell
        x0 = x0 + pad_x0
        y0 = y0 + pad_y0
        sx0 = x0 / width
        sy0 = y0 / height
        sx1 = (x0 + w) / width
        sy1 = (y0 + h) / height
```
Finally, [sx0, sy0, sx1, sy1] is the format of the detection boxes used for the detected part of the data in MMRS-1M.




## :bookmark: Citation
```bash
@article{zhang2024earthgpt,
  title={Earthgpt: A universal multi-modal large language model for multi-sensor image comprehension in remote sensing domain},
  author={Zhang, Wei and Cai, Miaoxin and Zhang, Tong and Zhuang, Yin and Mao, Xuerui},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  year={2024},
  publisher={IEEE}
}
```

## :memo: Acknowledgment
This paper benefits from [llama](https://github.com/facebookresearch/llama). Thanks for their wonderful work.

## :envelope: Contact
If you have any questions about EarthGPT, please feel free to contact w.w.zhanger@gmail.com.

