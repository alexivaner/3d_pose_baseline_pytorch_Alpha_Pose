# 2D Alpha Pose to 3D Skeleton 
 Another Contributor: [Rashid Ali](https://github.com/rashidch) <br>
 This is one of the repository code for Variable View Position and Angle Human Behavior inside the Elevator<br>
 For our paper click  [here](https://github.com/alexivaner)
 
 This code is for predicting 2D Alpha Pose to 3D Pose using 3D Pose Baseline. All of the neural network here is built using Pytorch. For full code including classification, you can click [here](https://github.com/alexivaner)<br>
 
 ## Related Repository
 I developed this code from related works below. Thank you for providing nice code for research purposes:
 1. [3D Pose Baseline](https://github.com/una-dinosauria/3d-pose-baseline)
2. [3D Pose Baseline Pytorch Implementation](https://github.com/weigq/3d_pose_baseline_pytorch)
3. [2D Open Pose to 3D Skeleton](https://github.com/ArashHosseini/openpose)
 
# OUR CONTRIBUTION
Below is our contribution in this repository:<br>
1. Using Alpha Pose as an input to estimate its 3D Pose Estimation
2. Improve 3D Pose Baseline Accuracy by tuning the hyperparameter using Optuna Hyperparameter Search
3. Provide function to map COCO Skeleton Format to Human3.6M Format
4. Provide function to transform 3D Skeleton to another reference skeleton (To match angle and position between two skeleton)
5. Provide normalization of Human3.6M skeleton using Eucledian Distances
6. Provide jupyter notebook for visualize all the skeleton result (You can use this one for research purposes)

# OUR TASK
## Problem Scenario
<img src="https://user-images.githubusercontent.com/57290644/118956032-d3d0b900-b991-11eb-9f57-f050fe01d50b.png" width="600">

## Previous Method
<img src="https://user-images.githubusercontent.com/57290644/118956139-ea771000-b991-11eb-906e-7c1edf6451c7.png" width="600">

## Our Method
<img src="https://user-images.githubusercontent.com/57290644/118956223-febb0d00-b991-11eb-9eff-603b1cf1c7e2.png" width="600">

# Result
## 2D Alpha Pose to 3D Result 
| | RGB Image | Alpha Pose | Human 3.6M 2D | Human 3.6M 3D |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Falling (Scenario 1) | ![image](https://user-images.githubusercontent.com/57290644/118960939-5ce9ef00-b996-11eb-97c9-e24cb63a0847.png) | ![image](https://user-images.githubusercontent.com/57290644/118960963-62473980-b996-11eb-881d-0d60934207c9.png) | ![image](https://user-images.githubusercontent.com/57290644/118960981-683d1a80-b996-11eb-8e59-3fd2972a0e71.png) | ![image](https://github.com/alexivaner/3d_pose_baseline_pytorch_Alpha_Pose/blob/main/img/test_dataset/Fall_4000.gif) |
| Falling (Scenario 2) | ![image](https://user-images.githubusercontent.com/57290644/118958239-d03e3180-b993-11eb-9a87-2e827783b541.png) | ![image](https://user-images.githubusercontent.com/57290644/118958259-d502e580-b993-11eb-81a6-77b018d9da49.png) | ![image](https://user-images.githubusercontent.com/57290644/118958335-e9df7900-b993-11eb-92a0-d989c86a5f04.png) | ![image](https://github.com/alexivaner/3d_pose_baseline_pytorch_Alpha_Pose/blob/main/img/test_dataset/Fall_1500.gif) |
| Walk Dog (Human3.6M Dataset) | ![image](https://user-images.githubusercontent.com/57290644/118961472-eef1f780-b996-11eb-9ae5-feda7bc69e2d.png) | ![image](https://user-images.githubusercontent.com/57290644/118961518-f9ac8c80-b996-11eb-942f-7674b21956d1.png) | ![image](https://user-images.githubusercontent.com/57290644/118961539-ffa26d80-b996-11eb-86d0-a7667f4d729e.png) | ![image](https://github.com/alexivaner/3d_pose_baseline_pytorch_Alpha_Pose/blob/main/img/test_dataset/2%20-%20Walkdog_PredAlpha_900.gif) |
| Direction (Human 3.6M Dataaset) | ![image](https://user-images.githubusercontent.com/57290644/118961871-60ca4100-b997-11eb-8715-0ab3a3d3a884.png) | ![image](https://user-images.githubusercontent.com/57290644/118961887-64f65e80-b997-11eb-8570-ca384437cd94.png) | ![image](https://user-images.githubusercontent.com/57290644/118961933-70498a00-b997-11eb-984e-e384424e647e.png) | ![image](https://github.com/alexivaner/3d_pose_baseline_pytorch_Alpha_Pose/blob/main/img/test_dataset/1%20-%20Direction_PredAlpha_80.gif) |

## Angle Transformation Result 
This test is using multicam dataset where the same action taken with 8 different camera angle at the same time. We try to transform all the angles to angle of camera 4. For example, we train our classification module with angle from camera 4, using this transformation, we do not need to train new data from another camera angle. Instead, we could transform other angle to camera 4.
|  | Test 1 - Standing | Test 2  - Falling |
| ------------- | ------------- | ------------- |
| RGB Image | <img src="https://user-images.githubusercontent.com/57290644/118962290-cc141300-b997-11eb-873b-b34093ff1733.png" width="400"> | <img src="https://user-images.githubusercontent.com/57290644/118964096-b6075200-b999-11eb-922c-5849f106e4db.png" width="400"> |
| 2D Pose Estimation | <img src="https://user-images.githubusercontent.com/57290644/118962307-d0d8c700-b997-11eb-9f73-1dd419b2a59b.png" width="400"> | <img src="https://user-images.githubusercontent.com/57290644/118964285-ef3fc200-b999-11eb-94de-7fa6cb0f5935.png" width="400"> |
| 3D Inference Result | <img src="https://user-images.githubusercontent.com/57290644/118962316-d3d3b780-b997-11eb-9448-80a83be9cca4.png" width="400"> | <img src="https://user-images.githubusercontent.com/57290644/118964617-434aa680-b99a-11eb-8b5c-0244761dfbb5.png" width="400"> |
| Transform another angle to CAM 4 | <img src="https://user-images.githubusercontent.com/57290644/118962346-dafac580-b997-11eb-9baa-c82792d448e8.png" width="400"> | <img src="https://user-images.githubusercontent.com/57290644/118964736-67a68300-b99a-11eb-9ee1-c26ffb85fcdc.png" width="400"> |
| Map back to 2D Skeleton | <img src="https://user-images.githubusercontent.com/57290644/118962612-21e8bb00-b998-11eb-9553-d287895ad414.png" width="400"> | <img src="https://user-images.githubusercontent.com/57290644/118964883-96245e00-b99a-11eb-8550-a1512d945058.png" width="400"> |

## Optimization with Optuna 
Original version is refer to original 3D Pose Baseline from [this repository](https://github.com/una-dinosauria/3d-pose-baseline) <br>
Pytorch version is refer to original 3D Pose Baseline from [this repository](https://github.com/weigq/3d_pose_baseline_pytorch) (I retrain with their default setting) <br>
We try to do hyperparameter tuning using optuna and found better result with better MJPE (Mean Per Join Position Error)

|  | direct. | discuss. | eat. | greet. | phone | photo | pose | purch. | sit | sitd. | somke | wait | walkd. | walk | walkT | avg |
| :--: | :--: | :--: | :--: | :--: |  :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| original version | 37.7 | 44.4 | 40.3 | 42.1 | 48.2 | 54.9 | 44.4 | 42.1 | 54.6 | 58.0 | 45.1 | 46.4 | 47.6 | 36.4 | 40.4 | 45.5|
| pytorch version | 35.9 | 42.9 | 37.3 | 40.2 | 43.1 | 51.2 | 44.0 | 37.9 | 51.9 | 53.0 | 41.4 | 42.1 | 43.6 | 32.8 | 35.2 | 42.2 |
| <b>Ours</b> | <b>35.0</b> | <b>40.8</b> | <b>36.0</b> | <b>39.1</b> | <b>42.8</b> | <b>48.7</b> | <b>41.8</b> | <b>37.0</b> | <b>47.8</b> | <b>47.9</b> | <b>40.2</b> | <b>41.1</b> | <b>41.7</b> | <b>31.4</b> | <b>33.0</b> | <b>40.3</b> |


# License
MIT
