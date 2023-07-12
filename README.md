# 102-Flower-Classification
The goal of this Repo is to utilize Deepl learning to categorize photos from the 102 Flowers collection. There are thousands of photos in the 102 Flowers collection, which includes 102 categories of flowers. The project's aim is to build a classification model that can correctly detect and classify new photos of flowers.
this dataset contains images of flowers belonging to 102 different categories. The images were acquired by searching the web and taking pictures. There are a minimum of 40 images for each category.

### The database was used in:
Nilsback, M-E. and Zisserman, A. Automated flower classification over a large number of classes.
Proceedings of the Indian Conference on Computer Vision, Graphics, and Image Processing (2008) 
http://www.robots.ox.ac.uk/~vgg/publications/papers/nilsback08.{pdf,ps.gz}.

### Installation Instructions:
- I have provided a Txt file that contains all the libraries that you need to run the notebook the file name is **"requirements.txt"** and also provides **"conda.yaml"** these two files for the final model.
- If you want to use mlflow and see the experiment tracking I did, you can use this command in cmd after activating the environment **"mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root ./artifacts --host 0.0.0.0 --port 5000"** before this you should download the database and the artifacts file.
- just download the dataset from this **[Dataset](https://www.robots.ox.ac.uk/~vgg/data/flowers/102/)** then download the repo and here you are ready to run the code or you can use the model.h5 instead of all the steps but unfortunately the files all can not be uploaded to GitHub due to size of them so I have attached a link **[link](https://drive.google.com/drive/folders/15vKH-LhAl14TOOTaxZgSVMH-wQ3Q5wcP?usp=sharing)** that you can use to download all others files that don't exist here.

### Usage Guide:
- I put the image paths and labels from the mat file into a dataframe to make it easier for me here is the snippet
  
 ![dataframe](https://github.com/Bassem-2000/Images/blob/main/Screenshot%202023-07-11%20143723.png?raw=true)
- after that, I used ImageDataGenerator from keras to load the data by applying some data augmentation to the training dataset here is the snippet
  
 ![ImageDataGenerator](https://github.com/Bassem-2000/Images/blob/main/Screenshot%202023-07-11%20143849.png?raw=true)

### Model Architecture:
- I used the Resnet Architecture and used different fine-tuning and architecture but my final model and architecture are done by applying fine-tuning to the final layers as I made the last 15 layers nontrainable and add some neurons here is the snippet for the model summary
  
 ![Architecture](https://github.com/Bassem-2000/Images/blob/main/Screenshot%202023-07-11%20144116.png?raw=true)


### Evaluation:
- I used different approaches to test the performance of the architecture and the model like accuracy, loss, Recall, Precision, and Confusion matrix all of these approaches were used on every architecture I did and you can see it from the mlflow experiment tracking you can download the database and files to test it by yourself, here are the final model performance:
  
 ![Accuracy](https://github.com/Bassem-2000/Images/blob/main/Screenshot%202023-07-12%20132106.png?raw=true)
 ![Accuracy](https://github.com/Bassem-2000/Images/blob/main/Accuracy_Run(8).png?raw=true)
 ![Loss](https://github.com/Bassem-2000/Images/blob/main/Loss_Run(8).png?raw=true)
 ![Recall](https://github.com/Bassem-2000/Images/blob/main/Recall_Run(8).png?raw=true)
 ![Precision](https://github.com/Bassem-2000/Images/blob/main/Prescision_Run(8).png?raw=true)
 ![Confusion Matrix](https://github.com/Bassem-2000/Images/blob/main/Confusion_Matrix_Run(8).png?raw=true)

### Example:
- I test the model with a random image and visualize it here you can see the image with the prediction:

 ![Confusion Matrix](https://github.com/Bassem-2000/Images/blob/main/Screenshot%202023-07-12%20132106.png?raw=true)
