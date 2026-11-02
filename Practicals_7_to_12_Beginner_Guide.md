# Practicals 7--12: Beginner-Friendly Git, Jenkins, Docker and Kubernetes Guide

> **How to use this guide:** Open this `README.md` during your
> practical. Find the practical number given by your examiner and follow
> each step in order. Read the **Where** line before typing a command.
> Commands below are for **Windows PowerShell**, usually inside VS Code
> → Terminal → New Terminal, unless stated otherwise.

## Before starting: very basic words

-   **Git:** a tool on your computer that records changes to files.
-   **GitHub:** a website that stores Git repositories online.
-   **Repository (repo):** a project folder plus its change history.
-   **Clone:** download a repository to your computer.
-   **Fork:** create your own GitHub copy of somebody else's repository.
-   **Branch:** a separate line of work where you can make changes
    safely.
-   **Commit:** save a snapshot of changes in Git.
-   **Push:** upload your local commits to GitHub.
-   **Pull request (PR):** ask the owner of a repository to review and
    merge your changes.
-   **Terminal:** a place where you type commands.
-   **Docker image:** a package containing an application and what it
    needs to run.
-   **Container:** a running instance created from an image.
-   **Jenkins:** a tool that automates build/test/deployment steps.
-   **Kubernetes:** a tool that manages applications running in
    containers.
-   **Minikube:** runs a small Kubernetes cluster on your computer.
-   **kubectl:** the command-line tool used to control Kubernetes.

## Before the exam: check which software is available

Open **VS Code → Terminal → New Terminal** and run these commands one at
a time. Press **Enter** after each command.

``` powershell
git --version
python --version
docker --version
docker compose version
java -version
minikube version
kubectl version --client
```

A version number should appear for each installed tool. If a command
says it is "not recognized," that tool is not installed or Windows
cannot find it in PATH. Do not continue to a practical that depends on a
missing tool until it is fixed.

-   Docker commands require **Docker Desktop to be open and running**.
-   Jenkins normally opens at `http://localhost:8080`.
-   GitHub is accessed in a browser at `https://github.com`.
-   Never put passwords or access tokens into a public repository or
    screenshots.
-   If your college has a specified repository, branch name, or code,
    use the college's details in place of the examples here.

------------------------------------------------------------------------

# PRACTICAL 7 --- GitHub Desktop: Fork, Clone, Branch, Commit, Push and Pull Request

## 1. Aim (write in journal)

To clone and fork a GitHub repository, create a branch, make and commit
a change, push the branch, and create a pull request using GitHub
Desktop.

## 2. Requirements

-   A GitHub account and internet connection.
-   GitHub Desktop installed.
-   A browser.
-   A text editor such as VS Code.
-   Example repository from the practical document:
    `https://github.com/KalyanM45/Spam-Email-Detection.git`

## 3. Understand the task

We will first look at another person's repository. We cannot normally
push directly to their repository unless they give us permission. A
**fork** makes a copy under our own account. We will make a branch in
our fork, edit `README.md`, save the change as a commit, push it to our
fork, and open a pull request to the original repository.

## 4. Procedure

### Step 1 --- Open GitHub Desktop

**Where:** Windows Start menu.

1.  Click **Start**.
2.  Type `GitHub Desktop`.
3.  Open it.
4.  If asked, sign in to your GitHub account.
5.  If GitHub Desktop is not installed, install it before continuing.

### Step 2 --- Clone the original repository

**Where:** GitHub Desktop.

1.  Click **File → Clone Repository**.
2.  Select the **URL** tab.
3.  Paste this repository URL:

``` text
https://github.com/KalyanM45/Spam-Email-Detection.git
```

4.  Choose a local folder where you want to save it. For example, a
    folder under `Documents`.
5.  Click **Clone**.
6.  Wait for the repository to download.

**Expected result:** GitHub Desktop shows the repository. Cloning only
downloads a copy to your computer; it does not give you permission to
upload changes to the original repository.

### Step 3 --- Understand restricted access

**Where:** GitHub Desktop / browser.

You may create a local branch, but pushing changes directly to someone
else's repository normally requires write permission. If you attempt to
push and are denied, that is why we fork the repository in the next
step. Do not keep trying to push to the original repository.

### Step 4 --- Fork the repository

**Where:** Browser.

1.  Open `https://github.com/KalyanM45/Spam-Email-Detection`.
2.  Sign in to GitHub.
3.  Click **Fork** near the top of the repository page.
4.  Choose your own GitHub account as the owner.
5.  Click **Create fork**.
6.  Wait until GitHub opens the new copy under your account.

**Expected result:** The repository page now belongs to your account.
This is your fork.

### Step 5 --- Clone your fork

**Where:** Browser, then GitHub Desktop.

1.  On your fork's GitHub page, click the green **Code** button.
2.  Copy the HTTPS repository URL. It should have your username in it.
3.  Return to GitHub Desktop.
4.  Click **File → Clone Repository → URL**.
5.  Paste the URL of **your fork**, not the original.
6.  Choose a local folder and click **Clone**.
7.  If GitHub Desktop asks which repository to use, make sure it is your
    fork.

### Step 6 --- Create a branch named `GIT-EXAM`

**Where:** GitHub Desktop.

1.  Make sure the cloned fork is selected.
2.  Click **Current Branch** near the top.
3.  Click **New Branch**.
4.  Type this exact branch name:

``` text
GIT-EXAM
```

5.  Click **Create Branch**.

**Expected result:** GitHub Desktop shows `GIT-EXAM` as the current
branch. A branch lets you make changes separately from the main branch.

### Step 7 --- Edit README.md

**Where:** GitHub Desktop, then VS Code or another text editor.

1.  In GitHub Desktop, choose **Repository → Show in Explorer** (wording
    may vary slightly).
2.  Find and open `README.md`.
3.  Add a simple line at the bottom, for example:

``` text
This change is for the GitHub practical.
```

4.  Save the file using **Ctrl + S**.
5.  Return to GitHub Desktop.

**Expected result:** The changed `README.md` appears in the **Changes**
list.

### Step 8 --- Commit the change

**Where:** GitHub Desktop.

1.  At the bottom-left, find the **Summary** box.
2.  Type:

``` text
Update README for practical
```

3.  Click **Commit to GIT-EXAM**.

**Expected result:** The change is recorded in your local Git history. A
commit is like a saved checkpoint.

### Step 9 --- Push the branch to your fork

**Where:** GitHub Desktop.

