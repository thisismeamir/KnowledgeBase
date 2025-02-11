---
undefined: ""
File: Knowledge Center/Lecture Notes/Gradle/Core Concepts.md
---
# Gradle Basics
In simple terms, Gradle is a build system, helping software development by automating building, testing, and deployment of software from the information given by the user as *build scripts*.

![[Pasted image 20250211195421.png]]

## Terms and Concepts 

### Projects 
A Gradle project is simply a piece of software that can be built, such as an application or a library. 

There are two types of projects in Gradle. Single project and Multi-project. A single project consists of a root project, while the multi-project include one root project and any number of sub-projects.

### Build Scripts
Build scripts describe to Gradle what the build process is, explaining steps to take to build the project. Each project can contain more than one build script.

### Dependency Management
Dependency Management is an automation process for declaring and resolving external resources required by the project. 

Each project typically includes some other projects, libraries, or sources; Gradle will resolve them during the build process.

### Tasks 
Tasks are units of works that Gradle does in the build process. These can be compiling code, or running your tests. 

Tasks are defined inside the build script or a plugin.

### Plugins
Plugins are used to extend Gradle and optionally contribute tasks to a project.

## Gradle Project Structure