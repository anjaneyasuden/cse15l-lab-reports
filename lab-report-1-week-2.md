# LAB REPORT 1
*In this lab report we will discuss the procedure in-order to get yourself ready for CSE15L this involves:* \
**Setting up VSCode,\
 Remotely Connecting,\
 Trying Some Commands,\
 Moving Files with scp,\
 Setting an SSH Key,\
 Optimizing Remote Running** 
 
 
## Setting up VSCode
 *In order to set up VSCode, make sure to go to the VSCode website and download it for your Operating System* 
 
 [VSCode Download Link](https://code.visualstudio.com/)\
 **The page should look something like this**\
 ![VSCodeDownloadImage](Screenshot%20(36).png)
 
 **When finished downloading make sure to open your application and the interface should look something like this** 
 
 ![Image](Screenshot%20(30).png)
 
 
## Remotely Connecting
 *In this section we will talk about how to remotely connect the client, (your computer) to the host, (the server).* 
 
 **In the case of using a Windows Operating System click the following link and follow the steps** \
 [Install the OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) 
 
 **After doing this and following the steps, we are going to look up our CS15L account:** \
 **This can be done through using the account look up tool provided below** \
 [UCSD Acount lookup tool](https://sdacs.ucsd.edu/~icc/index.php) \
 **Here you will be greeted with a page that looks something like this:** \
 ![AccountLookUp](Screenshot%20(38).png) 
 **Make sure to fill in your UCSD username & your UCSD PID and then follow the steps of the password reset for your cs15l account that is usally in the form of:** \
 **cs15lwiabc where abc is your unique identification** 
 
 **After you have waited 15-20 minutes for your password to reset, open back your VSCode and open a new Terminal which can be shown how to be done from the following pictures below**
![VSCodeTerminal](Screenshot%20(39).png)
**And then type in this command**
```
# ssh cs15lwi22abc@ieng6.ucsd.edu
```
*where abc is your unique account name*

**After typing that into your terminal your terminal will prompt you to type in your password but, dont worry if you cannot see letters being typed on the screen it is being typed it is just an added saftey measure** 
![ls-l](Screenshot%20(41).png)
**If everything was completed correctly you page should look like this**
![VSCodeTerminal](Screenshot%20(42).png)
**And Well Done you have successfully logged into the server!**


## Trying Some Commands 
*Now that you have successfully logged into the server we can try out some commands**

**If you run the command *cd* it changes the directory your currently in allows you to enter another directory**

**If you run the command *ls -l* it esentially lists all the people that have access to your files and the size of the file and the last modified date**
![ls-l](Screenshot%20(43).png)

**Using the ls command you can also enter someone elses directory who is on the server using:** 
```
# ls /home/linux/ieng6/cs15lwi22/cs15lwi22abc 
```
**Where abc is someone elses username***


## Moving Files with scp
*We will now talk about scp or secure copy protocol. this will enable us to copy files form our computer to the server*

**Start of by creating a new folder in your VSCode** \
**On the top of your VSCode click** \
file->Open Folder->New Folder \
And name ir CSE15L
**From here make a new file**
![Creatingafile](Screenshot%20(44).png)
**Name this file HelloWorld.java**
**Then paste this code into the *HelloWorld.java***
```
public class HelloWorld {
    public static void main(String [] args){
        System.out.println("Hello World!");
    }
}
```
**After you have created this HelloWorld.java file make sure to save it and run it with javac and java** \
**Then in the same terminal directory run this command in-order to copy it onto the server, you will once again be prompted to eneter your password**
```
scp HelloWorld.java cs15lwi22zz@ieng6.ucsd.edu:~/
```
**After that log back into your account using `ssh` you should be able to see your file on the server by running *ls*, now you have your file on the server you can run javac and java in-order to run your code**
![scp](Screenshot%20(46).png)


## Setting an SSH Key
*We will now learn how to setup SSH Keys in-order for us to allow simple and quick access to files on the server and on our client. It will make our lives a lot easier by eliminating the use of continuously typing out our password when copying files over or retrieving them*

**Using the command `ssh-keygen` we can generate a private and public key on our client that we can use to easily connect to the server** \
**If we are on Windows we use the command `ssh-add C:\Users\<username>/.ssh/id.rsa` in order to connect us to the server**
![ssh-keygeb](Screenshot%20(47).png)
**Now we can look into the server by logging on again and running the command `ls -a` to list the files on our directory if you can see this file here you proceed to the next step**

**If you are on Windows you have to now proceed to complete these steps in order to get your public key on the server, circled in the red pen make sure to run these commands on your POWERSHELL Terminal *(as admininstrator)*, after that in the blue pen make sure to add your `ssh -add` your files into the ssh agent, after that in the green what we are doing is: we are running `scp` in order for us to copy our public key C:\... to the servers authorized keys**
![ssh-keygeb](Screenshot%20(48).png) \
**After you are done with this you can easily log into the server without the need of a password!**


## Optimizing Remote Running
*In this section we will explain how to further optimize connecting to the server* \
**Here you can see us making an edit to a local file in our own directory**
![copying](Screenshot%20(50).png)
**After this in order to send it to our server in order for us to run it on there we use the command** \
`scp HelloWorld.java cs15lwi22aff@ieng6.ucsd.edu:~/` **This will overide our file from the sever and then from there its simply a matter of logging in and running the javac and java commands to see our edits**

