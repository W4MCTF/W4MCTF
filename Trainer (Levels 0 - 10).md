Trainer (Levels 0 - 10) 

## Level 0 (10)

SSH to the linux trainer:

trainer.threatsims.com

username: level0 password: level0

After logging in to level0 you will be looking for the password to level1.

The flag is always for the level in the challenge name. You will find it by completing the previous level.

The password will be the login to level1

![level0-1.png](../_resources/0e70e74e1f24433ba8ab4f501b1376d1.png)

Use `cat` to read the "level1_password" text. 

![level0-password.png](../_resources/bbbab85d15e146caa26ff0f09ce1c118.png)

### FLAG: 4202c26842398c1d0772ed9eed195113

Use `su - level1` to move to the next level. 

* * *

## Level 1 (10)

![level1-1.png](../_resources/5dad9770feb34ef79f4abd3a70f47d78.png)

Use `ls -la` to see all the files in the directory. 

Find the folder named "some_directory", and use `cd some_directory` to enter the subdirectory. 

Use `ls -la` to see all the files in the "some_directory" folder. 

There are two files, one called "maybe" and one called "level2_password". The one labeled "level2_password" seems like the obvious solution, but it doesn't hurt to check them both. 

Here, the strings in both files match, so copy one of the strings and use it to log in to the level. 

![level1-2.png](../_resources/66e2e0f65b3a43ec85a95ed369d76750.png)


### FLAG: 943430e07fd566bc96aa05fca3c96e48

Use `su - level2` and the password to move on to the next level. 

* * *

## Level 2 (10)

![level2-1.png](../_resources/d7960893978248b7b8a9e8a9ca5dc7c7.png)

Use `ls -la` to see the contents of the home directory. 

![level2-2.png](../_resources/b0bf18210fa6492d94ac007c3b8715a6.png)

Use `cd dir` to move to the "dir" directory. 

![level2-3.png](../_resources/b0aa0b0d06374982873933df031e1bf4.png)

Use `ls -la` to view the folder contents. 

Use `cd another_dir` to move to the next subdirectory. 

![level2-4.png](../_resources/738075646c8d4aa5b0709d6834717335.png)

Enter `ls -la` again to list the contents. 

Use `cd another_another_dir` to move into yet another subdirectory. 

![level2-5.png](../_resources/47b76fa57fcb496c9111042c80392636.png)

Put in another `ls -la` command to see this directory's contents. 

![level2-6.png](../_resources/561b1807d35a45bf89a6ab43b3494285.png)

Change directory again, moving into "some_directory" this time. 

Once the directory has changed, list the contents. 

![level2-7.png](../_resources/ebbd40623a9744e1a0a79be2c07c90b0.png)

Finally! A password file! 

Use `cat` to read the file text. 

![level2-8.png](../_resources/f9ada8378ef7488aad95e911d143db6d.png)

### FLAG: 2cadca6148093c403d82396252b8c4db

Move to the next level with `su -level3`. 

* * *

## Level 3 (10)

![level3-1.png](../_resources/1b7ea2a3ecf144bc9384cf24f0d4620c.png)

Pay attention to the clue in this level's welcome message. 

Using the `ls` command only lists *some* files in a directory. However, using `ls -la` shows all files (even hidden files), their owner, permissions, and other properties. 

Definitely make using `ls -la` a habit for CTFs, even if working with Linux isn't an everyday thing. 

Use `ls -la` to see *all* of the files in this directory. 


![level3-2.png](../_resources/e7e75e04043040ac839b435d64b1a7c8.png)

Notice that there are files here with `.` in front of the file name. This means that the file is hidden, and wouldn't be visible using `ls` alone. These files are still `cat`-able, so use `cat .level4_password` to obtain the password to the next level. 

![level3-3.png](../_resources/a23e6feb74614e85a4f46e2d602f78a3.png)

### FLAG: 72f6af6b0005adb15fbc91e1b140115f

Use `su - level4` to continue. 

* * *

## Level 4 (10)


