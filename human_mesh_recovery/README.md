# Human Mesh Recovery (HMR) part:


**"VITA: ViT Acceleration for Efficient 3D Human Mesh Recovery via Hardware-Algorithm Co-Design", DAC 2024**

Please check the instruction for running VITA.

<!-- <div align="center">
<img src="assets/potter.gif" height="160"> 
</div> -->



## Installation instructions

Please follow the installation instructions from [HybrIK](https://github.com/Jeff-sjtu/HybrIK) since our code is built based on HybrIK. 


## Download models

Please follow the download instructions from [HybrIK](https://github.com/Jeff-sjtu/HybrIK) to get the required files since our code is built based on HybrIK.

* Download the SMPL model `basicModel_neutral_lbs_10_207_0_v1.0.0.pkl` from [here](https://smpl.is.tue.mpg.de/) at `common/utils/smplpytorch/smplpytorch/native/models`.
* Download our VITA demo model from [ [Google Drive](https://drive.google.com/file/d/1tLpMCbC6-M3Yxxsn5OoHbo8JuJLO5opZ/view?usp=sharing)].

## Demo
First make sure you download the pretrained model and place it in the `${ROOT}/eval` directory, i.e., `./eval/vita_demo.pth`.

Also, make sure you have run this command in the installation instruction.

``` bash
python setup.py develop 
```

* Visualize POTTER on **images**:

``` bash
python scripts/demo_image_vita.py --img-dir examples/coco --out-dir examples/res_coco
```

* Visualize POTTER on **videos** (frame by frame reconstruction) and save results:

``` bash
python scripts/demo_video_vita.py --video-name examples/d1.mp4 --out-dir examples/res_d1
```

## Fetch data
Please follow the download instructions from [HybrIK](https://github.com/Jeff-sjtu/HybrIK) to get the dataset since our code is built based on HybrIK. 



## Training
Please download the pretrained weights first and place it in the `${ROOT}/model_files` directory, :
* Download our VITA pretrained weights from [ [Google Drive](https://drive.google.com/file/d/1l3PjYwGn2lx4xUWFZBLh9Q7iZSQG9sy0/view?usp=sharing)].

To train VITA:
``` bash
./scripts/train_smpl_cam.sh train_potter ./configs/vita_cam_w_pw3d.yaml
```
To evaluate:
``` bash
./scripts/validate_smpl_cam.sh ./configs/vita_cam_w_pw3d.yaml [ckp_path]
```

## Citing
If our code helps your research, please consider citing the following paper:

    @inproceedings{tian2024vita,
        title={VITA: ViT Acceleration for Efficient 3D Human Mesh Recovery via Hardware-Algorithm Co-Design},
        author={Tian, Shilin and Szafranski, Chase and Zheng, Ce and Yao, Fan and Louri, Ahmed and Chen, Chen and Zheng, Hao},
        booktitle={61st ACM/IEEE Design Automation Conference (DAC)},
        year={2024},
        organization={ACM/IEEE}
    }