1.  Click **Push origin** at the top.
2.  Wait for the upload to finish.

**Expected result:** Your `GIT-EXAM` branch is uploaded to your fork on
GitHub. If you see **Publish branch** instead of **Push origin**, click
**Publish branch**.

### Step 10 --- Create the pull request

**Where:** Browser.

1.  Open your fork on GitHub.
2.  GitHub may show **Compare & pull request**. Click it.
3.  Check the two sides carefully:
    -   **Base repository:** the original repository
        (`KalyanM45/Spam-Email-Detection`).
    -   **Base branch:** usually `main` (use the branch shown in your
        practical if different).
    -   **Head/compare repository:** your fork.
    -   **Compare branch:** `GIT-EXAM`.
4.  Add a title, for example `Update README for practical`.
5.  Add a short description, for example
    `Added a line to the README file.`
6.  Click **Create pull request**.

**Expected result:** GitHub opens the pull request page. A pull request
asks the original repository owner to review your change; it does not
mean the owner has already merged it.

### Step 11 --- Review or resolve a conflict (only if asked)

A **merge conflict** means Git cannot automatically combine two changes.

1.  Open the file GitHub says has a conflict.
2.  Review the competing lines.
3.  Keep the correct content and remove conflict markers such as
    `<<<<<<<`, `=======`, and `>>>>>>>`.
4.  Save the file.
5.  Commit the correction and push the branch again.
6.  If GitHub Desktop provides a conflict-resolution tool, follow its
    instructions.

Do not invent a conflict if none occurs; explain what a conflict means
if the examiner asks.

## 5. Common errors and fixes

-   **I cannot push to the original repository:** expected if you do not
    have write permission. Fork it, clone your fork, and push there.
-   **I cannot see the changed README:** save it first with Ctrl+S, then
    return to GitHub Desktop.
-   **I see "Publish branch":** click it; it uploads a new branch for
    the first time.
-   **I created the branch in the wrong repository:** select the local
    clone of your fork and create `GIT-EXAM` there.
-   **Pull request targets the wrong repository:** before creating it,
    confirm the base is the original repository and compare/head is your
    fork.

## 6. Result (write in journal)

The repository was forked and cloned. A branch named `GIT-EXAM` was
created, a change was committed and pushed to the fork, and a pull
request was submitted to the original repository.

## 7. Viva questions and answers

**Q1. What is Git?**\
Git is a tool that tracks changes in files.

**Q2. What is GitHub?**\
GitHub is a website that hosts Git repositories online.

**Q3. What is a repository?**\
A repository is a project folder together with its change history.

**Q4. What is cloning?**\
Cloning copies a repository from GitHub to our computer.

**Q5. What is forking?**\
Forking creates our own GitHub copy of another person's repository.

**Q6. What is a branch?**\
A branch is a separate line of work where we can make changes.

**Q7. What is a commit?**\
A commit saves a set of changes in Git history.

**Q8. What is pushing?**\
Pushing uploads local commits to a remote repository on GitHub.

**Q9. What is a pull request?**\
A pull request asks the repository owner to review and possibly merge
our changes.

**Q10. Why do we fork?**\
We fork so we can push changes to our own copy without needing write
permission to the original.

------------------------------------------------------------------------

# PRACTICAL 8 --- Jenkins Pipeline Connected to GitHub

## 1. Aim (write in journal)

To create a Jenkins Pipeline connected to a GitHub repository and
configure Jenkins to check the repository for changes and build the
project automatically.

## 2. Requirements

-   Windows computer, internet, browser.
-   Git and a GitHub account.
-   Java version supported by the Jenkins release installed.
-   Jenkins installed and running.
-   Python installed if the pipeline runs a Python file.
-   A GitHub repository containing `app.py` and `Jenkinsfile`.

**Important:** If Jenkins is not installed or does not open at
`http://localhost:8080`, complete the installation/start-up first. The
pipeline steps cannot work until Jenkins is running.

## 3. Create a simple project

### Step 1 --- Make a project folder

**Where:** Windows File Explorer.

1.  Go to Desktop.
2.  Right-click an empty space → **New → Folder**.
3.  Name it `jenkins-demo`.
4.  Open VS Code.
5.  Click **File → Open Folder** and select `jenkins-demo`.
6.  Click **Terminal → New Terminal**.

### Step 2 --- Create `app.py`

**Where:** VS Code Explorer.

1.  Click the **New File** icon.
2.  Name the file `app.py`.
3.  Paste:

``` python
print("Hello! My first Jenkins project is working.")
```

4.  Press **Ctrl + S**.

### Step 3 --- Create `Jenkinsfile`

**Where:** VS Code Explorer.

1.  Click **New File**.
2.  Name it exactly `Jenkinsfile` --- do not add `.txt`.
3.  Paste the following Pipeline code:

``` groovy
pipeline {
    agent any

    stages {
        stage('Check Python') {
            steps {
                bat 'python --version'
            }
        }

        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }
    }
}
```

4.  Press **Ctrl + S**.

This example is for a **Windows Jenkins agent** because it uses `bat`.
If your Jenkins agent is Linux, the commands must use `sh` instead.

### Step 4 --- Upload the project to GitHub

**Where:** Browser and VS Code terminal.

1.  Open GitHub in your browser and sign in.
2.  Click **+ → New repository**.
3.  Name it `jenkins-demo`.
4.  If you already have local files, leave the option to add a README
    unchecked.
5.  Click **Create repository**.
6.  Keep the repository page open. Copy the repository HTTPS URL.

In VS Code terminal, first check that you are inside the `jenkins-demo`
folder. Then run each command separately:

``` powershell
git init
git add .
git commit -m "Add first Jenkins pipeline"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with the HTTPS URL you copied. Do
not type the placeholder literally.

If Git asks for your identity, configure your name and email using the
name and email associated with your Git account:

``` powershell
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Then repeat the commit and push commands if needed. Do not share
authentication tokens.

**Expected result:** GitHub shows `app.py` and `Jenkinsfile`.

## 4. Configure Jenkins

### Step 5 --- Open Jenkins

**Where:** Browser.

1.  Open Chrome.
2.  Visit `http://localhost:8080`.
3.  Sign in.

If the page does not open, see troubleshooting below.

### Step 6 --- Create a Pipeline job

**Where:** Jenkins browser page.

