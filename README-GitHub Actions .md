#  GitHub Actions CI/CD Pipeline Flask App

### Task1: Setup:

#### Forked the repository
#### Using same repository where the flask source code is placed and I will create Flask-CICD.yml under .github\workflows for the pipeline to be extecuted via GitHub Actions.

- https://github.com/soumik5/CICD-Pipeline.git

#### Create staging branch

<img width="917" height="442" alt="image" src="https://github.com/user-attachments/assets/ab094cc1-2716-48c3-bbd5-b499453f516e" />

### Task2: GitHub Actions Workflow:

#### Create a .github/workflows directory in your repository.
#### Inside the directory, create a YAML file to define the workflow.

<img width="922" height="442" alt="image" src="https://github.com/user-attachments/assets/1912a7fe-d5f4-47b0-8c76-9416d59cb1bc" />

### Task3: Workflow Steps:

#### Define a workflow that performs the following jobs:

  - Install Dependencies: Install all necessary dependencies for the Python application using pip.
  - Run Tests: Execute the test suite using a framework like pytest.
  - Build: If tests pass, prepare the application for deployment.
  - Deploy to Staging: Deploy the application to a staging environment when changes are pushed to the staging branch.
  - Deploy to Production: Deploy the application to production when a release is tagged.
#### please refer to the workflows/Flask-CICD.yml where I have created the pipeline to execute the above steps.
<img width="1891" height="516" alt="image" src="https://github.com/user-attachments/assets/74693b4e-fd7b-4771-87d3-ab0541eb49d3" />

#### In production we have used the same EC2 machine where we have created python service for the flaskapp to be exceuted properly. As the service is alreay there in the EC2 machine we have just restared the service for deployment.

### Task4. Environment Secrets:

#### Use GitHub Secrets to store sensitive information required for deployments such as MONGO_URI, SECRET_KEY, EC2_SSH_KEY, EC2_HOST, EC2_USER etc.

<img width="1741" height="945" alt="image" src="https://github.com/user-attachments/assets/dec332c4-171b-4718-b009-ea225abe0e04" />

### Task5: GitHub Actions Workflow check.

#### my deploy-to-staging job runs sucessfully unless I have creted a relese in main branch for production deployment
<img width="1882" height="830" alt="image" src="https://github.com/user-attachments/assets/8d85cccb-42d0-4a55-8f14-6a11a318d67d" />

#### deploy-to-main job only runs successfully once I created a relese after deploy-to-staging job completed.
<img width="1836" height="807" alt="image" src="https://github.com/user-attachments/assets/33af793e-0fad-4389-bb48-93c4ee088087" />
<img width="1882" height="942" alt="image" src="https://github.com/user-attachments/assets/75b2923e-7050-41e0-a3e9-77ce5ea8b35b" />

#### my aaplication is also running on EC2.
<img width="1917" height="560" alt="image" src="https://github.com/user-attachments/assets/aa09bd89-c235-4ca8-98a4-628b11aaeeab" />





