# Installation
**Windows 11**

1.  [Directories](#Directories)
2.  [MCO](#MCO)
3.  [Python](#-Python)
4.  [Python modules](#Python-modules)
5.  [CUDA Toolkit](#CUDA-Toolkit)
6.  ['PyTorch' module](#'PyTorch-module')
7.  [FFMpeg](#FFMpeg)
8.  [MKVmerge](#MKVmerge)
9.  [AviSynth+](#AviSynth+)
10. [Avisynth+ filters and plugins](#Avisynth+-filters-and-plugins)
11. [AnimeSR](#AnimeSR)
12. [Real-CUGAN](#Real-CUGAN)
13. [ESRGAN](#ESRGAN)
14. [Models](#Models)
<!-- 15. [Vérification de l'installation](#Vérification-de-l-installation)-->

<br/><br/>

## Directories
-----------------------------------------
```
D
├── mco
├── mco_3rd_party
```
note: do not create the `mco` as it will be created
<br/>

## MCO
-----------------------------------------
- Change current directory (here, 'D'):
```bash
git clone https://github.com/JepEtau/mco.git
```
<br/>

## Conda
-----------------------------------------
- Miniconda: [Install](https://docs.conda.io/en/latest/miniconda.html), "Latest Miniconda Installer Links"
- [Managing environments](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)

```bash
conda create -n mco python=3.11
```

```bash
conda activate mco
```

<br/>


## Python modules
-----------------------------------------

From the **`mco`** directory:
```bash
pip install -r requirements.txt
```

<!-- TODO: investigate (requirements for dnn_superres)
```
    pip uninstall opencv-python
    pip uninstall opencv-contrib-python
    pip install opencv-python-rolling==4.7.0.20230211
``` -->


<br/>

## CUDA Toolkit
-----------------------------------------
- Version: 11.8
- Download link [NVDIA developper](https://developer.nvidia.com/cuda-11-8-0-download-archive):
    * Operating System: Windows
    * Architecture: x86_64
    * Version: 11
    * Installer Type: exe(local) or exe(network)

<br/>

## 'PyTorch' module
-----------------------------------------
- Version: 11.8
- Copy the command line from [PyTorch](https://pytorch.org/get-started/locally/)
- Example:
    * PyTorch: Stable (2.0.0)
    * OS: Windows
    * Package: Conda
    * Language: Python
    * Compute Platform: Cuda 11.8
- Execute the following wommand:
```
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

<br/>

## FFMpeg
-----------------------------------------
- [Download](https://ffmpeg.org/download.html), "release builds", version 6,  static

- Install in **`mco_3rd_party/ffmpeg-6.0-essentials_build`** directory

If a different version/directory is used, the [database/directories.ini](./database/directories.ini) file shall be modified

<br/>

## MKVmerge
-----------------------------------------
- [MKVToolNix](https://mkvtoolnix.download)
- "Installer (64-bits)"

<br/>

## AviSynth+
-----------------------------------------
- https://avs-plus.net/
- x64 version


## Avisynth+ filters and plugins
-----------------------------------------
- [AviSynth](http://avisynth.nl/index.php/Main_Page)
<br/>

**- If you do not use or do not know how to use AviSynth+**
- Before installing, the following directory structure shall be created
    ```
    mco_3rd_party
    ├── avisynth_plugins
        ├── plugins
        ├── plugins+
        ├── plugins64
        ├── plugins64+
    ```
- During the installation, select 'Customize Plugins Paths' option. Then set the directories accordingly to the above directory structure
<br/>

**- Otherwise, you should be able to find the directory to store the AviSynth+ filters/plugins**

- In **`plugins64+`** directory (use the x64 version for each filter/plugin)
    * ffms2.dll [[FFmpegSource](http://avisynth.nl/index.php/FFmpegSource)]
    * QTGMC.avsi  [[QTGMC](http://avisynth.nl/index.php/QTGMC)]
    * masktools2.dll [[MaskTools2](http://avisynth.nl/index.php/MaskTools2)]
    * DePan.dll, DePanEstimate.dll, mvtools2.dll [[MVTools2](http://avisynth.nl/index.php/MVTools)]
    * nnedi3.dll [[Nnedi3](http://avisynth.nl/index.php/Nnedi3)] (Release_W7_AVX2)
    * RgTools.dll [[RgTools](http://avisynth.nl/index.php/RgTools)]
    * Zs_RF_Shared.avsi [[Zs_RF_Shared](http://avisynth.nl/index.php/Zs_RF_Shared)]
    * eedi3.dll [[EEDI3](http://avisynth.nl/index.php/Eedi3)]
    * aWarpsharpMT.dll [[AWarpSharp2](http://avisynth.nl/index.php/AWarpSharp2)]
    * dfttest.dll [[Dfttest](http://avisynth.nl/index.php/Dfttest)]

<br/>

## AnimeSR
-----------------------------------------
- [AnimeSR](https://github.com/TencentARC/AnimeSR)

Change current directory to **`mco_3rd_party`**:
```bash
# Clone
git clone https://github.com/TencentARC/AnimeSR.git

# Install dependent packages
cd AnimeSR
pip install -r requirements.txt

# Install AnimeSR
python setup.py develop
```
<br/>

## Real-CUGAN
-----------------------------------------
- [Real-CUGAN](https://github.com/bilibili/ailab)

Change current directory to **`mco_3rd_party`**:
```bash
git clone https://github.com/bilibili/ailab.git
```
<br/>

## ESRGAN
-----------------------------------------
- [ESRGAN](https://github.com/JoeyBallentine/ESRGAN)

Change current directory to **`mco_3rd_party`**:
```bash
git clone https://github.com/joeyballentine/ESRGAN.git
```

**Install**
```bash
cd ESRGAN
pip install --user -r requirements.txt
```


## Models
-----------------------------------------
[Model Database](https://upscale.wiki/wiki/Model_Database)
<br/>
[OpenModelDB](https://openmodeldb.info/)

Create the following directory structure:
```
mco_3rd_party
├── models
    ├── animesr
    ├── pytorch
    ├── real_cugan
    ├── scunet
```

- In the `animesr` folder
    * AnimeSR_v2.pth [[Google Drive](https://drive.google.com/drive/folders/1gwNTbKLUjt5FlgT6PQQnBz5wFzmNUX8g?usp=share_link)]

<br/>
<!--
- In `dnn_superres`
    * EDSR_x2.pb [[github](https://github.com/Saafke/EDSR_Tensorflow/tree/master/models)]
    * FSRCNN_x2 [[github](https://github.com/Saafke/FSRCNN_Tensorflow/tree/master/models)] -->

- In the `pytorch` folder, depuis [OpenModelDB/](https://openmodeldb.info/)
    * 2x_LD-Anime_Skr_v1.0.pth [[Model Database](https://upscale.wiki/wiki/Model_Database#Anime_and_Cartoons)]
    * 1x_HurrDeblur_SuperUltraCompact_nf24-nc8_244k_net_g.pth
    * 2xESRGAN.pth [[Model Database](https://upscale.wiki/wiki/Model_Database#Pretrained_Models)]
    * realesr-animevideov3.pth
    * 2x_LD-Anime_Compact_330k_net_g.pth
    * 1x_BeaverIt.pth


<br/>

- In the `real_cugan` folder: [updated_weights.zip](https://github.com/bilibili/ailab/releases/tag/Real-CUGAN)
    * up2x-latest-conservative.pth
    * up2x-latest-denoise1x.pth
    * up2x-latest-denoise2x.pth
    * up2x-latest-denoise3x.pth
    * up2x-latest-no-denoise.pth

<br/>

- In the `scunet` folder:
    * [scunet_color_real_gan](https://github.com/cszn/KAIR/releases/download/v1.0/scunet_color_real_gan.pth)
    * [scunet_color_real_psnr.pth](https://github.com/cszn/KAIR/releases/download/v1.0/scunet_color_real_psnr.pth)

