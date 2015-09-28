# Cloning infoTabby and sharing your additions to her code #


Use this link as a reference for the Mercurial commands we describe:

Mercurial: The Definitive Guide


Why share? First of all, so you can access the latest improvements and additions to the code, and secondly to contribute to the development of the project and to the library community as a whole.


How do I share with other libraries?

Here’s the basic workflow:

1. You make your own google code copy of the project.
2. You create a copy of the files by downloading them from Google Code to your computer.
3. You make changes to the files on your computer.
4. You share your work by uploading a copy of your changes to your own copy of the project.


Strictly speaking this description is not quite accurate.  With the Mercurial Version Control system, the ‘download’ and ‘upload’ have additional information associated with them, such as a record of all changes that have been made to the files.

Using the language of Mercurial,  the basic workflow can be more precisely restated as:

1. You clone (create) a copy of the files  into your own (new) Google Code repository.
2. You then create a ‘local clone’ on your computer by pulling  the files (downloading them to your computer).
3. You make and commit these changes into your local copy on your computer.
4. You push (upload) the changes back up to your Google Code clone respository.

You may then offer your changes to the owner of the original repository that you cloned.  The owner ‘pulls’ the changes from your repository into his own local clone.  If he accepts them, he
pushes them into his server side repository.

A user clone allows users to contribute to projects without requiring official commit access permissions. If the project maintainers like the new code, they just "pull" the changes from the clone and merge them into an official project repository. It's all much more elegant than emailing patches back and forth - and anonymous contributors use the same tools as project owners..


On to the details...

Someone has created a Google code project, and placed some files into a repository under version control.  You  access the files in the repository by cloning them, making changes, and finally storing the result back on Google Code in their own repository.

The same steps also apply to cloning the repository yourself on a different computer.

As before, to follow this procedure you will need a Mercurial client such TortoiseHG.  If you have not done so already,  download and install Mercurial.



Creating your own infoTabby AIML repository

What is a repository?

Creating an AIML repository and sharing the results involves learning some new things.   Many people--even experts in computer science--have found these processes hard to grasp and incorporate at first.

The latest version of the library bot’s AIML files are stored in a repository on Google code. “Repository” refers to a central place where data is stored and maintained.   Google code is a web site storing thousands of repositories of code from a wide variety of projects.  One of these, the Ohio Virtual Reference Project, contains the AIML for the library reference bot.

The following instructions will show you how to create a “clone” of the library bot repository on Google code.  Then you will make your changes within your clone of the library bot.  If you are a trusted editor of the OVRP, you will be able to add your changes to the global library bot repository on Google code.


How to create your own repository
1. Create a free Google account. After you create your account,  go to
http://code.google.com/p/aiml-en-us-ovrp-infotabby/ and add this project to your
favorites.

2. Downwnload and install TortoiseHG.  TortoiseHG is a Mercurial client.  Mercurial is a system that allows multiple developers to work on the same project, and then merge the results of their independent work into a unified result. Here are instructions to help you  download and install Mercurial.



Let the cloning begin!

Now you’re ready to make a clone of the infotabby repository from Google code!

Open the command prompt. You’re not sure what the command prompt is? That’s O.K. Go to Start-->All Programs-->Accessories-->Command Prompt


<a href='https://picasaweb.google.com/lh/photo/UZlWTNaNJb7-cz00vDSJcA?feat=embedwebsite'><img src='https://lh6.googleusercontent.com/-hbKnzD6pjIk/Tkf4SV4xhnI/AAAAAAAAALs/LXamxN-3WCA/s800/menu.png' height='500' width='800' /></a>

Double click on “Command Prompt” and it should open, like this:

<a href='https://picasaweb.google.com/lh/photo/h_w7TF_NSxz_wtBFaUftEA?feat=embedwebsite'><img src='https://lh4.googleusercontent.com/-6FatN_qCt6c/Tk7GaN4VntI/AAAAAAAAAM8/rrJEbKosRkE/s800/command%252520prompt.png' height='355' width='689' /></a>

Now type the following:

cd\.    (hit enter)

mkdir Projects  (hit enter)

cd Projects (hit enter)

mkdir aiml-en-us-ovrp-infotabby

Now you are in a directory called c:\users\<your name>\Projects\ which has a subfolder called aiml-en-us-ovrp-infotabby.

To clone the Google code repository into this subfolder, type:

hg clone https://aiml-en-us-ovrp.infotabby.googlecode.com/hg/ aiml-en-us-ovrp-infotabby

and hit enter.

Please note! There is a space between hg/ and aiml-en-us-ovrp-infotabby! Don’t run this together! If you do, this command won’t work!


Now look in the subdirectory by typing:

cd aiml-en-us-ovrp-infotabby

Hit enter and you should see your copy of the aiml-en-us-ovrp-infotabby files.

Take a break. You’re ready to start customizing your bot!