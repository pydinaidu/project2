# project1
 

•	Launching Jenkins on EC2 Instance: The first step was setting up an EC2 instance on AWS and installing Jenkins to facilitate continuous integration and deployment.
 

 

•	Installing and Configuring Maven: To manage dependencies and build the project, I installed Maven, a popular build automation tool, and configured it to ensure smooth project compilation.

Install Maven Commands  
                     ------------------
            cd /opt/
           1) sudo wget http://www-eu.apache.org/dist/maven/m...
           2) sudo tar -xf apache-maven-3.5.3-bin.tar.gz
           3) sudo mv apache-maven-3.5.3/ apache-maven/
          4) sudo update-alternatives --install /usr/bin/mvn maven /opt/apache-maven/bin/mvn 
         Configuring Apache Maven Environment

            $ cd /etc/profile.d/
          $ sudo nano maven.sh
           ###################################################
        # Apache Maven Environment Variables
        # MAVEN_HOME for Maven 1 - M2_HOME for Maven 2
       export JAVA_HOME=usr/lib/jvm/java-11-openjdk-amd64
       export M2_HOME=/opt/apache-maven
        export MAVEN_HOME=/opt/apache-maven
       export PATH=${M2_HOME}/bin:${PATH}

      sudo chmod +x maven.sh
    sudo source maven.sh
        maven is successfully configured. when we type mvn --version it should display it version       everywhere in the system.

1.Install maven plugin and configure jenkins for maven Manage Jenkins-plugins-maven integration

 


Set maven path in Jenkins

 


•	Setting up JDK: Java Development Kit (JDK) was installed to enable Java development on the EC2 instance.
 
•	Integrating Jenkins with GitHub: I connected Jenkins to my GitHub repository, allowing it to trigger automated builds and deployments whenever new code changes were pushed.
Install git in Ubuntu

sudo apt-get install git

 
•	Setup Tomcat Server 🐈: Next, I installed and configured Tomcat, a widely used web server, and servlet container, on the same EC2 instance to host our JSP application.
•	Integrating Tomcat with Jenkins: I integrated Tomcat with Jenkins, enabling seamless application deployment to the Tomcat server during the build process.
Install Tomcat
       cd /opt
 wget https://downloads.apache.org/tomcat/tomcat-10/v10.1.11/bin/apache-tomcat-10.1.11.tar.gz.
 tar -xvzf apache-tomcat-10.1.11.tar.gz
mv apache-tomcat-10.1.11 tomcat
            cd tomcat/
 cd bin

 

 

 

•	Deploying the JSP App to Tomcat: Leveraging Jenkins, I set up the deployment process to automatically push the JSP web app to Tomcat after successful builds.
•	Poll SCM: To ensure timely updates, I configured Jenkins to poll the GitHub repository for changes periodically, triggering builds and deployments as needed.

