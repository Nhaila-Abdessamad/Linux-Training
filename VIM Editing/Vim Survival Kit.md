> About this lab : 

> In this short lab, we'll walk through the foundational tasks for new Vim users. In this lab, we'll cover file creation, the editing of system files, Vim navigation, and helpful resources. By the end of this lab, you'll gain essential skills needed to edit files within Linux systems.

## Table of Contents
* [SSH to your EC2 Instance](#ssh-to-your-ec2-instance)
* [Hello World Script](#)
* [execute the script](#)
* [Resources](#)


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

2. Press the i key to go to Insert Mode, which will cause a W10: Warning: Changing a readonly file error message.

3. Use ESC to return to Command Mode and u to ensure that no changes have been made, indicated by a message at the status

```

```




## resources

```

```