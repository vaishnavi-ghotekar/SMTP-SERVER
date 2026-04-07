# SMTP-Assessment
Set up and configure an SMTP server on a Linux machine and verify email sending functionality.



### Create security group (ports- 22, 25, 587)

<img width="1920" height="1080" alt="Screenshot (117)" src="https://github.com/user-attachments/assets/62f582a4-5fe4-4eaa-8603-a2ca00d53568" />

### Launch ubuntu instance 

<img width="1920" height="1080" alt="Screenshot (141)" src="https://github.com/user-attachments/assets/2f13bce2-c5a7-435f-9311-7e978abe06a7" />

### Step#1:Connect instance, (update && upgrate the system)

<img width="1920" height="1080" alt="Screenshot (142)" src="https://github.com/user-attachments/assets/1b410ab2-5c24-4ab9-8523-cad4a8f8cc28" />

<img width="1920" height="1080" alt="Screenshot (143)" src="https://github.com/user-attachments/assets/781eef28-a3f8-4d8a-8801-67452a9caf37" />


### Step#1:Install Postfix on Ubuntu

<img width="1920" height="1080" alt="Screenshot (145)" src="https://github.com/user-attachments/assets/b6d75850-d6ec-43a4-b08c-0e95db370e25" />

<img width="1920" height="1080" alt="Screenshot (146)" src="https://github.com/user-attachments/assets/6e4eb390-df97-466e-be9a-d94868235be4" />

### After installation of postfix, ensure that the myhostname parameter is configured As shown below

<img width="1920" height="1080" alt="Screenshot (148)" src="https://github.com/user-attachments/assets/d5be852e-f3c9-4081-b82d-22ae035018a5" />

### Create /etc/postfix/sasl/sasl_passwd file and add your gmail ID and password we have just created using below command

### cat /etc/postfix/sasl/sasl_passwd
### [smtp.gmail.com]:587 vaishnavighotekar@gmail.com:logwrbyaqcmwslqp
<img width="1920" height="1080" alt="Screenshot (153)" src="https://github.com/user-attachments/assets/71d1e634-a43b-42a3-958d-b081cf4f820c" />

### Step#2: Update Postfix main.cf file


<img width="1920" height="1080" alt="Screenshot (157)" src="https://github.com/user-attachments/assets/478054b1-8fe1-4dae-841e-eee736d31ea8" />





### Step #3:Generate Google App Password for Postfix 


<img width="1920" height="1080" alt="Screenshot (149)" src="https://github.com/user-attachments/assets/54f71bb9-95f8-451a-958e-2823a2b50094" />
<img width="1920" height="1080" alt="Screenshot (153)" src="https://github.com/user-attachments/assets/ace882df-8b93-4864-b3a7-a04cc4f71810" />

### Step #4:Add Gmail Username and App Password to Postfix configuration

<img width="1920" height="1080" alt="Screenshot (154)" src="https://github.com/user-attachments/assets/cc9628a8-049b-42e0-816b-9e738de37ab6" />

### Step #5:Secure Your Postfix Hash Database and Email Password Files


### Step #6:Configure Relay Host postfix with gmail


### Step #7:Add Custom Configuration


### Step #9:Send Email using sendmail
