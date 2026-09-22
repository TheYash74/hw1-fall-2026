# MSE 121, Fall 2026, HW1

**MSE 121 - Introduction to Computer Programming**  
**University of Waterloo, Fall 2026**  
**Instructor: Mark Smucker**  
**Assigned: September 16, 2026**

---

**Homework Due:** September 23, 2026. You will not submit your
answers; this date only indicates when the solutions will be
released.

**Instructions:** You may answer the following questions by hand or
using GitHub Codespaces.

For most questions, we will ask you to write a command or series of commands
to compute or find an answer to the question.  The goal of the homework is
to give you practice solving these sorts of problems.  For some questions, we will also
tell you the answer (not the commands) as a way to check your work as you progress, but
not all questions have this helpful aid.  Giving an answer to check your work
will not be possible on the quiz, for you will write your commands/pipelines without
access to a computer to check if they work.

**Getting Started:** Access the Homework 1 GitHub repository at the following URL: https://github.com/UWaterloo-MSE-121/hw1-fall-2026

In the top-right corner of the repository, click on "Fork" and then
"Create Fork". In the configuration window:

**Owner:** Ensure your personal GitHub username is selected from the dropdown, not the organization or another team.

**Repository name:** Leave this as the default name.

**Copy the main branch only:** Keep this box checked.

Click the green "Create fork" button. GitHub will take a few seconds
to generate your personal copy. Once redirected to your new
repository, click the green "Code" button, then "Codespaces", then
"Create codespace on main". This will start up an environment in the
cloud where you will be able to write code and save your progress.

You can always reopen this codespace at a later time via the green "Code" button on the repository.

## Sample Folder Structure

The following questions will allow you to understand the basic commands for navigating directories. These questions should be answered without running any commands.

Some of the questions below pertain to the following directory tree:

```sh
/workspaces/
 └── hw1-username/
     │
     ├── projects/
     │   ├── project1/
     │   │   ├── process.py
     │   │   ├── summary.txt
     │   │   └── data/
     │   │       ├── raw_data.txt
     │   │       └── processed_data.csv
     │   └── project2/
     │       ├── summary.txt
     │       └── notes/
     │           └── meeting-jan-01-2020.txt
     │
     ├── downloads/
     │   └── joke.jpg
     │
     ├── .gitignore
     ├── junkme.txt
     └── zipper.py
```

**Question 1.** If you wanted to read the manual page for the `ls` command, what should you type at the command prompt of a bash shell?
man ls

**Question 2.** If your current working directory is `hw1-username`, what files does running the command `ls` show?
projects, downloads, junkme.txt, zipper.py

**Question 3.** If your current working directory is `hw1-username`, what option do you add to `ls` to have the file listing include the file `.gitignore`?
-a

**Question 4.** If your current working directory is `hw1-username`, how can you change your working directory to `/workspaces/hw1-username/projects/project1/data` using `cd` and a relative pathname that starts with `projects`?
cd ./projects/project1/data

**Question 5.** If your current working directory is `data`, what is the easiest way to change to its parent directory, and what is its parent directory?
cd ..
/workspaces/hw1-username/projects/project1

**Question 6.** What is the absolute or full pathname to the `meeting-jan-01-2020.txt` file?
/workspaces/hw1-username/projects/project2/notes/meeting-jan-01-2020.txt

**Question 7.** If your working directory was the `notes` directory, and you ran `less Meeting-Jan-01-2020.txt` what would you expect to happen? Explain why.


**Question 8.** You do not know where you are in the directory tree. What command do you use to see what your current working directory is?


**Question 9.** If your current working directory is the `notes` directory, where do you end up after entering `cd ../../..`?


**Question 10.** If your current working directory is the `project2` directory, what relative pathname can you use to `cd` to `project1`?


**Question 11.** If you are in `hw1-username`, give both a relative pathname to `junkme.txt` from `hw1-username` and the full path name for `junkme.txt`.


**Question 12.** At the command prompt, what key do you press to see your previously entered commands?


**Question 13.** You are in `hw1-username` and want to `cd` to the `projects` directory, and have typed `cd p` so far. What key do you press to perform filename completion and have the `cd p` autocomplete to `cd projects/` for you?


