# CICD-Pipeline
## Jenkins CI CD pipeline for flask application
### Task1: Setup
### Step1:
We are going to use a cloud-based Jenkins service
- https://jenkinsacademics.herovired.com/
- Login to Cloud based Jenkins server
<img width="1915" height="962" alt="image" src="https://github.com/user-attachments/assets/647d6730-352f-4ee8-b256-42aa4d500834" />
<img width="1890" height="962" alt="image" src="https://github.com/user-attachments/assets/b367143f-0104-44cb-8ea1-0b5ece471782" />

### Step2:

#### Forked the repository
  
- (https://github.com/mohanDevOps-arch/flask_Practice.git)

#### My forked repository
- https://github.com/soumik5/flask_Practice.git

### Step3:
#### configure EC2 as a Jenkins node
- launching EC2
<img width="1907" height="892" alt="image" src="https://github.com/user-attachments/assets/adf1d8fa-812c-430b-9681-fc804b7071f1" />
<img width="1897" height="262" alt="image" src="https://github.com/user-attachments/assets/09a1c8b2-66b5-4e14-ac62-a8e1ded83f3a" />


- login to EC2
<img width="1032" height="911" alt="image" src="https://github.com/user-attachments/assets/be6d976e-3b24-45f3-90b5-7a0de8c81769" />

- update latest package
```
apt update -y
```
<img width="1447" height="940" alt="image" src="https://github.com/user-attachments/assets/4ad88654-223d-4c6c-b916-77e97c9df769" />

- install git for copying the source code
```
apt install git -y
git --version
```
<img width="1012" height="370" alt="image" src="https://github.com/user-attachments/assets/5a5b952c-ca4b-42f8-9f15-8318337ea5f0" />

- install python and pip
```
apt install python3 -y
python --version
apt install python3-pip -y
pip3 --version
```
<img width="1871" height="1002" alt="image" src="https://github.com/user-attachments/assets/863333c0-4303-4877-b118-1e10154f5dd5" />
<img width="1906" height="745" alt="image" src="https://github.com/user-attachments/assets/929879f3-493f-4a5e-9ab1-e651ee2ae180" />

- clone the forked git repository to EC2
```
git clone https://github.com/soumik5/flask_Practice.git
```
<img width="1470" height="907" alt="image" src="https://github.com/user-attachments/assets/3395fd50-9953-4ba9-9fa7-44eeb0c1c524" />

- Create and activate a virtual environment and then install dependecies

<img width="1882" height="922" alt="image" src="https://github.com/user-attachments/assets/fb53054c-94d6-47d8-a8d9-9e682e4dc5d1" />



- creating .env file
<img width="1532" height="870" alt="image" src="https://github.com/user-attachments/assets/892ca395-5019-40fe-ae93-d0b2109d81c7" />

- test application using pytest
<img width="1907" height="251" alt="image" src="https://github.com/user-attachments/assets/234c1c8a-1df3-4684-87bc-445e3c099cd2" />

## - Add the node (EC2 instance) to Jenkins server

<img width="1772" height="960" alt="image" src="https://github.com/user-attachments/assets/dd56df6d-bf3a-497e-94b7-cd800a4cef31" />
 













## GitHub Actions CI/CD Pipeline Flask App
