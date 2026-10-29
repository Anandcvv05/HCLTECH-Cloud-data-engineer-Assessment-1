# Cloud Computing and Linux Practical Assessment

**Name:** CVV ANAND  
**Student ID:** 23BTRCL176
**HCL ID:** HCLTFP2297504

## 📌 Project Overview

This repository documents the practical assessment covering SQL queries, Linux command-line operations, AWS cloud services, Identity and Access Management (IAM), and Microsoft Azure resource management. The objective is to demonstrate practical knowledge of database querying, Linux file management, AWS infrastructure inspection, secure S3 bucket access, and Azure Resource Group creation.

## 🛠️ Technologies Used

- **MySQL** – Database creation, table management, and SQL queries.
- **Linux / Ubuntu** – Directory navigation and file management.
- **Amazon Web Services (AWS)** – EC2 instance details and S3 access control using IAM policies.
- **Microsoft Azure** – Resource Group creation and configuration.

## 📂 Assessment Tasks

### Task 1: SQL – Find the Second-Highest Distinct Salary

**Objective:** Retrieve the second-highest distinct salary from an employee table.

**SQL Query:**

```sql
SELECT MAX(salary) AS SecondHighestSalary
FROM employee
WHERE salary < (
    SELECT MAX(salary)
    FROM employee
);
```

**Explanation:**
- The inner query retrieves the highest salary.
- The outer query filters salaries below the highest salary.
- `MAX(salary)` returns the highest remaining salary, which is the second-highest distinct salary.

**Expected Result:** The query returns the second-highest distinct salary available in the employee table.

### Task 2: Linux – Directory and File Management

**Objective:** Display the current working directory, create two files, list the files, and demonstrate the directory path and filenames.

**Commands:**

```bash
# Display the current working directory
pwd

# Create two files
touch task1.txt
touch task2.txt

# List files in the current directory
ls

# Display the current directory path
pwd

# Display the filenames with details
ls -l task1.txt task2.txt
```

**Explanation:**
- `pwd` displays the absolute path of the current working directory.
- `touch` creates empty files if they do not exist.
- `ls` lists files and directories.
- `ls -l` displays file details, including permissions, size, and modification time.

**Expected Result:** Two files, `task1.txt` and `task2.txt`, are created and displayed with their directory information.

### Task 3: AWS EC2 – Instance Details

**Objective:** Identify and display the EC2 instance type, IP address, and instance name.

**Procedure:**

1. Sign in to the AWS Management Console.
2. Navigate to **EC2 → Instances**.
3. Select the required EC2 instance.
4. Open the instance summary or details panel.
5. Record the following information:
   - **Instance Name:** The Name tag assigned to the instance.
   - **Instance Type:** The instance configuration, such as `t2.micro` or another configured type.
   - **Public IPv4 Address:** The public IP address, if assigned.
   - **Private IPv4 Address:** The private IP address used within the VPC.

**Expected Result:** The EC2 instance details are displayed in the AWS Management Console and documented using a screenshot.

### Task 4: AWS IAM – S3 Read-Only Access Policy

**Objective:** Create an IAM policy that grants read-only access to a specified Amazon S3 bucket.

**IAM Policy JSON:**

Replace `YOUR-BUCKET-NAME` with the actual S3 bucket name.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowBucketListing",
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket"
      ],
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME"
    },
    {
      "Sid": "AllowObjectRead",
      "Effect": "Allow",
      "Action": [
        "s3:GetObject"
      ],
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
    }
  ]
}
```

**Procedure:**

1. Open the AWS Management Console.
2. Navigate to **IAM → Policies → Create policy**.
3. Select the JSON editor.
4. Paste the policy above and replace the bucket name.
5. Validate the policy and create it with a descriptive name, such as `S3SpecifiedBucketReadOnly`.
6. Attach the policy to the required IAM user, group, or role.

**Explanation:**
- `s3:ListBucket` permits listing the specified bucket's contents.
- `s3:GetObject` permits reading objects inside that bucket.
- The bucket ARN applies to bucket-level listing.
- The `bucket-name/*` ARN applies to objects inside the bucket.
- No upload, deletion, or modification permissions are granted by this policy.

**Expected Result:** The attached identity receives the specified read-only S3 permissions, subject to other applicable IAM policies, bucket policies, and access controls.

### Task 5: Microsoft Azure – Create a Resource Group

**Objective:** Create an Azure Resource Group named `practical-pc` in a selected Azure region.

**Procedure:**

1. Sign in to the [Azure Portal](https://portal.azure.com/).
2. Search for **Resource groups**.
3. Click **Create**.
4. Select the appropriate Azure subscription.
5. Enter the Resource Group name: `practical-pc`.
6. Choose the required region.
7. Click **Review + Create**.
8. After validation, click **Create**.
9. Open the created Resource Group to verify its details.

**Explanation:** An Azure Resource Group is a logical container used to organize and manage related Azure resources. It supports centralized access control, monitoring, and lifecycle management.

**Expected Result:** The `practical-pc` Resource Group is created successfully in the selected region.

## 📸 Screenshots and Evidence

The assessment evidence includes screenshots demonstrating:

1. SQL query execution and the second-highest salary result.
2. Linux commands used to display the current directory and create files.
3. AWS EC2 instance information, including its type and IP addresses.
4. The created IAM policy for S3 read-only access.
5. The Azure Resource Group named `practical-pc`.

## 🎯 Learning Outcomes

- Practiced SQL aggregation and subqueries.
- Learned Linux directory navigation and file operations.
- Understood how to inspect EC2 instance configurations.
- Implemented least-privilege access at the S3 bucket and object level.
- Learned to create and verify Azure Resource Groups.
- Gained practical experience with database management, command-line tools, and cloud administration.

## 👨‍💻 Author

**CVV ANAND**  
**Student ID:** 23BTRCL176

---

*This README documents the practical tasks and their implementation steps. The accompanying screenshots serve as evidence of the work performed.*
