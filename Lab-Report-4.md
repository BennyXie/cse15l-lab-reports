# Intro to the Competition
## These are the steps that you should do in the competiton.  
1. Setup Delete any existing forks of the repository you have on your account  
If you haven't fork the repository, skip this step and go to step 2.  
Go to your lab7 repository.  
![image](https://user-images.githubusercontent.com/118026674/221046011-beb8b6f8-bf7c-4b92-97cf-9e678fda2a67.png)  
You need to confirm the delete action by typing the directory of this repository.  
Scroll down to the bottom and click "Delete this repository".  
![image](https://user-images.githubusercontent.com/118026674/221046109-01f62624-d76b-4bd2-8c8b-f2ff500a219a.png)  

2. Setup Fork the repository  
Go to the Lab7 github page ([lab7Github](https://github.com/ucsd-cse15l-w23/lab7)), then click on fork.  
![image](https://user-images.githubusercontent.com/118026674/221047271-200a184e-9411-4ed6-aaba-039d76dfa047.png)  
After clicking on "fork", click on create repository.  

3. The real deal Start the timer!  
Start your timer!

4. Log into ieng6
Go to your terminal, type `ssh <your-ieng6-account>` and then press `<enter>`.   
![image](https://user-images.githubusercontent.com/118026674/221048162-5494c31a-2e0d-4c37-9472-85ec434dd71d.png)  
Command "ssh" is to connect to the remote server.  
If you have set up the no-password-login, you are already in. If you haven't, type your password and press `<enter>`. 
  
5. Clone your fork of the repository from your Github account
Go to the lab7 repository you just forked and copy the link in ssh.  
![image](https://user-images.githubusercontent.com/118026674/221049366-d212ab82-6987-4026-bdf2-8f01f209dfd7.png)  
Then, go to your terminal, type `git clone <link-you just copied>`, and press `<enter>`.  
You cannot use the ssh clone if you haven't set it up.  
We are cloning the content in the repository into the server.  

6. Run the tests, demonstrating that they fail  
First, type `cd lab7` and press `<enter>` to change the current directory to lab7.  
Type `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and press `<enter>` to compile the code.
Type `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` and press `<enter>` to run the tester.  
The test should fail.  
![image](https://user-images.githubusercontent.com/118026674/221051687-08b59172-d9fc-48c6-8bf2-0755d636e346.png)  

7. Edit the code file to fix the failing test  
Type `nano ListExamples.java` to edit this java file.  
Press `ctrl + w` and type `input1 += 1` and press `<enter>`. Do this 3 times to move to the buggy part.  
Press `<left-arrow>` 6 times, press `<delete>`, and type `2` to fix the bug.  
![image](https://user-images.githubusercontent.com/118026674/221053331-20977004-d208-484c-8d9c-97294c43dadf.png)  
Press `ctrl + o` and press <enter> to save the change.  
Press `ctrl + x` to quit nano.  
8. Run the tests, demonstrating that they now succeed  
Hit `<UpArrow>` 5 times and press `<enter>` to compile the code.
Hit `<UpArrow>` 5 times and press `<enter>` to run the tester.  
![image](https://user-images.githubusercontent.com/118026674/221053573-49465b6d-b40b-4c51-905a-6a425be44d2d.png)  
Now we can see that we have fixed the bug.  
9. Commit and push the resulting change to your Github account  
Type `git add ListExamples.java` and press `<enter>` to add this file to your work flow.  
Type `git commit -m "1"` to commit the change.  
Type `git push` to push the change to your github.  
![image](https://user-images.githubusercontent.com/118026674/221055885-690d9c8e-d76a-4a49-b63a-d072bdc838c6.png)  
If your console shows this message, you succeed! Go to your github website repository to verify that it has worked.  
![image](https://user-images.githubusercontent.com/118026674/221056037-8e02a175-056d-4db4-944c-fbe1d99a0cf9.png)  
It worked! I hope you do well in the competition.  
