---
layout: post
title: How to include a Maven project as dependency in Gradle
summary: This question was asked on StackOverflow the other day and I came up with a "hackish" solution.
tags: [java, gradle]
---

This question was asked on StackOverflow the other day and I came up with a "hackish" solution:

It is possible to fake including a Maven dependency by setting a dependency on the output folder of the Maven project and having it built by Gradle.

Here is an example:

<script src="https://gist.github.com/tomasulo/72527c46bb725be480fbda8f8130969d.js"></script>

This way Gradle will execute a Maven build (compileMavenProject) before compiling. But be aware that it is not a Gradle "project" in the traditional sense and will not show up, e.g. if you run `gradle dependencies`. It is just a hack to include the compiled class files in your Gradle project.

You can use a similar technique to also include the Maven dependencies:

<script src="https://gist.github.com/tomasulo/b632dff1f7f1d280d5d897f88bfe8ad1.js"></script>

See: [https://stackoverflow.com/questions/35795250/maven-project-as-dependency-in-gradle-project/35796615#35796615](https://stackoverflow.com/questions/35795250/maven-project-as-dependency-in-gradle-project/35796615#35796615)
