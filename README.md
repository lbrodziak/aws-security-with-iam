<h1>AWS security with IAM</h1>

<h2>Description</h2>
In this project, I will demonstrate how to setup EC2 instances. Also I will create new IAM policy
for the EC2, create a user group with this policy attached and then create IAM user in this
group.
<br />


<h2>Languages and Utilities Used</h2>

- <b>AWS EC2</b>
- <b>AWS IAM</b>


<h2>Project walkthrough:</h2>

<p align="center">
First thing to do was creating an S3 bucket: <br/>
<img src="https://github.com/user-attachments/assets/bd1945bc-d64c-4261-bf98-56a3fc761599" height="80%" width="80%" alt="S3 name"/>
<br />
<br />
Next we need to set ACL to enabled (this will let us control acces to each object in bucket individually):  <br/>
  <img src="https://github.com/user-attachments/assets/680a920b-7205-43d7-a994-e7a1527eeea6" height="80%" width="80%" alt="S3 ACL"/>
<br />
<br />
To expose bucket objects to public we need to turn off "Block all public access setting": <br/>
  <img src="https://github.com/user-attachments/assets/13e699f3-8430-4b0c-8cae-2c90557319e6" height="80%" width="80%" alt="Unblock public access"/>
<br />
<br />
After creating the bucket we have to upload static website files. In this case index.html and asset files: <br/>
<img src="https://github.com/user-attachments/assets/c182d4ba-7757-42bf-82ef-187c9ade02d5" height="80%" width="80%" alt="Uploaded files"/>
<br />
<br />
Now after our files are in place it is time to setup website hosting. Option is located at the bottom of the bucket's properties tab:<br/>
 <img src="https://github.com/user-attachments/assets/88e6d4ef-015b-478f-ba6e-ae2486e05d85" height="80%" width="80%" alt="Uploaded files"/>
<br />
<br />
Now after our files are in place it is time to setup website hosting. Option is located at the bottom of the bucket's properties tab:<br/>
 <img src="https://github.com/user-attachments/assets/88e6d4ef-015b-478f-ba6e-ae2486e05d85" height="80%" width="80%" alt="Hosting setup"/>
<br />
<br />
After enabling the hosting we are presented with our website URL. But after clicking on it we encounter the 403 error:<br/>
<img src="https://github.com/user-attachments/assets/437ad859-f5c5-4ac3-9343-ac5aa0a0732a" height="80%" width="80%" alt="Error"/>
<br />
<br />
This is due to the fact that all objects in bucket are private by default. To make them public we need to go back to object list click the chebox next to object name and then go to Actions -> Make public using ACL. after that when we revisit the URL we are greted with our website:<br/>
  <img src="https://github.com/user-attachments/assets/d0df0e8e-1bf2-4de4-9e40-40ceba1038c4" height="80%" width="80%" alt="Website"/>
