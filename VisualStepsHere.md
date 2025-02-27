![github-header-image (1)](https://github.com/user-attachments/assets/fb42157b-093a-420d-8b69-372b0c74496f)

&nbsp;

&nbsp;

&nbsp;

&nbsp;



## **Steps:**

### **Clone the Repository**
```bash
git clone https://github.com/MJaloui/game-day-notifications--w--Terraform.git
cd game-day-notifications
```

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