1.  Click **New Item**.
2.  Enter job name `jenkins-demo`.
3.  Select **Pipeline**.
4.  Click **OK**.
5.  Scroll to the **Pipeline** section.
6.  Under **Definition**, select **Pipeline script from SCM**.
7.  Under **SCM**, select **Git**.
8.  In **Repository URL**, paste your GitHub repository URL.
9.  Set **Branch Specifier** to:

``` text
*/main
```

10. Set **Script Path** to:

``` text
Jenkinsfile
```

11. Click **Save**.

If GitHub asks for credentials because the repository is private,
configure suitable GitHub credentials in Jenkins. For a public
repository, credentials may not be needed.

### Step 7 --- Run the first build

**Where:** Jenkins.

1.  Open the `jenkins-demo` job.
2.  Click **Build Now**.
3.  Wait for the build to appear in **Build History**.
4.  Click the build number.
5.  Click **Console Output**.

**Expected output** should include:

``` text
Hello! My first Jenkins project is working.
```

The build should finish successfully. The console output is where you
look first when a build fails.

### Step 8 --- Configure Poll SCM

**Where:** Jenkins → job → Configure.

1.  Open the job.
2.  Click **Configure**.
3.  Find **Build Triggers**.
4.  Tick **Poll SCM**.
5.  Enter this schedule:

``` text
H/2 * * * *
```

6.  Click **Save**.

This asks Jenkins to check the repository regularly, approximately every
two minutes. It is repository polling, not a GitHub webhook.

### Step 9 --- Test automatic build

**Where:** GitHub website.

1.  Open `app.py` in your GitHub repository.
2.  Click the pencil/edit icon.
3.  Change the message to:

``` python
print("I changed my project. Jenkins should build it again.")
```

4.  Click **Commit changes**.
5.  Wait for the polling interval.
6.  Return to Jenkins and check **Build History**.
7.  Open the new build and check **Console Output**.

**Expected result:** Jenkins detects the repository change and starts
another build. This requires the Jenkins job to be configured correctly
and the repository to be accessible.

## 5. Common errors and fixes

-   **`localhost:8080` does not open:** Jenkins may not be installed or
    running. On Windows, press **Windows + R**, enter `services.msc`,
    press Enter, and look for the Jenkins service. Start it if installed
    and stopped. If it fails, check the Java/Jenkins installation.
-   **`git` is not recognized:** install Git, close and reopen VS Code,
    and try `git --version`.
-   **`python` is not recognized in Jenkins:** Python must be installed
    and available to the account running the Jenkins agent. Test
    `python --version` on that agent.
-   **Repository URL error:** copy the correct HTTPS URL from GitHub and
    paste it into Jenkins.
-   **`Jenkinsfile` not found:** ensure the file is named exactly
    `Jenkinsfile`, is in the repository root, and the Script Path is
    `Jenkinsfile`.
-   **No automatic build:** make sure Poll SCM is enabled, a schedule is
    entered, and the change was committed to the same branch Jenkins
    monitors.

## 6. Result (write in journal)

A Jenkins Pipeline was created and connected to a GitHub repository. The
project was built successfully, and Poll SCM was configured so Jenkins
could check the repository for changes.

## 7. Viva questions and answers

**Q1. What is Jenkins?**\
Jenkins is an automation tool used to build and test projects.

**Q2. What is a Pipeline?**\
A Pipeline is a sequence of steps Jenkins performs automatically.

**Q3. What is a Jenkinsfile?**\
A Jenkinsfile contains the Pipeline instructions.

**Q4. What is a Jenkins job?**\
A Jenkins job is a task configured in Jenkins.

**Q5. What is SCM?**\
SCM means Source Code Management; it manages source files and their
changes.

**Q6. What is Poll SCM?**\
Poll SCM makes Jenkins check the repository regularly for changes.

**Q7. What is a webhook?**\
A webhook sends a message to another application when an event happens,
such as a code push.

**Q8. What is a build?**\
A build is a process that runs steps on the project's files.

------------------------------------------------------------------------

# PRACTICAL 9 --- Build and Run a Docker Container

## 1. Aim (write in journal)

To create a Docker image for a simple web application, run it in a
container, test the application, and stop and remove the container.

## 2. Requirements

-   Windows computer.
-   Docker Desktop installed and running.
-   VS Code.
-   Internet connection to download the base image and Python package.

## 3. Procedure

### Step 1 --- Start Docker Desktop

**Where:** Windows Start menu.

1.  Open **Docker Desktop**.
2.  Wait until it finishes starting.
3.  Keep it running during the practical.

### Step 2 --- Create the project folder

**Where:** Windows File Explorer and VS Code.

1.  Go to Desktop.
2.  Create a folder named `ai-docker-app`.
3.  Open VS Code.
4.  Click **File → Open Folder** and select `ai-docker-app`.
5.  In VS Code, click **Terminal → New Terminal**.

### Step 3 --- Check Docker

**Where:** VS Code terminal.

Run:

``` powershell
docker --version
```

A Docker version should appear. Then run:

``` powershell
docker info
```

Docker should display client/server information. If it cannot connect,
open Docker Desktop and wait until it is running.

### Step 4 --- Create `app.py`

**Where:** VS Code Explorer.

1.  Click **New File** and enter `app.py`.
2.  Paste:

``` python
from flask import Flask, jsonify

app = Flask(__name__)

@app.route("/")
def home():
    return "AI application is running!"

@app.route("/predict")
def predict():
    return jsonify({"prediction": "This is a demo prediction"})

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

3.  Press **Ctrl + S**.

### Step 5 --- Create `requirements.txt`

**Where:** VS Code Explorer.

1.  Create a file named `requirements.txt`.
2.  Put this one line inside:

``` text
Flask
```

3.  Press **Ctrl + S**.

### Step 6 --- Create the `Dockerfile`

**Where:** VS Code Explorer.

1.  Create a file named exactly `Dockerfile`. Do not add `.txt`.
2.  Paste:

``` dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .

EXPOSE 5000

