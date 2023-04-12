# Operationalizing-an-AWS-ML-Project
## Dog Image Classfication

In this project, you will complete the following steps:

1. Train and deploy a model on Sagemaker, using the most appropriate instances. Set up multi-instance training in your Sagemaker notebook.
2. Adjust your Sagemaker notebooks to perform training and deployment on EC2.
3. Set up a Lambda function for your deployed model. Set up auto-scaling for your deployed endpoint as well as concurrency for your Lambda function.
4. Ensure that the security on your ML pipeline is set up properly.

### Step 1: Training and deployment on Sagemaker

- Created sagemaker notebook instance, I have used ml.t3.medium as this is suffiecint to run my notebook.

![image](https://user-images.githubusercontent.com/83595196/231103691-a5eee425-91d8-43ee-abbd-d509c4170eeb.png)

- S3 bucket for the job (udacitysolution-1234)

![image](https://user-images.githubusercontent.com/83595196/231358554-cf68cf5b-d44d-405f-956e-befedc6a8ac3.png)

- Single instance training (1 epoch because of budget constraints)

![image](https://user-images.githubusercontent.com/83595196/231351357-c879e756-f48a-4631-bd6c-1ebeb826b06a.png)

- Multi-instance training (4 instances, 1 epoch because of budget constraints)

![image](https://user-images.githubusercontent.com/83595196/231350922-de52f333-c6ef-4da0-82b5-51de3110325a.png)

- Deployment

![image](https://user-images.githubusercontent.com/83595196/231354962-db3fa311-e384-4c3f-bb1c-6d69fe3aadc5.png)

### Step 2: EC2 Training

We can train model on EC2 instance as well. I chose AMI with required library already installed. Deep Learning AMI GPU PyTorch 2.0.0  has latest PyTorch version. instance type selected was m5.xlarge because to low cost.

![image](https://user-images.githubusercontent.com/83595196/231374337-2e63b8b4-2f06-45a9-bf50-858df92f2c4f.png)

The following images shows the EC2 instance and the terminal running the **ec2train1.py** script for training the model.

### Step 3: Security and Testing
### Step 4: Auto-scaling and Concurrency



