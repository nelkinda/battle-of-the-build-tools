# Battle of the JVM Build Tools 2020

This repository contains the code examples for the blog article/study "Battle of the JVM Build Tools 2020".
In this context, JVM represents the target of software development.
That the build tool itself runs on the JVM is not required.

The goal is to explore building the following tasks:
* A simple Hello, World application
* A simple dummy library
* A multi-module application
* A single-module Spring application
* A multi-module Spring application

In the following languages:
Java and Kotlin

The current plan is to explore the following tools for building:
* GNU bash
* GNU make
* Apache Ant
* Apache Maven
* Gradle
* SBT

The following aspects are to be explored:
* Simple/vanilla setup effort
* Dependency management within the project
* Dependency management of third-party dependencies
* Size of build script
* Build performance on first run
* Build performance on consecutive runs
* Ease of creating an artifact manifest with meta information (license, maintainers, etc)
* Release creation
* Deployment via docker
* Deployment via ssh/systemd
* Signal-to-Noise Ratio (Unix philosophy: Silence is Golden)
* Including build information like git commit id in the artifact
* Calling arbitrary shell commands from within the build
  * And reuse their output at a specific stage
  * Generate code


Ideaes and Feedback welcome!
