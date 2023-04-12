# Operationalizing-an-AWS-ML-Project
## Dog Image Classfication

In this project, you will complete the following steps:

1. Train and deploy a model on Sagemaker, using the most appropriate instances. Set up multi-instance training in your Sagemaker notebook.
2. Adjust your Sagemaker notebooks to perform training and deployment on EC2.
3. Set up a Lambda function for your deployed model. Set up auto-scaling for your deployed endpoint as well as concurrency for your Lambda function.
4. Ensure that the security on your ML pipeline is set up properly.

### Step 1: Training and deployment on Sagemaker

- *Created sagemaker notebook instance* 
I have used ml.t3.medium as this is suffiecint to run my notebook.

![image](https://user-images.githubusercontent.com/83595196/231103691-a5eee425-91d8-43ee-abbd-d509c4170eeb.png)

- *S3 bucket for the job* (udacitysolution-1234)

![image](https://user-images.githubusercontent.com/83595196/231358554-cf68cf5b-d44d-405f-956e-befedc6a8ac3.png)

- *Single instance training* (1 epoch because of budget constraints)

![image](https://user-images.githubusercontent.com/83595196/231351357-c879e756-f48a-4631-bd6c-1ebeb826b06a.png)

- *Multi-instance training* (4 instances, 1 epoch because of budget constraints)

![image](https://user-images.githubusercontent.com/83595196/231350922-de52f333-c6ef-4da0-82b5-51de3110325a.png)

- *Deployment*

![image](https://user-images.githubusercontent.com/83595196/231354962-db3fa311-e384-4c3f-bb1c-6d69fe3aadc5.png)

### Step 2: EC2 Training

We can train model on EC2 instance as well. I chose AMI with required library already installed. Deep Learning AMI GPU PyTorch 2.0.0  has latest PyTorch version. instance type selected was m5.xlarge because to low cost.

![image](https://user-images.githubusercontent.com/83595196/231374337-2e63b8b4-2f06-45a9-bf50-858df92f2c4f.png)

The above image shows the EC2 instance and the terminal running the **ec2train1.py** script for training the model.

The adjusted code in ec2train1.py is very similar to the code in train_and_deploy-solution.ipynb. But there are few differences between the modules used - some modules can only be used in SageMaker. Much of the EC2 training code has also been adapted from the functions defined in the hpo.py starter script.
ec2train.py trains model with specific arguments while hpo.py takes argument for modell by parsing through command line. The later code can train multiple model with different hyperparameters.

### Step 3: Step 3: Lambda function setup 
After training and deploying your model, setting up a Lambda function is an important next step. Lambda functions enable your model and its inferences to be accessed by API's and other programs, so it's a crucial part of production deployment.

### Step 4: Lambda security setup and testing 

### Step 5: Lambda concurrency setup and endpoint auto-scaling

