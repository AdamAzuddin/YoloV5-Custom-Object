# YoloV5-Custom-Object

1. Set up yolov5
use this link: https://wandb.ai/onlineinference/YOLO/reports/YOLOv5-Object-Detection-Tutorial-Bounding-Box-Webcams-For-Zoom--VmlldzozMDEzNDM5
no need to install obs studio
follow until this header: Create Bounding Boxes With YOLOv5 On Your Webcam
the last test line should be python detect.py --source 0 
it should show webcam with coco trained

2. collect and label image
use roboflow, create a new project.
label those images and train them
export the dataset as YoloV5 format and show download code in jupyter notebook link. copy that link

3. train model
open: https://colab.research.google.com/github/roboflow-ai/notebooks/blob/main/notebooks/train-yolov5-object-detection-on-custom-data.ipynb#scrollTo=FYSXiR35rCDU

follow the code and run them
you can only use these lines in code block number 4:
#follow the link below to get your download code from from Roboflow
!pip install -q roboflow
from roboflow import Roboflow

in code block number 5, paste the copied link of roboflow image dataset. run it
next, just run next and next code block
at code block number 11, the model is trained. continue if you want.

4. download model
go to files on left side bar. navigate to yolov5/runs/train/yolov5s_results/weights/best.pt   dowload best.pt
next, navigate to yolov5/your-roboflow-project-name/data.yaml. download it.

5. edit detect.py

paste best.pt 
search for yolov5s.pt, replace it with best.pt
paste data.yaml in data/data.yaml
replace data variable in run function like this:
data=ROOT / 'data/data.yaml'

6. test

open anaconda
run activate yolov5
run python detect.py --source 0 
done!
