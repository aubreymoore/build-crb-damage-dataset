## Model 0 - Initial 3 class model

### Dataset

Images from the Guam07 roadside survey. Annotation was done using 
```
MODEL_WEIGHTS_URL = 'https://github.com/aubreymoore/code-for-CRB-damage-ai/raw/refs/heads/main/models/3class/train5/weights/best.pt'
```

### Training results:

mAP50: 0.834

## Model 1 - Images from 2 roadside surveys annotated using model 0

Dataset: Images from the 2 Guam roadside surveys (5A, 6A). Annotation performed using 
```
MODEL_WEIGHTS_URL = 'https://github.com/aubreymoore/code-for-CRB-damage-ai/raw/refs/heads/main/models/3class/train5/weights/best.pt'

```
### Training

```
yolo \
task=detect \
mode=train \
model=yolov8n.pt \
imgsz=640 \
data=/home/aubrey/dataset1/data.yaml \
epochs=1000 \
batch=-1 \
patience=100 \
name=dataset1_yolov8n
```

### Training results

/home/aubrey/dataset1/cod/runs/detect/dataset1_yolov8n

mAP50: 0.839

## Model 3 - Images from 6 roadside surveys annotated using model 0

### Dataset

Images from 6 Guam roadside surveys (5A, 6A, 7, 8, 9, 10). Annotation was done using
```
MODEL_WEIGHTS_URL = 'https://github.com/aubreymoore/code-for-CRB-damage-ai/raw/refs/heads/main/models/3class/train5/weights/best.pt'
```

### Training

```
yolo \
task=detect \
mode=train \
model=yolov8n.pt \
imgsz=640 \
data=/home/aubrey/dataset2/data.yaml \
epochs=1000 \
batch=-1 \
patience=50 \
name=dataset2_yolov8n
```

### Training results

/home/aubrey/dataset1/cod/runs/detect/dataset2_yolov8n

155 epochs completed in 14.570 hours.
mAP50: 0.853

## Model 4 - Model 3 retrained after removing bounding boxes touching top, left or right edges of image

### Dataset
### Training
### Training results



