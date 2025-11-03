Got it. You don't just want the commands, you want the *play-by-play* so you can focus on typing. No problem.

Here is a proper, step-by-step guide for each experiment. I've explained what each command does.

-----

### 🧪 Experiment 1: Version control using GIT

**Goal:** Set up Git on your machine, create a repository, and save (commit) a file.

1.  **Tell Git who you are:**
    [cite\_start]`git config --global user.name "AddyStarkte"` [cite: 78, 128]
2.  **Tell Git your email:**
    [cite\_start]`git config --global user.email "adityaubales@gmail.com"` [cite: 79, 129]
3.  **Create a new folder for your project:**
    `mkdir MyProject`
4.  **Go into that new folder:**
    `cd MyProject`
5.  **Turn this folder into a Git repository:**
    [cite\_start]`git init` [cite: 82, 91, 131]
6.  **Create a file:** Use a text editor (like Notepad, TextEdit, or `nano`) to create a file named `index.html`. Put some text in it, like "Hello World". Save it in your `MyProject` folder.
7.  **Add the file to Git's "staging area" (files to be saved):**
    [cite\_start]`git add index.html` [cite: 84, 91, 134]
8.  **Check the status of your repository:**
    [cite\_start]`git status` [cite: 137, 148] (You'll see `index.html` as a "new file").
9.  **Save your changes (a "commit") with a message:**
    [cite\_start]`git commit "First commit"` [cite: 167-168]
10. **(Optional) Link your local repository to a remote one on GitHub:**
    [cite\_start]`git remote add origin https://github.com/AddyStark16/devsecops.git` [cite: 162-163]
11. **(Optional) Verify the remote link:**
    [cite\_start]`git remote -v` [cite: 164]
12. **Rename your main branch (common practice):**
    [cite\_start]`git branch -M main` [cite: 173-174]
13. **(Optional) Push your saved changes to GitHub:**
    [cite\_start]`git pushu origin main` [cite: 175-177]
14. **See your commit history:**
    [cite\_start]`git log` [cite: 188, 194]

-----

### 🧪 Experiment 2: Version control using GITHUB

**Goal:** See how Git tracks changes to a file.

1.  **Create a file:** Use a text editor to make a file named `av.txt`. Put the text `Anubhav` inside it and save it.
2.  **Save this file in Git:**
    `git add av.txt`
    `git commit -m "Added av.txt"`
3.  **Add a new line to the file:**
    `echo Anubhav2 >> av.txt`
4.  **See the exact changes:** This command shows what lines were added or removed since your last save.
    [cite\_start]`git diff` [cite: 225, 258]
5.  **Check the status:** This tells you the file `av.txt` has been modified.
    [cite\_start]`git status` [cite: 231, 250-256]

-----

### 🧪 Experiment 3: Jenkins pipeline

**Goal:** Create a simple automated "Hello World" build job in Jenkins.

1.  [cite\_start]Start Jenkins and open it in your browser (usually `http://localhost:8080`)[cite: 370].
2.  [cite\_start]Log in. You'll have to create an admin user the first time[cite: 388, 413].
3.  [cite\_start]On the dashboard, click **New Item**[cite: 362].
4.  [cite\_start]Enter a name (e.g., "Sakec") and select **Pipeline** [cite: 421-422, 426]. Click **OK**.
5.  [cite\_start]Scroll down to the **Pipeline** section at the bottom of the page[cite: 438].
6.  [cite\_start]In the **Script** text box, paste this *exactly* [cite: 451-459]:
    ```groovy
    pipeline {
        agent any
        stages {
            stage('Hello') {
                steps {
                    echo 'Hello'
                }
            }
        }
    }
    ```
7.  [cite\_start]Click **Save**[cite: 462].
8.  [cite\_start]On your project's page, click **Build Now** to run it[cite: 463, 471]. [cite\_start]You will see a green "Hello" stage appear [cite: 478-479].

-----

### 🧪 Experiment 4: Selenium Tests in Jenkins Using Maven

**Goal:** Run a Java test (using Maven) from a Jenkins job.

1.  [cite\_start]In Jenkins, click **New Item**[cite: 563].
2.  [cite\_start]Enter a name and select **Freestyle project**[cite: 563, 597]. Click **OK**.
3.  (In a real setup, you'd link your source code repository here).
4.  Scroll down to the **Build** section.
5.  [cite\_start]Click **Add build step** and choose **Execute Windows batch command**[cite: 608].
6.  [cite\_start]In the **Command** box, you must first change to your project's directory and then run the Maven command[cite: 611].
    **Warning:** You MUST change the `cd` path to match your project's location.
    ```batch
    cd C:\Users\student\Downloads\java-testing-session-81-main java-testing-session-01-main
    mvn clean test
    echo success
    ```
7.  [cite\_start]Click **Save**[cite: 614].
8.  [cite\_start]Click **Build Now**[cite: 616].
9.  [cite\_start]To see the result, click the build number in the "Build History" and then **Console Output**[cite: 617].

-----

### 🧪 Experiment 5: Docker Installation (on Kali Linux)

**Goal:** Install the Docker program on Kali Linux.

1.  **Update your system's package lists:**
    [cite\_start]`sudo apt update && sudo apt upgrade -y` [cite: 781]
2.  **Install necessary helper packages:**
    [cite\_start]`sudo apt install apt-transport-https ca-certificates curl software-properties-common gnupg2 -y` [cite: 783-784]
3.  **Add Docker's official security key:**
    [cite\_start]`curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg` [cite: 786-787]
4.  **Add the Docker software repository:**
    [cite\_start]`echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null` [cite: 789-794]
5.  **Update lists again, then install Docker:**
    [cite\_start]`sudo apt update` [cite: 796]
    [cite\_start]`sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y` [cite: 797-798]
6.  **Start the Docker service:**
    [cite\_start]`sudo systemctl start docker` [cite: 806]
    [cite\_start]`sudo systemctl enable docker` [cite: 807]
7.  **Test the installation by running the "hello-world" container:**
    [cite\_start]`docker run hello-world` [cite: 766, 810]
    (You should see a "Hello from Docker\!" message) [cite\_start][cite: 915].

-----

### 🧪 Experiment 6: Running Containers

**Goal:** Run different applications (an OS, a web server) inside Docker containers.

1.  **Run an interactive Ubuntu container:** This pulls the image and drops you into a command prompt *inside* the container.
    [cite\_start]`docker run -it ubuntu bash` [cite: 1010, 1052]
2.  **You are now inside the container.** Type these commands to look around:
      * [cite\_start]`ls` [cite: 1058]
      * [cite\_start]`pwd` [cite: 1061]
3.  **Leave the container:**
    [cite\_start]`exit` [cite: 1074]
4.  **Run an Nginx web server container:**
      * `-d` runs it in the background.
      * `-p 8080:80` connects your computer's port 8080 to the container's port 80.
      * `--name my-nginx-server` gives it a friendly name.
        [cite\_start]`docker run --name my-nginx-server -p 8080:80 -d nginx` [cite: 1019, 1083]
        (You can now visit `http://localhost:8080` in your browser to see the "Welcome to nginx\!" page) [cite\_start][cite: 1097].
5.  **Run a Redis database container:**
    [cite\_start]`docker run --name my-redis-db -d redis` [cite: 1103]
6.  **List your *running* containers:**
    [cite\_start]`docker ps` [cite: 1023]
7.  **List *all* containers (including stopped ones):**
    [cite\_start]`docker ps -a` [cite: 1395]
8.  **Check the logs of your Redis container:**
    [cite\_start]`docker logs my-redis-db` [cite: 1205]

-----

### 🧪 Experiment 7: Security Testing using Snyk

**Goal:** Scan a project for known security vulnerabilities.

1.  **Install Snyk (assumes you have Node.js/npm):**
    [cite\_start]`npm install -g snyk` [cite: 1485, 1508]
2.  **Log in to your Snyk account:**
    [cite\_start]`snyk auth` [cite: 1487, 1513]
3.  [cite\_start]**A browser window will open.** Log in or sign up, then click the **Grant app access** button[cite: 1531].
4.  **Go back to your terminal. Make a new folder:**
    [cite\_start]`mkdir snyk-lab-project` [cite: 1547]
5.  **Go into that folder:**
    [cite\_start]`cd snyk-lab-project` [cite: 1548]
6.  **Create a `package.json` file (a manifest for Node.js projects):**
    [cite\_start]`npm init -y` [cite: 1549]
7.  **Install an *old, vulnerable* version of a package:**
    [cite\_start]`npm install express@4.16.0` [cite: 1563]
8.  **Run the security scan:**
    [cite\_start]`snyk test` [cite: 1498, 1570]
    (Snyk will scan your project and list all the vulnerabilities it found) [cite\_start][cite: 1572-1588].
9.  **Scan a Docker image for vulnerabilities:**
    [cite\_start]`snyk container test ubuntu:latest` [cite: 1506, 1608]

-----

### 🧪 Experiment 8: Static Application Security Testing (SAST) using SonarQube

**Goal:** Install SonarQube to scan your code for bugs and security hotspots (like hardcoded passwords). This is the most complex setup.

**Part 1 – Install Java (Prerequisite)**

1.  [cite\_start]`sudo apt update` [cite: 1814]
2.  [cite\_start]`sudo apt install openjdk-17-jdk -y` [cite: 1816]
3.  [cite\_start]`java -version` [cite: 1818]

**Part 2 – Install and Run SonarQube Server**
4\.  **Download SonarQube:**
[cite\_start]`wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.9.4.87374.zip` [cite: 1849]
5\.  **Unzip it:**
[cite\_start]`unzip sonarqube-9.9.4.87374.zip` [cite: 1859]
6\.  **Start the server (Linux command):**
[cite\_start]`./sonarqube-9.9.4.87374/bin/linux-x86-64/sonar.sh start` [cite: 1896]
(This will take a minute to start up).

**Part 3 – Set Up SonarQube in Your Browser**
7\.  [cite\_start]Open `http://localhost:9000` in your browser[cite: 1769].
8\.  [cite\_start]Log in with: **Username:** `admin` and **Password:** `admin` [cite: 1772-1773, 1925-1926].
9\.  You will be forced to change your password. Do this.
10\. [cite\_start]Follow the prompts to **Create Project**[cite: 1775]. [cite\_start]Give it a "Project Key" (e.g., `my-python-app`)[cite: 1776, 1963].
11\. When prompted, generate a **Token**. **COPY THIS TOKEN** and save it in a text file. [cite\_start]You will need it[cite: 1777, 1971].

**Part 4 – Install the Sonar Scanner**
12\. **Download the scanner:**
[cite\_start]`wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-5.0.1.3006-linux.zip` [cite: 1902]
13\. **Unzip it:**
[cite\_start]`unzip sonar-scanner-cli-5.0.1.3006-linux.zip` [cite: 1911]
14\. **Add the scanner to your system's PATH:** (This path *must* be correct for your system)
[cite\_start]`export PATH="$PATH:$HOME/Devsecops/sonar-scanner-5.0.1.3006-linux/bin"` [cite: 1939]
15\. **Verify the scanner is installed:**
[cite\_start]`sonar-scanner -v` [cite: 1782, 1939]

**Part 5 – Create a Project to Scan**
16\. **Make a new project folder:**
`mkdir sonar-py-project`
17\. **Go into that folder:**
`cd sonar-py-project`
18\. **Create a Python file with a security issue:**
\* Use a text editor: `nano app.py`
\* Paste this code inside:
\`\`\`python
import os

````
    def get_database_connection():
        # SonarQube should flag this hardcoded password as a security hotspot
        password = "mySuperSecretPassword123"
        print("Connecting to database with password:", password)
        return True
    
    get_database_connection()
    ```
    [cite_start][cite: 1948, 1950-1954]
* Save and exit the editor.
````

19. **Create the Sonar configuration file:**
      * Use a text editor: `nano sonar-project.properties`
      * Paste this code inside:
        ```properties
        sonar.projectKey=my-python-app
        sonar.projectName=My Python App
        sonar.projectVersion=1.0
        sonar.sources=.
        sonar.host.url=http://localhost:9000
        sonar.login=PASTE_YOUR_TOKEN_HERE
        ```
        [cite\_start][cite: 1962-1971]
      * [cite\_start]**CRITICAL:** Replace `PASTE_YOUR_TOKEN_HERE` with the token you copied from the SonarQube website in Step 11[cite: 1796, 1971].
      * Save and exit the editor.

**Part 6 – Run the Scan**
20\. **From inside your `sonar-py-project` folder, run the scanner:**
[cite\_start]`sonar-scanner` [cite: 1798, 2009]
21\. **Wait for it to finish.** You'll see "EXECUTION SUCCESS" in the terminal.
22\. **Go back to your SonarQube project in your browser (`http://localhost:9000`).** Refresh the page. [cite\_start]You will now see the scan results, which should highlight the hardcoded password as a "Security Hotspot"[cite: 1801, 1804].