![level4-1.png](../_resources/ccaba883df5644debd0ae8873117d45f.png)


Like the previous level, this level uses hidden files and folders with `.` in front of the object name. 

Use the same technique as was used in Level 3 to locate and interact with hidden files and directories. 


![level4-2.png](../_resources/54fe100351444fb2ab9bff072bb98bf8.png)

![level4-3.png](../_resources/a66e8cf5be204eb3af5e913692ca40dc.png)

![level4-4.png](../_resources/bfc78bc1688a444c9c5cb4562716e0c9.png)


### FLAG: 7b6c2552940f47a27fbd729ae0e2893c

* * *

## Level 5 (10)

![level5-1.png](../_resources/1a481985c042445f845bab43e76061bf.png)

In this level, the password file is in the `/home` folder for the Level 6 user. For the previous challenges, the files were always located in a directory within the corresponding level's `/home` directory. Now, it's necessary to change directories to another user's `/home` to find progress to the next level. 

The `cd` command is used to change directories, and the folder location is already known, as the Linux filesystem is usually similar among distributions. 

Use `cd /home/level6` to change home directories. 

![level5-3.png](../_resources/e5938495392b4b1680e9831eeb949a18.png)

Note that this will not always be possible - it is possible for this challenge because of (intentionally) misconfigured object permissions. 

List the directory contents and look around for interesting files. 

![level5-4.png](../_resources/93592d7798384b8b83e6d66f2a618ab5.png)

The Level 6 user's home directory has a lot of files and folders in it!

Ignore the subdirectories for now and scroll to the bottom of the list. 

![level5-5.png](../_resources/7743b19de6e24772b859bac0cd149dc3.png)

Open the "level6_password" file to obtain the password. 

![level5-6.png](../_resources/85b7c8db91814583939de3d87122e4ee.png)

### FLAG: 7cb1963d316b9a302cf6c204d35b7302

On to the next level!

* * *

## Level 6 (10)

![level6-1.png](../_resources/419084214e2d4c0ab4bb49ffbbbee1f0.png)

This level is a bit more complicated than any of the previous levels. A new command (or two) is necessary to complete this level in a reasonable way. 

One *could* take their time looking through each file, but that would take too long. To get through this level quickly, the use of `find` is necessary. 

Part of the file name contains the word "pass", and the file is in the Level 6 user's home directory. In previous challenges, the file name contained the entire word "password". To help narrow the search, start here: 

`find . -name *password*`

![level6-2.png](../_resources/20437bf990dc46a68e4da2250c6f2352.png)

While this search does return a valid result, it's not the correct one to complete the challenge. 

To narrow the search even further, pipe the results of the `find` command through `grep`. 

`find . | grep password`

![level6-3.png](../_resources/f60ff8584dad4c49816cc38af2ea03a4.png)

This produces a more specific result than the `find` command alone, and reveals the location of the password file for Level 7. 

Use `cat` to read the "level7_password" file text. 

![level6-4.png](../_resources/1491340e7f234676a361cb5543c47798.png)

### FLAG: RG8geW91IGV2ZW4gbGlmdCBicm8g

* * *

## Level 7 (10)

![level7-1.png](../_resources/c44f0c9ba4994fa4b427bee5f95082a5.png)

This level contains a bunch of junk files, all the same size, and all named "level8_passwordX" (where X is a number 1-100). A simple `grep` for a file with "password" in the name will not produce useful results on its own. There are other ways to figure out which files contains the actual password to Level 8. 

Start out with `ls -la` to see what's in the user's "home" folder. 

![level7-2.png](../_resources/4701f21d19d94e139ccaf8c6cdb2f4c2.png)

A directory called "password_directory" seems like the obvious choice. Use `cd password_directory` to change current working directory. 

For curiousity's sake, use `ls -la` to list the "password_directory" contents. 

![level7-3.png](../_resources/3363a86f9d75465c9d6739cfff7fcb16.png)

