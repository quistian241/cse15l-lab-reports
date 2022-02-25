# **Lab 4 Report**
## 1. *Expected Results*
> Here's a link to [my repository](https://github.com/quistian241/markdown-parse) and a link to [my copy of the tester repo](https://github.com/quistian241/markdown-parse-two-main).
> The expected results for each test is one link for `Snippet 1`, three valid links for `Snippet 2`  (not including b.com), and only one valid link in `Snippet 3`. 
> 1. ![test-one](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_4.png?raw=true)
> 2. ![test-two](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_5.png?raw=true)
> 3. ![test-three](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_6.png?raw=true)
>
> Based on this info we made our testers to accomidate and expect outputs matching this info: ![the-testers-for-snippets](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_3.png?raw=true)
>

## 2. *My Implementation Results*
> For `my repository` the results of running the tests was that of every test failing. Now while each tester for the three snippets failed there were no exceptions thrown, we only didn't get the expected outputs we wanted for each snippet. To be honest the code is in no way checking for any of the edgecases brought up in the Snippets. ![The_Image](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_1.png?raw=true)
>
> Here are the extended jdb results of my stacktrace (note the line numbers have changed for MarkdownParseTest but that's only because I added coments that moved the testers):
> ![MySnip1](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_MySnip1.png?raw=true) 
>
> ![MySnip2](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_MySnip2.png?raw=true) 
>
> ![MySnip3](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_MySnip3.png?raw=true) 
>

## 3. *Reviewed Code Results*
> For `the reviewed implementation` the results were a bit more interesting. Snippet 1 yeilded an assertion error since the code picked up three nonlinks on top of the correct only link. Then we actually get a pass for Snippet 2. Finally theres a StringIndexOutOfBoundsException thrown in the tester for Snippet 3 which we can see is caused by our code on line 17 of MarkdownParse. Condensed image: ![Le_Emagee](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_2.png?raw=true)
> 
> Snippet 1: ![AnoSnip1](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_AnoSnip1.png?raw=true)
>
> Snippet 3: ![AnoSnip3](https://github.com/quistian241/cse15l-lab-reports/blob/main/lab_4_images/Lab4_AnoSnip2.png?raw=true)
>

## 4. *Snippet 1 Solution?*
> I think the change could be easy as all you'd need to do is check for back ticks on the line and then see if they either are around the whole link (making it not a link), one in brackets and another outside, and if there's none or no pair. So basically find the backticks(if they even occur) and compare their positions to the entire link or inside of the backets (a backtick in parantehsies is absorbed into the link). I think this could probaly be done with a singular helper method (at least for singe backticks on the same line).
>

## 5. *Snippet 2 Solution?*
> Adding the helper method from the tester repo we worked on to my personal repo is this most efficient solution for Snippet 2. This is because my code picked up every link correctly minus the link with the nested parentheses (the entire purpose of said helper method).

## 6. *Snippet 3 Solution?*
> As for this code I'm not entirely sure how to handle it since it involves parentheses on \n's that may or may not have a closed parentheses. The limit for new lines is one \n above or below the link, spaces around (but not in) link allowed, and it also apply's to brackets. Just focusing on parentheses a possible solution is a mix of checking \n's one above and below the link (which we're also applying the Snip() command to so as to not include any spaces surrounding the actual link).
