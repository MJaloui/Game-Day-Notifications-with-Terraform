![github-header-image (1)](https://github.com/user-attachments/assets/fb42157b-093a-420d-8b69-372b0c74496f)

&nbsp;

&nbsp;

&nbsp;

&nbsp;


## **Steps To Prerequisites:**

&nbsp;

&nbsp;


### **Clone this Repository and go to Game Day Notifications directory **

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



### ** Verfiy if you have AWS CLI installed using the "version command"**

![image](https://github.com/user-attachments/assets/d1dc16e9-d75c-4615-92fb-1c56f3cba5c4)



### **If AWS CLI is not installed, you will not see any output. Use the "Pip install" command to install AWS CLI.


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
aws ssm put-parameter --name "nba-api-key" --value "<API_KEY>" --type "SecureString"
```

### **Run Terraform commands**
1. Initialize Terraform directory, provider plugins and set up local backend
```bash
terraform init
```
2. Format Terraform config files to make it clean, readable, and follow best practices.
```bash
terraform fmt
```
3. Check Terraform configuration for syntax errors and correctness
```bash
terraform validate
```
4. Show preview of changes Terraform will make to your infrastructure before applying them
```bash
terraform plan
```
5. Create or update the infrastructure based on the Terraform configuration.
```bash
terraform apply
```
6. Remove all resources defined in your Terraform configuration.
```bash
terraform destory
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






