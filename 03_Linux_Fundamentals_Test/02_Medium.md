# Medium Linux Questions

### 01 Basic Commands

1. How do you navigate to the root directory from the current working directory?
2. What is the difference between `ls` and `ls -l`?
3. How do you create a new file without using a text editor?
4. Which command is used to view the first 10 lines of a file, and how do you change the number of lines displayed?
5. What is the difference between `more` and `less` commands?
6. How do you display all files in a directory, including hidden ones, sorted by modification time?
7. How do you copy multiple files to a directory?
8. Which command allows you to replace all occurrences of a character in a file with another character?
9. How can you count the number of lines, words, and characters in a file?
10. How do you find the location of a command’s executable file?
11. Which command helps you find files by name in the current directory and its subdirectories?
12. What is the difference between `grep` and `find` commands?
13. How do you display only unique lines from a file?
14. What command can you use to compare two files and highlight the differences?
15. How do you sort the lines of a file in reverse order?
16. Which command allows you to display specific columns from a file?
17. How can you combine the output of two files line by line?
18. What is the purpose of the `ln` command, and how do you create a symbolic link?
19. How do you permanently delete a directory and all its contents?
20. How can you search for a specific pattern in all `.txt` files within a directory?

### 02 File Permissions

6. How do you recursively change permissions for all files in a directory?
7. What does the sticky bit do, and how do you set it on a directory?
8. How can you set default permissions for newly created files using `umask`?
9. What command is used to change both the owner and group of a file at once?
10. How do you remove execute permission for the group and others from a directory?

### 03 Users and Groups

11. What is the difference between `useradd` and `adduser` commands?
12. How do you delete a user along with their home directory?
13. Which command is used to lock a user account?
14. How can you change the primary group of a user?
15. What is the purpose of the `/etc/group` file?

### 04 Process Management

16. How do you display the parent process ID (PPID) of a process?
17. Which command is used to schedule a job to run at a specific time?
18. What is the difference between `kill` and `killall` commands?
19. How do you identify and kill processes consuming the most CPU resources?
20. How can you view the environmental variables of a specific process?

---

## Answers

### 01 Basic Commands

1. `cd /`
2. `ls` lists files and directories, while `ls -l` provides detailed information such as permissions, owner, and size.
3. `touch <filename>`
4. `head -n <number> <file>` displays the first `n` lines.
5. `more` allows forward navigation only, while `less` supports both forward and backward navigation.
6. `ls -a -lt`
7. `cp <file1> <file2> <destination_directory>`
8. `tr 'old_char' 'new_char' < input_file > output_file`
9. `wc <file>`
10. `which <command>`
11. `find . -name <filename>`
12. `grep` searches for patterns in file contents, while `find` locates files and directories by name.
13. `uniq <file>`
14. `diff <file1> <file2>`
15. `sort -r <file>`
16. `cut -d '<delimiter>' -f <fields> <file>`
17. `paste <file1> <file2>`
18. `ln -s <target> <link_name>`
19. `rm -rf <directory>`
20. `grep '<pattern>' *.txt`

### 02 File Permissions

6. `chmod -R <permissions> <directory>`
7. The sticky bit ensures only the owner can delete files in a directory. Set it with `chmod +t <directory>`.
8. `umask <value>`
9. `chown <user>:<group> <file>`
10. `chmod go-x <directory>`

### 03 Users and Groups

11. `useradd` is a low-level utility; `adduser` is more user-friendly.
12. `userdel -r <username>`
13. `passwd -l <username>`
14. `usermod -g <group> <username>`
15. It defines groups and their members on the system.

### 04 Process Management

16. `ps -o ppid= -p <PID>`
17. `at <time>`
18. `kill` targets a specific PID, while `killall` targets processes by name.
19. Use `top` or `htop` to identify and `kill <PID>` to terminate.
20. `cat /proc/<PID>/environ`