CMD ["python", "app.py"]
```

3.  Press **Ctrl + S**.

The folder should now contain:

``` text
ai-docker-app/
├── app.py
├── requirements.txt
└── Dockerfile
```

### Step 7 --- Build the Docker image

**Where:** VS Code terminal. Make sure the terminal is in the
`ai-docker-app` folder.

Run:

``` powershell
docker build -t ai-docker-app .
```

Wait for the process to finish. The dot `.` at the end is important: it
tells Docker to use the current folder as the build context.

**Expected result:** the image build completes. Check it with:

``` powershell
docker images
```

You should see `ai-docker-app` in the image list.

### Step 8 --- Run the container

**Where:** VS Code terminal.

Run:

``` powershell
docker run -d --name ai-container -p 5000:5000 ai-docker-app
```

Meaning: - `-d` runs it in the background. - `--name ai-container` gives
the container a name. - `-p 5000:5000` maps port 5000 on your computer
to port 5000 in the container. - `ai-docker-app` is the image name.

Check that it is running:

``` powershell
docker ps
```

**Expected result:** `ai-container` appears in the list.

### Step 9 --- Test the application

**Where:** Browser.

Open these addresses:

-   Home page: `http://localhost:5000`
-   Demo prediction: `http://localhost:5000/predict`

Expected home-page text:

``` text
AI application is running!
```

Expected prediction response:

``` json
{"prediction":"This is a demo prediction"}
```

This is a demonstration response, not a real trained AI model.

### Step 10 --- Check logs if the page does not open

**Where:** VS Code terminal.

``` powershell
docker logs ai-container
```

Read the error. The container must be running and port 5000 must not be
in use by another application.

### Step 11 --- Stop the container

**Where:** VS Code terminal.

``` powershell
docker stop ai-container
```

The running container should stop.

### Step 12 --- Remove the container

**Where:** VS Code terminal.

``` powershell
docker rm ai-container
```

This removes the stopped container, not the image or project files.

### Step 13 --- Verify

Run:

``` powershell
docker ps
```

The stopped container should no longer appear among running containers.
Then run:

``` powershell
docker images
```

The `ai-docker-app` image should still appear.

## 4. Common errors and fixes

-   **Docker cannot connect:** open Docker Desktop and wait until it is
    ready.
-   **`Dockerfile` not found:** check that it is named exactly
    `Dockerfile`, has no `.txt` extension, and is in the current folder.
-   **Build fails while downloading:** check internet access and try
    again.
-   **Port already allocated:** another program is using port 5000. Stop
    that program or use a different host port, for example
    `-p 5001:5000`, then open `http://localhost:5001`.
-   **Container name already in use:** remove the old container if
    appropriate: `docker rm -f ai-container`, then run the `docker run`
    command again.
-   **Page does not open:** run `docker ps` and
    `docker logs ai-container`.

## 5. Result (write in journal)

The Docker image was built successfully, the application was run in a
container, its output was tested through a browser, and the container
was stopped and removed after testing.

## 6. Viva questions and answers

**Q1. What is Docker?**\
Docker is a tool used to package and run applications in containers.

**Q2. What is a Docker image?**\
An image is a package used to create containers.

**Q3. What is a container?**\
A container is an isolated environment in which an application runs.

**Q4. What is a Dockerfile?**\
A Dockerfile contains instructions for building a Docker image.

**Q5. What does `docker build` do?**\
It builds a Docker image from a Dockerfile.

**Q6. What does `docker run` do?**\
It creates and starts a container from an image.

**Q7. What does `docker ps` show?**\
It shows running containers.

**Q8. What does port mapping do?**\
It lets us access an application in the container through a port on our
computer.

**Q9. What is Flask?**\
Flask is a Python library for creating web applications.

**Q10. Is this a real AI model?**\
No. It returns a sample prediction for demonstration.

------------------------------------------------------------------------

# PRACTICAL 10 --- Run Frontend, AI Service and Database Using Docker Compose

## 1. Aim (write in journal)

To define and run a web application with separate frontend, AI-service,
and database containers using Docker Compose.

## 2. Requirements

-   Docker Desktop installed and running.
-   VS Code.
-   Internet connection.
-   A browser.

## 3. Understand the folder structure

We will create this exact structure:

``` text
ai-compose-app/
├── docker-compose.yml
├── frontend/
│   ├── index.html
│   └── Dockerfile
└── ai/
    ├── app.py
    ├── requirements.txt
    └── Dockerfile
```

**Important:** there are two files named `Dockerfile`, one inside
`frontend` and one inside `ai`. Neither file should end with `.txt`.

## 4. Procedure

### Step 1 --- Start Docker Desktop

Open Docker Desktop and wait until it is running.

### Step 2 --- Create the folders

**Where:** VS Code.

1.  Create a folder on the Desktop named `ai-compose-app`.
2.  Open it in VS Code using **File → Open Folder**.
3.  In the Explorer panel, create two folders: `frontend` and `ai`.
4.  Create the files shown in the folder structure above.

### Step 3 --- Create `ai/app.py`

**Where:** VS Code → `ai` folder → `app.py`.

Paste:

``` python
from flask import Flask, jsonify

app = Flask(__name__)

@app.route("/")
def home():
    return jsonify({"message": "AI model service is running"})

@app.route("/predict")
def predict():
    return jsonify({"prediction": "This is a demo prediction"})

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

Save with **Ctrl + S**.

### Step 4 --- Create `ai/requirements.txt`

Put this one line in the file:

``` text
Flask
```

Save with **Ctrl + S**.

### Step 5 --- Create `ai/Dockerfile`

Paste:

``` dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .

EXPOSE 5000

CMD ["python", "app.py"]
```

Save with **Ctrl + S**.

### Step 6 --- Create `frontend/index.html`

Paste:

``` html
<!DOCTYPE html>
<html>
<head>
  <title>AI Application</title>
</head>
<body>
  <h1>Web-Based AI Application</h1>
  <button onclick="getPrediction()">Get Prediction</button>
  <p id="result"></p>

  <script>
    async function getPrediction() {
      try {
        const response = await fetch("http://localhost:5000/predict");
        const data = await response.json();
        document.getElementById("result").innerText = data.prediction;
      } catch (error) {
        document.getElementById("result").innerText =
          "Unable to get prediction. Please check the AI service.";
      }
    }
  </script>