**Question 14.** What is the name of the `/` directory when we say it to people (we do not say "forward slash directory")?


## Folder Structure

The following questions will allow you to understand the folder structure of the various datasets. These questions should be answered by writing/using commands rather than by manually viewing the folders.

**Question 1.** You first `cd data` to go inside the directory.  You want to see everything and all the details.  What command do you run/execute?



**Question 2.** You then `cd mini-32m` to enter the `mini-32m`
directory.  You want to see the sizes of the files in your current
directory in a human readable format, e.g. you want to see 1.1M rather
than 1102171 bytes.  What command do you run?


**Question 3.** As is good practice for a data analyst, you decide to read the `README.md` in `mini-32m`.  What would be the preferred way to read the file inside the terminal, and what is a better way to read it all nicely formatted?



**Question 4.** What is the rating scale used in the `ratings.csv` file? (You just need to read the README.md file to find this information.)


## Dataset Basics: mini-32m

After reading `README.md` to learn about the `mini-32m data`, be sure to explore the data with tools like `head`, `tail`, and `less` to get a feel for it.


**Question 1.** You want to see what the `movies.csv` and `ratings.csv` files look like and decide to look at the first 10 lines of each file.  What commands do you use? 



**Question 2.** First, write a single command to only show the last line of the `ratings.csv` file.  Next, using any reasonable means, what is the movie title for this movie?  You should find that the movie is "Corpse Bride (2005)".  


**Question 3.** Write a short pipeline of commands to determine the number of movies in the `movies.csv` file. Hint: the first line of the dataset contains the column headers.  When you get it right, your pipeline will output 23144 as the answer.


**Question 4.** Write a single pipeline of commands to determine the number of unique users in the `ratings.csv` file.  When correct, your pipeline should output `982`.


## Dataset Basics: bike-share-toronto

The following questions will allow you to understand basic information
about the `bike-share-toronto` dataset. These questions should be
answered by writing/using commands rather than by manually viewing the
folders.

You should first manually read the corresponding `README.md` file for
the `bike-share-toronto` dataset to learn about its data, and then use
simple tools like `head`, `tail`, and `less` to visually inspect the
data before beginning.  You should first `cd` to the
`data/bike-share-toronto` directory so that your answers match
up with ours. 


**Question 1.** The `user_type_code` column of the `trips.csv` file represents whether a trip was taken by a Casual (C) or Member (M) user.  Write a pipeline to output the number of casual and member trips.  In other words, how many trips did casual users make, and how many trips did members make? Each row/line in the data file is a separate trip.  You may use only these tools, but not all are needed: `cut`, `awk`, `tail`, `uniq -c`, `sort`, and `cat`.  You may use whatever options you want on any of these commands.

Tutorial on `uniq -c`:

The `uniq` command takes **already sorted input** and returns the unique lines of input, i.e. it removes
duplicate lines.  You must sort the input to uniq.

`uniq -c` also takes sorted input and prepends (prefixes) to each line the number of times
that line was in the file.

For example, if the input was:
```
apple
apple
banana
banana
banana
cherry
```
The output with `uniq -c` would be:
```
     2 apple
     3 banana
     1 cherry
```
So, you may get some leading spaces, then the count of occurrences, a space, and then what the line was.

For this problem, when you have a correct pipeline, it will output:
```sh
158888 C
536836 M
```
Telling us that there were 158,888 casual trips, and 536,836 member trips.


**Question 2.** Write a pipeline that starts with `tail +2 trips.csv` and pipes its output to `awk` that then pipes its output to `wc -l` to determine how many trips were over 1 hour long using the `trips.csv` data.  The correct answer is `13499` trips.



**Question 3.** Using the `duration_seconds` column of the `trips.csv` file, write a short pipeline of commands to determine the longest trip that was taken.  Your pipeline should output the number `1134776` when correct.  


## Dataset Basics: ferry-ticket-counts

The following questions will allow you to understand basic information about the `ferry-ticket-counts` dataset. These questions should be answered by writing/using commands rather than by manually viewing the folders.  First, `cd` to this dataset's directory.

