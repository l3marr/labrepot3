# Alternative uses and options for the `find` command
* All of these uses and options for `find` were found through ChatGPT with the prompt "what are some uses for the find command". 

## 1.) Search for files by extention using `-name`
> You can use the `-name` option in conjunction with `find` to locate all files that meet a specific criteria 
* In this case, we an use the `-name` option and have it search for all files ending in ".txt":
Upon running ` find stringsearch-data -name "*.txt"`: 
* This option is useful because it allows you to search for files based on the name of the file


> stringsearch-data/technical/biomed/1471-2350-3-1.txt
stringsearch-data/technical/biomed/1471-2350-3-12.txt
stringsearch-data/technical/biomed/1471-2350-3-7.txt
stringsearch-data/technical/biomed/1471-2350-3-9.txt
stringsearch-data/technical/biomed/1471-2350-4-2.txt
stringsearch-data/technical/biomed/1471-2350-4-3.txt
stringsearch-data/technical/biomed/1471-2350-4-4.txt
stringsearch-data/technical/biomed/1471-2350-4-6.txt
stringsearch-data/technical/biomed/1471-2369-3-1.txt
stringsearch-data/technical/biomed/1471-2369-3-10.txt
stringsearch-data/technical/biomed/1471-2369-3-6.txt
(and so on..) 

You can refine the search by adding more to the -name command:
Ex: look for all files that end in the number 1`:

`find stringsearch-data -name "*1.txt"`

> stringsearch-data/technical/911report/chapter-1.txt
stringsearch-data/technical/911report/chapter-11.txt
stringsearch-data/technical/911report/chapter-13.1.txt
stringsearch-data/technical/biomed/1468-6708-3-1.txt
stringsearch-data/technical/biomed/1471-2091-2-11.txt
stringsearch-data/technical/biomed/1471-2091-3-31.txt
stringsearch-data/technical/biomed/1471-2091-4-1.txt
stringsearch-data/technical/biomed/1471-2105-1-1.txt

(and so on...)

## 2.) Find files based on size
* The `-size` option is useful because it allows you to search for files based on specific size criteria
> You can use the `-size` option to search for files based on size criteria 
* Ex: Using `find stringsearch-data -size +1k`
* This command will find all files with a size of 1kb or greater 
> stringsearch-data/technical/biomed/1471-2334-2-5.txt
stringsearch-data/technical/biomed/1471-2334-2-6.txt
stringsearch-data/technical/biomed/1471-2334-2-7.txt
stringsearch-data/technical/biomed/1471-2334-3-10.txt
stringsearch-data/technical/biomed/1471-2334-3-11.txt
stringsearch-data/technical/biomed/1471-2334-3-12.txt
stringsearch-data/technical/biomed/1471-2334-3-13.txt
stringsearch-data/technical/biomed/1471-2334-3-15.txt
stringsearch-data/technical/biomed/1471-2334-3-9.txt
(and so on...)

* As we can see, there are many files that meet this criteria 

>We can be more specific by changing the -size criteria:
* `find stringsearch-data -size +100k` 
* This command will find all files with a size of 100 kilobytes or larger
> stringsearch-data/technical/911report/chapter-1.txt
stringsearch-data/technical/911report/chapter-12.txt
stringsearch-data/technical/911report/chapter-13.2.txt
stringsearch-data/technical/911report/chapter-13.3.txt
stringsearch-data/technical/911report/chapter-13.4.txt
stringsearch-data/technical/911report/chapter-13.5.txt
stringsearch-data/technical/911report/chapter-3.txt
stringsearch-data/technical/911report/chapter-6.txt
stringsearch-data/technical/911report/chapter-7.txt
stringsearch-data/technical/911report/chapter-9.txt
stringsearch-data/technical/biomed/1471-2105-3-2.txt
stringsearch-data/technical/government/About_LSC/State_Planning_Report.txt
(and so on..) 

## 3). Using the -type option 
* The `-type` option is useful because it allows you to search for files based on its type for example, a txt file.
> We can search based on type (Ex: file or directory) using the `type` option 
* `find stringsearch-data -type f` 

> stringsearch-data/technical/biomed/1471-2369-3-9.txt
stringsearch-data/technical/biomed/1471-2369-4-1.txt
stringsearch-data/technical/biomed/1471-2369-4-5.txt
stringsearch-data/technical/biomed/1471-2377-1-2.txt
stringsearch-data/technical/biomed/1471-2377-2-4.txt
stringsearch-data/technical/biomed/1471-2377-2-6.txt
(and so on..)

> We can also use `-type` to search for directories which we will soon notice are much less abundant than files 
* `find stringsearch-data -type d`
> stringsearch-data/.git/branches
stringsearch-data/.git/info
stringsearch-data/.git/hooks
stringsearch-data/technical/911report
stringsearch-data/technical/biomed
stringsearch-data/technical/government
stringsearch-data/technical/government/About_LSC
stringsearch-data/technical/government/Alcohol_Problems
stringsearch-data/technical/government/Env_Prot_Agen

(some examples of directories) 

## 4). Using the -amin option 
* This option is useful because it can be used to find files that have been recently opened.
> We can use the `-amin` option to find files based on the time that they were last accessed

> This will find all files that have been accessed 10 minutes ago or later:
* `find stringsearch-data -amin +10`

> stringsearch-data/technical/biomed/1471-2407-2-12.txt
stringsearch-data/technical/biomed/1471-2407-2-15.txt
stringsearch-data/technical/biomed/1471-2407-2-16.txt
stringsearch-data/technical/biomed/1471-2407-2-17.txt
stringsearch-data/technical/biomed/1471-2407-2-18.txt
stringsearch-data/technical/biomed/1471-2407-2-19.txt
stringsearch-data/technical/biomed/1471-2407-2-22.txt
stringsearch-data/technical/biomed/1471-2407-2-23.txt
stringsearch-data/technical/biomed/1471-2407-2-3.txt
(and so on) 

> We can also use the `-amin` option to look for files that have been accessed n minutes ago or less
* `find stringsearch-data -amin -1` 

> Nothing is returned because none of the files or directories have been accessed in a minute or less ago