</body>
</html>
```

Save with **Ctrl + S**.

### Step 7 --- Create `frontend/Dockerfile`

Paste:

``` dockerfile
FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80
```

Save with **Ctrl + S**.

### Step 8 --- Create `docker-compose.yml`

**Where:** the main `ai-compose-app` folder, not inside `frontend` or
`ai`.

Paste this code exactly; YAML indentation matters:

``` yaml
services:
  frontend:
    build: ./frontend
    ports:
      - "8080:80"
    depends_on:
      - ai

  ai:
    build: ./ai
    ports:
      - "5000:5000"
    depends_on:
      - database

  database:
    image: postgres:16
    environment:
      POSTGRES_USER: aiuser
      POSTGRES_PASSWORD: aipassword
      POSTGRES_DB: aidb
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  postgres_data:
```

Save with **Ctrl + S**.

This file defines three services: `frontend`, `ai`, and `database`. The
database is started and its volume preserves database data, but this
demo code does not actually save predictions to the database.

### Step 9 --- Open the terminal in the project folder

**Where:** VS Code → Terminal → New Terminal.

If the terminal is not already in the project folder, enter:

``` powershell
cd "$HOME\Desktop\ai-compose-app"
```

If your folder is in a different location, use its actual path.

### Step 10 --- Check Docker Compose

Run:

``` powershell
docker compose version
```

A version should appear.

### Step 11 --- Build and start all services

Run:

``` powershell
docker compose up --build
```

Wait for Docker to build the frontend and AI images and start all three
services. The first run can take several minutes. Keep this terminal
open while testing.

**Expected result:** logs appear for the services and no fatal error
stops the application.

### Step 12 --- Test the frontend

**Where:** Browser.

Open:

``` text
http://localhost:8080
```

Expected: the page displays **Web-Based AI Application** and a **Get
Prediction** button.

### Step 13 --- Test the AI service directly

**Where:** Browser.

Open:

``` text
http://localhost:5000/predict
```

Expected JSON:

``` json
{"prediction":"This is a demo prediction"}
```

### Step 14 --- Test the button

Return to `http://localhost:8080` and click **Get Prediction**.

Expected text:

``` text
This is a demo prediction
```

**If the button fails:** the sample HTML calls
`http://localhost:5000/predict` from a different port. The browser may
block the request because of CORS. First confirm that Step 13 works. If
direct access works but the button fails, report/check the browser
console and the AI service CORS configuration. Do not claim the button
worked unless you tested it.

### Step 15 --- Check the containers

Open a **second** VS Code terminal (leave the first terminal running),
and enter:

``` powershell
docker compose ps
```

**Expected result:** services named `frontend`, `ai`, and `database`
should be listed and their status should indicate that they are running.

To inspect logs, run:

``` powershell
docker compose logs
```

### Step 16 --- Stop the application

Return to the first terminal where `docker compose up --build` is
running and press **Ctrl + C**.

Then run:

``` powershell
docker compose down
```

This stops and removes the Compose containers. Project files remain. The
named database volume remains unless you explicitly remove it.

## 5. Common errors and fixes

-   **`docker compose` is not recognized or unavailable:** check Docker
    Desktop installation and run `docker compose version`.
-   **YAML error:** check spaces/indentation in `docker-compose.yml`;
    use the code above exactly.
-   **Port 8080 or 5000 already in use:** stop the other application
    using that port or change the left side of the port mapping and use
    the corresponding browser address.
-   **Frontend opens but prediction fails:** visit
    `http://localhost:5000/predict` directly. If it works, the issue may
    be the browser's cross-origin (CORS) restriction in the sample
    frontend.
-   **A service exits:** use `docker compose ps` and
    `docker compose logs` to find the error.

## 6. Result (write in journal)

Docker Compose was used to define and run a web application with
separate frontend, AI-service, and database containers. The webpage and
demo prediction were tested, and the application was stopped after
testing.

## 7. Viva questions and answers

**Q1. What is Docker Compose?**\
It is a tool for defining and running multiple containers using one
configuration file.

**Q2. What is `docker-compose.yml`?**\
It defines the services and settings for the Compose application.

**Q3. What does `docker compose up --build` do?**\
It builds the required images and starts the services.

**Q4. What does `docker compose down` do?**\
It stops and removes the containers created by Compose.

**Q5. Why separate frontend, AI and database?**\
Each part has its own service, so it is easier to build and manage them
separately.

**Q6. What is a frontend?**\
It is the part of the application the user sees and interacts with.

**Q7. What is PostgreSQL?**\
It is a database system used to store and organize information.

**Q8. What is a volume?**\
A volume stores data separately from a container so the data can remain
after the container is removed.

**Q9. Does this demo save predictions to the database?**\
No. It starts a database container, but the demo code does not save
predictions to it.

**Q10. Is this a real AI application?**\
No. It returns a sample prediction.

------------------------------------------------------------------------

# PRACTICAL 11 --- Deploy and Scale a Docker Application Using Kubernetes and Minikube

## 1. Aim (write in journal)

To set up a local Kubernetes cluster using Minikube, deploy a Dockerized
application, and scale it from one replica to three replicas and back to
one.

## 2. Requirements

-   Docker Desktop installed and running.
-   Minikube installed.
-   kubectl installed.
-   VS Code.
-   Internet connection for downloading images.

## 3. Procedure

### Step 1 --- Start Docker Desktop

Open Docker Desktop and wait until it is running.

### Step 2 --- Check the required tools

**Where:** VS Code → Terminal → New Terminal.

Run each command:

``` powershell
docker --version
minikube version
kubectl version --client
```

A version number should appear for each command. If not, install the
missing tool before continuing.

### Step 3 --- Create the project folder

Create a Desktop folder named `ai-model-app`. Open it in VS Code using
**File → Open Folder**.

### Step 4 --- Create `app.py`

Create a file named `app.py` and paste:

