# **Lab 2 Report**
## 1. *Fixing an Infinite Loop*
> ![Code_Change_Diff1](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode2.png?raw=true) 
> ## Test file for the failure-inducing input: [test-file2.md](https://github.com/quistian241/markdown-parse/blob/fc7f7bdd4a667f143947a60013e8ec83f827b395/otherTestCases/test-file2.md)
> ![Symptom_of_Fail1](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode2_before.png?raw=true)
>
> The symptom shown in the above image is that of an infinite loop. The symptom is caused by the existance of text that isn't a link, and the bug is the lack of a break method when nonlink text pops up. We fix the infinite loop by adding in if-break statement where if there is no next open bracket found on the file then the program stops along with a change to the while condition to avoid a index error. 
> ## The output after change is used:
> ![Symptom_of_Fixed1](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode2_after.png?raw=true)

***

## 2. *Reject extra space between ](*
> ![Code_Change_Diff2](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode3.png?raw=true) 
> ## Test file for the failure-inducing input: [test-file-group.md](https://github.com/quistian241/markdown-parse/blob/fc7f7bdd4a667f143947a60013e8ec83f827b395/otherTestCases/test-file-group.md)
> ![Symptom_of_Fail2](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode3_before.png?raw=true)
> 
> The symptom shown in the above image is that of a wrong link included. The code should only identify links as such if a closed bracket **]** is followed immediately by an open parenthesis **(**. That lack of idenifying if the **](** is happening creates the symptom of including the nonlink in the links array. This promblem is fixed my our addition of a checker to see if the index after the found end bracket is an open parenthesis. 
> ## The output after change is used:
>![Symptom_of_Fixed2](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode3_after.png?raw=true)

***

## 3. *Fix Lone [*
> ![Code_Change_Diff2](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode4.png?raw=true) 
> ## Test file for the failure-inducing input: [test-file7.md](https://github.com/quistian241/markdown-parse/blob/fc7f7bdd4a667f143947a60013e8ec83f827b395/otherTestCases/test-file7.md) and [test-file8.md](https://github.com/quistian241/markdown-parse/blob/main/otherTestCases/test-file8.md)
> ![Symptom_of_Fail2](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode4_before.png?raw=true)
> 
> The symptom in the above image is that of an index being out of bounds. Looking at the code through the exception text I saw that the index out of bound happened at the start of an internal while loop, and was also caused by a closed bracket **]** not existing on the same line as an open bracket **[**. In order to fix this bug that caused and exception to occur I put an if-break statement that checked to see if the index of the closed bracket was -1.
> ## The output after change is used:
>![Symptom_of_Fixed2](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode4_after.png?raw=true)

***
