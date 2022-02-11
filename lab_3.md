# **Lab 3 Report**
## 1. *SSH Config File*
> First I navigated to my .ssh folder in my local computer. As seen in the image below I navigate to my users, main user (mine is crist), then found the .ssh folder and opened it. From there I created a textfile and named it config (got rid of the .txt mod).
>
>
> ![File_image](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_3_images/Lab3_1.png?raw=true)
>
> I then added the text below with my added info to the file saved the changes (with ctr + s).
> ```
> Host ieng6
>    HostName ieng6.ucsd.edu
>    User cs15lwi22zzz (use your username)
> ```
>
> ![File_Enards](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_3_images/Lab3_2.png?raw=true)
>
> After creating the above file I ran the command `ssh ieng6` and was able to sign in very quickly to my ssh, as demonstrated below. 
> 
> ![the_demo_stration](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_3_images/Lab3_3.png?raw=true)
## 2. *SSH with Alias*
> Now the changing of an alias is actually rather simple, all one must do is go back to the config file and change the ieng6 text next to host to whatever you want it to be. Obviously since this is a change to save time the new name should be short and easy to type. 
> ![my_new_online_aliass](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_3_images/Lab3_4.png?raw=true)
>
> Then after making and saving said change I demonstrate loging into my SSH with my new stylish alias.
>
> ![new_cool_al-booty-identification](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_3_images/Lab3_6.png?raw=true)
>
## 3. *SCP with Alias*
>