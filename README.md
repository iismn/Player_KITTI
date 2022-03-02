![header](https://capsule-render.vercel.app/api?type=rect&color=timeGradient&text=KITTI%20PLAYER&fontSize=20)

## <div align=left>REPO INFO</div>  
- KITTI Raw Dataset Player
- Initial Release (v1.0.0)

## <div align=left>REPO CONFIG</div>  
### kitti2bag.py
- Main PKG
### utils.py
- Veloyne PCL Label Packing
* File Directory Consist with
```bash
├── 2011_09_26
│   ├── 2011_09_26_synced
│   │    ├── oxts 
│   │    ├── label 
│   │    ├── points 
│   │    ├── camera 1~4 
│   │    ├── camtoimu.txt
│   │    ├── imutovel.txt
│   │    └── camtovel.txt
│   └── 2011_09_26_extract
│        └── oxts 
├── kitti2bag.py
└── util.py
``` 



## <div align=left>REPO USE</div> 
```bash
wget https://s3.eu-central-1.amazonaws.com/avg-kitti/raw_data/2011_09_26_drive_0084/2011_09_26_drive_0084_sync.zip
wget https://s3.eu-central-1.amazonaws.com/avg-kitti/raw_data/2011_09_26_drive_0084/2011_09_26_drive_0084_extract.zip
wget https://s3.eu-central-1.amazonaws.com/avg-kitti/raw_data/2011_09_26_calib.zip
unzip 2011_09_26_drive_0084_sync.zip
unzip 2011_09_26_drive_0084_extract.zip
unzip 2011_09_26_calib.zip
python kitti2bag.py -t 2011_09_26 -r 0084 raw_synced .
```

## <div align=left>ADD INFO</div>
#### SEMANTIC KITTI for LIO-SAM
- Only 2011_09_30 work
- Odometry 00~07 Not Tested

Kitti_player, a player for KITTI raw datasets
Datasets can be downloaded from: http://www.cvlibs.net/datasets/kitti/raw_data.php

Allowed options:
help           h    help message
directory      d    *required* - path to the kitti dataset Directory
frequency      f    set replay Frequency
all            a    replay All data
velodyne       v    replay Velodyne data
gps            g    replay Gps data
imu            i    replay Imu data
grayscale      G    replay Stereo Grayscale images
color          C    replay Stereo Color images
viewer         V    enable image viewer
timestamps     T    use KITTI timestamps
stereoDisp     s    use pre-calculated disparities
viewDisp       D    view loaded disparity images
frame          F    start playing at frame...
gpsPoints      p    publish GPS/RTK markers to RVIZ, having reference frame as <reference_frame> [example: -p map]
synchMode      S    Enable Synch mode (wait for signal to load next frame [std_msgs/Bool "data: true"]

kitti_player needs a directory tree like the following:  
└── 2011_09_26_drive_0001_sync
    ├── image_00              
    │   └── data              
    │   └ timestamps.txt      
    ├── image_01              
    │   └── data              
    │   └ timestamps.txt      
    ├── image_02              
    │   └── data              
    │   └ timestamps.txt      
    ├── image_03              
    │   └── data              
    │   └ timestamps.txt      
    ├── oxts                  
    │   └── data              
    │   └ timestamps.txt      
    ├── velodyne_points       
    │   └── data              
    │     └ timestamps.txt    
    └── calib_cam_to_cam.txt  

