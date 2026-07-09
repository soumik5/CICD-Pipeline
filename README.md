# CICD-Pipeline
# Jenkins CI CD pipeline for flask application
## Task1: Setup
### Step1:
We are going to use a cloud-based Jenkins service
- https://jenkinsacademics.herovired.com/
- Login to Cloud based Jenkins server
<img width="1915" height="962" alt="image" src="https://github.com/user-attachments/assets/647d6730-352f-4ee8-b256-42aa4d500834" />
<img width="1890" height="962" alt="image" src="https://github.com/user-attachments/assets/b367143f-0104-44cb-8ea1-0b5ece471782" />


### Step2:
#### configure one EC2 as a Jenkins node
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

- Add the node (EC2 instance) to Jenkins server

<img width="1772" height="960" alt="image" src="https://github.com/user-attachments/assets/dd56df6d-bf3a-497e-94b7-cd800a4cef31" />

## Task2: Source Code:

#### Forked the repository
  
- (https://github.com/mohanDevOps-arch/flask_Practice.git)

#### My forked repository where the flask source code is placed and Jenkins file will be pushed into this repository once created
- https://github.com/soumik5/flask_Practice.git

 
## Task3: Jenkins Pipeline:
- Now create Jenkins pipeline locally. you can refer to the Jenkinsfile for detailed pipeline steps.

#### -Build: Install dependencies using pip.

#### -Test: Run unit tests using a testing framework like pytest.

#### -Deploy: If tests pass, deploy the application to a staging environment.

- I will push the locally created Jenkinsfile to the main branch of my forked repository once I Configure the pipeline to trigger a new build whenever changes are pushed to the main branch of the repository.

## Task4: Triggers:

#### create a new item and then select pipeline, give it a name, for me it is Flaskapp-Jenkins-Soumik5

<img width="1506" height="842" alt="image" src="https://github.com/user-attachments/assets/c6d83fe8-bc5a-4fc4-b71d-e64852c065f3" />

#### Now under the Trigger section select trigger option. I will use GitHub hook trigger for GITScm polling

<img width="1692" height="771" alt="image" src="https://github.com/user-attachments/assets/c0dfe7be-f209-4fad-bdb9-9b1a232bb85c" />

#### Under the pipeline section select below option and click save and apply.

- Definition: Pipeline script from SCM
- SCM: Git
- Repository URL: https://github.com/soumik5/flask_Practice.git
- Branch Specifier: */main
- Script Path: Jenkinsfile

<img width="1737" height="912" alt="image" src="https://github.com/user-attachments/assets/cbb457c4-4560-41eb-b9b4-31d471fe4125" />

#### Now create webhook inside your git repository in order trigger the build pipeline once somonce pushes anything to your repository

<img width="1667" height="935" alt="image" src="https://github.com/user-attachments/assets/2e809183-d95b-481a-9c1e-0b6277441984" />

<img width="1901" height="847" alt="image" src="https://github.com/user-attachments/assets/8a327771-d24e-4522-9b06-a3e54bdf5c6d" />


#### Now once you add the the jenkins file it will auto trigger the pipeline using webhook.

<img width="1877" height="897" alt="image" src="https://github.com/user-attachments/assets/465aedbb-a1bd-45d3-8f8f-eff9fc735ca5" />

#### My pipeline got executed automatically and successfully completed.

<img width="1882" height="882" alt="image" src="https://github.com/user-attachments/assets/65afebbc-8514-4e43-b003-bcd92a724e57" />

<img width="1897" height="922" alt="image" src="https://github.com/user-attachments/assets/a284cd22-fc6a-4da4-8f5e-9cbb9ac22b5c" />


#### webhook log

<img width="1892" height="427" alt="image" src="https://github.com/user-attachments/assets/86f332fd-8f69-4074-9ece-1de1deb4b10f" />

## Task5: Notifications:

#### Set up a notification system to alert via email when the build process fails or succeeds.

#### create credential
- Add credential
- select type of credential: username with password
- Username: give the email ID from where you want to send the notification.
- Password: create new app password for jenkins if MFA is enabled for the mail ID.

<img width="1785" height="171" alt="image" src="https://github.com/user-attachments/assets/a60fe195-6bb9-4087-98fe-a62e2b6d3d7b" />

#### Configure notification using 

- Go to manage jenkins and select System
<img width="1931" height="907" alt="image" src="https://github.com/user-attachments/assets/04003cea-000e-43c6-95dd-14a4e0ea3fa9" />

- Look for 'Extended E-mail Notification' section
- SMTP server: smtp.gmail.com
- SMTP Port: 587
- Credentials: use your credential
- Select the checkbox for Use TLS

<img width="1842" height="907" alt="image" src="https://github.com/user-attachments/assets/9c19fc39-af3d-4be4-9af5-5fb3cc68f98c" />


#### You can see I got an email upon successful pipeline execution after configuration.

<img width="1527" height="737" alt="image" src="https://github.com/user-attachments/assets/f6bac16d-070e-4fc2-89bb-3e408abfd9d2" />



















## GitHub Actions CI/CD Pipeline Flask App