``` python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "AI Model Application is Running!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

Save with **Ctrl + S**.

### Step 5 --- Create `requirements.txt`

Create the file and enter:

``` text
Flask
```

Save it.

### Step 6 --- Create the `Dockerfile`

Create a file named exactly `Dockerfile` and paste:

``` dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["python", "app.py"]
```

Save it.

### Step 7 --- Build the Docker image

**Where:** VS Code terminal inside the `ai-model-app` folder.

``` powershell
docker build -t ai-model-app:latest .
```

Wait for the build to finish. Check:

``` powershell
docker images
```

You should see `ai-model-app`.

### Step 8 --- Start Minikube

Make sure Docker Desktop is running. In the terminal, run:

``` powershell
minikube start --driver=docker
```

This may take a few minutes the first time.

### Step 9 --- Check the Kubernetes node

Run:

``` powershell
kubectl get nodes
```

**Expected result:** the Minikube node should eventually show status
`Ready`.

### Step 10 --- Load the image into Minikube

Because the image was built on your computer, load it into Minikube:

``` powershell
minikube image load ai-model-app:latest
```

This is important when using a locally built image without publishing it
to a registry.

### Step 11 --- Create `deployment.yaml`

In VS Code, create a file named `deployment.yaml` in the main
`ai-model-app` folder. Paste this YAML exactly; indentation matters:

``` yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ai-model-app
spec:
  replicas: 1
  selector:
    matchLabels:
      app: ai-model-app
  template:
    metadata:
      labels:
        app: ai-model-app
    spec:
      containers:
        - name: ai-model-app
          image: ai-model-app:latest
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 5000
```

Save with **Ctrl + S**.

### Step 12 --- Deploy the application

**Where:** VS Code terminal in the same folder as `deployment.yaml`.

``` powershell
kubectl apply -f deployment.yaml
```

**Expected result:** Kubernetes reports that the deployment was created
or configured.

### Step 13 --- Check the deployment and pod

Run:

``` powershell
kubectl get deployments
```

Then:

``` powershell
kubectl get pods
```

Wait until the pod status becomes `Running`. It may take a little time.

### Step 14 --- Open the application

Run:

``` powershell
kubectl port-forward deployment/ai-model-app 5000:5000
```

Keep this terminal open while testing. Open the browser and visit:

``` text
http://localhost:5000
```

Expected text:

``` text
AI Model Application is Running!
```

### Step 15 --- Scale up to three replicas

Open a **second** terminal, leaving the port-forward terminal open. Run:

``` powershell
kubectl scale deployment ai-model-app --replicas=3
```

Check:

``` powershell
kubectl get deployments
kubectl get pods
```

**Expected result:** Kubernetes attempts to maintain three replicas;
wait until three pods are running/ready. The `READY` count in the
deployment should eventually show `3/3`.

### Step 16 --- Scale back to one replica

Run:

``` powershell
kubectl scale deployment ai-model-app --replicas=1
```

Check again:

``` powershell
kubectl get deployments
kubectl get pods
```

**Expected result:** the deployment should eventually show one ready
replica.

## 4. Common errors and fixes

-   **Minikube will not start:** check Docker Desktop is running, then
    try `minikube status` and read the error.
-   **Node is not Ready:** wait a little, run `kubectl get nodes` again,
    and check Minikube status.
-   **Pod shows `ImagePullBackOff` or `ErrImagePull`:** run
    `minikube image load ai-model-app:latest`, check the image name in
    `deployment.yaml`, and confirm `imagePullPolicy: IfNotPresent`.
-   **Pod shows `CrashLoopBackOff`:** inspect the application error with
    `kubectl logs deployment/ai-model-app`.
-   **Three pods do not appear immediately:** wait, then run
    `kubectl get pods` again.
-   **Browser cannot open the app:** make sure the pod is running and
    the `kubectl port-forward` command is still running.

## 5. Result (write in journal)

A local Kubernetes cluster was started using Minikube. The Dockerized
application was deployed, accessed through a browser, scaled from one
replica to three replicas, and then scaled back to one replica.

## 6. Viva questions and answers

**Q1. What is Kubernetes?**\
Kubernetes is a system for managing applications that run in containers.

**Q2. What is Minikube?**\
Minikube runs a small Kubernetes cluster on a local computer.

**Q3. What is kubectl?**\
kubectl is a command-line tool used to communicate with Kubernetes.

**Q4. What is a pod?**\
A pod is the smallest unit Kubernetes manages and it contains one or
more containers.

**Q5. What is a Deployment?**\
A Deployment manages application pods and maintains the requested number
of replicas.

**Q6. What is scaling?**\
Scaling means increasing or decreasing the number of application
replicas.

**Q7. What does `replicas: 3` mean?**\
It tells Kubernetes to maintain three copies of the application.

**Q8. What does `kubectl apply -f deployment.yaml` do?**\
It creates or updates Kubernetes resources using the YAML file.

**Q9. Why use `minikube image load`?**\
It makes a locally built Docker image available inside Minikube.

**Q10. Why use port-forwarding?**\
It allows us to access the application through a local computer port.

------------------------------------------------------------------------

# PRACTICAL 12 --- Automate Deployment Using GitHub, Docker, Jenkins and Kubernetes

## 1. Aim (write in journal)

To automate retrieving application code from GitHub, building a Docker
image, pushing the image to Docker Hub, and deploying the application to
Kubernetes using Jenkins.

## 2. Requirements

-   Windows computer and internet.
-   VS Code, Python, Git and a GitHub account.
-   Docker Desktop and Docker Hub account.
-   Java version supported by the installed Jenkins release.
-   Jenkins installed and running.
-   Minikube and kubectl installed.
-   Jenkins agent must be able to use Docker and kubectl and access the
    Minikube cluster.

**Important:** this practical has many dependencies. A working Docker
command in your own VS Code terminal does not guarantee it will work
inside Jenkins, because Jenkins may run under a different Windows
account.

## 3. Understand the workflow

The pipeline should follow this order:

1.  Keep the project code in GitHub.
2.  Jenkins reads the `Jenkinsfile` from GitHub.
3.  Jenkins builds a Docker image.
4.  Jenkins signs in to Docker Hub using a saved Jenkins credential and
    pushes the image.
5.  Jenkins runs `kubectl apply` to deploy the application to
    Kubernetes.
6.  We check the Jenkins console output and Kubernetes pod status.

This is a demonstration Flask app; it does not train a real AI model.

## 4. Create the project files

### Step 1 --- Create the folder

**Where:** Windows File Explorer and VS Code.

1.  Create a Desktop folder named `ai-model-app`.
2.  Open it in VS Code using **File → Open Folder**.
3.  Create these five files in the same folder:

``` text
ai-model-app/
├── app.py
├── requirements.txt
├── Dockerfile
├── deployment.yaml
└── Jenkinsfile
```

### Step 2 --- Create `app.py`

Paste:

``` python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "AI Model Application is Running!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

Save with **Ctrl + S**.

### Step 3 --- Create `requirements.txt`

Paste:

``` text
Flask
```

Save it.

### Step 4 --- Create `Dockerfile`

Paste:

``` dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["python", "app.py"]
```

Save it.

### Step 5 --- Create `deployment.yaml`

Paste this valid YAML. Replace `YOUR_DOCKERHUB_USERNAME` with your
actual Docker Hub username before deploying:

``` yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ai-model-app
spec:
  replicas: 1
  selector:
    matchLabels:
      app: ai-model-app
  template:
    metadata:
      labels:
        app: ai-model-app
    spec:
      containers:
        - name: ai-model-app
          image: YOUR_DOCKERHUB_USERNAME/ai-model-app:latest
          imagePullPolicy: Always
          ports:
            - containerPort: 5000
```

