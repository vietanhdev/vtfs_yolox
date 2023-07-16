# YOLOX for VIA Traffic Sign dataset

These instructions guide you to train and infer the YOLOX model on [VIA Traffic Sign dataset](https://github.com/makerhanoi/via-datasets).

## 1. Prepare environment

- Clone and install YOLOX using instructions from the official repository:

```
git clone https://github.com/Megvii-BaseDetection/YOLOX
```

- Clone source code for training with VIA Traffic Sign dataset:

```
cd YOLOX
git clone https://github.com/vietanhdev/vtfs_yolox.git
```

## 2. Dataset preparation

Download and extract VIA traffic sign dataset:

```
bash vtfs_yolox/download_data.sh
```

## 3. Training

```
export YOLOX_DATADIR=datasets/vtfs/
python3 tools/train.py -f vtfs_yolox/exps/tfs_nano.py -b 8
```

## 4. Inference 

```
python vtfs_yolox/pth_inference.py webcam -f vtfs_yolox/exps/tfs_nano.py -c best_ckpt.pth.tar --conf 0.25 --nms 0.45 --tsize 416 --device cpu --save_result
```



