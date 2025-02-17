# Assignment 1 (Week 4, Day 1): Introduction to AWS IAM & DynamoDB

## Objective

- Understand the basics of **AWS IAM** (Identity and Access Management).
- Create an AWS IAM user with appropriate permissions.
- Explore the **DynamoDB** service in the AWS console, examining how tables are created and managed.
- Document your initial observations and setup steps for future reference.

## Instructions

### Part 1: Set Up AWS IAM

1. **Sign In / Create AWS Account**
   - If you do not already have one, create an AWS account (free tier is available).
   - If you have an existing account, sign in to the AWS Management Console.
2. **Create an IAM User**
   - In the AWS console, navigate to **IAM**.
   - Create a new user (e.g., `student-iam-user`) with **programmatic and/or console access** depending on your needs.
   - Assign at least one policy granting access to **DynamoDB** (you can use a custom policy or a managed policy like `AmazonDynamoDBFullAccess` for learning purposes).

### Part 2: Explore DynamoDB

1. **Open DynamoDB Console**
   - From the AWS console, select **DynamoDB** under the list of services.
2. **Create a Test Table**
   - Choose a table name (e.g., `TestTable`) and set a **partition key** (e.g., `id`).
   - Use the default settings (on-demand capacity or provisioned capacity) for a quick setup.
3. **View Table and Data**
   - Explore the **Items**, **Metrics**, and **Indexes** sections in the DynamoDB console.
   - Optionally, add a sample item (e.g., a key-value pair) to see how data is stored.

### Part 3: Document Your Findings

- **Note the Steps**
  - Record your **IAM user** creation process, **DynamoDB table** settings, and any observations about the console interface.
- **Take (Optional) Screenshots**
  - If allowed, capture screenshots of your IAM user summary or the newly created DynamoDB table.

### Part 4: Reflect & Plan

- Think about how you might integrate DynamoDB with a future application or React project.
- Consider best practices like **least privilege** for IAM policies (e.g., do not give overly broad permissions in a real-world setting).

---

## Submission

4. **GitHub Repository**
   - Create a repository named `aws-intro-lab`.
   - Include a **README.md** (or a markdown file of your choice) summarizing:
     - Steps you took to create the IAM user and basic DynamoDB setup.
     - Any relevant screenshots, if possible (you can paste them into the repo or link externally).
   - Push these files to your GitHub repo.
5. **Submission Link**
   - Provide the link to your **`aws-intro-lab`** GitHub repository through your usual submission channel.

---

## Rubric

| Criteria                                     | Limited (0 pts)                                       | Partial (3 pts)                                                      | Complete (5 pts)                                                                       |
| -------------------------------------------- | ----------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| **1. AWS Account Access**                    | No AWS account or no successful login                 | Account exists but set up partially or with issues                   | Successfully logged in or created an AWS account                                       |
| **2. IAM User Creation**                     | IAM user not created or incorrect permission settings | IAM user created with limited documentation or uncertain permissions | IAM user properly created with clearly defined and documented permissions              |
| **3. DynamoDB Table Exploration**            | No table created or unable to demonstrate table setup | Table created but minimal exploration or unclear documentation       | DynamoDB table created with at least one item; console features noted                  |
| **4. Documentation & Observations**          | Little to no notes or unclear steps                   | Some notes on process, but missing details or clarity                | Clear, step-by-step documentation (README) including relevant observations/screenshots |
| **5. Code/Repo Organization** (README, etc.) | No GitHub repo or incomplete project files            | Repo exists but lacks structure or clear documentation               | Well-organized repo with a clear README, reflecting all setup steps                    |
