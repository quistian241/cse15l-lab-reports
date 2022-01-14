# **Lab 1 Report**
## 1. *Downloding Stuff* 

 [Download VSCode here.](https://code.visualstudio.com/) After downloding the app should look like this when opened:

![VSCode](https://github.com/quistian241/cse15l-lab-reports/blob/main/VSCode_ScreenShot.png?raw=true)

Make sure that OpenSSH is installed ([Windows_Only](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)). 

From there you can look up your course-specific account for the class here: 

[Class_Account_Link](https://sdacs.ucsd.edu/~icc/index.php)

## 2. *Remotely Connecting*

Once you reset your password for the course specific acount head over to VSCode and open a terminal. Use this command but replace the *zz* with the letters in your course specific acount.

`$ ssh cs15lwi22zz@ieng6.ucsd.edu`

A message will most likely pop-up due to this being the first time you've connected to the server that looks like this.
```
⤇ ssh cs15lwi22zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```
Just type `yes` and press enter, then type in your freshly reset password to finish signing in. Then something like this should pop-up:
![Signing_In](https://github.com/quistian241/cse15l-lab-reports/blob/main/VSCode1.png?raw=true)

The terminal has now connected your computer to another one in the CSE basement, and any comands run will do so using the remote computer. The local computer (yours) will now be called the **client** and the remote basement computer the **server**.

## 3. *Run Some Commands*

General commands: `cd`, `ls`, `pwd`, `mkdir`, and `cp`

Specific useful commands to try:

- `cd ~`
- `cd`
- `ls -lat`
- `ls -a`
- `ls <directory>` where `<directory>` is `/home/linux/ieng6/cs15lwi22/cs15lwi22abc`, where the `abc` is one of the other group members’ username
- `cp /home/linux/ieng6/cs15lwi22/public/hello.txt ~/`
- `cat /home/linux/ieng6/cs15lwi22/public/hello.txt`

Running these commands should yeild results similar looking to this:

![Command_EX](https://github.com/quistian241/cse15l-lab-reports/blob/main/VSCode2.png?raw=true)

**To Log Out:**
- Ctrl-D
- Run the command `exit`
 

## 4. *Moving Files over SSH with scp*

In order to test the `scp` command, which copy's/moves files over to the **server**, you must first create a file on your computer called `WhereAmI.java`. This can be done in VSCode and the file must contain the following contents:
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

After creating the file run the commands `javac` and `java` on the **client** (your computer). Then in this same directory run this command (once again replacing the *zz* with your acounts letters):

`scp WhereAmI.java cs15lwi22zz@ieng6.ucsd.edu:~/`

You should then input your password to sign in just like with the `ssh`. Log back into the ssh and use `ls` to hopefully see the file in the directory. 

![The_Before_LS](https://github.com/quistian241/cse15l-lab-reports/blob/main/VSCode6.png?raw=true)

![LS_See_File?](https://github.com/quistian241/cse15l-lab-reports/blob/main/VSCode3.png?raw=true)

Stay on the **server** and run the `javac` and `java` commands then exit.

## 5. *SSH Keys*

The act of logging in everytime you want to update or move anything into this directory is tetious, so one thing you could create to make it more convinient is a thing called an *ssh key*. Follow the below setup to roughly match what you should do:

```
# on client (your computer)
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/joe/.ssh/id_rsa): /Users/joe/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/joe/.ssh/id_rsa.
Your public key has been saved in /Users/joe/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 joe@Joes-Mac-mini.local
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|       . . + .   |
|      . . B o .  |
|     . . B * +.. |
|      o S = *.B. |
|       = = O.*.*+|
|        + * *.BE+|
|           +.+.o |
|             ..  |
+----[SHA256]-----+
```

If you’re on Windows, follow the extra ssh-add steps here: [Extra_Steps](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)

This created both a private and public key but the only important one for us is the public one. **Copy the public key** to the .ssh directory of your user acount on the **server** just similarly to the below text:

```
$ ssh cs15lwi22zz@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
$ <logout>
# back on client
$ scp /Users/joe/.ssh/id_rsa.pub cs15lwi22@ieng6.ucsd.edu:~/.ssh/authorized_keys
# You use your username and the path you saw in the command above
```
## **or** 

![The_same_thing_but_I_did_it_on_the_terminal!](https://github.com/quistian241/cse15l-lab-reports/blob/main/VSCode4.png?raw=true)

After this is done you should be able to `ssh` or `scp` without having to enter your password. 

## 6. *Making Remote Running Even More Pleasant*

- Write commands in quotation marks to directly run them on the remote **server**:

`$ ssh cs15lwi22@ieng6.ucsd.edu "ls"`

- And you can use semicolons to run multiple command lines (for most terminals):

`$ cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI`

- You can use the up-arrow on your keyboard to reuse any previously used commands

What all these combined look like in practice:

![The_Code_In_Practice](https://github.com/quistian241/cse15l-lab-reports/blob/main/VSCode5.png?raw=true)
