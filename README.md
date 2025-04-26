# AWS Critical Thinking Project: Cloud Cost Optimization

## Project Overview

In this project, I explored multiple strategies to **optimize cloud costs** within an AWS environment.  
I personally carried out each activity — from understanding AWS pricing models to right-sizing resources and designing a comprehensive cost optimization strategy.

The goal was to learn practical techniques to **reduce AWS costs** without compromising **performance** or **reliability**.

---

## 1. Understanding AWS Pricing Models

AWS offers several pricing options. I studied the major ones:

| Pricing Model       | Description |
|----------------------|-------------|
| On-Demand Instances  | Pay for compute capacity by the second with no long-term commitments. Best for short-term, unpredictable workloads. |
| Reserved Instances   | Commit to a 1-year or 3-year term for a big discount (up to 72%) compared to On-Demand. Best for steady-state usage. |
| Spot Instances       | Bid for unused EC2 capacity at up to 90% discount. Best for fault-tolerant and flexible applications. |

I also used the **AWS Pricing Calculator** to estimate the monthly cost of running an EC2 instance.

> Example:
> - EC2 Instance Type: `t3.medium`
> - Region: `us-east-1`
> - Estimated Cost: **$28.08/month**

![Screenshot (329)](https://github.com/user-attachments/assets/fa8c5685-42e6-41d1-b53b-5a61742050dd)

## 2. Right-Sizing Resources

Right-sizing means adjusting the size of cloud resources to match the workload requirements — ensuring we don't overpay for unused capacity.

### Steps I followed:
- Opened the **AWS Cost Explorer**.
- Identified underutilized EC2 instances with CPU utilization consistently below **20%**.
- Example:
  - `t3.large` instance with 8% CPU usage.
- Action: 
  - Recommended downgrade to `t3.medium` — saving about **30%** monthly on that instance.


---
![Screenshot (325)](https://github.com/user-attachments/assets/0d27f250-3852-4214-abdd-01d0f7dcf542)
![Screenshot (326)](https://github.com/user-attachments/assets/2fb7008a-aef7-4883-894f-3cf89fc21740)
![Screenshot (327)](https://github.com/user-attachments/assets/008e0711-abc7-42b4-a8cc-6969927738e8)

## 3. Reserved Instances vs. Spot Instances

|  | Reserved Instances | Spot Instances |
|--|---------------------|----------------|
| **Cost Savings** | Up to 72% discount | Up to 90% discount |
| **Commitment** | 1 or 3 years | No commitment |
| **Availability** | Always available | Not guaranteed — can be interrupted |
| **Best Use Cases** | Steady workloads, production | Batch jobs, big data, flexible workloads |

### Real-World Usage:
- **Reserved Instances**: Ideal for a web app backend that always needs to be online.
- **Spot Instances**: Perfect for machine learning training jobs or data processing where interruptions are acceptable.

---

## 4. Tagging for Cost Allocation

Tagging is very powerful for tracking AWS costs across projects and teams.

### Steps I took:
- Implemented tags like:
  - `Project: CloudOptimization`
  - `Environment: Dev`
  - `Owner: Oyedokun`
- Applied these tags to EC2 instances, S3 buckets, and RDS databases.
- Enabled **Cost Allocation Tags** in the AWS Billing dashboard.


This made it easy to filter and attribute costs to specific projects, environments, or teams.

---
![Screenshot (328)](https://github.com/user-attachments/assets/3f6584f7-58f1-4d9a-8a36-3d35002dd5e7)

## 5. Reviewing AWS Bill

I logged into the **AWS Billing Dashboard** and analyzed my past bills.

### Observations:
- EC2 was taking up about **65%** of the total monthly bill.
- S3 and EBS were contributing about **20%**.
- Miscellaneous services (like CloudWatch logs) made up the remaining **15%**.

### Potential Savings Identified:
- Right-size EC2 instances.
- Enable S3 lifecycle policies to move old data to cheaper storage classes like **S3 Glacier**.


---

## 6. Designing a Cost Optimization Strategy

Based on everything I learned, here’s the cost optimization plan I designed:

### 6.1 Instance Rightsizing
- Continuously monitor instance usage.
- Downsize underutilized instances.
- Use **Auto Scaling** groups to handle variable workloads.

### 6.2 Leverage Reserved Instances
- Purchase Reserved Instances for steady-state EC2 workloads (1-year commitment).
- Choose the `No Upfront` option initially to reduce cash outflow.

### 6.3 Utilize Spot Instances
- Use Spot Instances for development, testing, or data-processing workloads.
- Implement auto-replacement strategies if spot instances are interrupted.

### 6.4 Implement Cost Allocation Tags
- Mandatory tagging across all projects for better visibility and accountability.

### 6.5 Storage Optimization
- Move infrequently accessed data to **S3 Glacier** or **S3 Intelligent-Tiering**.
- Delete unused EBS volumes and snapshots.

### 6.6 Continuous Monitoring
- Set up **AWS Budgets** and **Cost Anomaly Detection** for proactive monitoring.

---

## Project Repository Structure


## Final Thoughts

This project taught me the real-world importance of cost optimization strategies in AWS.  
Small adjustments like **rightsizing** or **tagging** can lead to **huge cost savings** over time.

I now feel confident in planning and optimizing AWS environments not just for performance, but also for **cost efficiency**.
