### 1. Create AWS Free Tier Account

Visit the [AWS Free Tier](https://aws.amazon.com/free/) page and follow the instructions to create a new AWS account.
Ensure that you understand the terms and conditions of the AWS Free Tier.

### 2. Install Git on your Machine

Download and install Git on your local machine. You can find the Git installer for various operating
systems [here](https://git-scm.com/downloads).

### 3. Connect Git Bash with AWS CodeCommit

Follow these steps to connect Git Bash with AWS CodeCommit:

- Open Git Bash on your machine.

- Configure Git with your AWS credentials:

```bash
git config --global credential.helper '!aws codecommit credential-helper $@'
git config --global credential.UseHttpPath true
```

- Configure AWS CLI with your credentials:

```bash
aws configure
```

- Follow the prompts to enter your AWS Access Key ID, Secret Access Key, region, and preferred output format.

### 4. Clone the vulnerable code from the Git repository

Use the following command to clone the vulnerable code repository:

```bash
git clone https://github.com/asecurityguru/aws-vulnerable-code-without-buildspec
```

Navigate to the cloned directory using:

```bash
cd aws-vulnerable-code-without-buildspec
```

### 5. Create a new AWS Code repository

Go to the [AWS CodeCommit Console](https://console.aws.amazon.com/codecommit/) and create a new repository. Follow the
prompts to configure the repository settings.

### 6. Push Vulnerable application code to AWS CodeCommit using Git Bash

Follow these steps to push the vulnerable application code to AWS CodeCommit:

- Navigate to the local repository directory:

```bash
cd path/to/aws-vulnerable-code-without-buildspec
```

- Initialize a Git repository (if not already initialized):

```bash
git init
```

- Add the AWS CodeCommit repository as a remote:

```bash
git remote add origin <AWS CodeCommit repository URL>
```

- Add and commit the files:

```bash
git add .
git commit -m "Initial commit"
```

- Push the code to AWS CodeCommit:

```bash
git push -u origin master
```

Replace `<AWS CodeCommit repository URL>` with the URL of the AWS CodeCommit repository you created in step 5.

Now, your vulnerable application code is pushed to the AWS CodeCommit repository.

Note: Make sure you have the necessary permissions and access to the AWS CodeCommit repository. Adjust AWS CLI
configurations accordingly if needed.

Certainly! Here's a step-by-step guide:

### 7. Create a SonarCloud Account and Set Buildspec.yaml in AWS Repository

#### Part 1: Setting Up Buildspec.yaml in AWS Repository

1. Navigate to your AWS repository.

2. Click on your repository name to access the repository.

3. Add a new file by clicking on the "Add file" button.

4. In the new file editor, paste your code.

5. Specify the file name as `buildspec.yml`. AWS conventionally uses this name for the build specification file. You can
   choose a different name, but remember to adjust references accordingly later.

6. Authorize the changes with your credentials, providing your name and a security email.

7. Commit the changes to the repository.

8. Verify that the new file [`buildspec.yml`](./buildspec.yml) has been successfully added by checking the repository.

#### Part 2: Creating a SonarCloud Account and Obtaining Project Key, Project Organization, and Token

1. In the next chapter, we will create a SonarCloud account. Navigate to
   the [SonarCloud website](https://sonarcloud.io/) and sign up for an account.

2. Once logged in, create a new project on SonarCloud.

3. Retrieve the project key and project organization from SonarCloud. These values are essential for integrating
   SonarCloud with your AWS repository.

4. Generate an authentication token on SonarCloud. This token will be used to establish a secure connection between
   SonarCloud and your AWS repository.

Now, you are ready to proceed with the next steps in your DevSecOps AWS and Terraform course, integrating SonarCloud
into your CI/CD pipeline for enhanced code quality analysis.

