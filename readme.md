How to setup multiple github accounts on your local machine?
============================================================

1. create a config file under your ~/.ssh

$ touch config


#config file 
Host github.com
  User git
  IdentityFile ~/.ssh/mainaccount-id_rsa

Host github.com-secondaccount
  HostName github.com
  User git
  IdentityFile ~/.ssh/secondaccount-id_rsa


2. chmod your file with permissions 700 
$ chmod 700 config


3. try it out:

$ cd ~
$ mkdir somerepo
$ cd somerepo
$ git init


4.  Create a Readme file and commit it.
$ echo "Hello World!" > readme.md
$ git add .
$ git commit -m "my first commit"


5. In order to configure your repo to "communicate" to github using the correct identity/credentials, add a remote origin. 
Assuming your github username for your new account is gituser.

The  "github.com-secondaccount" section is absolutely important and it must match the Host that you defined in your ~/.ssh/config file.

$ git remote add origin github.com-secoundaccount:gituser/somerepo.git


6. Finally push the repo:

$ git push origin master



7. 
