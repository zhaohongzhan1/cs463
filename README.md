# Anomaly training

This part is mainly responsible for training the model that identifying the anomaly of welding.

## Setting up

Can be used directly from yolov5 folder code or official web (https://github.com/ultralytics/yolov5) clone yolov5 file.
`git clone https://github.com/ultralytics/yolov5`

when finished cloned, go to the yolov5 folder and install the required code environment using the following instructions
`cd yolov5`
`pip install -r requirements.txt`

## Basic training instruction
instruction
`python train.py --img 640 --epochs 3 --data path/to/your/dataset --weights yolov5n.pt`
                                                                           `yolov5s.pt`
                                                                           `yolov5m.pt`
                                                                           `yolov5l.pt`
                                                                           `yolov5x.pt`
Training results are saved in yolov5/runs/train
note: Currently the best training results are weights selected yolov5s.pt and epochs > 200.

Advanced training instruction
Please refer to https://docs.ultralytics.com/yolov5/tutorials/tips_for_best_training_results/

## Testing

instruction
`python detect.py --source path/to/your/test/file --weight path/to/your/model --conf 0.5`
--source: path of the test file/folder
--weight: path of the trained model
--conf: Set the minimum display confidence level

## Other
1.Eesume training that was interrupted unexpectedly
`python train.py --resume path/to/last.pt`

2.Use the previously trained model for training
`python train.py --data path/your/new/data --weights path/to/best.pt`
