<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam)

**Author:** Łukasz Brodziak  
**Email:** lukasz.brodziak@gmail.com

---

![Image](http://learn.nextwork.org/surprised_maroon_fierce_chinese_gooseberry/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

In this project, I will demonstrate... I'm doing this project to learn...

### Tools and concepts

Services I used were EC2 and IAM.
Key concept learnt in this project were:
1. Creating EC2 instances and using custom tags.
2. Creating IAM user groups
3. Creating IAM policies
4. Creating IAM users and adding them to User Groups

### Project reflection

This project took me approximately 30 minutes to create this project

---

## Tags

Tags are labels used for organizing AWS resources. They can be used to define environments each resource belongs to. Tttt

The tag I’ve used on my EC2 instances is called env. The value I’ve assigned for my instances are production and development.

![Image](http://learn.nextwork.org/surprised_maroon_fierce_chinese_gooseberry/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

IAM Policies are rules which define permissions to cloud resources. In other words they define who can do what with resources.

### The policy I set up

For this project, I’ve set up a policy using JSON

I’ve created a policy that allows the user to do any action on EC2 instances except for creating and deleting tags within development environment.

### When creating a JSON policy, you have to define its Effect, Action and Resource.

The Effect defines is some action is allowed or denied on resource.
Action states which action(s) are covered by the effect
Resource defines the resource the action(s) are performed on

---

## My JSON Policy

![Image](http://learn.nextwork.org/surprised_maroon_fierce_chinese_gooseberry/uploads/aws-security-iam_1c864649)

---

## Account Alias

An account alias is a nickname that substitutes numerical account ID in login URL, making it easier to remember.

Creating an account alias took me a minute.

![Image](http://learn.nextwork.org/surprised_maroon_fierce_chinese_gooseberry/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### Users

IAM users are cloud users with specific permissions.

### User Groups

IAM user groups are groups of users with the same permissions. They simplify setting permissions for users as users inherit permissions form the group(s) they are in.

The policy attached to user group is inherited by the users iin the group thus making permission management simpler.

---

## Logging in as an IAM User

The first way is by emailing tham sign-in instructions the second is by provideing thatm with CSV file cotaining credentials.

Once I logged in as my IAM user, I noticed some of the services were showing a red message "Access denied" this is due to the User policy having only an EC2 policy therefore allowing user access only to these resources

![Image](http://learn.nextwork.org/surprised_maroon_fierce_chinese_gooseberry/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

I tested my JSON IAM policy by logging to AWS console as an IAM user from Dev IAM group. Then I tried to stop dev EC2 instance which ended with success and failed to stop dev env EC2 instance as expected by group policy.

### Stopping the production instance

Whe I tried to stop the prod instance I got an error indicating that the user doesn't have permission for this operation. This is correct as the User group the user belongs to has permissions only for dev env instances

![Image](http://learn.nextwork.org/surprised_maroon_fierce_chinese_gooseberry/uploads/aws-security-iam_0e7a9d6a)

---

## Testing IAM Policies

### Stopping the development instance

Next, when I tried to stop the development instance it failed. This was because the group policy allows users only to change EC instances that are tegged with develpment tag.

![Image](http://learn.nextwork.org/surprised_maroon_fierce_chinese_gooseberry/uploads/aws-security-iam_1811801c)

---

## The IAM Policy Simulator

### How I used the simulator

---

---
