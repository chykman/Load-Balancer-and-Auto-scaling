# Load-Balancer-and-Auto-scaling

## 7. Project and Command steps

### 7.1. Creating the target group

- We are going to create target groups for our Load balancer
 
 - Go to the ec2 section and select target groups
   ![image](https://github.com/user-attachments/assets/78eec541-62f2-4e5a-bc3c-52db3c262470)

   - Go to the Create target groups section
    ![image](https://github.com/user-attachments/assets/ac2fa742-c9c3-4d99-9faa-cb642b91dca6)
  -
   ![image](https://github.com/user-attachments/assets/466452e3-29e4-4f3b-8638-a0af7855457f)

-
![image](https://github.com/user-attachments/assets/16f8f996-f920-4706-ab77-7d19bb98afaa)

- The target group has been created
- -
- 
  - You go to register your instances in the group, in this case I am only allowed to have one instance running
    ![image](https://github.com/user-attachments/assets/9ae2f7ce-a513-42c2-b3fe-a041e6179d07)
    - Create the target group
      ![image](https://github.com/user-attachments/assets/f7568164-3bb4-440c-9c00-d499c483a849)
      -
      ![image](https://github.com/user-attachments/assets/810b6542-31f3-417f-aef8-b876d938c796)

--
### 7.2. Creating the Load Balancer

- On the EC2 section go to the Load balancer
  ![image](https://github.com/user-attachments/assets/cd7d65c7-8e13-4610-a298-b4e233e69dc2)

  - Click on Create load balancer
    ![image](https://github.com/user-attachments/assets/d2438da5-cb0b-47a9-bd1c-ae12a6389f4b)

    - Click on Create Apllication Load balancer
      ![image](https://github.com/user-attachments/assets/9eea044b-e394-4004-8405-802f97bbfe28)

      - Fill in the required fields
       ![image](https://github.com/user-attachments/assets/db5d691f-29ec-41a5-bcf3-637ff181b004)
      - Fill in the details for your network mapping
        ![image](https://github.com/user-attachments/assets/8ec4f057-66db-452a-a97a-68636721a7c4)
        - Select the newly created target group in the default action
          ![image](https://github.com/user-attachments/assets/b21d32d3-085a-41e3-aeba-ed04feeb6cda)

          - Finalise and create the Load balancer
            ![image](https://github.com/user-attachments/assets/ec566f08-5a42-4c83-8cb4-04b5036cdf5b)

            - Load balancer has been created
            ![image](https://github.com/user-attachments/assets/932bf0cc-226c-4f39-acbf-5cc1c6767854)
       - Go to your target group and checkt the health of your server, it shows that it is healthy
       - - ![image](https://github.com/user-attachments/assets/f5ab834c-e0b1-4eae-b7f3-b76bf9ffa76e)
        
           ### Command Prompt Connection
           - Try and reach the public ip of your instance through command prompt , you won't be able to reach it
             ![image](https://github.com/user-attachments/assets/b7a9fef8-e202-444c-9dac-ed5676a53002)

             - After confirming my firewall, web server configuration, health check , NACL I was able to ping the ope ip address
               ![image](https://github.com/user-attachments/assets/70a90acd-4bb5-45aa-9950-9270d047764f)

### 7.2. Creating the Autoscaling group
- Go to the search bar and search for Auto scaling group and create
  ![image](https://github.com/user-attachments/assets/69efd849-c2f6-4925-88a9-e1f69aab35ab)
  - ![image](https://github.com/user-attachments/assets/91af3697-4a81-4134-bfe3-cc80575b3417)
  - Click on Create template
  - ![image](https://github.com/user-attachments/assets/d9dd9b93-1288-4f07-8a31-1eec97ecef9a)
 
  - Enter a name for you launch template 
    ![image](https://github.com/user-attachments/assets/bfb3b2fa-afcf-4e08-89be-82d6d2d9afc5)

    -Select a quick start OS image
    ![image](https://github.com/user-attachments/assets/dc74b17d-0b55-47bd-97a2-7b4aa7b89afe)

    - Input other details and create your auto scaling group lauch template
      ![image](https://github.com/user-attachments/assets/12683d49-8d70-4f5f-af1e-ac4e1e307f44)

      - Now return to auto scaling groups settings
        ![image](https://github.com/user-attachments/assets/3f6fb107-107a-4068-8b87-c2f89538af46)

        - Name your launch template
        ![image](https://github.com/user-attachments/assets/49622b82-95ef-4cf6-8840-630f03fb9a0e)
 - fill in the required info and click on next
  ![image](https://github.com/user-attachments/assets/b685fdbc-ab68-4c03-b2fa-0700ac0b8fa8)
-fill in the required info and click on next
  ![image](https://github.com/user-attachments/assets/be7d79fe-7753-4e69-99e2-1b20e70922c3)
-fill in the required info and click on next
![image](https://github.com/user-attachments/assets/777433a9-5286-4208-a45a-1097c088a963)
-fill in the required info and click on next
![image](https://github.com/user-attachments/assets/4ea90e09-bd8b-42f5-ae4b-f838b7bd71f0)
-fill in the required info and click on next
![image](https://github.com/user-attachments/assets/f7b54c6b-5b4c-4bf3-aec6-f70221fa1a81)

-Enter the tags and click next
![image](https://github.com/user-attachments/assets/a80d53b3-41d0-4bd7-8a3e-91e4150f3b4c)

-Review settings 
![image](https://github.com/user-attachments/assets/b3481f90-272b-4def-9c9c-3942404db8fd)

- Once done click next
 ![image](https://github.com/user-attachments/assets/be7cf3b5-d4d4-49e1-9cbd-b0cf261017be)

-Auto scaling group ws created successfully
![image](https://github.com/user-attachments/assets/a1727d81-8227-4171-b178-e8b96e1f6c5c)

- Click on the new auto scaling group
![image](https://github.com/user-attachments/assets/1f34d405-9f9a-4121-9454-fa61505d5091)

- Go to instance management, you'll observe that the scaling group has created a new and healthy instance
  ![image](https://github.com/user-attachments/assets/f982fcdb-8d29-425c-910f-a56a92b6bfe9)














 







            

  







---
