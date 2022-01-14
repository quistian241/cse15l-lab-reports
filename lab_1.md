# **Lab 1 Report**
## 1. *Downloding Stuff* 

 [Download VSCode here.](https://code.visualstudio.com/) After downloding the app should look like this when opened:

![VSCode](https://github.com/quistian241/cse15l-lab-reports/blob/main/VSCode_ScreenShot.png?raw=true)

Make sure that OpenSSH is installed ([Windows_Only](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)). 

From there you can look up your course-specific account for the class here: 

[Class_Account_Link](https://sdacs.ucsd.edu/~icc/index.php)

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