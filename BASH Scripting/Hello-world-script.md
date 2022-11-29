# ENV-Setup.
>After finishing this markdown:
- You will be able to SSH to the EC2 Instance allocated to you.
- Install The Required Packages to start Developing, Compiling, Testing & Deploying your smart Contracts.


## Table of Contents
* [SSH to your EC2 Instance](#ssh-to-your-ec2-instance)
* [Hello World Script](#)
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
vi hello-world.sh
```


2. copy the following script in the file you just created

```
#!/bin/bash

#These are are comments

echo "Hello World"
```


## execute the script

- First Make the script you just created executable using the folllowing command

```
chmod +x hello-world.sh
```

- Than run this command to execute it

```
./hello-world.sh
```

## What s Next

- we go for a bit more complicated script 
- follow this link to get on it [(link)].

## Resources


