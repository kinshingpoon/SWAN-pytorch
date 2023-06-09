## Reducing Semantic Confusion: Scene-aware Aggregation Network for Remote Sensing Cross-modal Retrieval (ICMR2023 Oral)

Basic code to thank [GaLR](https://github.com/xiaoyuan1996/GaLR) by Yuan et al.

## Introduction

Recently, remote sensing cross-modal retrieval has received incredible attention from researchers. However, the unique nature of remote-sensing images leads to many semantic confusion zones in the semantic space, which greatly affects retrieval performance. We propose a novel scene-aware aggregation network (SWAN) to reduce semantic confusion by improving scene perception capability. In visual representation, a visual multiscale fusion module (VMSF) is presented to fuse visual features with different scales as a visual representation backbone. Meanwhile, a scene fine-grained sensing module (SFGS) is proposed to establish the associations of salient features at different granularity. A scene-aware visual aggregation representation is formed by the visual information generated by these two modules. In textual representation, a textual coarse-grained enhancement module (TCGE) is designed to enhance the semantics of text and to align visual information. Furthermore, as the diversity and differentiation of remote sensing scenes weaken the understanding of scenes, a new metric, namely, scene recall is proposed to measure the perception of scenes by evaluating scene-level retrieval performance, which can also verify the effectiveness of our approach in reducing semantic confusion. By performance comparisons, ablation studies and visualization analysis, we validated the effectiveness and superiority of our approach on two datasets, RSICD and RSITMD. The source code is available at https://github.com/kinshingpoon/SWAN-pytorch.

![pipline](figures/pipline.png)

## Implementation

Installation

```
python==3.8.5
torch==1.11.0
torchvision==0.12.0
```

Train

```bash
# RSITMD Dataset
python train.py -g 0 -m SWAN -e SWAN --data_name rsitmd  -p checkpoint/ --epochs 50 -kf 1
# RSICD Dataset
python train.py -g 0 -m SWAN -e SWAN --data_name rsicd  -p checkpoint/ --epochs 50 -kf 1
```

Test

```bash
python test_single.py --resume 'path to model checkpoint'
```

## Datasets

All experiments are based on [RSITMD](https://github.com/xiaoyuan1996/AMFMN/tree/master/RSITMD) and [RSICD](https://github.com/201528014227051/RSICD_optimal) datasets.

## Results

![result](figures/result.png)



## Citation

If you find this code useful for your work or use it in your project, please consider citing:

```
@inproceedings{pan2023reducing,
  title={Reducing Semantic Confusion: Scene-aware Aggregation Network for Remote Sensing Cross-modal Retrieval},
  author={Pan, Jiancheng and Ma, Qing and Bai, Cong},
  booktitle={Proceedings of the 2023 ACM International Conference on Multimedia Retrieval},
  pages={398--406},
  year={2023}
}
```
