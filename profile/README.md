# BEV Fusion with PointPainting & Heading Extract

## Goals

- Sensor Fusion을 통한 **3D Object Detection, Segmentation**
  - BEV Fusion 앞단 부분의 Fusion 방식 변경
  - PointPainting 모델을 활용하여 LiDAR Point Cloud Painting
  - 그 결과 나온 LiDAR Painting을 BEV로 변환
  - BEV로 변환된 LiDAR Point를 BEV Fusion Shared-BEV Encoder 형태로 Encoding
- **Heading** 시각화

> **BEV Fusion을 main으로 진행 → Feature Extractor를 변경해보며 성능 비교**
> 
> - BEVFusion : Multi-Task Multi-Sensor Fusion with Unified Bird’s-Eye View Representation
> - PointPainting : Sequential Fusion for 3D Object Detection

> **BEV Fusion의 Output에 추가적인 알고리즘 개발**
> 
> - 장애물의 위치, 크기, Heading, Object Tracking 등 후처리 작업 

## Definitions

> VoxelNet 기반인 **BEV Fusion의 Sensor Fusion 방식을 Pointpainting Model로 변경**하여 Voxelize 범위를 줄여 기존 Model과 성능을 비교한다. <br>
장애물의 위치, 크기, **Heading, Object Tracking 등 후처리 작업**을 진행한다.
> 

## Overview
<img src = "https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fb17daaef-a691-4340-8c69-d14d42b4e96e%2FBEV_Fusion__PointPainting.png?table=block&id=49c258e5-f892-420a-b54f-3b408f62b062&spaceId=b8076850-8628-41ea-9b5e-a3111230d0da&width=2000&userId=f870e9fc-2ee6-43cd-9de6-36b30dcf91c5&cache=v2" alt = "Process → BEV Fusion + PointPainting " />

> **2D Camera와 3D LiDAR**를 **Sensor Fusion**하여 3D Object Detection을 하는 방법을 제안한 **BEV Fusion의 Sensor Fusion 방식을 Pointpainting Model로 변경**
Image의 정보를 잃지 않으면서 원하는 Object의 LiDAR 정보를 가져온다. 
> <br> Detection 하고자 하는 객체만 Voxelize한 Feature를 학습시킨다. 
> <br> **Image 정보를 손실하지 않는 PointPainting의 장점과 World 좌표계의 정보를 담을 수 있는 BEV 장점을 모두 활용할 수 있는지 확인**한다.
> <br> 이후 장애물의 위치, 크기, **Heading, Object Tracking** 등 **후처리 작업**을 진행한다.

## Feature Implementation, Requirementes List 

- 2D Camera & 3D LiDAR Sensor Fusion
- **3D Object Detection**
- **BEV**
- **Heading**
- Object Tracking

## Skills

`C++` `Python` `PyTorch` `Cuda` `OpenCV`
