# CS Hub Git/GitHub Workshop  
-----

All the commands you see below need to be executed in a Terminal (Mac or Linux) or Git Bash (Windows)

## Hands-on steps to follow:
First things first, configure Git from the command line:  
Make sure to replace [NAME] with your full name, and [EMAIL] with the email address registered in your GitHub account

```sh
  git config --global user.name "[NAME]"
  git config --global user.email "[EMAIL]"
  git config --global color.ui auto
  git config --global push.default simple
```

_You can probably understand what the first 2 lines do, but what about the last 2?_

Check your Present Working Directory:

```sh
  pwd
```

List the contents of the directory:

```sh
  ls -la
```  

Cool, now go back to your browser and browse to the short URL on the whiteboard in front of you.  
You'll need to "fork" this repository _(what does forking mean?)_  

After you successfully fork the repo, click on the green "Clone or Download" button. You'll see a URL and a button next to it that says "Copy to Clipboard". Guess what you gonna do? Oh My God! You are AMAZING! and yes, just click on the copy button and go back to your terminal / git bash window  

Let's clone the repo we just forked (paste the URL you copied instead of the [ADDRESS] part):

```sh
  git clone [ADDRESS]
```

_List the contents of the directory now, you still remember how to do that, right?_  
_Confirm that you have 2 .md file and a "names" directory_  

This cloned all the contents of the selected repo into a directory of the same name.  
Let's change our present working directory into the repo we just cloned:

```sh
  cd git_workshop_2016
```

Check which "remotes" do you have in the repo you just cloned:  
_Don't worry if you don't understand this now, you'll get why we checked this later_  

```sh
  git remote -v
```

Change your present working directory into "names":

```sh
  cd names
```

Create a text file and inserts a number into it.  
Replace [NUMBER] with a random number of your choice.
Replace [NAME] with your initial & last name.

```sh
  echo "[NUMBER]" > [NAME].txt
```

_List the contents of your directory to ensure that a text file with your name was created._  
_Try to display the contents of the file from the command line._

Go up one level into the parent directory (the repo we cloned):

```sh
  cd ..
```

Let's check what Git believes has changed in the repo:

```sh
  git status
```

_What do you understand from the "status" command? Let's discuss it._  

Let's add the file we created into Git staging area.  
Actually, let's add everything in our directory (including all files and sub-directories) into the staging area:

```sh
  git add .
```

_Check Git status again, what has changed?_

Seems like we're ready to commit the changes. Let's do that:

```sh
  git commit -m "Added my name in a text file!"
```

_What do you think "-m" option is for?_

Now, let's push the changes we made into the repo's source (GitHub):

```sh
  git push
```

_it will probably prompt you for your GitHub credentials, enter your username and password accordingly_

Well done! Now pay attention on how we gonna open a "pull request" _(what does that even mean?)_, and how will that work (We'll wait for everyone to get to this step, then Marwan will take it from there, so just sit tight)

-----

So you're comfortable with how the absolute basics & pull requests work? Pat yourself on the shoulder, you had a very good start with Git!

Let's carry on ...

Now, to be able to pull the changes from the original repo (the one you forked out from), we need to add it as an upstream in our remotes list:

```sh
  git remote add upstream https://github.com/m-alani/git_workshop_2016.git
```

_Check what remotes do you have now and notice what has changed._  

Let's fetch the original repo:

```sh
  git fetch upstream
```

Now that we synced our repo with upstream "original" repo, let's inspect what happened:

```sh
  git branch
```

_This command lists the branches you have in your local repo. Notice that the branch with "*" before it is the current active branch._  
_Did you notice that there is an "upstream/master" branch? Where did that come from? Let's talk about it_  

Make sure that we are on our local "master" branch:

```sh
  git checkout master
```

Finally, let's merge the changes we pulled from the upstream remote (or at least try to):

```sh
  git merge upstream/master
```

This brings your local repo up to sync with the remote repo you origiannly forked from.  

This also concludes this quick tutorial about Git & GitHub basics!  

Time to ask away if you have anything in mind.
