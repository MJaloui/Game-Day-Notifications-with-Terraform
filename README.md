# **Game Day Notifications -W- Terraform**



## **🔷 Project Highlights 🔷**

⛹🏾‍♀️ This repository provides an alert system that sends real-time NBA game day score notifications to subscribed users via SMS or Email.

⛹🏾‍♀️ It integrates **Amazon SNS**, **AWS Lambda**, **Amazon EventBridge**, and **NBA APIs** for seamless sports updates.

⛹🏾‍♀️ The solution is designed using **Infrastructure as Code (IaC)** with **Terraform** to automate the deployment and destruction of the system.

## **🔧 Capabilities 🔧**

**The Game Day Notifications -W- Terraform performs the following actions:**

🔹 Fetches live NBA game scores using the SportsData.io API.

🔹 Sends formatted score updates to subscribed users via SMS/Email using Amazon SNS.

🔹 Automates notifications and updates using scheduled events through Amazon EventBridge.

🔹 Implements AWS Lambda functions to process data and trigger notifications.

🔹 Configures security and IAM roles based on the least privilege principle for all services involved.

## **🚨 Technologies 🚨**

🔹 **Cloud Provider**: AWS

🔹 **Infrastructure as Code**: Terraform

🔹 **Core Services**: SNS, Lambda, EventBridge

🔹 **External API**: NBA Game API (SportsData.io)

🔹 **Programming Language**: Python 3.x

🔹 **IAM Security**: Least privilege policies for Lambda, SNS, EventBridge, and Systems Manager

---

## **👀 Instructions 👀**   

**🔹 Prerequisites 🔹**

🔹 Free account with subscription and API Key at [SportsData.io](https://sportsdata.io/)

🔹 Personal AWS account with a basic understanding of AWS and Python

🔹 AWS CLI installed and configured with your personal account

🔹 Terraform CLI version 1.10.5 installed on your local environment

---

### **Steps:** ➡️❗ [Click Here To View Detailed Visual Steps](https://github.com/your-repository/Link-to-VisualStepsHere) ❗⬅️

1. **Clone the Repository:**

    ```bash
    git clone https://github.com/ifeanyiro9/game-day-notifications.git
    cd game-day-notifications
    ```

2. **Store API Key as Secret in Parameter Store:**

    1. Run the AWS CLI command with your API key to store it in Parameter Store:

3. **Run Terraform Commands:**

    1. **Initialize Terraform directory, provider plugins, and set up the local backend:**
        ```bash
        terraform init
        ```

    2. **Format Terraform config files to make them clean, readable, and follow best practices:**
        ```bash
        terraform fmt
        ```

    3. **Check Terraform configuration for syntax errors and correctness:**
        ```bash
        terraform validate
        ```

    4. **Show preview of changes Terraform will make to your infrastructure before applying them:**
        ```bash
        terraform plan
        ```

    5. **Create or update the infrastructure based on the Terraform configuration:**
        ```bash
        terraform apply
        ```

    6. **Remove all resources defined in your Terraform configuration:**
        ```bash
        terraform destroy
        ```

4. **Add Subscriptions to the SNS Topic:**

    1. After creating the SNS topic, head to the **SNS topic name**.
    
    2. Navigate to the **Subscriptions** tab and click **Create subscription**.
    
    3. **Select a Protocol:**

        - For **Email**:
            - Choose **Email**.
            - Enter a valid email address.
        
        - For **SMS (phone number)**:
            - Choose **SMS**.
            - Enter a valid phone number in international format (e.g., +1234567890).

    4. Click **Create Subscription**.

    5. **If you added an Email subscription:**
        - Check the inbox of the provided email address.
        - Confirm the subscription by clicking the confirmation link in the email.

5. **Test the System:**

    1. Open the Lambda function in the AWS Management Console.
    2. Create a test event to simulate execution.
    3. Run the function and check **CloudWatch Logs** for errors.
    4. Verify that SMS notifications are sent to the subscribed users.

---

## **✔️ Keynotes ✔️**

🔹 Designing a notification system with AWS SNS and Lambda.

🔹 Securing AWS services with least privilege IAM policies.

🔹 Automating workflows using EventBridge.

🔹 Integrating external APIs into cloud-based workflows.

🔹 Automated the entire solution with Infrastructure as Code tool Terraform.

---

## **🌱 Opportunities for Growth 🌱**

🔹 Expand notifications to other sports or teams.

🔹 Implement user preferences for different types of alerts.

🔹 Integrate advanced analytics to provide personalized game insights.

---

## **🧠 What I Learned 🧠**

🔹 Designing a notification system with AWS SNS and Lambda.

🔹 Securing AWS services with least privilege IAM policies.

🔹 Automating workflows using EventBridge.

🔹 Integrating external APIs into cloud-based workflows.

🔹 Automated the entire solution with Infrastructure as Code tool Terraform.
