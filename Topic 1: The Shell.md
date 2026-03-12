# What does the -l flag to ls do? Run ls -l / and examine the output. What do the first 10 characters of each line mean? (Hint: man ls)

* -l是long listing format
* 前10碼是file mode
* 第1碼(d/-/l)代表directory file link
* 後9碼是三個組別(User/Group/Other)的讀寫執行(rwx)

範例output
```
mix060514@TWTPED2012044B:~/pj/text2sql$ ll
total 776
drwxr-xr-x 11 mix060514 mix060514   4096 Feb  6 09:30 ./
drwxr-xr-x  3 mix060514 mix060514   4096 Jan 30 15:18 ../
-rw-r--r--  1 mix060514 mix060514     52 Feb  2 10:24 .dockerignore
drwxr-xr-x  8 mix060514 mix060514   4096 Feb 10 17:02 .git/
-rw-r--r--  1 mix060514 mix060514    149 Feb  2 10:24 .gitignore
mix060514@TWTPED2012044B:~/pj/text2sql$ ll /
total 2292
drwxr-xr-x  22 root root    4096 Feb 25 14:34 ./
drwxr-xr-x  22 root root    4096 Feb 25 14:34 ../
lrwxrwxrwx   1 root root       7 Apr 22  2024 bin -> usr/bin/
drwxr-xr-x   2 root root    4096 Feb 26  2024 bin.usr-is-merged/
drwxr-xr-x   2 root root    4096 Apr 22  2024 boot/
```
# In the command find ~/Downloads -type f -name "*.zip" -mtime +30, the *.zip is a “glob”. What is a glob? Create a test directory with some files and experiment with patterns like ls *.txt, ls file?.txt, and ls {a,b,c}.txt. See Pattern Matching in the Bash manual.

# What’s the difference between 'single quotes', "double quotes", and $'ANSI quotes'? Write a command that echoes a string containing a literal $, a !, and a newline character. See Quoting.

# The shell has three standard streams: stdin (0), stdout (1), and stderr (2). Run ls /nonexistent /tmp and redirect stdout to one file and stderr to another. How would you redirect both to the same file? See Redirections.

# $? holds the exit status of the last command (0 = success). && runs the next command only if the previous succeeded; || runs it only if the previous failed. Write a one-liner that creates /tmp/mydir only if it doesn’t already exist. See Exit Status.

# Why does cd have to be built into the shell itself rather than a standalone program? (Hint: think about what a child process can and cannot affect in its parent.)

# Write a script that takes a filename as an argument ($1) and checks whether the file exists using test -f or [ -f ... ]. It should print different messages depending on whether the file exists. See Bash Conditional Expressions.

# Save the script from the previous exercise to a file (e.g., check.sh). Try running it with ./check.sh somefile. What happens? Now run chmod +x check.sh and try again. Why is this step necessary? (Hint: look at ls -l check.sh before and after the chmod.)

# What happens if you add -x to the set flags in a script? Try it with a simple script and observe the output. See The Set Builtin.

# Write a command that copies a file to a backup with today’s date in the filename (e.g., notes.txt → notes_2026-01-12.txt). (Hint: $(date +%Y-%m-%d)). See Command Substitution.

# Modify the flaky test script from the lecture to accept the test command as an argument instead of hardcoding cargo test my_test. (Hint: $1 or $@). See Special Parameters.

# Use pipes to find the 5 most common file extensions in your home directory. (Hint: combine find, grep or sed or awk, sort, uniq -c, and head.)

# xargs converts lines from stdin into command arguments. Use find and xargs together (not find -exec) to find all .sh files in a directory and count the lines in each with wc -l. Bonus: make it handle filenames with spaces. (Hint: -print0 and -0). See man xargs.

# Use curl to fetch the HTML of the course website (https://missing.csail.mit.edu/) and pipe it to grep to count how many lectures are listed. (Hint: look for a pattern that appears once per lecture; use curl -s to silence the progress output.)

# jq is a powerful tool for processing JSON data. Fetch the sample data at https://microsoftedge.github.io/Demos/json-dummy-data/64KB.json with curl and use jq to extract just the names of people whose version is greater than 6. (Hint: pipe to jq . first to see the structure; then try jq '.[] | select(...) | .name')

# awk can filter lines based on column values and manipulate output. For example, awk '$3 ~ /pattern/ {$4=""; print}' prints only lines where the third column matches pattern, while omitting the fourth column. Write an awk command that prints only lines where the second column is greater than 100, and swaps the first and third columns. Test with: printf 'a 50 x\nb 150 y\nc 200 z\n'

# Dissect the SSH log pipeline from the lecture: what does each step do? Then build something similar to find your most-used shell commands from ~/.bash_history (or ~/.zsh_history).