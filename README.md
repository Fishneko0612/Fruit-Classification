# Fruit Classification
This model classifies different types of fruits. It can identify fruits like apples, oranges or bananas in images, which is useful for automatic fruit sorting, supermarket checkouts, and farm monitoring.

<img width="261" height="180" alt="image" src="https://github.com/user-attachments/assets/32aa4de5-c04a-40bf-ab3b-9032c4f38248" />


## The Algorithm
This re-trained ResNet-18 model was created on Jetson Nano and trained on a dataset of various fruit images. When it runs, it uses the imagenet.py program with the model to recognize the fruit in the image.

## Running this project
1. Make sure that both the Jetson Inference library and Python3 are installed on your Jetson Nano.
2. Download fruit-data folder, fruit-model folder and fruit-result image.
3. Open the terminal and unzip files(if needed).
<img width="440" height="167" alt="image" src="https://github.com/user-attachments/assets/519835e4-2956-4715-ad89-0b11fa649880" />

4. Use "cd <your folder paths>" to locate the downloaded folders. For example, I downloaded it to the "classification" folder.
```
   cd jetson-inference/python/training/classification
```
<img width="921" height="94" alt="image" src="https://github.com/user-attachments/assets/90b6d9f3-8173-4f9f-944b-235ce788318d" />

5. Since I already trained the model and placed it in the "model" folder, you don't need to train it again. 
6. Set the net and data variables as shown below:
```
   NET=fruit-model
   DATASET=fruit-data
```
7. Run this command to test an image:
```
 imagenet.py --model=$NET/fruit/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/classname.txt $DATASET/test/1/3.jpg fruit-result.jpg
```
8. Locate the "fruit-result" image and click on it, then you can view the type of fruit and the accuracy.
   
   <img width="232" height="180" alt="image" src="https://github.com/user-attachments/assets/60011bdc-daa2-40fb-830e-3db91163e804" />

## Video
[View a video explanation here](video link)
