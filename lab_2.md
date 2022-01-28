# **Lab 2 Report**
## 1. *Fixing an Infinite Loop*
> ![Code_Change_Diff1](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode2.png?raw=true) 
> ## Test file for the failure-inducing input: [Link](https://github.com/quistian241/markdown-parse/blob/main/test-file2.md)
> ![Symptom_of_Fail1](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode2_before.png?raw=true)
>
> The symptom shown inak method when such an example occurs. We fix this bug by  the above image is that of an infinite loop. The symptom is caused by the existance of text that isn't a link, and the bug is the lack of a break method when nonlink text pops up. We fix the infinite loop by adding in if-break statement where if there is no next open bracket found on the file then the program stops along with a change to the while condition to avoid a index error. 
> ![Symptom_of_Fix1](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode2_after.png?raw=true)
---

## 2 *Reject extra space between ](*
> ![Code_Change_Diff2](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode3.png?raw=true) 
> ## Test file for the failure-inducing input: [Link](https://github.com/quistian241/markdown-parse/blob/main/test-file-group.md)
> ![Symptom_of_Fail2](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode3_before.png?raw=true)
>