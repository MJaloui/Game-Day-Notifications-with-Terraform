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

&nbsp;

&nbsp;

1. Run this aws cli command with your api key to store it in Paremeter store
   
```bash
aws ssm put-parameter --name "nba-api-key" --value "<Your_API_KEY_Here>" --type "SecureString"
```
![image](https://github.com/user-attachments/assets/9f402d6a-411e-4c5f-8b32-e364b59ceb07)


### **Run Terraform commands**

&nbsp;

&nbsp;

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

![image](https://github.com/user-attachments/assets/77e9a1bf-d313-4422-8359-74094e957da8)



### **Add Subscriptions to the SNS Topic**

&nbsp;

&nbsp;

1. After creating the topic, sign into AWS and head on the SNS topic name.

   ![image](https://github.com/user-attachments/assets/15489f06-9059-4862-a2b2-02415e4ef8bc)

![image](https://github.com/user-attachments/assets/e9ff2444-3449-4b61-8b52-7dd8a9bd8a95)

![image](https://github.com/user-attachments/assets/fee1a23a-6b0e-4c9b-bfd4-56a5ffb52f35)


2. Navigate to the Subscriptions tab and click Create subscription.

![image](https://github.com/user-attachments/assets/665413fc-21f1-471f-a13a-3ad3856b5997)



3. Select a Protocol:
- For Email:
  - Choose Email.
  - Enter a valid email address.
- For SMS (phone number): (not required, I only selected email)
  - Choose SMS.
  - Enter a valid phone number in international format (e.g., +1234567890).

![image](https://github.com/user-attachments/assets/e1728125-4368-477a-985f-2adf2fe9ef57)

![image](https://github.com/user-attachments/assets/59f1f5dc-3469-4a60-88db-a2ec38dbac98)



4. Click Create Subscription.

![image](https://github.com/user-attachments/assets/9516abdc-7f49-4e3f-bd65-2aea697a60f1)


   
5. If you added an Email subscription:
- Check the inbox of the provided email address.
- Confirm the subscription by clicking the confirmation link in the email.
- You will recieve a confirmation reciept.

![image](https://github.com/user-attachments/assets/85ebb6e0-d956-40fd-85be-747b8bb7cd11)

![image](https://github.com/user-attachments/assets/aed18409-e44a-447d-b0b0-432c4835b217)

![image](https://github.com/user-attachments/assets/d21b81dd-65eb-4683-9a00-f06dd9622a9a)

6. Refresh the browser that is displaying the subcription, you can verify it was confirmed.

![image](https://github.com/user-attachments/assets/b7ad0bf4-d36b-482d-9cf9-ecef70c58aa7)



### **Test the System**

&nbsp;

&nbsp;

1. Open the Lambda function in the AWS search bar.


![image](https://github.com/user-attachments/assets/6ccca890-5342-4f7b-91eb-92a7da6ed07a)


2. Create a test event to simulate execution.
  
  - Click the most recent function created.

![image](https://github.com/user-attachments/assets/2e895589-f161-4766-ba3e-9a22cc8541c3)

  
  - Scroll down to "Test" tab.

![image](https://github.com/user-attachments/assets/c48572fb-5c2b-441b-ab49-4967d477823c)

  - Select "Create new event" and enter a "Event name".

![image](https://github.com/user-attachments/assets/47654e64-8c1b-42c2-9c72-30699ffd1d5d)


3. Test the function and check CloudWatch Logs for errors.

   - A green page with a message displays "Executing functions: succeeded".
   - If it is not successful, a red screen will be displayed stating it was unsuccessful. 

   ![image](https://github.com/user-attachments/assets/8fe68b5b-d374-4b1a-8926-36ba07bb6438)




5. Verify that SMS notifications are sent to the subscribed users.















*******************************************************************8



6. Remove all resources defined in your Terraform configuration.

    
```bash
terraform destory
```

![image](https://github.com/user-attachments/assets/abf562ee-eeba-44f4-b189-5afc1fd9dab5)



 - Notice all resources that are being deleted will display below. Verify the resources before deleting.

![image](https://github.com/user-attachments/assets/488d02de-ae80-4fc8-ad6e-a666abb35a43)


  - Enter the value "yes" to confirm deleting all the resources.

![image](https://github.com/user-attachments/assets/9629de58-6e7d-4240-be8d-79e400709769)

![image](https://github.com/user-attachments/assets/774d3aa6-ff49-45fa-a7b5-019502d968fe)

