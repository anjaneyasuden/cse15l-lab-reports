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

**If you run the command *cd* it changes the directory your currently in allows you to enter a certain directory**
