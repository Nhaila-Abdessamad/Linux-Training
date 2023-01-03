> About this lab : 

> In this short lab, we'll walk through the foundational tasks for new Vim users. In this lab, we'll cover file creation, the editing of system files, Vim navigation, and helpful resources. By the end of this lab, you'll gain essential skills needed to edit files within Linux systems.

## Table of Contents
* [SSH to your EC2 Instance](#ssh-to-your-ec2-instance)
* [Creating, Opening, and Exiting a File](#)
* [Making a Simple Change to a File](#)
* [Changing a System File](#)
* [Simple Navigation](#)
* [Inserting, Copying, and Deleting Text](#)
* [Undoing and Redoing](#)
* [Resources for Getting Help](#)



## Creating, Opening, and Exiting a File


### Sub-Task 1a - Create a New File, Save and Exit

1. Open Vim:

```
vim
```
2. Press the i key and note that the bottom left says you are in Insert Mode. Type in some text such as: Mimsy were the borogroves or It was a dark and stormy night.

3. When done entering the text, use ESC to return to Command Mode.

4. Write the new file to disk with:

```
:w myfirstnovel.txt
```
5. Then exit Vim with:

> Note: You can specify a filename at the outset, such as in Step 1. Then saving and exiting can skip Step 4, and in Step 5 the command would then be:

```
:wq
```

### Sub-Task 1b - Open an existing (read-only) file, exit w/o saving changes

1. Edit the /etc/hosts file with:


```
vim /etc/hosts
```

2. Press the ``` i ```key to go to Insert Mode, which will cause a W10: Warning: Changing a readonly file error message.

3. Use ESC to return to Command Mode and u to ensure that no changes have been made, indicated by a message at the status. line of Already at oldest change.


4. Exit the file with:
 
```
:q!
```


### Making a Simple Change to a File



1. Copy a Vim documentation file for our use:
```
cp /usr/share/vim/vim82/doc/help.txt ~/vimhelp.txt
```

2. Edit the file with:

```
vim ~/vimhelp.txt
```

3. Navigate to the text VIM - main help file.

4. Change the word VIM to Vim by putting the cursor on the ```I``` and pressing ```cw``` to change the rest of the word to im.

5. Then hit ```ESC``` to exit Insert Mode.

6. Navigate to the ```m``` in main and use the ```~``` character to change it to ```M```.

7. Then do the same for the ```h``` in help and the ```f``` in file.

8. Press ```ESC``` to ensure you are back in Command Mode.

9. Save and exit with:

```
:wq
```
### Changing a System File

1. Edit the /etc/hosts file with:

sudo -i vim /etc/hosts

2. Supply the cloud_user's password (or the required user's).

3. Using the cursor keys (if necessary), go to the line that reads:

```127.0.0.1       localhost```

4. Press ```A``` which enters Insert Mode, and moves you to the end of the line.

5. Now add a ```space``` and ```snowblower``` to the end of the line so that it reads:

```127.0.0.1       localhost snowblower```

6. Save and exit the file by first pressing ```ESC``` and then ```ZZ```.

7. Verify the change was written with:

```grep snowblower /etc/hosts```

8. Confirm that the name is resolvable with:

```ping -c 4 snowblower```

- The ping should work properly, if not, check the line to ensure there is a space between localhost and snowblower.

### Simple Navigation

> Note: You must have created the vimhelp.txt in Task 2 for this to work.

1. Edit the ~/vimhelp.txt file:
```
vim ~/vimhelp.txt
```

2. Go to the top of the file with ```gg```.

3. Go to the bottom of the file with ```G```.

4. Go to line 25 with ```25G```.

5. Go to 50% of the way through the file with ```50%```.

6. Go to the top with ```gg```.

7. Press ```w``` 5 times to move forward 5, then ```gg``` to return to the top of the file.

8. Press ```25w``` to move forward 25 words, then ```5b``` to move backwards 5 words.

9. Use ```h,j,k,l``` to move around, then use the ```cursor keys```.

10. Press ```gg``` to go to the top.

11. Use ```/Vim```, ```ENTER``` to find the first instance of Vim.

12. Use ```n``` to go to the next and subsequent instances.

13. Use ```N``` to go back to previous instances.

14. Go to the bottom of the file using ```G```.

15. Use ```?help``` to search backwards.

16. Exit without saving using ```q!```.

### Inserting, Copying, and Deleting Text

> Note: You must have created the vimhelp.txt in Task 2 for this to work.

1. Edit the ~/vimhelp.txt file:
```
vim ~/vimhelp.txt
```
2. Go to the top of the file with gg and then navigate to the line that starts with Get out of Vim.

3. Press o to add a line under the current line.

4. On that line, add the following text, taking care to line up the : with the other instances of : on other lines:

> ATTENTION:  Do NOT Reboot to Exit Vim!

5. When added, hit the ESC key to return to Command Mode, and use ^ to go back to the front of the word ATTENTION. Then press 0 (zero) to go to the very beginning of the line.

6. Next, place the cursor on the empty line between your current line and the one that reads Jump to a subject, and delete the empty line by pressing dd.

7. Now copy the ATTENTION line by moving to it and pressing yy.

8. Go to line that starts with Jump Back and use p to paste the copied line below it.

9. Then place your cursor on the blank line in between the current line and the one that begins with Get specific help and press the yy keys to copy the blank line.

10. Next create four more blank lines by using 4p.

11. Now highlight or select all of the blank lines, except the last one, before Get specific help by putting your cursor on the top blank line, pressing V and moving your cursor to the next-to-last blank line (selecting four lines). Delete those lines by pressing d once.

12. While on the remaining blank line below the copied line (the one beginning with ATTENTION:), press i to enter Insert Mode and use the spacebar to insert spaces until the cursor is under the D in Do NOT. Add the text You'll Regret it!, and press ESC to return to Command Mode.

13. Move the cursor to the line above the current one, which puts your cursor in between the words to and Exit on that line, and press J to join the line below to the end of the current line.


### Undoing and Redoing

> Note: You must have done the steps in Task 5 for this to work.

1. Now undo your changes one at a time by pressing u. You'll tire quickly of this, so hold down the u key until all changes to the file are reversed.

2. When you have reached the last undo possible, you will see the status line reflect with the text Already at oldest change.

3. Restore all changes to the file by pressing Ctrl-r repeatedly, noting what each "change" is made up of, and also what the status line says about how many changes were made.

4. When all changes have been redone, you'll see Already at newest change.


> Note: For the next task to work properly, ensure that you redo all the changes.

> Saving and/or Exiting

> Note: You must have done the steps in Task 6 for this to work.

5. Save your changed buffer to a new file by typing:
```
:w ~/changedhelp.txt
```
6. Look to see if you are in that buffer, or in the old buffer by pressing:
```
Ctrl-g
```
7. Confirm that there is only a single buffer, and that it's the vimhelp.txt buffer, including changes, with:
```
:ls
```
8. Exit the changed buffer without saving any changes with:
```
:q!
```

### Resources for Getting Help

1. Run vim with no file argument:
```
vim
```
2. In Command Mode, use ```:help``` to get into Help Mode.

3. Exit Help Mode with :q, just to show Vim you can!

4. Invoke help for how to move around with :h motion.

5. Peruse the text, then press the Ctrl-f key combo to move a screen forward, then use Ctrl-b to move back a screen.

6. While in the motion help page, bring up the help for Ctrl-f with :h Ctrl-f and read about that.

7. Look up the help for how to load Vim with just its defaults, so when something goes wrong you can troubleshoot it with :h --clean.

8. When done, quit out of Help Mode with :q and completely out of Vim with by pressing ESC to ensure you're in Command Mode, then :q! to completely exit.

9. Navigate to the Vim help documentation directory with:

10. cd /usr/share/vim/vim80/doc  # Remember, it may be vim81!

11. Use the following command to find what files in the directory have the "motion" keyword in them:
```
grep -wn motion *.txt
```
>Note the results. The file visual.txt should be the last one listed.

12. Edit the visual.txt file and go straight to line 295 (or the line number indicated) where motion is located with:
```
vim +295 visual.txt
```
> Note that you are placed on the beginning of line 295.

13. Exit the visual.txt file with:
```
 :q!
```

14. Rerun the command to edit visual.txt with a search for motion instead:
```
vim +/motion visual.txt
```

>Note: You may have a message about it being read-only, but hit ENTER to continue.

15. When the file is loaded, turn search highlighting on with :set hlsearch and you'll see that motion is highlighted. You can ignore it if there are other highlighted words than motion, those are not actual highlights, just color codes.

16. Exit Vim with :q! and rerun the previous grep command. But add | less to the end of it so that the output will go into the less pager, and you can scroll through and see what other places your search term is found:
```
grep -wn motion *.txt | less
```
17. Repeat this any time you need to find a term in the Vim help files. It's a marvelous source of good information for the curious Vim-ster!


## resources

```

```