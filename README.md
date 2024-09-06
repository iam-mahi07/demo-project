# GitHub Actions demo-project

This repo walks you through and explains you the implementation of a CI/CD Pipeline with GitHub Actions for Automated Deployment and Rollback.

# What I achieved: 

I've created a remote repository to host the source code of the application on GitHub, tracked and committed all the files and folders of the project and pushed to GitHub to host it on a web. Also, created a CI/CD pipeline using GitHub Actions workflow for building the Docker image and pushing it to ECR, and deploying to ECS. This workflow (pipeline) triggers whenever an event is occured (push).

# Prerequisites of the project:
1. AWS Account: With permissions to create an ECS Cluster, Task Definitions, IAM roles, and ECR.
2. Git Bash: Install on local machine to execute git commands.
3. GitHub Repository: To host the web application code (project source code).
4. GitHub Secrets: Store AWS credentials (AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY), AWS region (AWS_REGION), and ECR repository URI (ECR_REPOSITORY_URI) in GitHub Secrets.

# Steps to implement the project:

1. Create an AWS account.
2. Create an ECR private registry to store the images.
3. Create an ECS cluster. Then create a task definition, that creates a task and task has a container to run the application. In order to expose the application we need a service same as Kubernetes services, we create service to run the task.
4. Once all these are setup, then commit and push the source code to the main branch.

   Steps to track, commit and push the source code to GitHub:
   
   a) Go to the path where you've all the files and folders of the project.

   b) Right click and click on "Open Git Bash Here". Git Bash will open directly and the path would also be selected instead of manually entering the path to choose the files and folders using cd command.

   c) git init : Initialize the Git repository at the same path where you've all the files and folders of the project. 

   d) git add * : This will track all files and folders.

   e) git commit -m "message" . : This will commit all files and folders that are tracked. if " . " is used at the end of the command and to commit single file use name. 

   f) git branch -M main : This will forcefully renames the master branch to main on Git Bash to match it with main branch on GitHub to avoid any errors during the push. 

   g) git remote add origin "https URL of git repo" : This command adds a remote repository (referred to as origin) to your local repository. It links your local Git repository to a remote repository stored on a 
      server (e.g., GitHub).

   h) git push -u origin main: This command pushes your local main branch to the origin remote repository and sets origin main as the default upstream branch. This means in future, you can just use git push 
      without specifying the remote or branch.

5. Since "push" is an event, it triggers the workflow (the script in the YAML file). The pipeline will run all the steps in the YAML file, such as it checkouts the code, builts the Dockerfile to create an image and push the image to ECR and deploys the application on ECS. 

By following all the steps mentioned above will ensure to implement a CI/CD pipeline using GitHub actions for a seamless automated deployment of application on ECS and rollback. 

#ThanksVisitAgain 👋
   
