#build-tool #web-dev
[Source](https://www.simplilearn.com/tutorials/maven-tutorial/what-is-maven)
### Maven Intro
Maven is an open-source build tool from the Apache Software Foundation to build, publish and deploy several projects at once.

Maven is written in Java and used to build projects written in C#, Scala, Ruby etc. 

Maven provides the following benefits:
1. Builds
2. Documentation
3. Dependency Management
4. Automatic Parent versioning
5. Reports
6. SCM (Source Code Management)
7. Distribution
8. Releases
9. Huge, continuously growing repository of user libraries
10. Ability to set up projects easily, using best practices
11. Consistent usage across all projects
12. <mark style="background: #FF5582A6;">Mailing list (?)</mark>
13. <mark style="background: #FF5582A6;">It is extensible - plugins can easily be written using scripting languages or Java (?)</mark>

Maven is a comprehensive, maintainable, reusable and simple model for projects. It provides a set of tools and plugins that can interact with the **declarative** model.

### Maven as a Build Tool
Maven as a build tool allows us to create an executable application from the source code. Maven does the following:
	Compiling source code -> Packaging compiled codes into JAR files -> installing packaged code in local repository or server or central repository.

#Question How is a JAR file deployed?

Maven's versatility and usefulness comes from the use of [[POM | Project Object Model]] files written in an XML format. The POM file is located in the home directory - when a task is executed, maven searches for the POM in the current directory.

Maven is typically used for Java-based projects, helping to download dependencies, which may refer to libraries or JAR files. Maven resolves dependencies and gets the correct JAR files for the right versions.

### Using Maven
When you’re ready to start [using Maven](https://www.simplilearn.com/tutorials/maven-tutorial/how-to-install-maven "using Maven"), keep these three things in mind:

1.  Configure Maven in Java, using Project Object Model (POM) found in a pom.xml file.
2.  All Maven-related configuration settings are found in the POM. You can edit and configure plug-ins in the `<plugins>` tag of a pom.xml file.
3.  Maven provides default settings for configurations, so you don’t have to add every configuration into the pom.xml file.

### Steps/Process Involved in Building a Project

Here are the steps to follow when building a [Maven project](https://www.simplilearn.com/tutorials/maven-tutorial/maven-project-in-eclipse "Maven project"):

-   Add or write the code to create the application creation, and process it into the source code repository.
-   Edit any necessary configuration / pom.XML / plugin details.
-   Build the actual application.
-   Save your build process output as either a WAR or EAR file to a local server or other location.
-   Access the file from the local location or server and deploy it to the production or client site.
-   Update the application document by changing the date and updated application version number, if necessary.
-   Create and generate a report as requested for the application or the requirement.

### Drawbacks
-   Maven requires installation in the working system and the Maven plug-in for the IDE
-   If the Maven code for an existing dependency is unavailable, you cannot add that dependency using Maven itself
-   Some sources claim that Maven is slow