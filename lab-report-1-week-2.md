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
 ![VSCodeDownloadImage](https://user-images.githubusercontent.com/97692945/149403551-3d1e8695-8da0-44ec-82b5-188d1901c97e.png)
 
 **When finished downloading make sure to open your application and the interface should look something like this** 
 
 ![VSCodeInterface](https://user-images.githubusercontent.com/97692945/149404004-7b5c36d1-8394-47c4-8254-713639c91914.png)
 
 
 ## Remotely Connecting 
 *In this section we will talk about how to remotely connect the client, (your computer) to the host, (the server).* 
 
 **In the case of using a Windows Operating System click the following link and follow the steps** \
 [Install the OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) 
 
 **After doing this and following the steps, we are going to look up our CS15L account:** \
 **This can be done through using the account look up tool provided below** \
 [UCSD Acount lookup tool](https://sdacs.ucsd.edu/~icc/index.php) \
 **Here you will be greeted with a page that looks something like this:** \
 ![AccountLookUp](https://user-images.githubusercontent.com/97692945/149406491-da45605c-8537-4249-9e58-20b8dcf336bc.png) 
 **Make sure to fill in your UCSD username & your UCSD PID and then follow the steps of the password reset for your cs15l account that is usally in the form of:** \
 **cs15lwiabc where abc is your unique identification** 
 
 **After you have waited 15-20 minutes for your password to reset, open back your VSCode and open a new Terminal which can be shown how to be done from the following pictures below**
![VSCodeTerminal](https://user-images.githubusercontent.com/97692945/149407233-4ff76a3b-beb7-47dc-845e-4583ddd7de92.png)
![VSCodeTerminal](https://user-images.githubusercontent.com/97692945/149407687-a164d5ab-3504-4aef-94c3-a2af105163f3.jpg)
**And then type in this command**
```
# ssh cs15lwi22abc@ieng6.ucsd.edu
```
*where abc is your unique account name*

**After typing that into your terminal your terminal will prompt you to type in your password but, dont worry if you cannot see letters being typed on the screen it is being typed it is just an added saftey measure** 
![VSCodeTerminal](https://user-images.githubusercontent.com/97692945/149408428-9acd3450-b2f2-4c71-8e17-cdefc6cf7b40.png)

**If everything was completed correctly you page should look like this**
![VSCodeTerminal](https://user-images.githubusercontent.com/97692945/149408679-7fa52e74-9ea9-45ac-b22b-9603ac62b97c.png)
**And Well Done you have successfully logged into the server!**


## Trying Some Commands 
*Now that you have successfully logged into the server we can try out some commands**

**If you run the command *cd* it changes the directory your currently in allows you to enter another directory**

**If you run the command *ls -l* it esentially lists all the people that have access to your files and the size of the file and the last modified date**
![ls-l](https://user-images.githubusercontent.com/97692945/149409849-e3c88022-2ba2-46e6-bc39-d635ec5310f0.png)

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
![Creatingafile](https://user-images.githubusercontent.com/97692945/149411830-a22b48fc-ba8f-4391-b94c-8d200d50ace3.jpg)
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
![scp](https://user-images.githubusercontent.com/97692945/149413575-ac59cd32-7b59-40ac-8a49-45fc360aae48.png)


## Setting an SSH Key
*We will now learn how to setup SSH Keys in-order for us to allow simple and quick access to files on the server and on our client. It will make our lives a lot easier by eliminating the use of continuously typing out our password when copying files over or retrieving them*

**Using the command `ssh-keygen` we can generate a private and public key on our client that we can use to easily connect to the server** \
**If we are on Windows we use the command `ssh-add C:\Users\<username>/.ssh/id.rsa` in order to connect us to the server**
![ssh-keygeb](https://user-images.githubusercontent.com/97692945/149467276-fa067998-58aa-40d7-87e1-efd393081b45.png)
