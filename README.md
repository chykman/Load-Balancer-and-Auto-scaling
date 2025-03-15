

# **Load Balancer and Auto Scaling in AWS**

## **1. Project Overview**
This project demonstrates how to **set up and configure an AWS Application Load Balancer (ALB) with Auto Scaling** to improve **availability, fault tolerance, and scalability** of web applications. The goal is to ensure that application traffic is efficiently distributed across multiple EC2 instances and that the system can dynamically scale based on demand.

### **Key Components:**
- **Target Groups** – Manage the registered EC2 instances.
- **Application Load Balancer (ALB)** – Distributes incoming traffic.
- **Auto Scaling Group (ASG)** – Automatically adjusts the number of EC2 instances.
- **Health Checks & Monitoring** – Ensure instance availability.

---

## **2. Objectives**
- Implement **AWS Load Balancer** to **distribute network traffic** across multiple instances.
- Configure **Auto Scaling** to automatically **add or remove instances** based on demand.
- Enable **high availability** and **fault tolerance** by maintaining a minimum number of healthy instances.
- Perform **connectivity testing** and validate system resilience.

---

## **3. Purpose**
- **Prevent single points of failure** by balancing requests across multiple instances.
- **Improve scalability** by dynamically adjusting infrastructure based on traffic load.
- **Enhance reliability** with automatic recovery from failed instances.

---

## **4. Prerequisites**
- An **AWS account** with necessary permissions.
- Familiarity with **EC2, Load Balancers, and Auto Scaling**.
- A running **web server** (Apache/Nginx) installed on EC2 instances.

---

## **5. Use Case**
This setup is beneficial for:
- **Web applications** that experience fluctuating traffic.
- **E-commerce platforms** requiring consistent uptime.
- **Cloud-based microservices** needing distributed load balancing.

---

## **6. Performance Goals**
- **99.9% uptime** through high availability.
- **Auto healing** – Instances automatically replaced when terminated.
- **Efficient resource utilization** to optimize costs.

---

## **7. Project Steps and Commands**

### **7.1. Creating the Target Group**
1. Navigate to **EC2 Dashboard** → **Target Groups**.  
   ![Select Target Groups](https://github.com/user-attachments/assets/78eec541-62f2-4e5a-bc3c-52db3c262470)

2. Click on **Create Target Group**.  
   ![Create Target Group](https://github.com/user-attachments/assets/ac2fa742-c9c3-4d99-9faa-cb642b91dca6)

3. Choose **Instances** as the target type and configure health checks.  
   ![Configure Target Group](https://github.com/user-attachments/assets/466452e3-29e4-4f3b-8638-a0af7855457f)

4. Confirm and finalize the **Target Group** creation.  
   ![Target Group Created](https://github.com/user-attachments/assets/16f8f996-f920-4706-ab77-7d19bb98afaa)

5. Register an EC2 instance in the Target Group.  
   ![Register Instance](https://github.com/user-attachments/assets/9ae2f7ce-a513-42c2-b3fe-a041e6179d07)

---

### **7.2. Creating the Load Balancer**
1. In the **EC2 Dashboard**, navigate to **Load Balancers**.  
   ![Select Load Balancer](https://github.com/user-attachments/assets/cd7d65c7-8e13-4610-a298-b4e233e69dc2)

2. Click **Create Load Balancer** → **Application Load Balancer**.  
   ![Create ALB](https://github.com/user-attachments/assets/9eea044b-e394-4004-8405-802f97bbfe28)

3. Enter a **Load Balancer Name** and configure **Listener Settings**.  
   ![ALB Configuration](https://github.com/user-attachments/assets/db5d691f-29ec-41a5-bcf3-637ff181b004)

4. Select **VPC and Subnets** under **Network Mapping**.  
   ![Network Mapping](https://github.com/user-attachments/assets/8ec4f057-66db-452a-a97a-68636721a7c4)

5. Assign the previously created **Target Group**.  
   ![Attach Target Group](https://github.com/user-attachments/assets/b21d32d3-085a-41e3-aeba-ed04feeb6cda)

6. Finalize and create the **Application Load Balancer**.  
   ![ALB Created](https://github.com/user-attachments/assets/ec566f08-5a42-4c83-8cb4-04b5036cdf5b)

7. Verify **Target Group Health**, ensuring instances are marked **Healthy**.  
   ![Target Group Health](https://github.com/user-attachments/assets/f5ab834c-e0b1-4eae-b7f3-b76bf9ffa76e)

---

### **7.3. Testing Connectivity**
1. Attempt to **ping the public IP** of the instance via the command prompt.  
   ![Ping Test](https://github.com/user-attachments/assets/b7a9fef8-e202-444c-9dac-ed5676a53002)

2. If unsuccessful, check **Security Groups, NACLs, and Firewall Rules**.  
3. Once corrections are made, the **ping should be successful**.  
   ![Successful Ping](https://github.com/user-attachments/assets/70a90acd-4bb5-45aa-9950-9270d047764f)

---

### **7.4. Creating the Auto Scaling Group**
1. Navigate to **Auto Scaling Groups** and create a new group.  
   ![Select Auto Scaling](https://github.com/user-attachments/assets/69efd849-c2f6-4925-88a9-e1f69aab35ab)

2. Click **Create Launch Template**.  
   ![Create Launch Template](https://github.com/user-attachments/assets/d9dd9b93-1288-4f07-8a31-1eec97ecef9a)

3. Assign a **Launch Template Name** and choose an **AMI**.  
   ![Launch Template Configuration](https://github.com/user-attachments/assets/bfb3b2fa-afcf-4e08-89be-82d6d2d9afc5)

4. Configure settings and create the **Auto Scaling Group**.  
   ![Auto Scaling Group Created](https://github.com/user-attachments/assets/a1727d81-8227-4171-b178-e8b96e1f6c5c)

5. Verify that the **Auto Scaling Group has launched an instance**.  
   ![Instance Created](https://github.com/user-attachments/assets/f982fcdb-8d29-425c-910f-a56a92b6bfe9)

---

### **8. Auto Healing & Scaling**
1. **Manually terminate an instance** and observe Auto Scaling automatically creating a replacement instance.  
   ![Terminate Instance](https://github.com/user-attachments/assets/72ab7725-53e8-4f19-b8f8-54d517bcceda)

2. Auto Scaling detects the instance failure and creates a **new healthy instance**.  
   ![New Instance Created](https://github.com/user-attachments/assets/5590c5fe-d5ed-4b17-8a11-d0f15efd75e1)

---

## **9. Conclusion**
- The **Application Load Balancer** effectively distributes traffic across multiple instances.
- **Auto Scaling** dynamically adjusts infrastructure based on traffic demand.
- The system achieves **high availability, fault tolerance, and self-healing**.
