

# Introduction
This is a YOLOV7 based APEX and CSGO Aimbot
![apex](sample/apex.jpg)
![csgo](sample/csgo.jpg)
`Note: This is an educational purposes only software, do not use it for any commercial or illegal purposes, we will not be responsible for any unauthorized usage of this software` 

## If you like it, please give me a star, thanks!

# Features
- Model can differentiate the enemy and friend
- PID smooth moving
- Individual process to display detection results in real time
- Customize personalized settings through config file
- Tensorrt speed up (solving the shaking problem when speed is fast)
- Encrypt onnx and trt model
- Manage users using `http://www.ruikeyz.com/`
- Save screenshot while locking or detected -> collect new dataset (false positive and negative)
- Annotate images using current models -> faster annotation
- Package to exe

# Environment
My envrionment uses python3.7
```
conda create -n apex python=3.7
conda activate apex
pip install pipwin
pipwin install pycuda
pip install -r requirements.txt
```
Copy `cuda11.3 with tensorrt` to the base directory [download here](https://cowtransfer.com/s/83210de2f95c4d)

# Export pt to onnx (This repo provides the onnx model, thus ignore)
`python utils/export_pt_to_onnx.py --weights weights/best.pt --grid --end2end --simplify --topk-all 12 --iou-thres 0.65 --conf-thres 0.35 --img-size 640 640`

# Run 
Running for apex (default hold left button to auto aim):

`python apex.py`

Running for csgo (default hold side button to auto aim and shoot):

`python csgo.py`

You can get the customized settings in `configs/apex.yaml` or `configs/csgo.yaml`, set your suitable `smooth` hyperparameter

# Annotate the dataset using current model
`python utils/anno_imgs.py --data_dir your_dataset_dir --engine_path your_trt_engine_path`

# Contact

This repository is the open-source community version and does not provide an executable .exe program. If you need the .exe program, please go to this repository: https://github.com/ApexPluto/ApexPluto_AIMBOT, or you can join our QQ group is 644134220 for technical communication
