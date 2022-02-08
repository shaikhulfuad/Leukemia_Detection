# Leukemia_Detection
Leukemia is the most common type of childhood cancer and accounts for approximately 25% of the pediatric cancers. It can be cured if it's detected at it's early stage. Here the job was to tackle one of the major childhood cancer types by creating a model to classify abnormal cell(leukemia cell) from normal cell images. We evaluated the results by building a CNN model from scratch and approaching a Transfer learning model to classify between two classes.

**1.Exploration**

Dataset from kaggle https://www.kaggle.com/andrewmvd/leukemia-classification![image](https://user-images.githubusercontent.com/54286216/153010661-2913b2bb-9a30-4ff2-b1c4-07f7df3c978f.png)

The dataset is splitted into two section: all(leukemia) and hem(normal). The number of images for each of the class:
![1](https://user-images.githubusercontent.com/54286216/153012046-8bf77022-2d20-42c6-a648-a49856f867c8.JPG)

By using the numpy and tqdm library the images for each of the class has been visalized

Leukemia Cells:

![2leukemiacells](https://user-images.githubusercontent.com/54286216/153012664-c6931add-0ba5-44f0-8e0a-2aa972981ef0.JPG)


Normal Cells:
![3normalcell](https://user-images.githubusercontent.com/54286216/153012727-f67fbbe5-7791-4916-aba3-21c84129a5aa.JPG)


**2.Processing**

At first labeled the dataset: hem:0, all:1.

Splitted the dataset into training, validation and testing by creating seperate folder for each

![4](https://user-images.githubusercontent.com/54286216/153013313-39d43086-8bc6-4ef3-a476-c2da821d0140.JPG)

For training images used data aumentation techniques:
    
    Horizontnal and vertical flip
    zoom_range = 0.2
    shear_range(angular) = 0.2

All the images from training, validation and testing brought to similar pixel(256X256). Then scaled the image(1/255) to fixed range(0-1)


**3.Model Building**

CNN

![8](https://user-images.githubusercontent.com/54286216/153032622-45b0fbd4-87b2-4ace-b7b1-c3bf050caf8c.JPG)

        steps per epoch = 16
        epoch = 15
        validation steps = 2

Transfer learning model(InceptionV3)
        
        input shape = (224,224,3)
        pooling = 'avearge'
        weights = 'imagenet'
        
        steps per epoch = 16
        epoch = 15
        validation steps = 2


**4.Results**

CNN performance evaluation:

![9cnn](https://user-images.githubusercontent.com/54286216/153034361-31fe2b4a-92a0-4cd1-b960-d525668c1724.JPG)
![10cnnloss](https://user-images.githubusercontent.com/54286216/153034479-20bf4b9b-7aea-47cf-b8a6-f1dabb00c342.JPG)

Accuracy and loss fluctuates although the results are pretty good. Training accuracy is nearly around 80% and loss value is less. There is also a little overfitting issue for validation data.

InceptionV3 performance evaluation:

![14incepv3](https://user-images.githubusercontent.com/54286216/153035180-318f058a-aac3-48b4-8e74-c62cc92fd802.JPG)
![15incepv3loss](https://user-images.githubusercontent.com/54286216/153035202-1480545e-244a-40cf-8e0b-ae25ca9fb35f.JPG)


Here the results do not fluctuates and came in more constant pattern. Training accuracy improved and loss value minimzed. Although the validation result is still overfitting but increase in training accuracy decreases the overfitting issue.

![chart](https://user-images.githubusercontent.com/54286216/153037155-0f5d47a5-9245-40f8-a47d-bc4c76ccad20.jpg)

According to training result, the values of testing data came quite good and there is no overfitting or underfitting issue. Contrasting to the models, transfer learning approach gave better result over building a convolutional neural network model. The accuracy would have been way better if both the classes had equal amounts of images. The dataset is highly imbalanced as
