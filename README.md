# How To Use Git On Your Personal Hosting

This is a presentation on how to use git on your personal hosting. :)


1. Get a hosting plan with CPanel access
1. Enable SSH
1. Enable/Install Git
1. Using SSH, create a directory to store your Git Repository
1. Create a new SSH user and set a password for your Git system:
  ```
  #After below command, system will ask to set password.
  sudo adduser git
  ```
1. Logout and log back in with your Git user and create a bare repository (It's VERY important to set it as a "bare" repository!!!):
  ```
  #Login to server
  #to test, use localhost
  ssh git@IP_ADDRESS_OF_SERVER

  #Create repository
  git init --bare example-git-repository.git
  ```
1. Now you can push from your local computer to your remote repository:
  ```
  mkdir example-git-repository
  cd example-git-repository
  git init
  touch README.md
  git add README.md
  git commit - "first commit - added README.md"
  git remote add origin git@IP_ADDRESS_OF_SERVER:example-git-repository.git
  git push -u origin master
  ```
1. Enjoy your private git repository!
