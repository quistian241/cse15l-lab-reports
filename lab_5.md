# **Lab 5 Report**
## 1. *How The Different Results Were Found*
>
> First I ran `bash script.sh > results.txt` inside both implementations of markdown-parse to create a file that had all the results of running a test on each file. 
> 
> Then compared those results using the command of `diff markdown-parse/results.txt markdown-parse-main-three/markdown-parse-main/results.txt`, where the first class path is for **my markdown-parse implementation** and the secound classpath is for **the provided one back in lab 9**. This command prints out all the differences line by line in each of our results.txt files. 
>
> One noteable change made to script.sh one that first prints out the file name and the test result on the same line. This change is one that allows you to identify not only the differences between the two files but know which .md file it coresponds to since they aren't always in order. 
>
> **The script.sh change:**
> ```
> for file in test-files/*.md;
> do
>   echo -n -e  "${file##*/}\t"
>   java MarkdownParse $file
> done
> ```

## 2. *First Test Discrepancy*
>  While there were multiple choices to choose from this first discrepancy comes from a difference in output on file '201.md'. 
> ![image-of-diff](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_5_images/Lab5_2.png?raw=true)
>
> As seen from there the provided implementation seems to find a link baz and mine doesn't. Taking the provided contents of file 201.md and running it through this   [CommonMark demo site](https://spec.commonmark.org/dingus/) we find that there should be no link found in this file, therefore the provided implementation contains a bug. Looking at the md-parse implementation it seems that there is no place where it checks that the end bracket `]` and the open paren `(` are right next to each other or not, so it included link baz despite it not being a vaild link. My md-parse code does have a check for `]` bing next to `(` so it does not include baz as a link. 
>
> **The contents of 201.md:** 
>```
>[foo]: <bar>(baz)
>
>[foo]
>```
> **Provided md-parse with no check for ](:**
> 
> ![the-image-baka](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_5_images/Lab5_3.png?raw=true)
>
> **Personal md-parse**
> ![personal-flex?]()
>

## 3. *Second Test Discrepancy*
> This next one is another bug where the provided implementation is incorrect. (not picking on the provided code these were just the easiest to explain)
> ![image-of-diff-two]()
>
> From the image we see that the my md-parse does not find a link and the provded md-parse says it does. However looking at the contents of 580.md it clear that the provided md-parse is incorrect. Looking at the text for 580.md below we see that since there's an exclamation point `!` right next to the open bracket `[` that it's an image not a link. And double checking on this [site](https://spec.commonmark.org/dingus/) we conform out suspicions (provided you add some text in the `[]` so something pops up). 
> ```
> ![](/url)
>
> ```