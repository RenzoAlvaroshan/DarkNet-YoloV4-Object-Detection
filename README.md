# Learning Notes - DarkNet YoloV4 Object Detection Tutorial for Windows 10

![hqdefault](https://user-images.githubusercontent.com/55566616/128143459-7fb461b1-7ab4-4bc8-91d4-6ffdd941aff1.jpg)

Learning Notes - DarkNet YoloV4 Object Detection Tutorial for Windows 10

---

Source: [YouTube Com (2021) - Darknet YOLOv4 Object Detection Tutorial for Windows 10 on Images, Videos, and Webcams (TheCodingBug channel)](<https://www.youtube.com/watch?v=FE2GBeKuqpc&t=7s>)

**Table of Contents**:
1. Introduction: (0:00)
2. Prerequisite: (0:21)
3. Download Darknet: (03:31)
4. Copy cuDNN and OpenCV Files: (3:55)
5. Build Darknet using Visual Studio: (4:50)
6. Object Detection on Images: (8:53)
7. Object Detection on Videos: (9:48)
8. Object Detection on Webcams: (10:34)

---

## 01 Introduction

**Purpose**: This is a tutorial on Installing DarkNet Yolov4 prepared by, and adopted from, TheCodingBug channel from YouTube. This learning notes is for my own guide for future reference and is shared for you who encounter a problem on installing DarkNet Yolov4 for Windows 10 using Nvidia CUDA GPU and OpenCV.

**Steps**:
1. Building DarkNet
2. Object Detection on Images
3. Object Detection on Videos
4. Object Detection on Webcam

---

## 02 Prerequisite

1. [Anaconda](https://www.anaconda.com/products/individual) — package manager for mutiple version of virtual environment for Python and associated packages
4. [Visual Studio](https://visualstudio.microsoft.com/downloads/) – Integrated Development Environment (IDE) by Microsoft®
5. [CUDA](https://developer.nvidia.com/cuda-toolkit-archive) — Computing Unified Device Architecture (NVIDIA® GPU computing device driver)
6. [CUDNN](https://developer.nvidia.com/rdp/cudnn-archive) — CUDA® Deep Neural Network (NVIDIA®)
7. [OpenCV](https://github.com/AlexeyAB/darknet) — Python/C++ library for Computer Vision machine learning

### (1) Anaconda Installer

Download [Anaconda Installer](anaconda.com/products/individual): `anaconda.com/products/individual` then install it with default options.

<img width="1440" alt="Screen Shot 2021-08-04 at 16 25 46" src="https://user-images.githubusercontent.com/55566616/128157585-ae41933a-ee18-471f-8e02-cbc2fe4537a7.png">

<img width="490" alt="Anaconda3 2020 11 (64-bit) Setup" src="https://user-images.githubusercontent.com/55566616/126862344-4c2dab10-b0c8-44df-a60e-2480f2d75c7f.png">
<img width="491" alt="ANACONDA  Choose the folder in which to instal Anaconda3 2020 11 (64-bit)" src="https://user-images.githubusercontent.com/55566616/126862348-409286e2-6648-4f38-8917-55f68b22d734.png">
<img width="492" alt="Anaconda3 2020 11 (64-bit) Setup" src="https://user-images.githubusercontent.com/55566616/126862350-e348542b-7c5d-4bf3-8b91-b775248fa60a.png">
<img width="494" alt="Anaconda3 2020 11 (64-bit) Setup" src="https://user-images.githubusercontent.com/55566616/126862351-30e796ad-1f3b-4ceb-8404-673a6c1cbf54.png">
<img width="496" alt="2020 11 (64-bit) Setup" src="https://user-images.githubusercontent.com/55566616/126862355-be434046-0792-4a68-a556-73d1e5eb9948.png">

### (2) Microsoft Visual Studio

Next, download [Visual Studio Community 2019 16.7.2](https://visualstudio.microsoft.com/vs/community/) – the Community Edition: `https://visualstudio.microsoft.com/vs/community/`

<img width="1440" alt="Screen Shot 2021-08-04 at 16 32 31" src="https://user-images.githubusercontent.com/55566616/128158376-40d6c9bf-6643-48db-b7bc-dd477432e5a2.png">

Then, run the installer:

<img width="1440" alt="Screen Shot 2021-08-04 at 16 37 30" src="https://user-images.githubusercontent.com/55566616/128158980-a0ce3357-d1f6-4dd3-b871-5fd3c67ccec9.png">

Select `Desktop development with C++` option for Studio Code C++ support

<img width="1440" alt="components Language packs" src="https://user-images.githubusercontent.com/55566616/126863268-c9f0dd02-4bc3-4408-a886-0dc58b908d85.png">

<img width="1440" alt="Installation details" src="https://user-images.githubusercontent.com/55566616/126863270-c24e8363-53b4-405d-b130-51cbd7b83ade.png">

You may need to reboot your computer after installing Visual Studio.

### (3) Cuda Toolkit Update

Now download [CUDA Toolkit 11.0 Update Downloads](developer.nvidia.com/cuda-11.0-update1-download-archive?target_os=Windows&target_arch=x86_64): `developer.nvidia.com/cuda-11.0-update1-download-archive?target_os=Windows&target_arch=x86_64`

Choose `Windows` operating system for `Select Target Platform`.

<img width="1440" alt="Resources" src="https://user-images.githubusercontent.com/55566616/126863551-7019a69a-7f41-4b75-bc71-7ee6a98f8afb.png">

<img width="1440" alt="CUDA Toolkit Archive" src="https://user-images.githubusercontent.com/55566616/126863557-16f0e0f4-6d68-4004-9386-608281295170.png">

Choose `CUDA Toolkit 11.0 Update 1 Downloads`:

<img width="1440" alt="CUDA Toolkit 11 0 Update 1 Downloads" src="https://user-images.githubusercontent.com/55566616/126863575-928096f3-e790-4bc5-8eb6-fb0d728b8247.png">

Choose the following options:

* Operating System: `Windows`
* Architecture: `x86_84`
* Version: `10`
* Installer Type: `exe (local)`

<img width="1440" alt="Pasted Graphic 11" src="https://user-images.githubusercontent.com/55566616/126863930-4190691d-becf-4379-bd5b-90c09b9f3dd2.png">
<img width="1440" alt="Pasted Graphic 12" src="https://user-images.githubusercontent.com/55566616/126863932-eeda04b4-03fa-402f-8944-4c65650a8fd9.png">
<img width="1440" alt="cuDNN Download" src="https://user-images.githubusercontent.com/55566616/126863933-9c7b22b7-f63c-4293-9688-4b22d8dbe9d0.png">

Click `Download cuDNN v8.0.5 (November 9th, 2020), for CUDA 11.0` to expand the driver list:

<img width="1440" alt="Library for Windows and Linux, Ubuntulx86_64   PPC architecture)" src="https://user-images.githubusercontent.com/55566616/126863946-19fcb2f6-e307-4fd3-9ef0-c860377ee33d.png">

Click `cuDNN Library for Windows (x86)` now the driver will be downloading.

Extract the driver file (.zip) you just downloaded:

<img width="1440" alt="Pasted Graphic 15" src="https://user-images.githubusercontent.com/55566616/126863951-ecae92ed-050c-4e9d-b630-7851aa87ad2b.png">

Then copy the extracted files and folder inside `cudnn-11.0-windows-x64-v8.0.5.39` to:

`(C:) › Program Files › NVIDIA GPU Computing Toolkit › CUDA › v11.0 >`

<img width="1440" alt="Pasted Graphic 17" src="https://user-images.githubusercontent.com/55566616/126863961-5e1d3db3-6e89-4724-b816-daa72bd57cee.png">

Here you will replace some files and folders with new ones:

* `bin`
* `include`
* `lib`
* `NVIDIA_SLA_cuDNN_Support.txt`

<img width="1440" alt="Pasted Graphic 16" src="https://user-images.githubusercontent.com/55566616/126863972-8e0c6784-cfd8-4273-9ba1-fe68bca4b165.png">




---

## 03 Download Darknet

First, download [Darknet](http://github.com/AlexeyAB/darknet) from `AlexeyAB/darknet` repository on GitHub (.zip format)

<img width="1440" alt="Pasted Graphic 10" src="https://user-images.githubusercontent.com/55566616/126861852-cc87ef82-91a2-497c-9b66-49793437c5b4.png">

Then, create a folder name `darknet` in your root directory `C:\`

<img width="1440" alt="Pasted Graphic 11" src="https://user-images.githubusercontent.com/55566616/126861865-c60c8e81-fcd4-47a5-82d9-fa6f2568e8b4.png">

Open this directory: `C:/darknet/darknet-master/build/darknet/x64`

<img width="1440" alt="Pasted Graphic 12" src="https://user-images.githubusercontent.com/55566616/126861871-e08c4975-5208-4bac-9e9b-b9aaa6e8b8e0.png">

Open new window: `C:/Program Files/NVIDIA GPU Computing Toolkit/CUDA/v10.1/bin/cudnn64_7.dll`

<img width="1440" alt="Pasted Graphic 13" src="https://user-images.githubusercontent.com/55566616/126861884-8a8c3150-7182-4dcb-a6ac-1eb621de3b67.png">

Copy the `cudnn64_7.dll` file to here: `darknet › darknet-master › build › darknet › x64`

<img width="1440" alt="Pasted Graphic 14" src="https://user-images.githubusercontent.com/55566616/126861890-64059fb1-9dd3-427f-bb2e-7518ae9e91a9.png">

From `OpenCV_CUDA > build › install > x64 > vc16 > bin`, copy `opencv_world440.dll` to `darknet › darknet-master › build › darknet › x64`

<img width="1440" alt="Pasted Graphic 15" src="https://user-images.githubusercontent.com/55566616/126861897-d1b6ffb3-5ba2-460e-b301-eca64d70e382.png">

Inside `darknet › darknet-master › build › darknet`, open `darknet.vcxproj` file using code editor

<img width="1440" alt="Pasted Graphic 16" src="https://user-images.githubusercontent.com/55566616/126861903-0f480e8d-0d23-4527-800b-df8333699ed6.png">

Inside `darknet.vcxproj` file, find `CUDA 10` (ctrl+F) and change it to your CUDA version. For example: `CUDA 10.1`

<img width="1440" alt="Pasted Graphic 17" src="https://user-images.githubusercontent.com/55566616/126861908-cd7c64f0-2c60-48ed-8846-476ff7e01f44.png">

Inside `darknet › darknet-master › build › darknet`, open `yolo_cpp_dil.vcxproj` file using code editor

<img width="1440" alt="Pasted Graphic 18" src="https://user-images.githubusercontent.com/55566616/126861912-3e3dcbdf-9a58-4d02-93e5-8a73f8b426b6.png">

Inside `yolo_cpp_dil.vcxproj` file, find `CUDA 10` (ctrl+F) and change it to your CUDA version. For example: `CUDA 10.1`

<img width="1440" alt="Pasted Graphic 19" src="https://user-images.githubusercontent.com/55566616/126861915-313fae1a-52aa-44a7-9d4c-4451ffefe5bb.png">

Open `yolo_cpp_dil.vcxproj` file using Visual Studio

<img width="1440" alt="Visual Studio" src="https://user-images.githubusercontent.com/55566616/126861920-6efcce61-9e97-4363-843c-d7544696e983.png">

Click `OK`

<img width="1440" alt="Pasted Graphic 22" src="https://user-images.githubusercontent.com/55566616/126861921-eea4d344-59eb-4c6c-88ef-99b7b4a55e92.png">

Change the `Debug` to `Release`

![Pasted Graphic 23](https://user-images.githubusercontent.com/55566616/126861961-b7f2a70c-7f8d-43de-8cda-f17657215629.jpg)

On the right side, right click on `yolo_cpp.dll`

<img width="1440" alt="Pasted Graphic 25" src="https://user-images.githubusercontent.com/55566616/126861965-f1631286-7c76-40ef-8e68-c1b9201fa778.png">

Click `Build`

<img width="1440" alt="Pasted Graphic 27" src="https://user-images.githubusercontent.com/55566616/126861967-f2b4d191-310d-4e65-874c-a7f0be246e64.png">

Once it is done without any error, close it.

<img width="1440" alt="Pasted Graphic 40" src="https://user-images.githubusercontent.com/55566616/126861970-ccf897f4-4f0b-40ac-b389-4af08fcd1a84.png">

Open `darknet.sln` with Visual Studio

<img width="1440" alt="Visual Studio" src="https://user-images.githubusercontent.com/55566616/126861972-acc82f3d-596b-48ce-9b2d-5e435957b3b2.png">

Change `Debug` -> `release` and `Win32` -> `x64`

<img width="1440" alt="Pasted Graphic 41" src="https://user-images.githubusercontent.com/55566616/126861978-adcea0b8-c486-493f-b887-93ba6c0253ff.png">

Right click on `darknet.sln`, then click `properties`

![Pasted Graphic 31](https://user-images.githubusercontent.com/55566616/126862000-b1b64b7c-88ca-48fe-a1b7-9bfaf5c2b7c7.jpg)

Click `C/C++`, go to `Additional Include Directories`. Click the dropdown button and click `<Edit...>`

![Pasted Graphic 32](https://user-images.githubusercontent.com/55566616/126862003-0cbc6b39-7bc5-4660-b684-31fe90d5c07b.jpg)

The display after clicking `Edit`

<img width="1440" alt="Pasted Graphic 33" src="https://user-images.githubusercontent.com/55566616/126862004-e6236332-4e2f-4eae-912f-3b6e7bd7371f.png">

Go to `OpenCV_CUDA › build > install > include` and copy the path

<img width="1440" alt="Pasted Graphic 35" src="https://user-images.githubusercontent.com/55566616/126862008-e30c62d9-31e8-4e39-96d1-467ce063401a.png">

Copy and paste `OpenCV_CUDA\build \instal/\include` path to the `darknet.sln Additional Include Directories`

<img width="1440" alt="Pasted Graphic 36" src="https://user-images.githubusercontent.com/55566616/126862010-0724255d-7d96-4f06-909c-7cc4265ae62b.png">

Edit the `Preprocessor Definitions`

<img width="1440" alt="Pasted Graphic 37" src="https://user-images.githubusercontent.com/55566616/126862013-b939ee91-fec6-45ef-9195-b729bec51a5d.png">

(optional) if you do not have a high end GPU: remove `CUDNN_HALF`

<img width="1440" alt="Pasted Graphic 38" src="https://user-images.githubusercontent.com/55566616/126862015-2ed1277a-f5a2-496c-8d6d-8f17379e5b67.png">

Go to `CUDA C/C++` -> `Device` -> `Edit Code Generation`

<img width="1440" alt="Pasted Graphic 39" src="https://user-images.githubusercontent.com/55566616/126862017-feaf0993-9fc8-424e-9602-5ae0af571ae8.png">

Remove `compute_75,sm_75`

<img width="1440" alt="Pasted Graphic 42" src="https://user-images.githubusercontent.com/55566616/126862020-59a0afae-bed4-4410-b534-091b54160426.png">

Go to `Linker` -> `General` > `Edit Additional Library Directories`

<img width="1440" alt="Pasted Graphic 43" src="https://user-images.githubusercontent.com/55566616/126862023-f56f1b41-e181-4d64-b941-0d6b62dcf2e1.png">

Go to `OpenCV_CUDA > build › install › x64 › vc16 › lib` and copy the path

<img width="1440" alt="Pasted Graphic 44" src="https://user-images.githubusercontent.com/55566616/126862024-997ee2d8-5df5-4b5b-afda-a63592870830.png">

Paste it to `Linker -> General > Edit Additional Library Directories`

<img width="1440" alt="Pasted Graphic 45" src="https://user-images.githubusercontent.com/55566616/126862030-f4c9d006-d3c9-494f-83bc-304cb21f9d76.png">

Right click on `darknet` and `build`

<img width="1440" alt="Pasted Graphic 46" src="https://user-images.githubusercontent.com/55566616/126862040-8b98a7f6-aa14-4089-927c-09af950283b7.png">

After finished without error, close the Visual Studio. You will find your `darknet.exe` inside `darknet › darknet-master › build › darknet › x64`

<img width="1440" alt="Pasted Graphic 47" src="https://user-images.githubusercontent.com/55566616/126862044-a003219c-6d23-476f-8511-7fc12988bdec.png">

Download `YoloV4.weights` file

<img width="1440" alt="Pasted Graphic 49" src="https://user-images.githubusercontent.com/55566616/126862054-32b6c0ea-6df8-4722-924e-fce7836de8a3.png">

<img width="1440" alt="Pasted Graphic 50" src="https://user-images.githubusercontent.com/55566616/126862062-3e1addb9-df49-45f0-84b8-617105d8388b.png">

Copy the `yolov4.weights` to here: `darknet > darknet-master > build › darknet > x64`

<img width="1440" alt="Pasted Graphic 51" src="https://user-images.githubusercontent.com/55566616/126862073-635fb67b-db25-4bff-86aa-5ef39047cc44.png">

Also copy a video to test the model (for ex: `japan.mp4`)

<img width="1440" alt="Pasted Graphic 52" src="https://user-images.githubusercontent.com/55566616/126862074-cec7e1bd-e0bd-47c2-9285-505509d4c814.png">

---

## 04 Copy cuDNN and OpenCV Files: (3:55)



---

## 05 Build Darknet using Visual Studio: (4:50)




---

## 06 Object Detection on Images: (8:53)

Open Anaconda prompt. Run: `darknet.exe detector test cfg/coco.data cfg/yolov4.cfg yolov4. weights`

<img width="1440" alt="Pasted Graphic 53" src="https://user-images.githubusercontent.com/55566616/126862079-0c10c9d3-3b87-4eb5-8da4-74024cc72f60.png">

Input image file name

<img width="1440" alt="Pasted Graphic 54" src="https://user-images.githubusercontent.com/55566616/126862082-e0fdff17-7f3c-4b70-bd3c-50fdd364683c.png">

This is the result

<img width="1440" alt="bicyclo 0 92" src="https://user-images.githubusercontent.com/55566616/126862121-8fc16275-c943-45a5-b891-60e68573de08.png">

Predicting time needed

<img width="1440" alt="Pasted Graphic 56" src="https://user-images.githubusercontent.com/55566616/126862124-cab09038-4111-4192-a45e-15f2f2d76118.png">

---

## 07 Object Detection on Videos: (9:48)

Run this command: `darknet. exe detector demo cfg/coco.data cfg/yolov4.cfg yolov4.weights japan.mp4`

<img width="1440" alt="Pasted Graphic 58" src="https://user-images.githubusercontent.com/55566616/126862126-f2a8f9e0-5fa6-4a3e-9ff2-43853e3a35aa.png">

This is the result:

<img width="1440" alt="Pasted Graphic 59" src="https://user-images.githubusercontent.com/55566616/126862128-ae3aeac9-5b16-4951-ac08-8d5210437ed3.png">

The Average FPS: 13.5

<img width="1440" alt="Pasted Graphic 60" src="https://user-images.githubusercontent.com/55566616/126862132-1dd9314c-0496-4eac-9b2c-14b7c78aa55d.png">

---

## 08 Object Detection on Webcams: (10:34)

Run this command: `darknet.exe detector demo cfg/coco.data cfg/yolov4.cfg yolov4.weights-c 0`

<img width="1440" alt="Pasted Graphic 61" src="https://user-images.githubusercontent.com/55566616/126862139-c8865cf3-9019-4aa7-946f-e154cc5bf5b1.png">

---

Thank you for reading the repository 🙏

Good luck! 💪


---

tag: `#learning` `#notes` `#darknet` `#yolov4` `#object` `#detection` `#tutorial` `#windows` `#2021` `#thecodingbugchannel` `#youtube` `#$$$$$`
