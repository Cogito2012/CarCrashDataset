# :oncoming_automobile: CarCrashDataset
This repo contains our car crash dataset (CCD) for traffic accident anticipation.

## Contents
0. [Overview](#overview)
0. [Download](#download)
0. [Description](#description)
0. [Citation](#citation)

<a name="overview"></a>
## :globe_with_meridians:  Overview 

<img src="assets/CCD.png" 
alt="RIT-18 Samples" width="600"/></a>

Car Crash Dataset (CCD) is collected for traffic accident analysis. It contains real traffic accident videos captured by dashcam mounted on driving vehicles, which is critical to developing safety-guaranteed self-driving systems. CCD is distinguished from existing datasets for diversified accident annotations, including environmental attributes (day/night, snowy/rainy/good weather conditions), whether ego-vehicles involved, accident participants, and accident reason descriptions. An overview of our accident annotations are dipicted in the figure above.

<a name="download"></a>
## :file_cabinet:  Download 

Download from [Google Drive](https://drive.google.com/drive/folders/1ao-wCdQkWRYJMtWlDLPQEg9_y9d5K803?usp=sharing)

<a name="description"></a>
## :card_index_dividers:  Description

### File structure of the dataset
```
CarCrash
├── codes                    # useful codes for analyzing the dataset
├── vgg16_features
│   ├── positive             # feature files of possitive (accident) videos
│   │   ├── 000001.npz
│   │   ├── ...
│   │   └── 001500.npz
│   ├── negative             # feature files of negative (normal) videos
│   │   ├── 000001.npz
│   │   ├── ...
│   │   └── 003000.npz
│   ├── train.txt            # list file of training split 
│   └── test.txt             # list file of testing split 
├── res101_features
│   # the same structure as folder `vgg16_features`
├── videos
│   ├── Normal               # normal driving videos
│   │   ├── 000001.mp4
│   │   ├── ...
│   │   └── 003000.mp4
│   ├── Crash-1500           # crash accident videos
│   │   ├── 000001.mp4
│   │   ├── ...
│   │   └── 001500.mp4
│   └── Crash-1500.txt       # annotation file for crash accident
└── README.txt
```

### Annotation Format

The annotations of 1,500 accident videos are saved in the file `CarCrash/videos/Crash-1500.txt`. For each line, the followings are provided:

 > * **vidname**: Video name of each accident video, i.e., `000001`
 > * **binlabels**: Binary labels of all 50 frames for each video. Label `1` indicates accident frame.
 > * **startframe**: The zero-padded starting frame of each video in original untrimmed YouTube video.
 > * **youtubeID**: The numeric ID of original YouTube video identifier.
 > * **timing**: Timing conditions, i.e., `Day` and `Night`.
 > * **weather**: Weather conditions, i.e., `Normal`, `Snowy`, and `Rainy`.
 > * **egoinvolve**: Boolean identifier to indicate wheather the ego-vehicle is involved in the accident of this video.

 **Note**: Current version of CCD only provides the temporal annotations and environmental attributes listed above. For more detailed annotations such as traffic accident reasons and tracklets, we will release them soon.


 <a name="citation"></a>
## :bookmark_tabs:  Citation

Please cite our paper if you find our dataset useful.

```
@InProceedings{BaoMM2020,
    author = {Bao, Wentao and Yu, Qi and Kong, Yu},
    title  = {Uncertainty-based Traffic Accident Anticipation with Spatio-Temporal Relational Learning},
    booktitle = {ACM Multimedia Conference},
    month  = {May},
    year   = {2020}
}
```

If you have any questions about the dataset, please feel free to contact [Wentao Bao](mailto:wb6219@rit.edu).