You should first manually read the corresponding `README.md` file for the `ferry-ticket-counts` dataset to learn about its data, and then use simple tools like `head`, `tail`, and `less` to visually inspect the data before beginning.


**Question 1.** Write a single command to determine how many lines are in the `ferry-ticket-counts.csv` file.



**Question 2.** Write a pipeline of commands to determine the number of unique calendar days present in the `ferry-ticket-counts.csv` file. Hint: start with `cut` to only extract the timestamps.  A correct pipeline will output `4126`.


## Dataset Questions: mini-32m

To answer these questions, `cd` to the mini-32m dataset directory.

**Question 1.** When processing the `movies.csv` file, can ',' (a
comma) be used as the column separator by unix commands like cut, awk,
and sort? Write a pipeline of commands to prove whether this is true
or false using `awk`. Hint: first assume it is true, then see if every
line in the file would be separated into 3 columns. (Super double
hint: This was explained in lecture.)


**Question 2.** Write a pipeline of commands to determine the distribution of ratings in the `ratings.csv` file. In other words, how many of the ratings in the file are 5.0 stars, 4.5 stars, ..., 0.5 stars?  

A correct pipeline will output:
```sh
   6152 0.5
   6427 1.0
   6666 1.5
  15650 2.0
  22408 2.5
  50440 3.0
  67187 3.5
  83808 4.0
  44729 4.5
  36770 5.0
```
and show us that the most common rating is 4.0 stars.


**Question 3.** Write a single pipeline of commands to determine which `userId` has rated the most movies, along with the number of ratings they have made.  For this problem, you will likely need to use the default field separator for sort, i.e. whitespace.  When you use sort without specifying the field separator, it defaults to whitespace, and the breaks between fields are defined to be between a non-blank character and a blank character, and thus any blanks at the start of the line are part of the first field.  When you sort numerically, numbers may include leading blanks without any issue, which is super handy for this problem.  Hint: you should numerically sort the output of `uniq -c` as part of your solution.

You should find that userId 95481 has rated 4113 movies.



**Question 4.** What is the title of the movie with the most ratings? Hint: First write a pipeline of commands to determine which `movieId` has the most ratings in `ratings.csv`, then write a single command to output the line of `movies.csv` for this movie given the movieId you find with your pipeline.


**Question 5.** What is the title of the movie that has the most 5.0 star ratings? Hint: First write a pipeline of commands starting with `awk` to determine which `movieId` has the most 5.0 ratings in `ratings.csv`, then write a single command to determine the movie title for this `movieId` in `movies.csv`.


## Dataset Questions: bike-share-toronto

The following questions will allow you to gain detailed information
about the `bike-share-toronto` dataset. These questions will need to
be answered by chaining multiple commands together.

**Question 1.** Write a single pipeline of commands to determine the
top 5 starting stations with the most trips.  Each data row is a trip.
Also, write another command to determine the station name that
corresponds to the busiest station.


**Question 2.** Write a pipeline of commands to determine the number of round trips made. That is, how many trips started and ended at the same station?


**Question 3.** Write a pipeline of commands to determine the number of trips that never ended. That is, how many trips are missing an `end_station_id` (i.e., the `end_station_id` is `""`)?


**Question 4.** Write a pipeline of commands to determine the number
of trips that started between January 15, 2024 and January 20, 2024
inclusive.  Hint: Because dates and times are always written like:
`"2024-01-01 00:00:08"`, i.e. in the format of `"YYYY-MM-DD HH:MM:SS"`, you
can safely make string comparisons.  For example, `"2024-01-01 00:00:08"` is less
than `"2024-01-02 00:01:29"` because we will compare
the strings character by character and when we get to the DD portion,
01 comes before 02 because 1 comes before 2.  Likewise, you could
compare any datetime in the format of `"YYYY-MM-DD HH:MM:SS"` to
`"2024-02-01"`
and check if it was less than `"2024-02-01"` to find all datetimes that occur
before the start of February 1, 2024 (you could also compare to `"2024-02-01 00:00:00"` to
do the same thing).


