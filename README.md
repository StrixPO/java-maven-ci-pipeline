# 🚀 Java Maven CI Pipeline with Jenkins

This project demonstrates a **basic Java HelloWorld application** built and deployed using **Jenkins CI** with **Apache Maven**. It simulates a real-world CI/CD setup, useful for DevOps learning and resume experience.

---

## 🧱 Tech Stack

- Java (JDK 8/11)
- Apache Maven
- Jenkins (running in Docker)
- GitHub

---

## 📁 Project Structure

hello-java-maven/ 

├── src/ main/ java/ com/ example/

│  └── HelloWorld.java 

└── pom.xml

## 🔧 Setup Instructions

### 1. Clone this repository

```
git clone https://github.com/StrixPO/java-maven-ci-pipeline.git
```
2. Run Jenkins in Docker (Windows-friendly one-liner)
```
docker run -d --name jenkins -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts
```
3. Setup Jenkins Job
```
Go to http://localhost:8080
```
Unlock Jenkins using initial admin password from the container logs:
```
docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```
  - Install recommended plugins
  - Set up a new Freestyle project

In "Source Code Management", select Git:
```
https://github.com/StrixPO/java-maven-ci-pipeline.git
```

In Build Steps, choose:
Invoke top-level Maven targets
Goals: clean package

✅ Build Verification
  - Click Build Now
  - Check Console Output

You should see:
```
[INFO] BUILD SUCCESS
```
📸 Screenshot
![image](https://github.com/user-attachments/assets/5e108892-faec-40bb-a452-d57e83dd8638)

📚 Outcome
  - Understand basic CI/CD pipeline setup
  - Configured Jenkins for Maven builds
  - Learned how to use Jenkins build triggers and console outputs

🧠 Notes
  - Maven was configured globally under Manage Jenkins → Global Tool Configuration
  - Jenkins container was isolated and persistent via Docker volume

🔗 Author
Rusar Pradhan
