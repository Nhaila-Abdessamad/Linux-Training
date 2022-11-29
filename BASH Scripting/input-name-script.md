
## Table of Contents
* [SSH to your EC2 Instance](#ssh-to-your-ec2-instance)
* [Input Name Script](#)
* [execute the script](#)
* [Resources](#)


## SSH to your EC2 Instance
- Open Your CMD
- SSH To your EC2 Instance using the following command By changing the IP adress.
```
ssh ec2-user@Public-IP-Address
```
- You Will Be Prompted to enter a password (Enter The one we gave you) 

- LET THE GAMES BEGIN:

## Create Hello World Script

1. Use the following command to create and open an empty hello-world File 


```
vi input-script.sh
```


2. copy the following script in the file you just created

```
#!/bin/bash

#These are comments

echo "Please enter your name: "

read name

echo -e "Hello $name! \n"
```


## execute the script

- First Make the script you just created executable using the folllowing command

```
chmod +x input-script.sh
```

- Than run this command to execute it

```
./input-script.sh
```

## What s Next

- we go for a bit more complicated script 
- follow this link to get on it [input-script](link).

## Resources

- [advanced_bash_scripting linuxtopia](https://www.linuxtopia.org/online_books/advanced_bash_scripting_guide/complexfunct.html)

