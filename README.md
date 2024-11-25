![Screenshot 2024-11-25 at 12 44 07 AM](https://github.com/user-attachments/assets/76040dce-fa03-484e-9d80-e37fc644a039)# Calorie Tracker


## Problem Statement
Obesity is a growing and serious public health concern that continues to rise globally, necessitating immediate attention. Maintaining a healthy lifestyle, including a balanced diet and regular exercise, is crucial in managing and preventing obesity. While a good exercise regimen is essential, equally important is the need for a well-balanced, nutrient-rich meal plan to support overall health and wellness.

To address this pressing need, I developed a Calorie Tracker application designed to help individuals take control of their dietary habits and make informed decisions about their nutrition. This application empowers users to track their daily calorie intake and nutrient consumption with precision, enabling them to maintain a healthy lifestyle.

## Solution Proposed
Calorie Tracker is an application that provides users the features to track daily calorie intake and provide nutritional information on macro nutrients such as fat, carbohydrates, protein for the food item consumed by the user. User’s can also monitor their weight by logging their weights in the application which can be visualized from a graph, and it also provides nutrition facts for a range of food items which empowers the user's to plan their diet and reach their fitness goals. 

## Application Features
* Users can register and login using application custom login or through Amazon Cognito
* On successful Login, users can view list of food items
* Users can add new food items
* Users can view macronutrient breakdown for a particular food item
* Users can add the food they have consumed in a day in the food log by selecting dropdown or by giving an image to know about the total calories consumed and the macronutrients breakdown.
* Users can log their weight and can see their weight history plotted in the form of a graph


## Tools and Technologies used:
  * Frontend: HTML, Javascript, Bootstrap, ChartJs
  * Backend: Python Django framework

## AWS components
* **Amazon RDS** : PostgreSQL is used as the database for the application to store all the user and food details.
* **Amazon S3** : Amazon S3 buckets are used to store application Images, Sagemaker data dump and CI/CD pipeline application data.
* **Amazon CloudFront** : Amazon CloudFront is used to render application Images.
* **AWS Lambda** : Lambda function created for application S3 bucket is used to trigger email to admin when images are uploaded to S3 bucket.
  Lambda function created for Amazon Lex chatbot is used to fetch the calories of the food items from the dynamoDB.
* **Amazon Simple Notification Service (SNS)** : SNS topic is created for sending email to admin once images are uploaded to S3 bucket.
* **Amazon Rekognition** : Rekognition has been used to detect the food which has been uploaded by the user and if the labels returned  match the labels present in the application then the food is added automatically to the food log.

## Instructions to run project locally

#### Create a virtual environment
```
python -m venv venv
  ```
#### Activate the virtual environment

* macOS:
```
source venv/bin/activate
```

* Windows:
```

venv\scripts\activate
```

#### Install required dependencies
```
pip install -r requirements.txt
```
#### Set up a PostgreSQL database
* With PostgreSQL up and running, in a new Terminal window run:
```
dropdb --if-exists food
```
* Start psql, which is a terminal-based front-end to PostgreSQL, by running the command:
```
psql postgres
```
### Create a new PostgreSQL database:
```
CREATE DATABASE food;
```
Create a new database admin user:
```
CREATE USER yourusername WITH SUPERUSER PASSWORD 'yourpassword';
```
#### To quit psql, run:
```
\q
```

#### Set up environment variables
```
touch .env
```
#### We need to add below details in env
```
SECRET_KEY=''
DEBUG=True
DATABASE_NAME=''
DATABASE_USER=''
DATABASE_PASS=''
DATABASE_HOST=''
AWSAccessKeyId=''
AWSSecretKey=''
REGION_NAME=''
```

#### Run migrations
```
python manage.py makemigrations
python manage.py migrate
```

#### Create an admin user to access the Django Admin interface
```
python manage.py createsuperuser
```

#### Run the application
```
python manage.py runserver
```

## Why I did this project

I implemented this project to address the growing concern of obesity and the need for maintaining a healthy lifestyle. With the rise in unhealthy eating habits and sedentary lifestyles, tracking calorie intake and nutritional information has become increasingly important for people aiming to achieve their fitness goals. The goal of this project was to create an intuitive and user-friendly application that empowers individuals to make informed decisions about their diet and exercise regimes. By providing features like calorie tracking, macronutrient breakdown, and weight monitoring, this application serves as a practical tool to help users stay accountable and motivated in their journey toward better health and well-being. It bridges the gap between awareness and action, making healthy living more accessible and manageable for users.


## Future Enhancements

1. I am working now to add chatbot capability and SSO login using AWS Cognito.
2. Incorporate machine learning algorithms to recommend personalized meal plans based on the user’s dietary preferences, fitness goals, and daily calorie requirements.
3. Add a feature to scan barcodes of packaged food items for instant retrieval of nutritional information.
4. Add the ability to log and track daily water intake to ensure users stay hydrated, complementing their diet and fitness regime.
5. Continuously update and expand the food database to include global cuisines, restaurants, and rare ingredients
6. Generate detailed weekly and monthly reports summarizing calorie intake, weight trends, and macronutrient distribution to help users analyze their progress.

## Likes 

1. The application is intuitive and easy to use, making it accessible for users of all ages and fitness levels.
2. Users can add food items through a dropdown or image upload, offering convenience and multiple input methods.
3. The graphical representation of weight history provides a clear and motivating way for users to monitor their progress over time.
4. Encourages users to be mindful of their dietary habits and nutritional intake, aiding them in achieving fitness goals.


## Dislikes

1. The current image recognition system may struggle to identify complex dishes or multiple items in a single image.
2. Users must manually log their meals and weights, which may lead to inconsistent tracking.
3. The food database might initially lack information on certain cuisines or regional foods, limiting its utility for some users.


## Images of Application


### Login

![Screenshot 2024-11-25 at 12 44 07 AM](https://github.com/user-attachments/assets/5a629946-50cc-4951-b5e4-a7745996e1f5)

### Food List

![Screenshot 2024-11-25 at 12 40 48 AM](https://github.com/user-attachments/assets/d1daaeb2-11ba-479d-8fc8-85ac1ae65a26)

### Food Details

![Screenshot 2024-11-25 at 12 41 48 AM](https://github.com/user-attachments/assets/ef803459-f7ba-45e5-a643-cc82fc013116)

### Category

![Screenshot 2024-11-25 at 12 42 04 AM](https://github.com/user-attachments/assets/a0b5d249-17df-438c-9353-8c76799b5862)

### Food Log

![Screenshot 2024-11-25 at 12 42 04 AM](https://github.com/user-attachments/assets/22cb9b4b-b4ad-4387-8481-a71543930515)

### Weight Log

![Screenshot 2024-11-25 at 12 42 42 AM](https://github.com/user-attachments/assets/b7fd5662-2e6f-421f-8e41-b0fe135cbdb9)














