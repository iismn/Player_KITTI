# SEMANTIC KITTI to BAG

## How to run

```bash
wget https://s3.eu-central-1.amazonaws.com/avg-kitti/raw_data/2011_09_26_drive_0084/2011_09_26_drive_0084_sync.zip
wget https://s3.eu-central-1.amazonaws.com/avg-kitti/raw_data/2011_09_26_drive_0084/2011_09_26_drive_0084_extract.zip
wget https://s3.eu-central-1.amazonaws.com/avg-kitti/raw_data/2011_09_26_calib.zip
unzip 2011_09_26_drive_0084_sync.zip
unzip 2011_09_26_drive_0084_extract.zip
unzip 2011_09_26_calib.zip
python kitti2bag.py -t 2011_09_26 -r 0084 raw_synced .
```
