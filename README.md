 # DevOps Lab Work

**Shri Radhey Mishra – 500110514**

---

## DevOps Lab 1 – Basic Git Commands (Lab-2)

[https://github.com/ShriRadhey-Mishra/Lab-2.git]

In this Lab, we performed and understood the working of some basic Git commands such as:

- `git add <file_name>`: We can add any file specified, or all the files in our Working Directory to the Staging area.
- `git commit`: After adding our files to the Staging area, we commit those files to the local repository, which we have linked to our remote repository on GitHub.
- `git push`: Using this command, we push the content of the Local Repository to the remote Repository, where we have our content stored.
- `git init`: Using this command, we initialize our local working directory as a git Directory. It generates a `.git` directory which helps us to perform git actions in the directory.
- `git status`: Using this command, we check what is the status of the current branch we are in. We can see what files are added, unstaged, uncommitted etc.
- `git clone`: We use this command when we are making a clone of a Remote Repository to our local system, where we can make changes to the content.

Using these commands, we can make a directory in our Local machine, initialize it as a git directory, create files in it, add them to the staging area, commit them to the local repository and then create a remote link with the remote repository and push the content to the remote repository.

---

## DevOps Lab 2 – Branching and Merging (Lab-2)

[https://github.com/ShriRadhey-Mishra/Lab-2.git]

In this Lab, we performed and understood working with branches in git, working parallelly with peers, and merging the branches. We performed the experiment in the last repository. We used the following commands:

- `git branch`: We use this command to check what branches we have in our pipeline yet. We can create branches using the syntax, `git branch branch_name`, to create a new branch.
- `git switch`: We use this command to switch between the branches.
- `git checkout`: We use this command to check out a specific commit using the commit id which we can get from the `git log --oneline` command. However, using the flag `-b`, we can also create branches using this command using the syntax: `git checkout -b branch_name`.
- `git merge branch2 branch1`: This command allows us to merge the content of branch2 to branch1. If there is any conflict during merge, it will pop a diff where we can then merge the code manually, resolving the conflict.
- `git rebase`: Instead of actually merging the branch, we move the base of a branch to the base we desire.

We use these commands to perform a merge, where we make some commits in the main branch, then branch off to a new branch where we make some commits, then merge these branches and resolve the merge conflict.

---

## DevOps Lab 3 – Submodules (Repo1, Repo2, Repo3)

- [https://github.com/shriradhey-mishra/repo1.git]
- [https://github.com/shriradhey-mishra/repo2.git]
- [https://github.com/shriradhey-mishra/repo3.git]

In this lab we performed and understood the working and the use of git submodules.

Using the command `git submodule add <git_link>` we can create a reference directory of the repository on the remote location. Using this reference directory we can access the content for our local repository.

In this lab particularly, we created 3 different repositories namely, Repo1, Repo2, and Repo3. In Repo1, we had a MAIN file which only had an HTML file. In Repo2 we have a CSS file and in Repo3 we have a JS file. In Repo1, we now use the submodule command to add Repo2 and Repo3 as the submodules, and access their content for our MAIN HTML file.

---

## DevOps Lab 4 – Hosting using GitHub Pages (ShriRadhey-Mishra.github.io, Repo1)

[https://github.com/ShriRadhey-Mishra/ShriRadhey-Mishra.github.io.git]

When we have created a repository, we can host either its HTML content or the README markdown page on GitHub Pages, just by following these simple steps:

1. Write a markdown or an HTML which you want to be hosted.
2. Push it to the repository whose content you want to host.
3. Go to the settings in that repository and then select GitHub Pages.
4. Select “Deploy from Branch” in the source section (selected by default).
5. Then in the branch section, select the branch and save.
6. Now in the custom domain, link your GitHub repository’s location and save.

You’ll see a “Your site is live at: <source_location>”, where you’ll either see the HTML or the markdown file’s content.

Using GitHub Pages, we can simply host any repository we want.

---

## DevOps Lab 5 – Subversion (Lab_5)

[https://github.com/ShriRadhey-Mishra/Lab_5.git]

Subversion, just like git, is another Version Control System, which we can use instead of Git. Subversion is a centralized VCS unlike git which is a distributed VCS. In this lab, we performed and understood the working of some basic subversion (svn) commands such as:

- `svn checkout <repo_url>`: We use this command to check out a working copy from a remote SVN repository to our local system.
- `svn add <file_name>`: This command is used to add new files or directories to version control in our local working copy.
- `svn commit -m "<message>"`: After adding or modifying files, this command commits our changes to the remote SVN repository with a log message.
- `svn update`: This command updates our local copy with the latest changes from the remote repository.
- `svn status`: Displays the status of files in our working directory, showing which files are modified, added, or missing.
- `svn branch` (usually via `svn copy`): Subversion doesn’t have a separate command for branching; instead, we create a branch by copying the trunk to a branch directory using:  
  `svn copy <repo_url>/trunk <repo_url>/branches/<branch_name> -m "creating branch"`
- `svn merge`: To merge changes from a branch back to the trunk, we use:  
  `svn merge <repo_url>/branches/<branch_name>` from the trunk directory.
- `svn resolve`: Used to resolve conflicts after a merge operation.

Using these commands, we can check out a working copy from a remote SVN repository, create or modify files, add them to version control, commit the changes to the repository, and even create and merge branches as needed.

---

## DevOps Lab 6 – Containerization using Docker (Lab_8)

[https://github.com/ShriRadhey-Mishra/Lab_8.git]

Docker is a platform that allows us to automate the deployment of applications inside lightweight, portable containers. These containers package an application along with all its dependencies, making it easy to run the application in any environment without worrying about system compatibility issues.

In this lab, we built a Dockerfile to containerize a Python application that uses FastAPI. By doing this, we ensured that the application can be run consistently on any system that supports Docker.

Dockerfile Breakdown:

- `FROM ubuntu`: Defines the base image to be used, which in this case is Ubuntu.
- `RUN apt update -y`: Updates the package list inside the container.
- `RUN apt install python3 python3-pip pipenv -y`: Installs Python, pip, and pipenv to manage Python environments and dependencies.
- `WORKDIR /app`: Sets the working directory inside the container to /app.
- `COPY . /app/`: Copies all the files from the current directory to the container’s working directory.
- `RUN pipenv install -r requirements.txt`: Installs all the required dependencies specified in the `requirements.txt` file.
- `EXPOSE 80`: Indicates that the application will listen on port 80 inside the container.
- `CMD pipenv run python3 ./main.py`: Defines the default command to run the FastAPI application when the container starts.

Using Docker in this lab helped us to package the Python + FastAPI application into a container image, which can be shared, deployed, and run anywhere with consistent results.

---

## DevOps Lab 7 – Build using GitHub Actions (Lab_8)

[https://github.com/ShriRadhey-Mishra/Lab_8.git]

In this lab, we took the file content from the last lab and we automated its build process using GitHub Actions. GitHub Actions is a Continuous Integration and Continuous Deployment (CI/CD) tool that allows us to automate workflows directly from our GitHub repository. Using GitHub Actions, we can automate the process of building, testing, and deploying our applications whenever we push code changes to our repository.

In this lab, we created a GitHub Actions workflow to automate the build process of our Dockerized FastAPI Python application. This ensured that our application’s Docker image gets built and pushed to Docker Hub automatically on every push to the repository.

Workflow breakdown:

- `name: docker image build`: Defines the name of the workflow.
- `on: push`: Triggers the workflow to run every time a push is made to the repository.
- `jobs: build`: Defines a job named build which contains the steps to be executed.
- `runs-on: ubuntu-latest`: Specifies the environment where the job will run.
- `steps`: Contains a sequence of actions to perform in this job.
  - `uses: actions/checkout@v3`: Checks out the source code from the repository.
  - `Check if secret is present`: Checks if the Docker token secret is available in GitHub secrets.
  - `Log in to Docker Hub`: Logs into Docker Hub using the provided username and secret token.
  - `Build Docker image`: Builds the Docker image from the Dockerfile in the repository using the command `docker build`.
  - `Push Docker image`: Pushes the built Docker image to the specified Docker Hub repository.

Using this GitHub Actions workflow, we automated the build and deployment of our FastAPI Docker application, making our development and deployment process faster, more reliable, and efficient.

---

## DevOps Lab 8 – Build using Jenkins (Lab_8)

[https://github.com/ShriRadhey-Mishra/Lab_8.git]

Jenkins is an open-source automation server that helps automate parts of the software development process, especially building, testing, and deploying. Unlike GitHub Actions, which is cloud-native and tightly integrated with GitHub, Jenkins provides a flexible, self-hosted solution for CI/CD workflows.

In this lab, we configured a Jenkins pipeline to automate the build and deployment of our Dockerized FastAPI Python application. On every code push or manual build trigger, Jenkins fetches the code, builds a Docker image, and pushes it to Docker Hub.

### 🔧 Pipeline Job:
We created a Pipeline Job in Jenkins to define our build steps in code (using a `Jenkinsfile`):

1. `agent any`: Tells Jenkins to run the pipeline on any available agent node.  
2. **Stage: Checkout** – Checks out the source code from the connected Git repository.  
3. **Stage: Docker Login** – Logs into Docker Hub using credentials configured in Jenkins Credential Manager.  
4. **Stage: Build Docker Image** – Builds the Docker image from the Dockerfile in the project directory.  
5. **Stage: Push Docker Image** – Pushes the built image to our Docker Hub repository.

### 📄 Reference Jenkinsfile:
```groovy
pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-creds') // Jenkins credentials ID
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Docker Login') {
            steps {
                sh "echo ${DOCKERHUB_CREDENTIALS_PSW} | docker login -u ${DOCKERHUB_CREDENTIALS_USR} --password-stdin"
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t yourdockerhubusername/fast_api_dockerize .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push yourdockerhubusername/fast_api_dockerize'
            }
        }
    }
}

