# AWS IAM User Provisioning Showcase 🔒

This repository documents the process of creating an admin user account in AWS IAM to demonstrate user management and adherence to the principle of least privilege.

## 1. Users and Permissions

| User Name | Role | Attached Policy |
| JohnAdmin | SystemAdmin | :--- |
| **AdminUser** | Full administrative access. | AWS Managed Policy: `AdministratorAccess` |


## 2. Implementation Steps

### Step 2.1: Creating the AdminUser

1.  Navigated to the IAM Dashboard in the AWS Console.
   ![image](https://github.com/user-attachments/assets/b68ee1e8-b578-49db-95c6-d6ac6deb790a)

2.  Clicked 'Create user' and named the user 'User name' and assigned initial password. Selected option to have user change the password at first login.
   ![image](https://github.com/user-attachments/assets/32586787-5352-40a4-97cf-0d52840681d7)

   ![image](https://github.com/user-attachments/assets/efc4f526-7764-468a-9df5-9b43611753ab)


### Step 2.2: Assigned the Custom Policy (SystemAdministrator)

1. Assigned the appropriate policy to give user system admin access.
   ![image](https://github.com/user-attachments/assets/54bab45b-0703-4151-8b0d-b862d17b4949)

2. Review and Create new user, after verifying all information is correct.
   ![image](https://github.com/user-attachments/assets/6603a87c-b2ec-41a8-be89-45f6d254a71c)



**Policy JSON:**

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "cloudwatch:Describe*",
                "cloudwatch:Get*",
                "cloudwatch:List*",
                "logs:Describe*",
                "logs:Get*",
                "logs:FilterLogEvents"
            ],
            "Resource": "*"
        }
    ]
}
# AWS IAM User Provisioning Showcase 🔒

This repository documents the process of creating two distinct user accounts in AWS IAM to demonstrate user management and adherence to the principle of least privilege.

## 1. Users and Permissions

| User Name | Role | Attached Policy |
| :--- | :--- | :--- |
| **AdminUser** | Full administrative access. | AWS Managed Policy: `AdministratorAccess` |
| **LimitedMonitoringUser** | Read-only access to monitoring and log services. | Custom Managed Policy: `CloudWatchLogsReadOnlyPolicy` |

## 2. Implementation Steps

### Step 2.1: Creating the AdminUser

1.  Navigated to the IAM Dashboard in the AWS Console.
2.  Clicked 'Add user' and named the user 'AdminUser'.
3.  ... (Detailed steps)

### Step 2.2: Creating the Custom Policy (CloudWatch & Logs Read-Only)

We created a custom policy to grant only necessary permissions.

**Policy JSON:**

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "cloudwatch:Describe*",
                "cloudwatch:Get*",
                "cloudwatch:List*",
                "logs:Describe*",
                "logs:Get*",
                "logs:FilterLogEvents"
            ],
            "Resource": "*"
        }
    ]
}
