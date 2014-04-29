Repository command cheat scripts


Install
$ apt-get install git
$ yum install git-core



Identity Configuration:
$ git config --global user.name "username"
$ git config --global user.email "user@gmail.com"


View Username:
$ git config user.name


Remote Origin:

#adding remote origin
$ git remote add origin https://github.com/user/repo.git

#reset remote origin
$ git remote set-url origin git://new.url.here

#view remotes
$ git remote -v


Resync .gitignore
$ git rm -r --cached
$ git add --all # or git add .
$ git commit -m "resync"
$ git push


Push: 
$ git add --all # or git add .
$ git commit -m "first"
$ git push

 
Cloning:
clone into directory
$ git clone https://github.com/repo.git /opt/repo-folder


Add Existing Repo to Github: 
$ git init
$ git add --all
$ git commit -m "adding new"
$ git remote add origin https://github.com/user/repo.git
$ git push origin master






