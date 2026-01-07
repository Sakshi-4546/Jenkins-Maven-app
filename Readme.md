# Maven Application Build Using Jenkins  
## Project Overview

This project demonstrates how to build a Java Maven application using Jenkins. Jenkins is used to automate the process of pulling source code from Git, compiling the application, running tests, and generating build artifacts (.jar / .war).

## Prerequisites

Ensure the following are installed on the Jenkins server:

1) Java (JDK)  
2) Maven  
3) Jenkins  
4) Git

## Steps to Create

### Step 1 :- Create the following structure on jenkins server (powershell)
```text
mavenApp/
├── pom.xml
└── src
    ├── main
    │   └── com
    │       └── fortune
    │           └── app
    │               └── App.java
    └── test
        └── com
            └── fortune
                └── app  
                    └──Test.java

```  
![](./Img/Screenshot%20(285).png)

![](./Img/Screenshot%20(286).png)

### Step 2 :- Configure Tools in Jenkins

#### 1) Go to Manage Jenkins → Tools Configuration
#### 2) Configure:  
- JDK → select installed Java version     

![](./Img/Screenshot%20(287).png)

#### - Maven → give name (e.g. Maven3) and select version

![](./Img/Screenshot%20(288).png)

### Step 3 :- Create Jenkins Job (Freestyle)

![](./Img/Screenshot%20(289).png)

### Step 4 :- Configure Source Code Management
- Create repository on github and **set webhook**  

then

#### 1) Select Git  
#### 2) Enter Repository URL
#### 3) Branch: main or master

![](./Img/Screenshot%20(290).png)

#### 4) Triggers: Select Github hook trigger for GITScm polling

![](./Img/Screenshot%20(291).png)

### Step 5 :- Add Build Step

#### 1) Go to Build → Add build step  
#### 2) Select Invoke top-level Maven targets

Configure:

Maven Version : mymaven  
Goals : clean package

![](./Img/Screenshot%20(292).png)

### Step 6 :- Push your file to github

![](./Img/Screenshot%20(293).png)

### Step 6 :- Check your build started
![](./Img/Screenshot%20(294).png)

### Step 7 :- Check .jar file is created
![](./Img/Screenshot%20(295).png)




