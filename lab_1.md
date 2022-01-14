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

## 5. *SSH Keys*

## 6. *Making Remote Running Even More Pleasant*
