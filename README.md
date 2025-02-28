# **Game Day Notifications -W- Terraform**



## **🔷 Project Highlights 🔷**

⛹🏾‍♀️ This repository provides an alert system that sends real-time NBA game day score notifications to subscribed users via SMS or Email.

⛹🏾‍♀️ It integrates **Amazon SNS**, **AWS Lambda**, **Amazon EventBridge**, and **NBA APIs** for seamless sports updates.

⛹🏾‍♀️ The solution is designed using **Infrastructure as Code (IaC)** with **Terraform** to automate the deployment and destruction of the system.

## **🔧 Capabilities 🔧**

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

### **Steps:** ➡️❗ [Click Here To View Detailed Visual Steps]([https://github.com/MJaloui/Game-Day-Notifications--w--Terraform/blob/main/VisualStepsHere]) ❗⬅️



1. Clone this Repository:

```bash
git clone https://github.com/ifeanyiro9/game-day-notifications.git
cd game-day-notifications
```

2. Store API Key as Secret in Parameter Store.

3. Run Terraform Commands:

    - Initialize, format, check Terraform, show preview of changes, create or update the infrastructure, and remove all resources.
      

4. Add Subscriptions to the SNS Topic.
        
5. Test the System.

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

