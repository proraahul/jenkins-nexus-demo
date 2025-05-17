# Jenkins Pipeline for Java Maven Project Deployment

This project uses a Jenkins Declarative Pipeline to automate building, testing, packaging, and deploying a Java-based web application using Apache Maven, Nexus, and Tomcat.

## Pipeline Stages Explained

### 1. Checkout Code
Fetches the code from the GitHub repository (`https://github.com/Rahul-training/Devops`).

### 2. Maven Installation
Downloads and extracts Apache Maven 3.9.4 into the Jenkins workspace.

### 3. Compile Sample Application
Compiles the Java project using Maven.

### 4. Test Sample Application
Runs unit tests on the project.

### 5. Package Sample Application
Packages the application into a `.war` file for deployment.

### 6. Nexus Artifact Upload
Uploads the `.war` file to a Nexus repository for artifact management.

### 7. Upload Nexus Artifact (Duplicate stage)
This stage duplicates the previous upload logic and can be merged or removed based on use case.

### 8. Tomcat Prerequisites Installation
Installs Java Runtime Environment (JRE) required for running Tomcat.

### 9. Install Apache Tomcat Server
Downloads and configures Tomcat 8.5.24, including user roles and port changes.

### 10. Deploy Sample Application To Tomcat Server
Copies the WAR file to Tomcat's `webapps` directory and starts the server.

---

## Requirements

- Jenkins installed
- Maven and Java installed on the Jenkins server (if not done in pipeline)
- Nexus configured with appropriate credentials
- Tomcat installation configuration files: `tomcat-users.xml` and `context.xml`
- A user named `cloudadmin` (as used in `runuser`)
- GitHub access permissions to the repo

---

## Notes

- Update placeholders like `your-credentials-id`, `your.group.id`, `your-repo-name`, and `http://your-nexus-url` with your actual configuration.
- Ensure the Jenkins user has sudo privileges for installation and service management commands.
