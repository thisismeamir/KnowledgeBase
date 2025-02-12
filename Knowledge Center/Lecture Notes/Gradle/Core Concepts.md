---
undefined: ""
File: Knowledge Center/Lecture Notes/Gradle/Core Concepts.md
sticker: lucide//newspaper
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
A Gradle project will look similar to the following:
```
project 
├── gradle ① 
│ ├── libs.versions.toml ②
│ └── wrapper 
│       ├── gradle-wrapper.jar 
│       └── gradle-wrapper.properties 
├── gradlew ③ 
├── gradlew.bat ③ 
├── settings.gradle(.kts) ④ 
├── subproject-a 
│       ├── build.gradle(.kts) ⑤ 
│       └── src ⑥ 
└── subproject-b 
        ├── build.gradle(.kts) ⑤ 
        └── src ⑥
```
1. Gradle directory to store wrapper files and more
2. Gradle version catalog for dependency management.
3. Gradle wrapper scripts
4. Gradle setting file to define a root project name and subprojects.
5. Gradle build scripts of two subprojects.
6. Source code and/or additional files for the projects.

### Gradle Wrapper Basics
The recommended way toe execute any Gradle build is with the Gradle wrapper. The Wrapper script invokes a declared version of Gradle, downloading it beforehand if necessary:
![[Pasted image 20250212115557.png]]
The wrapper is available as a `gradlew` or `gradlew.bat` file. The wrapper provides the following benefits:
- Standardizes a project on a given Gradle version.
- Provisions the same Gradle version for different users.
- Provisions the Gradle version for different execution environments.

> [!IMPORTANT] Using the Gradle Wrapper
> It is always recommended to execute a build with the Wrapper to ensure a reliable, controlled, and standardized execution of the build.
> ```bash
> ./gradlew build
> ```

#### Understanding Wrapper Files
The following files are part of the Gradle Wrapper:

```
.
├── gradle 
│ └── wrapper 
│ ├── gradle-wrapper.jar ① 
│ └── gradle-wrapper.properties ② ├── gradlew ③
└── gradlew.bat ④
```
1. `gradle-wrapper.jar`: This is a small jar file that contains the Gradle Wrapper code. It is responsible for downloading and installing the correct version of Gradle for a project if it's not already installed.
2. `gradle-wrapper.properties`: This file contains configuration properties for the Gradle Wrapper, such as the distribution URL (where to download Gradle from) and the distribution type (ZIP or TARBALL).
3. `gradlew` and `gradlew.bat`: These are shell scripts (Unix based and Windows respectively) that act as a wrapper around `gradle-wrapper.jar`. It is used to execute Gradle tasks without needing to manually install Gradle.

> [!DANGER] 
> You should never change these files!
> If you want to view or update the Gradle version of your project, use the command line. Do not edit the wrapper files manually.
> ```bash
> ./gradlew --version
> ./gradlew wrapper --gradle-version 7.2
> ```

## Settings File Basics
The primary role of the `settings.gradle` file is to add subprojects to your build. Gradle supports single and multi-project builds.

> [!NOTE] 
> - For single project builds, the setting file is optional.
> - For multi-project builds, the setting file is mandatory and declares all sub-projects.
