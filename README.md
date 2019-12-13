# Face Recognition Attendance System

![alt homepage](https://github.com/YuHengKit/FaceRecognitionSystem/blob/master/homepage.PNG?raw=true)

<h1>Team HKL</h1>
<p>Members : </p>
<p>1. HAU ZHE XUAN</p>
<p>2. KIT YU HENG</p>
<p>3. LIM JUN SHIUN</p>

## Overview

A face recognition based attendence system with Raspberry Pi. (Note: At least Raspberry Pi 3 to run smoothly.)

Python module providing face recognition functionalities:
  - Managing faces photos
  - Training models
  - Making predictions
  
 <h1>System Architecture</h1>
<img src="https://user-images.githubusercontent.com/11400016/67187028-ea143d00-f41b-11e9-87c2-511f3ec8c1cf.png" />

## The recognition module
```__init__.py``` contains the face_cascade object, a common resource used in face detection.

```trainer.py``` is responsible of feeding the dataset to different models for training.
Three models are available: ```LBPH, FisherFace``` and ```EigenFace```.
The recognizer will compares three results from each model and get the most frequenct result.

```recognizer.py``` uses pretrained models to make predictions.

```capture.py``` adds photos to user profile.


## The django web interface
- Login
- Homepage: showing last stats of the system
- Add user: to add new faces
- Capture page: to take faces photos from a local or remote device
- Train page: to train models
- Attendence page: shows attendence records
- A RESTful API interface to send attendence records (from the raspberry pi in the prototype device)


## Environment
Python: > 3.6

Install libraries: ```pip3 install -r requirements.txt```


## Running
Please install postgreSQL and change the details in ```setting.py```.
Initialize the database from django:
- ```python3 manage.py makemigrations```
- ```python3 manage.py migrate```
- ```python3 manage.py createsuperuser```

Start the server:
```python3 manage.py runserver```

Reset database:
```python manage.py flush```


<h1>Domain Model</h1>
<img src="https://user-images.githubusercontent.com/11400016/67187139-2778ca80-f41c-11e9-9e0d-8ac02b5dc316.png" />

<h1>Entity-Relationship Diagram</h1>
<img src="https://user-images.githubusercontent.com/11400016/67187172-3b243100-f41c-11e9-8e39-abd7306cb451.png" />

<h1>Class Diagram</h1>
<img src="https://user-images.githubusercontent.com/11400016/69170362-eec03400-0b34-11ea-9c4d-0a9aa00d3b3b.png" />

<h1>Database Table</h1>
<img src="https://user-images.githubusercontent.com/11400016/70039481-04cdfa00-15f5-11ea-9fbb-ff192d5572bd.png" />

<h1>Normalized Table</h1>
<img src="https://user-images.githubusercontent.com/11400016/70039442-ecf67600-15f4-11ea-8384-3534617b4e74.PNG" />

