# End-to-end-Sign-Language-Detection using YOLOv5

## Introduction

Sign Language Detection is a project aimed at recognizing and interpreting hand gestures from sign language. This end-to-end solution employs the YOLOv5 object detection model to identify sign language phrases such as "Hello," "I love you," "Yes," "No," and "Please." The model can help bridge communication gaps and facilitate better understanding between individuals who use sign language and those who don't.

## Model Architecture

The project utilizes the YOLOv5 object detection model, a popular and efficient deep learning model for real-time object detection. YOLOv5 comes in various sizes (small, medium, large, and extra-large) to cater to different computing capabilities. In this implementation, I have selected small model size that balances accuracy and speed while running on various devices.

## Dataset

The training dataset comprises a collection of annotated images and corresponding labels for the sign language phrases "Hello," "I love you," "Yes," "No," and "Please." The dataset is preprocessed and split into training, validation, and test sets to train and evaluate the YOLOv5 model effectively.

## Training

The YOLOv5 model is trained on the annotated dataset using transfer learning. By fine-tuning the pre-trained YOLOv5 model on our sign language dataset, we can leverage the model's knowledge from other object detection tasks and apply it to our specific domain. The training process involves optimizing the model's parameters to achieve accurate sign language detection.

## Inference

After training the YOLOv5 model, we can perform inference on new images or real-time video streams. The model predicts bounding boxes around the sign language phrases present in the input data and provides the corresponding class labels. This information is then used to interpret the detected gestures, making sign language accessible to a wider audience.

## Usage

To use this Sign Language Detection project, follow these steps:

1. Clone the repository to your local machine:
   ```
   git clone https://github.com/ShubhamMohanty680/End-to-end-Sign-Language-Detection.git
   ```
2. Created virtual enviorment using cmd in the cloned repository:
```
   conda create -p sign python==3.8
   conda activate sign
```
3. Install the required dependencies by running:
   ```
   pip install -r requirements.txt
   ```

4. Run the notebook to train YOLOv5 model.

5. Run the application using the command:
   ```
   python app.py
   ```
6. Access the application: Open your web browser and go to http://localhost:8080 to access the text summarization service.

7. Select the image for which prediction is to be made.

8. The script will output the image or video with bounding boxes and class labels of detected sign language phrases.

9. For making prediction on video change route to to http://localhost:8080/live

## Results

The trained YOLOv5 model achieves high accuracy and real-time performance, allowing for seamless sign language detection in a variety of scenarios. The model's performance has been evaluated on the test set, and the results are presented in the project's documentation.

## Conclusion

Sign Language Detection using YOLOv5 is a promising project that empowers individuals who use sign language to communicate with the broader community. By leveraging the power of deep learning and computer vision, this project aims to make sign language more accessible and inclusive for everyone.




# Outputs

### For Homepage
![Screenshot 2023-11-17 115722](https://github.com/ShubhamMohanty680/End-to-end-Sign-Language-Detection/assets/101620532/257119b4-38db-4a4b-820b-1b961027df79)


### For Prediction Results tab
![Screenshot 2023-11-17 133754](https://github.com/ShubhamMohanty680/End-to-end-Sign-Language-Detection/assets/101620532/3e8d2ed5-95f5-4878-bb30-3b17f9ab0495)






# AWS-CICD-Deployment-with-Github-Actions


## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 315865595366.dkr.ecr.us-east-1.amazonaws.com/simple-app

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = 
