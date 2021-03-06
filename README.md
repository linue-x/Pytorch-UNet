# Pytorch-UNet
Exploring knowledge distillation of unet for audio super resolution
## Requirements
* `torch==0.4.0`
* `torchsummary==1.5`
* `tqdm`

## Training the model
First, we run the model on teacher mode and student mode：
```
usage: python train.py --mode MODE 

optional arguments:
  -h, --help            show this help message and exit
  --mode MODE           Choose training mode, student or teacher
``` 
For example, to run the model on teacher mode, you would type:
```
python train.py --mode=teacher
```
After training the student model and the teacher model, we train the distillation model.
```
python train_dis.py 
```
## Test the model
```
usage: python predict.py --mode MODE

optional arguments:
  -h, --help            show this help message and exit
  --mode MODE           Which model will be predicted? student, teacher or student_dis?
```
For example, to predict the model on teacher mode, you would type:
```
python predict.py --mode=teacher
```
## Get snr and lsd matrics
get the lsd, snr matric of student, student_dis, teacher model 
```
python get_matric.py
```