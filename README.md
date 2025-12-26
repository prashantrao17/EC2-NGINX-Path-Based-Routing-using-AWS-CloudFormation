🌍 EC2 NGINX Path-Based Routing using AWS CloudFormation

This mini project demonstrates how to deploy an EC2 instance with NGINX using AWS CloudFormation, configured for path-based routing to serve different HTML pages for all planets in the solar system.

📌 Project Overview

Launches an Amazon EC2 instance using CloudFormation

Installs and configures NGINX automatically using UserData

Implements path-based routing (e.g., /earth, /mars, /venus)

Hosts static HTML pages for all planets

Uses AWS Security Groups to allow HTTP traffic

Fully Infrastructure as Code (IaC) solution

🛠️ Technologies Used

AWS CloudFormation (YAML)

Amazon EC2

NGINX Web Server

Amazon Linux 2

Linux Bash Scripting

🗂️ Project Structure
.
├── template.yaml        # CloudFormation template
├── nginx.conf           # Custom NGINX configuration (embedded in UserData)
└── README.md            # Project documentation

🌐 Supported Routes

Each route displays a dedicated HTML page:

URL Path	Page
/earth	Earth
/moon	Moon
/mars	Mars
/mercury	Mercury
/venus	Venus
/jupiter	Jupiter
/saturn	Saturn
/uranus	Uranus
/neptune	Neptune
🚀 Deployment Steps
1️⃣ Prerequisites

AWS Account

EC2 Key Pair (existing)

VPC and Subnet IDs

IAM user with CloudFormation & EC2 permissions

2️⃣ Upload CloudFormation Stack

Open AWS CloudFormation Console

Click Create stack → With new resources

Upload the template.yaml file

Provide required parameters:

KeyName

VpcId

SubnetId

Acknowledge IAM permissions (if prompted)

Click Create Stack

🌍 Accessing the Website

Once the stack status is CREATE_COMPLETE:

Go to EC2 Console

Copy the Public DNS / Public IP of the instance

Open browser and visit:

http://<Public-IP>/earth
http://<Public-IP>/mars
http://<Public-IP>/venus

📄 Sample Output
Welcome to Earth
Welcome to Mars
Welcome to Jupiter

🔐 Security Configuration

Security Group allows:

HTTP (Port 80) from 0.0.0.0/0

No SSH exposed publicly unless explicitly added

🧠 Key Learning Outcomes

Infrastructure as Code using CloudFormation

EC2 automation using UserData

NGINX path-based routing

AWS networking (VPC, Subnets, Security Groups)

Real-world deployment troubleshooting

⚠️ Common Issues & Fixes
Issue	Solution
Invalid VPC/Subnet ID	Ensure region matches resource
Instance rollback	Use supported instance type
Stack in ROLLBACK_COMPLETE	Delete stack and recreate
Port not opening	Check Security Group rules
📌 Future Enhancements

Add Application Load Balancer

Use Auto Scaling Group

Enable HTTPS with ACM

Host dynamic content

Store HTML files in S3

👨‍💻 Author

Prashant Jagtap
B.Tech IT | AWS & Cloud Enthusiast
IEEE Member

⭐ Acknowledgment

This project was built as a learning mini project to understand AWS CloudFormation and NGINX routing concepts.