Save it. Do not leave the placeholder in the final file.

### Step 6 --- Create `Jenkinsfile`

Create a file named exactly `Jenkinsfile` (no `.txt` or `.groovy`
extension). For a Windows Jenkins agent, paste this Pipeline:

``` groovy
pipeline {
    agent any

    environment {
        DOCKERHUB_USERNAME = 'YOUR_DOCKERHUB_USERNAME'
        IMAGE_NAME = 'ai-model-app'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t %DOCKERHUB_USERNAME%/%IMAGE_NAME%:latest .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASSWORD'
                )]) {
                    bat 'echo %DOCKER_PASSWORD%| docker login -u %DOCKER_USER% --password-stdin'
                    bat 'docker push %DOCKERHUB_USERNAME%/%IMAGE_NAME%:latest'
                    bat 'docker logout'
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
            }
        }
    }
}
```

Replace `YOUR_DOCKERHUB_USERNAME` in the Jenkinsfile with the same
username used in `deployment.yaml`. Save the file.

**Security:** do not type your Docker Hub password directly into this
file. Use a Jenkins credential. Use a Docker Hub access token if
appropriate for your account. Never share it in screenshots.

## 5. Create the GitHub repository and push the files

### Step 7 --- Create the GitHub repository

**Where:** Browser.

1.  Open GitHub and sign in.
2.  Click **+ → New repository**.
3.  Name it `ai-model-app`.
4.  If your project files already exist locally, leave the option to add
    a README unchecked.
5.  Click **Create repository**.
6.  Copy the repository's HTTPS URL.

### Step 8 --- Push the project to GitHub

**Where:** VS Code → Terminal → New Terminal.

Move to the project folder:

``` powershell
cd "$HOME\Desktop\ai-model-app"
```

If your folder is elsewhere, use its actual path.

Check Git:

``` powershell
git --version
```

Then run these commands one at a time:

``` powershell
git init
git add .
git commit -m "Add application and deployment pipeline"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with the HTTPS URL copied from
GitHub.

**Expected result:** GitHub shows all five files. If the terminal says
the remote already exists, check it using `git remote -v` rather than
repeatedly adding the remote.

## 6. Build and test the Docker image

### Step 9 --- Check Docker

Make sure Docker Desktop is running. In VS Code terminal:

``` powershell
docker --version
docker info
```

Both should work.

### Step 10 --- Build the image

**Where:** VS Code terminal inside `ai-model-app`.

``` powershell
docker build -t ai-model-app:latest .
```

Check:

``` powershell
docker images
```

### Step 11 --- Test the container

Run:

``` powershell
docker run -d --name ai-model-test -p 5000:5000 ai-model-app:latest
```

Open `http://localhost:5000` in a browser. Expected:

``` text
AI Model Application is Running!
```

Stop and remove this test container:

``` powershell
docker stop ai-model-test
docker rm ai-model-test
```

## 7. Push the image to Docker Hub once manually (initial verification)

This confirms the Docker Hub repository and username before configuring
Jenkins.

### Step 12 --- Log in to Docker Hub

**Where:** VS Code terminal.

``` powershell
docker login
```

Follow the prompt. Do not include your password in a command that may be
saved or shared.

### Step 13 --- Tag and push the image

Replace `YOUR_DOCKERHUB_USERNAME` with your actual username:

``` powershell
docker tag ai-model-app:latest YOUR_DOCKERHUB_USERNAME/ai-model-app:latest
docker push YOUR_DOCKERHUB_USERNAME/ai-model-app:latest
```

**Expected result:** the push finishes without an error. Open Docker Hub
in the browser and check that the `ai-model-app` repository/image
appears.

## 8. Start Kubernetes

### Step 14 --- Start Minikube

Make sure Docker Desktop is running, then run:

``` powershell
minikube start --driver=docker
```

### Step 15 --- Check the Kubernetes node

``` powershell
kubectl get nodes
```

The Minikube node should show `Ready`.

### Step 16 --- Apply the deployment once manually to verify it

Check that the username in `deployment.yaml` is correct, then run:

``` powershell
kubectl apply -f deployment.yaml
```

Check:

``` powershell
kubectl get deployments
kubectl get pods
```

Wait until the pod is `Running`.

If the pod shows `ImagePullBackOff`, check the image name and Docker Hub
username in `deployment.yaml`.

### Step 17 --- Test the deployed application

Run:

``` powershell
kubectl port-forward deployment/ai-model-app 5000:5000
```

Keep that terminal open and open `http://localhost:5000` in the browser.

Expected:

``` text
AI Model Application is Running!
```

Stop port-forwarding with **Ctrl + C** when finished.

## 9. Configure Jenkins credentials and Pipeline

### Step 18 --- Check that Jenkins opens

**Where:** Browser.

Open:

``` text
http://localhost:8080
```

If Jenkins does not open, check whether it is installed and running
before continuing.

### Step 19 --- Add Docker Hub credentials

**Where:** Jenkins browser page.

1.  Open **Manage Jenkins → Credentials**.
2.  Open the appropriate global credentials area (menu wording can vary
    by Jenkins version).
3.  Click **Add Credentials**.
4.  Set:
    -   **Kind:** Username with password
    -   **Username:** your Docker Hub username
    -   **Password:** your Docker Hub password or access token
    -   **ID:** `dockerhub-creds`
    -   **Description:** `Docker Hub login`
5.  Click **Create**.

The ID must match the `credentialsId` in the Jenkinsfile. Keep the
credential private.

### Step 20 --- Create the Jenkins Pipeline job

**Where:** Jenkins.

1.  Click **New Item**.
2.  Enter `ai-model-pipeline`.
3.  Select **Pipeline**.
4.  Click **OK**.
5.  Scroll to **Pipeline**.
6.  For **Definition**, choose **Pipeline script from SCM**.
7.  Choose **Git** as SCM.
8.  Enter your GitHub repository URL.
9.  Set **Branch Specifier** to:

``` text
*/main
```

10. Set **Script Path** to:

``` text
Jenkinsfile
```

11. Click **Save**.

### Step 21 --- Update GitHub if you changed files after the first push

If you edited `Jenkinsfile` or `deployment.yaml` after pushing, run in
VS Code terminal:

``` powershell
git add Jenkinsfile deployment.yaml
git commit -m "Update deployment pipeline"
git push
```

If there is no new change to commit, Git may say there is nothing to
commit; that is okay.

