
## 🧰 Prerequisites

- Jenkins installed and running
- Java (OpenJDK 17+)
- User `cloudadmin` with appropriate permissions
- Internet access for downloading Maven & Tomcat

## 🚀 Jenkins Pipeline Stages

### 1. Install Maven
Downloads and extracts Maven 3.9.4.

### 2. Compile Application
Compiles Java code using Maven.

### 3. Test Application
Runs unit tests using Maven.

### 4. Package Application
Packages the app as a WAR file.

### 5. Install Prerequisites
Installs Java runtime (OpenJDK 17).

### 6. Install Apache Tomcat
- Downloads Tomcat 8.5.24
- Extracts and configures:
  - `tomcat-users.xml` for GUI authentication
  - `context.xml` for remote access
  - Changes Tomcat port to 8081

### 7. Deploy WAR to Tomcat
- Copies `addressbook.war` to `webapps/`
- Starts Tomcat server under `cloudadmin` user

## 🛠 Configuration Files

### `tomcat-users.xml`

```xml
<user username="cloudadmin" password="ansibleawx@123" roles="manager-gui,admin-gui,manager-script"/>
