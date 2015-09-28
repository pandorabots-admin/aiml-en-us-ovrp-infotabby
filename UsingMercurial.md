### Editing the Files ###
For example edit update.aiml and add one category.

Then

**hg add**

**hg  commit -u <your user name>  -m “Made a change to update.aiml”**

**hg push**

At this point you need the password from Source-->Googlecode.com password

II. Creating a repository for your own project on Google code

Download and install Mercurial command line.

Make sure to check the last check box on the installation screen along with the readme, this allows you to access Mercurial from the command line.

Create your Google code project.

This part’s easy, follow the steps enter the words and navigate youself to the main project screen. It helps if you already have a Google account.

Now we get to the fun part. Open your command line in windows, by going to Start->run->type cmd in the input box and click ok. Or if you have style double click the short-cut you’ve created for yourself on the desktop.

You’ll want to navigate to a folder where you can store your project.

For the sake of this example, lets say your project is named testproject and is in the root of c:\.
first back out to the root with:
cd \

Then make a directory to store the project in:

**mkdir testproject**

enter the directory

**cd testproject**

Now you want to take a clone of your googlecode repository, to do this type the following command:
hg clone https://testproject.googlecode.com/hg/ testproject

The last parameter is the directory to copy it into on the local file system.

This should result in Mercurial spewing out some output identifying that it has correctly downloaded.

To check, type:
**cd testproject**
**dir**

If it was successful, you’ll see a directory called “.hg”
If it’s there, now you want to make your first commit. Create a text file called readme and dump it in the directory with the .hg in. To add your new files type:

**hg add**

Next you’ll want to commit them, type:

**hg commit -u <your user name> -m "added first file to repository"**

So you have commited your first change to the repository, but this does not mean it’s gone up to the main node on Google, it is currently just committed to your local file server. To commit the changes back up to Google’s servers, you’ll need to run the following:

**hg push**

This will prompt you for a user name and password, the password IS NOT YOUR DEFAULT PASSWORD. Go to your accounts hosting page to find it.

Now, if your like me, i.e. LAZY, you don’t want to have to enter your username and password each friggin’ time you want to push. You want an automated way to authenticate your https googlecode push actions. The way to get around this is to open the “.hg” directory and find the file “hgrc”. Edit this in your preferred text editor. Where you see the line

default = https://testproject.googlecode.com/hg

change it to

https://(your username here):(your password here)@testproject.googlecode.com/hg

And Voila! everytime you push, it automatically skips the login and password steps.
I hope this helps, I spent sometime this weekend trawling the internet for clues as to how to do this most basic of processes but could find no simple explanation, written in a language people could understand.
