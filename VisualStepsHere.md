![github-header-image (1)](https://github.com/user-attachments/assets/fb42157b-093a-420d-8b69-372b0c74496f)

&nbsp;

&nbsp;

&nbsp;

&nbsp;


## **Steps To Prerequisites:**

&nbsp;

&nbsp;


### **Clone this Repository and go to Game Day Notifications directory**

```bash
git clone https://github.com/MJaloui/game-day-notifications--w--Terraform.git
cd game-day-notifications--w--Terraform
```


### **Download Terraform if you don't have this tool**

  - **To verify if you have Terraform, use the "version" command.**

```bash
terraform --version
```

![image](https://github.com/user-attachments/assets/22ba24f3-1219-4466-9d52-08eb6fada2de)

    
  - **If no output is displayed, then it's not installed. Use wget command to install Terraform.**
    (you can research the latest version online and change the version in the command)

```bash 
wget https://releases.hashicorp.com/terraform/1.4.5/terraform_1.10.5_linux_amd64.zip
```

![image](https://github.com/user-attachments/assets/67bdd9c6-a21b-453c-9cf9-c704a47581e2)


### **Extract the Terraform binary from the downloaded ZIP file using unzip command**

```bash
unzip terraform_1.4.5_linux_amd64.zip
```

### **Move it to /usr/local/bin/ with the "mv" (move) command to make it globally accessible from any terminal session**

```bash
sudo mv terraform /usr/local/bin/
```

![image](https://github.com/user-attachments/assets/a8f17475-6ab3-4709-9a87-ba653c32d473)



### ** Verfiy if you have AWS CLI installed using the "version" command**

![image](https://github.com/user-attachments/assets/d1dc16e9-d75c-4615-92fb-1c56f3cba5c4)



### **If AWS CLI is not installed, you will not see any output. Use the "Pip install" command to install AWS CLI.**


```bash
pip install aws cli
```

### **Configure AWS if you had to install Terraform or AWS CLI**

    - The information needed can be found in your AWS account, you may need to create a Secret Access Key if you don't already have one. Input "json" for your format.

```bash
aws configure
```

![image](https://github.com/user-attachments/assets/974a2958-7609-4e61-84e7-ecf249a8b55d)

&nbsp;

&nbsp;

### **Steps to project:**

&nbsp;

&nbsp;


### **Store API Key as secret in Parameter store**

1. Run this aws cli command with your api key to store it in Paremeter store
   
```bash
aws ssm put-parameter --name "nba-api-key" --value "<Your_API_KEY_Here>" --type "SecureString"
```
![image](https://github.com/user-attachments/assets/9f402d6a-411e-4c5f-8b32-e364b59ceb07)


### **Run Terraform commands**
1. Initialize Terraform directory, provider plugins and set up local backend
   
```bash
terraform init
```

![image](https://github.com/user-attachments/assets/57fa27f0-4a22-427e-89a0-640510ae308e)

![image](https://github.com/user-attachments/assets/64d11d80-ada5-4faf-903b-30388bd2093c)



2. Format Terraform config files to make it clean, readable, and follow best practices.

```bash
terraform fmt
```

![image](https://github.com/user-attachments/assets/c6efebef-b359-4883-8aee-ef7a947b0a2d)



3. Validate Terraform configuration for syntax errors and if it's correct.

```bash
terraform validate
```

![image](https://github.com/user-attachments/assets/9cc9f06e-98b9-46bc-8040-79464868231d)


4. Show preview of changes Terraform will make to your infrastructure before applying them

  - You will be able to see what actions Terraform will perform.

```bash
terraform plan
```

![image](https://github.com/user-attachments/assets/5766ab43-9bdd-482e-8bc3-b73a159f301d)

![image](https://github.com/user-attachments/assets/d6d18adb-27c3-4362-ae8c-f6c327521fdd)




5. Create or update the infrastructure based on the Terraform configuration.


```bash
terraform apply
```


### **Add Subscriptions to the SNS Topic**
1. After creating the topic, head on the SNS topic name.
2. Navigate to the Subscriptions tab and click Create subscription.
3. Select a Protocol:
- For Email:
  - Choose Email.
  - Enter a valid email address.
- For SMS (phone number):
  - Choose SMS.
  - Enter a valid phone number in international format (e.g., +1234567890).

4. Click Create Subscription.
5. If you added an Email subscription:
- Check the inbox of the provided email address.
- Confirm the subscription by clicking the confirmation link in the email.

### **Test the System**
1. Open the Lambda function in the AWS Management Console.
2. Create a test event to simulate execution.
3. Run the function and check CloudWatch Logs for errors.
4. Verify that SMS notifications are sent to the subscribed users.















*******************************************************************8



6. Remove all resources defined in your Terraform configuration.

  - Enter the value "yes" to confirm deleting all the resources.
    
```bash
terraform destory
```

![image](https://github.com/user-attachments/assets/abf562ee-eeba-44f4-b189-5afc1fd9dab5)

![image](https://github.com/user-attachments/assets/5ceee3a0-0688-4db9-84b9-a7e022e70d6f)

 - Notice all rources that are being deleted will display below. Verify the resources before deleting.
   
![image](https://github.com/user-attachments/assets/77e9a1bf-d313-4422-8359-74094e957da8)


  - To cofirm deleting the resources, enter the value "yes". 




![image](https://github.com/user-attachments/assets/9629de58-6e7d-4240-be8d-79e400709769)

![image](https://github.com/user-attachments/assets/774d3aa6-ff49-45fa-a7b5-019502d968fe)

