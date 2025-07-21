# ☁️ Terraform-Powered CI/CD Pipeline on AWS for Java Web App

## 🚀 Project Overview

This project demonstrates a complete DevOps pipeline for deploying a Java-based web application using infrastructure as code (IaC) with Terraform on AWS. The pipeline is powered by Jenkins, SonarQube, and Apache Tomcat across three EC2 instances provisioned automatically. The application code, configuration files, and deployment automation scripts are hosted in the GitHub repository `physicstutoring-Website`.

## 🛠️ Tools & Technologies

- **Terraform** for infrastructure provisioning
- **AWS EC2** (3 instances: Jenkins, Tomcat, SonarQube)
- **Jenkins** for CI/CD pipeline
- **SonarQube** for static code analysis
- **Apache Tomcat** as the web application server
- **Maven** for build automation
- **GitHub** for source control

## 🧾 Project Structure

```
physicstutoring-Website/
├── main.tf                  # Terraform configuration file for infrastructure provisioning
├── terraform.tfvars         # Terraform variables
├── variables.tf             # Terraform variable definitions
├── jenkinsfile              # Jenkins pipeline definition
├── installtomcat.sh         # Bash script to install Apache Tomcat on EC2
├── jenkinsinstall.sh        # Bash script to install Jenkins on EC2
├── sonarqubeinstall.sh      # Bash script to install SonarQube on EC2
├── physicstutors/           # Java web app project folder
│   ├── pom.xml              # Maven project descriptor
│   └── src/
│       └── main/
│           └── webapp/
│               ├── index.html
│               └── WEB-INF/
│                   └── web.xml
```

## 🔧 What I Did

### 1. **Version Control & Initialization**

- Created a GitHub repository named `physicstutoring-Website`.
- Cloned the repository locally and created the required folder structure.

### 2. **Infrastructure Provisioning**

- Wrote `main.tf`, `variables.tf`, and `terraform.tfvars` files to:
  - Provision **3 EC2 instances** on AWS:
    - **Jenkins Instance** for running CI/CD pipeline
    - **Tomcat Instance** for hosting the Java web application
    - **SonarQube Instance** for code analysis
  - Passed user-data shell scripts to automatically install Jenkins, Tomcat, and SonarQube respectively.
- Used **Terraform environment variables** (AWS\_ACCESS\_KEY and AWS\_SECRET\_KEY) on the host machine for secure access to AWS.

### 3. **Jenkins Configuration**

- Installed Jenkins plugins: Maven Integration, Deploy to Container, SonarQube Scanner, and others.
- Connected Jenkins to GitHub repo and configured Webhook.
- Added **Maven** tool installation and **SonarQube server** configuration in Jenkins.

### 4. **Pipeline Creation**

- Created a `jenkinsfile` with stages:
  - **Test**: Validate the build
  - **Build**: Use Maven to package the application
  - **Analyse**: Scan source code using SonarQube
  - **Quality Gate**: Enforce code quality
  - **Deploy**: Automatically deploy to Tomcat server

### 5. **Deployment**

- Application deployed to Apache Tomcat running on a dedicated EC2 instance.
- Verified the application via browser access to the Tomcat public IP.

## 🌐 Live Application & Testing

- Jenkins Dashboard and Job Status
- SonarQube dashboard showing code analysis reports
- Web app accessible via Apache Tomcat

## 🎓 Key Takeaways

- Built a complete automated CI/CD pipeline using open-source tools.
- Mastered provisioning with Terraform and connecting multiple components across EC2 instances.
- Improved skills in secure AWS access, script automation, Jenkins configuration, and SonarQube integration.
- Learned end-to-end DevOps cycle from source code to deployment.

---

*Prepared by: Yinka Ajibola*

