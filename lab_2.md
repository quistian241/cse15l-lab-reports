# **Lab 2 Report**
## 1. *Fixing an Infinite Loop*
> ![Code_Change_Diff1](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode2.png?raw=true) 
> ## Test file for the failure-inducing input: [Link](https://github.com/quistian241/markdown-parse/blob/main/test-file2.md)
> ![Symptom_of_Fail1](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_2_images/VSCode2_before.png?raw=true)
> The symptom shown in the above image is that of an infinite loop. The symptom is caused by the existance of text that isn't a link, and the bug is the lack of a break method when such an example occurs. 