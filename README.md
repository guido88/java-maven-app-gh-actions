A Java Maven App
---

This is just a demo app to show how to build and deploy it automatically with a CI/CD Pipeline using Github Actions workflow.


Workflow Overview (.github/worflows)
---

This workflow is triggered on every push to the master branch. It performs the following steps:

Checkout Code
---

Retrieves the code from the repository to be used in subsequent steps.

Set Up JDK 17
---

Sets up the JDK version 17 required to build the Java project.

Bump Project Version
---
Automatically bumps the project version using Maven's build-helper and versions plugins.

Build with Maven
---
Builds the Java project and packages it into a JAR file using Maven.

Build & Push Docker Image
---
Builds a Docker image with the new project version and pushes it to Docker Hub.

Commit and Push Changes
---
Commits the new version number to the repository to keep track of changes.

Setup SSH for EC2
---
Configures SSH for connecting to an EC2 instance.

Copy files on EC2 and Run Docker Container
---
Transfers necessary files to the EC2 instance and executes a script to run the Docker container.
