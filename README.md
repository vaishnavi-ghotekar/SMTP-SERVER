# SMTP-Assessment
Set up and configure an SMTP server on a Linux machine and verify email sending functionality.



### Create security group (ports- 22, 25, 587)

<img width="1920" height="1080" alt="Screenshot (117)" src="https://github.com/user-attachments/assets/62f582a4-5fe4-4eaa-8603-a2ca00d53568" />

### Launch ubuntu instance 

<img width="1920" height="1080" alt="Screenshot (141)" src="https://github.com/user-attachments/assets/2f13bce2-c5a7-435f-9311-7e978abe06a7" />

### Step#1 :Connect instance, (update && upgrate the system)

<img width="1920" height="1080" alt="Screenshot (142)" src="https://github.com/user-attachments/assets/1b410ab2-5c24-4ab9-8523-cad4a8f8cc28" />

<img width="1920" height="1080" alt="Screenshot (143)" src="https://github.com/user-attachments/assets/781eef28-a3f8-4d8a-8801-67452a9caf37" />


### Step#2 :Install Postfix on Ubuntu

<img width="1920" height="1080" alt="Screenshot (145)" src="https://github.com/user-attachments/assets/b6d75850-d6ec-43a4-b08c-0e95db370e25" />

<img width="1920" height="1080" alt="Screenshot (146)" src="https://github.com/user-attachments/assets/6e4eb390-df97-466e-be9a-d94868235be4" />

### After installation of postfix, ensure that the myhostname parameter is configured As shown below

<img width="1920" height="1080" alt="Screenshot (148)" src="https://github.com/user-attachments/assets/d5be852e-f3c9-4081-b82d-22ae035018a5" />


### Step3 #:Generate Google App Password for Postfix 


<img width="1920" height="1080" alt="Screenshot (149)" src="https://github.com/user-attachments/assets/54f71bb9-95f8-451a-958e-2823a2b50094" />

### Create sasl_passwd file inside the ( /etc/postfix/sasl/ ) and add your gmail ID and password we have just created using below command

### cat /etc/postfix/sasl/sasl_passwd | o/p : ( [smtp.gmail.com]:587 vaishnavighotekar@gmail.com:logwrbyaqcmwslqp )
<img width="1920" height="1080" alt="Screenshot (153)" src="https://github.com/user-attachments/assets/71d1e634-a43b-42a3-958d-b081cf4f820c" />


### Step#4 : Update Postfix main.cf file (vim /etc/postfix/main.cf)

<img width="1920" height="1080" alt="Screenshot (157)" src="https://github.com/user-attachments/assets/478054b1-8fe1-4dae-841e-eee736d31ea8" />
# relayhost = [smtp.gmail.com]:587
# Enable SASL authentication
smtp_sasl_auth_enable = yes
# Disallow methods that allow anonymous authentication
smtp_sasl_security_options = noanonymous
# Location of sasl_passwd
smtp_sasl_password_maps = hash:/etc/postfix/sasl/sasl_passwd
# Enable STARTTLS encryption
smtp_tls_security_level = encrypt
# Location of CA certificates
smtp_tls_CAfile = /etc/ssl/certs/ca-certificates.crt

### Step5 #:Add Gmail Username and App Password to Postfix configuration

<img width="1920" height="1080" alt="Screenshot (154)" src="https://github.com/user-attachments/assets/cc9628a8-049b-42e0-816b-9e738de37ab6" />

### Step6 #:Secure Your Postfix Hash Database and Email Password Files

### chown root:root /etc/postfix/sasl/sasl_passwd 

### chmod 600 /etc/postfix/sasl/sasl_passwd 

<img width="1920" height="1080" alt="Screenshot (156)" src="https://github.com/user-attachments/assets/080e0626-757b-4520-a96f-e24c037cb42a" />


### Step7 #:Configure Relay Host postfix with gmail

### Set the relayhost

relayhost = [smtp.gmail.com]:587

<img width="1920" height="1080" alt="Screenshot (159)" src="https://github.com/user-attachments/assets/186a0c13-1cfa-4aaa-b9b0-368639741aba" />




<img width="1920" height="1080" alt="Screenshot (160)" src="https://github.com/user-attachments/assets/a096891a-15af-4c05-851d-810dec4b5b3d" />

### Restart the system

### Step9# :Send Email using sendmail

sendmail example@gmail.com
From: root@gmail.com
Subject: Test mail
Testing Email
.
<img width="1920" height="1080" alt="Screenshot (163)" src="https://github.com/user-attachments/assets/893dbcaa-3277-481f-8a63-56ddf62934a3" />
<img width="1920" height="1080" alt="Screenshot (165)" src="https://github.com/user-attachments/assets/ee3e133f-104d-4453-8726-cabccbd7120d" />



----------------------------------------------------------------------------------------------------------------------------



### I built a bulk email automation system using Python and SMTP. I used Docker to run MailHog for testing email delivery and verified messages through a web interface (make sure port 1025 and 8025 is open)


### execute a command to run a container (docker run -d -p 1025:1025 -p 8025:8025 mailhog/mailhog )
<img width="1919" height="150" alt="Screenshot 2026-04-28 151334" src="https://github.com/user-attachments/assets/21386e25-13ee-4963-9a6c-0f38e3e9537d" />

### I created a Python script and executed it successfully (send_bulk.sh)
<img width="650" height="62" alt="Screenshot 2026-04-28 151401" src="https://github.com/user-attachments/assets/38804e72-d454-4093-babc-dc3adcc2d5dd" />

<img width="726" height="672" alt="Screenshot 2026-04-28 151251" src="https://github.com/user-attachments/assets/c64a34ec-afbf-4e04-9ec2-5746e2ec820d" />

### I received emails in MailHog, which is created inside the container.
<img width="1919" height="1077" alt="Screenshot 2026-04-28 152052" src="https://github.com/user-attachments/assets/c06455d9-c558-46a7-b7f8-e9606a070579" />
