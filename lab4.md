# Lab 4

## Step 4 - *Log into ieng6*  
To access ssh, I simply use the `ssh` command. No password is prompted.  
```
ssh cs15lfa23sa@ieng6.ucsd.edu <enter>
```
![Image](lab4_step4.png)

## Step 5 - *Clone your fork of the repository from your Github account (using the SSH URL)*  
To clone my fork of the repository, I navigated to my repository and copied the SSH URL. In my bash terminal, I used the `git clone` command as shown below.  
```
git clone git@github.com:ElvinLit/lab7.git <enter>
```
![Image](lab4_step5.png)

## Step 6 - *Run the tests, demonstrating that they fail*
To run the tests, I first navigate to my lab7 directory using `cd`, and then run a `javac` and `java` command to compile and run the tests. When I pressed tab after `cd lab`, lab7/ is autofilled.  
```
cd lab <tab> <enter>
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java <enter>
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests <enter>
```
![Image](lab4_step6.png)
