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