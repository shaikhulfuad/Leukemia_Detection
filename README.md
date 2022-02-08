# Leukemia_Detection
Leukemia is the most common type of childhood cancer and accounts for approximately 25% of the pediatric cancers. It can be cured if it's detected at it's early stage. Here the job was to tackle one of the major childhood cancer types by creating a model to classify abnormal cell(leukemia cell) from normal cell images. We evaluated the results by building a CNN model from scratch and approaching a Transfer learning model to classify between two classes.

**1.Exploration**

Dataset from kaggle https://www.kaggle.com/andrewmvd/leukemia-classification![image](https://user-images.githubusercontent.com/54286216/153010661-2913b2bb-9a30-4ff2-b1c4-07f7df3c978f.png)

The dataset is splitted into two section: Lekemuia(all) and Normal(hem). The number of images for each of the class:
![1](https://user-images.githubusercontent.com/54286216/153012046-8bf77022-2d20-42c6-a648-a49856f867c8.JPG)

By using the numpy and tqdm library the images for each of the class has been visalized

Leukemia Cells:

![2leukemiacells](https://user-images.githubusercontent.com/54286216/153012664-c6931add-0ba5-44f0-8e0a-2aa972981ef0.JPG)


Normal Cells:
![3normalcell](https://user-images.githubusercontent.com/54286216/153012727-f67fbbe5-7791-4916-aba3-21c84129a5aa.JPG)


**2.Processing**

Splitted the dataset into training, validation and testing by creating seperate folder for each

![4](https://user-images.githubusercontent.com/54286216/153013313-39d43086-8bc6-4ef3-a476-c2da821d0140.JPG)

For training images used data aumentation techniques:
    
    Horizontnal and vertical flip
    zoom_range = 0.2
    shear_range(angular) = 0.2