"password_directory" appears to be filled with radom files; all seem to have been created on the same date and at the same time. The file sizes are all exactly the same. 

[I used `cat level8_password1` to take a look at the contents of one of the files. I chose this file because it was one of two files that I noticed with a creation date and time of Aug 22 at 23:52. However, the string of text inside this file doesn't contain a password or any other useful data.]

![level7-4.png](../_resources/535da4bea74d41ed900dfe8002204e19.png)


![level7-5.png](../_resources/e07b29faeced44f1b49d2e92b6729672.png)

The second file with a creation date and time of Aug 22 23:52 was "level8_password68". 


![level7-6.png](../_resources/e3c20929b62f40f2a5b4aecba4ed47ba.png)

Use `cat level8_password68` to view the file's contents. 

![level7-7.png](../_resources/ba9d8801b4e74b5a96dd6ba4b0918374.png)

Conveniently, this file contained the password for Level 8! 

This may not work on every similar CTF challenge; this may have admittedly been more of a lucky shot than a technical solution. Nevertheless, the password has been found! 

Use `su - level8` and the password in "level8_password68" to continue. 

### FLAG: bGV0J3MgZmluZCBzb21ldGhpbmcg

* * *

## Level 8 (10)

![level8-1.png](../_resources/a76198d2fa4d47648b0da2e558ddb84b.png)

To solve this level's challenge, find an executable file and run it to print out the flag. Sounds easy enough!

As with every other level, `ls -la` to see what's in the user's home directory is a good place to start. 

![level8-2.png](../_resources/3ae56e7cdf4542429ef768e061265c32.png)

**So.** **Many.** **Subdirectories.**

This definitely won't be solved by looking at each file in each "dirX" directory. 

Still, the solution won't be complicated because the hint gives enough information to use a relatively simple `file` command. 

Use `file . -type f -executable -print` to find the file containing the password. 

Here's a breakdown of the command and arguments used.

- `find`: used to locate objects within the Linux file structure.
- `.` : searches from the root of the present working directory. 
- `-type f`: denotes the type of object to look for. `f` represents the word "file". 
- `-executable`: narrows the search results to only executable files, excluding all other types. 
- `-print`: presents the search results in the terminal window. 

![level8-3.png](../_resources/6c7791a01e794e948777ba8e5a53b82e.png)

Note that one file is found that matches each of these search attributes. It is located in the user's home directory, in "dir24", in the subdirectory "subdir13". The file name is "level9_password".

Now, use the "strings" command to view the strings inside the executable file without actually executing the file. 

![level8-4.png](../_resources/f37e62d22afd40628a98bbeaf825f85b.png)

In the first several lines, the password is printed in plain text.

### FLAG: 96ab15e954f1267ea04c35de2d771c2b

* * *

## Level 9 (10)


![level9-1.png](../_resources/32f3bc8379fb4732a47d1676809a8478.png)

Most anyone who has ever done any sort of simple password cracking is familiar with "rockyou.txt". RockYou is exceptionlly popular wordlist for learning brute force cracking using tools like JohnTheRipper. 

For this exercise, locate the word "evilhacker" in the "rockyou.txt" file, and use the line number as the password to Level 10. 

Use `cd /usr/share/wordlists` to change to the Wordlists directory, where "rockyou.txt" is located. 

To find "evilhacker" in the wordlist, as well as the line number it's ok, use the `grep` command to search within the contents of the "rockyou.txt" file. 

`grep -n "evilhacker" rockyou.txt`

Here's a breakdown of the `grep` command and the arguments used. 

- `grep`: a tool used to locate specific patterns within files. 
- `-n`: tells `grep` to show the line number of the search string within the file. 
- `"evilhacker"`: the search string. 
- `"rockyou.txt"`: the file where the string may be found. 

The `grep` search should return a line number and the search term, separated by a colon, as shown below. 

![level9-3.png](../_resources/d0601882e31646589ee0a23b606d2ba3.png)

The line number is the password to Level 10. 

### FLAG: 955830

Use `su - level10` to continue.

* * *


