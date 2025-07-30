# Fruit Classification
This model classifies different types of fruits. It can identify fruits like apples, oranges or bananas in images, which is useful for automatic fruit sorting, supermarket checkouts, and farm monitoring.

## The Algorithm
This re-trained ResNet-18 model was created on Jetson Nano and trained on a dataset of various fruit images. When it runs, it uses the imagenet.py program with the model to recognize the fruit in the image.

## Running this project
1. Make sure that both the Jetson Inference library and Python3 are installed on your Jetson Nano.
2. Download the "changes" folder, which includes data folder, model folder and fruit-result image.("changes" was originally just a code name I used for testing, and I also want to change its name ><)
3. Open the terminal and unzip files(if needed).
4. Navigate to the classification directory:
```
   cd jetson-inference/python/training/classification
```
5. Since I already trained the model and placed it in the "model" folder, you don't need to train it again. 
6. Set the net and data variables as shown below:
```
   NET=models/fruit/fruit
   DATASET=data/fruit/fruit
```
7. Run this command to test an image:
```
   imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/classname.txt $DATASET/test/1/3.jpg fruit-result.jpg
```
8. Locate the "fruit-result" image and click on it, then you can view the type of fruit and the accuracy.

## Video
[View a video explanation here](video link)
