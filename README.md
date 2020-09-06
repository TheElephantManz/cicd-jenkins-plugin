# ServiceNow CI/CD Jenkins Plugin. 

See https://github.com/jenkinsci/servicenow-cicd-plugin going forward. 
Archiving.

This plugin provides build steps with easy parameter setup to help you get started faster with setting up a CI and CD pipeline for developing apps on the Now Platform.
# This workflow will build a Java project with Maven
# For more information see: https://help.github.com/actions/language-and-framework-guides/building-and-testing-java-with-maven

name: Java CI with Maven

on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up JDK 1.8
      uses: actions/setup-java@v1
      with:
        java-version: 1.8
    - name: Build with Maven
      run: mvn -B package --file pom.xml
$ mvn deploy -Dregistry=https://maven.pkg.github.com/TheElephantManz -Dtoken=GH_TOKEN
