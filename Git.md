# Git1

**version control** is a system that records my changing history that I have done in my code in order to visit any version whenever i need.

Git is a distributed version control system that saves aversion of my project each time i make a change in order to onep any version i may need. Git depends on local operations because most important information can be found there. Git prevents the loss of data so it's not only giving me the chance to restore my old versions; it also saves all of the them in case of unexpected accedents.

Files in Git can reside in three main states which are:

* committed
* modified
* staged

to import an excisting project into Git i firstly should Switch to the target project’s directory, then i Use the git init command. after that in order to tracking the repository files i type the following demands:
* $ git add *.c
* $ git add LICENSE
* $ git commit -m “any message here”

and now if I want to make an edit on my project in my local machine I should follow these steps:

#1 copy the URL for my online project and use the command ``` $ git clone [ your project URL] ```
 
#2 check your project by using the command ```$ ls ```

#3 to open my code using the command ```code . ```

**my project will be opened on my local device**

#4 then I can track all files in a repository by using the command: ```$ git add * ```

#5 now I need to check the file status using the command : ```$ git status ```


#6 commiting my changes in order to keep notes if me or someone else opened my project. i can commit each change alone using the command
``` $ git commit -m “made change x,y,z” ``` , or commiting all changes together using the command ``` $ git commit -a ```

#7 finally I need to push my changing to a remote repository using the following command: ``` $ git push origin master ```