## 10. Important Jenkins agent check

Before running the full pipeline, the Jenkins agent must be able to run
Docker and kubectl. A Windows Jenkins service may run as a different
account from the one used in VS Code.

Check the agent environment for:

``` powershell
docker --version
kubectl get nodes
```

Docker should respond, and Kubernetes should show Minikube as `Ready`.
If these commands work in your personal terminal but fail in Jenkins,
the Jenkins agent's environment or permissions must be configured. Do
not assume that a working local terminal means the pipeline can deploy.

## 11. Run the Jenkins pipeline

### Step 22 --- Start the build

**Where:** Jenkins.

1.  Open the `ai-model-pipeline` job.
2.  Click **Build Now**.
3.  Wait for the new build under **Build History**.
4.  Click the build number.
5.  Click **Console Output**.
6.  Read the first error if the build fails.

The pipeline should: 1. Build the Docker image. 2. Sign in to Docker Hub
using the saved Jenkins credential. 3. Push the image. 4. Apply
`deployment.yaml` to Kubernetes.

**Expected final line for a successful build:**

``` text
Finished: SUCCESS
```

If it shows `Finished: FAILURE`, read Console Output to identify which
stage failed. Do not claim success unless it is shown.

## 12. Verify the final deployment

In VS Code terminal, run:

``` powershell
kubectl get deployments
kubectl get pods
```

The `ai-model-app` deployment should eventually have one ready replica
and the pod should be `Running`.

To view application logs:

``` powershell
kubectl logs deployment/ai-model-app
```

To open the app again:

``` powershell
kubectl port-forward deployment/ai-model-app 5000:5000
```

Keep that terminal open and visit `http://localhost:5000`.

## 13. Common errors and fixes

-   **Jenkins does not open:** check whether Jenkins is installed and
    running; on Windows, open `services.msc` and look for the Jenkins
    service.
-   **Docker works in VS Code but not Jenkins:** Jenkins may run under
    another account or agent. Configure that agent's Docker access.
-   **Jenkins cannot find `docker`:** Docker CLI must be installed and
    available in the Jenkins agent's PATH.
-   **Jenkins cannot run `kubectl`:** kubectl must be installed and
    available to the Jenkins agent, and the agent must have access to
    the Minikube cluster configuration.
-   **Docker Hub login fails:** verify the saved username/token and
    ensure the credential ID is exactly `dockerhub-creds`.
-   **`ImagePullBackOff`:** check the Docker Hub username, repository
    name, tag, and whether the image was pushed successfully.
-   **`Jenkinsfile` not found:** check the file name, GitHub repository,
    branch `main`, and Script Path `Jenkinsfile`.
-   **YAML error:** check indentation in `deployment.yaml`.
-   **Jenkins build fails:** open the build's **Console Output** and fix
    the first failing command before trying again.

## 14. Result (write in journal)

The application code was stored in GitHub, packaged into a Docker image,
pushed to Docker Hub, and deployed to Kubernetes through a Jenkins
Pipeline. The build and Kubernetes status were checked to verify the
result.

## 15. Viva questions and answers

**Q1. What is Git?**\
Git is a tool used to track changes in files.

**Q2. What is GitHub?**\
GitHub is an online platform for storing and sharing Git repositories.

**Q3. What is Docker?**\
Docker packages an application and its required files into an image.

**Q4. What is Docker Hub?**\
Docker Hub is an online service for storing and sharing Docker images.

**Q5. What is Kubernetes?**\
Kubernetes manages applications that run in containers.

**Q6. What is Minikube?**\
Minikube creates a small local Kubernetes cluster.

**Q7. What is Jenkins?**\
Jenkins automates build, test, and deployment tasks.

**Q8. What is a Jenkins Pipeline?**\
It is a sequence of tasks Jenkins runs automatically.

**Q9. What is a Jenkinsfile?**\
A file that contains the Pipeline instructions.

**Q10. What is CI/CD?**\
CI/CD describes practices that automate software integration and
delivery/deployment.

**Q11. Why use Jenkins credentials?**\
They let Jenkins authenticate securely without writing the password
directly in the Jenkinsfile.

**Q12. Why check `kubectl get pods`?**\
It shows the Kubernetes pods and their current status.

------------------------------------------------------------------------

# Quick command revision

  ----------------------------------------------------------------------------------------------
  Command                                                    Easy meaning
  ---------------------------------------------------------- -----------------------------------
  `git --version`                                            Check Git installation

  `git init`                                                 Start Git tracking in a folder

  `git status`                                               Check changed files

  `git add .`                                                Stage changes

  `git commit -m "message"`                                  Save a checkpoint

  `git push`                                                 Upload commits to GitHub

  `docker --version`                                         Check Docker installation

  `docker build -t name .`                                   Build a Docker image

  `docker images`                                            List images

  `docker run -p 5000:5000 name`                             Start a container with port mapping

  `docker ps`                                                List running containers

  `docker logs container-name`                               View container logs

  `docker stop container-name`                               Stop a container

  `docker rm container-name`                                 Remove a stopped container

  `docker compose up --build`                                Build and start Compose services

  `docker compose ps`                                        Check Compose services

  `docker compose down`                                      Stop/remove Compose containers

  `minikube start --driver=docker`                           Start local Kubernetes

  `kubectl get nodes`                                        Check Kubernetes nodes

  `kubectl apply -f deployment.yaml`                         Create/update Kubernetes resources

  `kubectl get deployments`                                  Check deployments

  `kubectl get pods`                                         Check pods

  `kubectl scale deployment ai-model-app --replicas=3`       Set three replicas

  `kubectl port-forward deployment/ai-model-app 5000:5000`   Access app through localhost
  ----------------------------------------------------------------------------------------------

## Final exam reminders

1.  Read the **Where** line before each command so you know which
    program to use.
2.  Run commands one at a time. Wait for the output before moving to the
    next step.
3.  Replace placeholders such as `YOUR_GITHUB_REPOSITORY_URL` and
    `YOUR_DOCKERHUB_USERNAME` with your own details.
4.  Keep file names exactly as shown. `Dockerfile` and `Jenkinsfile`
    should not have `.txt` at the end.
5.  YAML indentation matters. Copy the examples exactly.
6.  If something fails, stop and read the error instead of running every
    remaining command.
7.  Never expose your GitHub token, Docker Hub password, or Jenkins
    credentials.
8.  A practical is complete only when you verify the output; do not
    write that it succeeded if it did not.
