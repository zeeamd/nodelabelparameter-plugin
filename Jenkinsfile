#!/usr/bin/env groovy

String mavenCommand = 'mvn clean install -Dmaven.test.failure.ignore=true'
String testReports = '**/target/surefire-reports/**/*.xml'

  node {
        checkout scm
        withEnv([
            "JAVA_HOME=${tool 'jdk7'}",
            "PATH+MAVEN=${tool 'mvn'}/bin",
        ]) {
            sh mavenCommand
        }
        junit testReports
    }

stage 'build'
