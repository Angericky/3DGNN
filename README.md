# 3DGNN
This is a Caffe implementation of 3DGNN 

<img src="./overallpipeline.png"/>

## Setup

### Requirement
Required CUDA (7.0) + Ubuntu14.04.

### Installation

For installation, please follow the instructions of [Caffe](https://github.com/BVLC/caffe) and [DeepLab v2](https://bitbucket.org/aquariusjay/deeplab-public-ver2).

### Data Preparation
1. Download the provided data (https://mycuhk-my.sharepoint.com/:u:/r/personal/1155051740_link_cuhk_edu_hk/Documents/model.zip?csf=1&e=RGs6HI).
2. Download the prepared training data (prepared hdf5 data) (https://mycuhk-my.sharepoint.com/:u:/r/personal/1155051740_link_cuhk_edu_hk/Documents/traindata.zip?csf=1&e=8hBkce.).
3. Download the testing data  (https://mycuhk-my.sharepoint.com/:u:/r/personal/1155051740_link_cuhk_edu_hk/Documents/testdata.zip?csf=1&e=6PnqDn).
4. Download the original provided data (https://mycuhk-my.sharepoint.com/:u:/r/personal/1155051740_link_cuhk_edu_hk/Documents/provided_data.zip?csf=1&e=1BAUNL).

### Usage

1. Clone the repository.

2. Build Caffe and matcaffe:

   ```shell
   cd caffe_code
   make -j8 && make matcaffe
   ```

3. Inference:

   - Evaluation code is in folder 'matlabscript'. 
   - Download trained models and unzip it. Pretrained model is saved in folder "model/nyu_40/". 
   ```shell
   cd matlabscript
   run nyu_crop_data_mask_msc.m
   ```
   - The result is saved in folder "../result/nyu_40_msc/"
4. Training:

   - Training data preparation
   ```shell
       cd matlabscript
       run generatedata (setting training = true)
       cd ..
       cd train_data_hdf5_file_generate
       python generate_hdf5
       cd ..
      ```
      We have also provided the training data in folder "traindata/"
   - Run caffe training


   
## Citation
If you use our code for research, please cite our paper:

```
@inproceedings{qi20173d,
  title={3D Graph Neural Networks for RGBD Semantic Segmentation},
  author={Qi, Xiaojuan and Liao, Renjie and Jia, Jiaya and Fidler, Sanja and Urtasun, Raquel},
  booktitle={ICCV},
  year={2017}
}
```

## Question
If you have any question or request about the code and data, please email me at qxj0125@gmail.com . If you need more information for other datasets plesase send email. 

## License
MIT License
