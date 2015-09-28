# Creating your own project on Google Code #


### Create an account on Google Code ###

The page http://http://code.google.com/ is called the “Google code home page”.

In this example, we are going to create a project called aiml-en-us-ovrp-infotabby.  However you do not need to create this project as it already exists.  If you want to create your own Google Code project, follow these directions and substitute your project name for aiml-en-us-ovrp-infotabby.

- Navigate to http://code.google.com/hosting/createProject

(Starting from the Google code home page, navigate to
Project Hosting-->Project Hosting on Google Code-->Create a New Project)


Enter

**Project Name**: aiml-en-us-ovrp-infotabby

**Project Summary**:
infotabby is an AIML based virtual agent designed for libraries. She was created to answer FAQs and light reference questions.

For the namespace convention used in naming this project, see
[.md](.md)

**Version Control System**: Mercurial

**Source code license**: Apache 2.0

**Project labels**: chatbot, AIML, ALICE, chat bot, chatterbot, conversational agent, virtual agent, virtual assistant, virtual human



<a href='https://picasaweb.google.com/lh/photo/klsBfzrhxiMyTrQEdBmndw?feat=embedwebsite'><img src='https://lh6.googleusercontent.com/-Lwm7UuWDnEk/TlEsIqNGMuI/AAAAAAAAANQ/64t0ZEtVsNI/s800/IT2.png' height='691' width='800' /></a>





---

Clicking on “Create Project” generates this page: http://code.google.com/p/aiml-en-us-ovrp-infotabby
Let’s call this the **“project home page”**.


We’ve established a project name; and next we create authentication credentials for the project, by establishing a project password using your google account settings page.


Sidebar: Project Summary subtab -- You can modify some of the options that you set during project creation, as well as set up blogs, analytics, and a custom project logo. This also provides another opportunity to set up project labels, which will help others find your project.


Navigate from the project home page  to your account settings.(in our example: http://code.google.com/p/aiml-en-us-ovrp-infotabby) following the link Profile-->Settings.  You are offered a password to use, and optionally you may elect to use your google account password.


Sidebar: To delete a project, go to Project Summary-->Advanced-->Delete


You will need your password each time you transfer code to your project.   Our next step is to populate the new project with initial AIML.



### 2. Placing your code under revision control ###

Now, we assume you have an existing directory on your local machine in your home directory.  Different versions of windows locate your home directory differently.  But you can always get to it using
%UserProfile%\projects\infotabby, that we want to put under revision control.  For what follows please ensure you’ve already installed  -put link here- the Mercurial revision control system (**Below we use the terms “HG” and “Mercurial” interchangeably.  For those of you who didn’t study science, HG is the abbreviation for the element Mercury).  .**

One very important point about creating a clone repository with Mercurial is that you must create a repository in an empty directory.  The general procedure is, create an empty directory as a sibling of the existing directory, then make that sibling directory the repository.  To get your files under revision control, you will copy or move them to the new directory after it has been designated as a clone.  The following takes us through these steps one by one.

Let's begin by getting to the windows shell with

**Start-->All Programs-->Accessories-->Command Prompt**

By default the command Prompt should open in a directory called your home directory which has a path name like

c:\Users\YourName\

(if your user name is YourName) or in general

%UserProfle%


Sidebar: You can also get to your home directory using the command prompt and executing cd:\> echo %UserProfile%




Change directory to projects with

cd projects

Within the projects directory, Let’s say initially the code is in the subdirectory infotabby  (projects/infotabby)

Within the project directory Create an empty sibling directory aiml-en-us-ovrp-infotabby (i.e. %UserProfile%\projects\aiml-en-us-ovrp-infotabby)

mkdir aiml-en-us-ovrp-infotabby

Staying in the parent directory %UserProfile%\Projects, execute:

hg clone https://drwallace@code.google.com/p/aiml-en-us-foundation-fakekirk/ aiml-en-us-foundation-fakekirk

hg clone https://aiml-en-us-ovrp-infotabby.googlecode.com/hg/ aiml-en-us-ovrp-infotabby

(Warning!  There is a space between “...com/hg/” and “aiml-en-...”)



Sidebar: Google Code will display this command on the Source tab.  If you are the owner of the Project, Google Code, it will appear as



hg clone https://yourname@code.google.com/p/aiml-en-us-foundation-infotabby/ aiml-en-us-ovrp-infotabby



Obviously your project will have a different name, and your user name will differ from “yourname”, but you can follow this case study as an example.


Since this is the first time we've done this, you should have a command line console with these messages:





You should also notice two things.  One, In the file explorer, the folder for the clone directory should be displayed with a small green check mark:


<a href='https://picasaweb.google.com/lh/photo/l23LQ06rc6dy91-9EUgAxA?feat=embedwebsite'><img src='https://lh6.googleusercontent.com/-BYWhBuF-0Aw/TlEtAArgLhI/AAAAAAAAANg/5uz71JbR7Ns/s800/filecheck.png' height='67' width='610' /></a>









Secondly, inside the clone folder you should see a single folder called .hg.  Mercurial stores its internal data structures – the metadata – inside that .hg directory.  For a complete description of the .hg folder see http://mercurial.selenic.com/wiki/Repository




Now copy a single test file from infotabby to aiml-en-us-ovrp-infotabby:

copy infotabby\pickup.aiml aiml-en-us-ovrp-infotabby\pickup.aiml

Next, change directory to the clone directory

cd aiml-en-us-ovrp-infotabby

To place the file under Mercurial version control, execute

hg add 

Next you will want to commit the file to your local HG repository.  What is the difference between “add” and “commit”?   “Add” tells Mercurial which files to put under version control.  The directory may contain files that are not under version control.  Mercurial will never notice these unless you inform HG that is should be begin keeping track of them - and you do this by using the “add” command.   So what’s a “commit”?  A “commit” means that you have been working on the files in your directory, and you have reached a point where the files are stable and you want  Mercurial to record the fact that it should remember the changes to these files.
Next you’ll want to commit them, type:
hg commit -u <your user name> -m "added first file to repository"


If the commit works, you will not see any messages.

The next step is to “push” the code up to the repository on Google code.  What is the difference between “commit” and “push”?  Basically you have two different repositories, one on your machine and one in the cloud.   You want them to be the same, but now one of them is different, because you have committed a change to it.  To synchronize them, use the command “push”.

At this point you are the owner of the repository in the cloud, and the only one who can push changes to it.  Later you may decide to authorize others to make changes.  For the moment you are the only person allowed to push changes to the repository.


Execute

hg push

This will prompt you for a user name and password, the password IS NOT YOUR DEFAULT PASSWORD. Go to your Google Code Profile-->Settings to find it.

Typing your username and password over and over again will quickly get annoying.  You can avoid the repetition by editing the file  %UserProfile%\mercurial.ini" and  under the section headed by [auth](auth.md) add these lines (those prefixed by the characters gc.prefix)


[auth](auth.md)
gc.prefix =  https://aiml-en-us-ovrp-infotabby.googlecode.com/hg/
gc.username = YourName@gmail.com
gc.password = password


IMPORTANT: edit this file with your own username!  Here we use YourName as an example.



The gc.prefix is arbitrary.  You can define additional repositories (with optionally different user names) too. Just add another 3 lines per for the additional repository to the [auth](auth.md)section like so:

[auth](auth.md)
gc.prefix =  https://aiml-en-us-ovrp-infotabby.googlecode.com/hg/
gc.username = YourName@gmail.com
gc.password = password

gc2.prefix =  https://aiml-en-us-ovrp-infotabby.googlecode.com/hg/
gc2.username = AnotherName@gmail.com
gc2.password = password2


Setting up your mercurial.ini file is the best way to push changes, as the push command just works.

The characters “gc...” are arbitrary, make them up to suit yourself.  And you can read more details about what we suggest you do.  If you are still learning about hg we recommend you visit http://hginit.com/01.html for a short rapid introduction to it.


### 3. Multiple Repositories ###

A Google Code Project may optionally consist of multiple repositories.  Why would we want multiple repositories?  In our terminology, the “latest and greatest” AIML set is called the
Development Snapshot Repository.   Those who want these latest changes as a starting point for their project may clone or download from the Development Snapshot Repository.

Consider however a bot author who started with an earlier release of the AIML.   They may want to continue working with the branch they started with initially, because the latest Snapshot changes may conflict with their own work.   However they may wish to merge their changes back into this earlier version.  Or perhaps they may uncover an error in the earlier release, and wish to share the correction.   For these reasons the Project also contains Official Production Repositories, corresponding to earlier releases of the AIML.

To create a new repository within a Project, navigate to

Under Administer-->Source

Suppose we decide that the latest Snapshot should be preserved as a release numbered 1-0.  If we add a new repository it might be called v1-0.aiml-en-us-ovrp-infotabby.

This repository would have the URL

https://v1-0.aiml-en-us-ovrp-infotabby.googlecode.com/hg


Sidebar: Why use a version number like 1-0 instead of the more typical 1.0?  The reason is that Google Code uses the repository name as a subdomain of googlecode.com in the URL for the repository.  The “.” character would confuse this naming convention because the “.” would add an extra level of subdomain name.


---



## Practical Scenario ##

Let us consider a scenario involving an AIML botmaster named Doubly Aimless. Doubly Aimless is an AIML developer who wants to work on and contribute to the Development Snapshot.   Doubly creates a server-side clone repository and then makes a second local copy of that clone on his computer.  He makes changes to the local copy and pushes the changes back to the server side clone.

Doubly then contacts Dr. Wallace and asks him to examine and accept (merge) the changes into the main Development Snapshot.   This section covers examples of Doubly submitting both acceptable and unacceptable changes.

Doubly initiates these steps to work with the ALICE AIML code:


### 1. Find the project ###

Dr. Wallace is the owner of a Google Code project called aiml-en-us-foundation-alice.  Doubly Aimless finds out about the project from an announcement on Dr. Wallace’s blog.  Doubly logs in to his Google account and navigates to

http://aiml-en-us-foundation-alice.googlecode.com


### 2. Create a Google Code clone repository ###

In the project aiml-en-us-foundation, Doubly goes to “Source” and clicks on “Create a Clone.”

Doubly fills out a form naming and describing the clone (see picture).  Then Google Code creates a server side clone, with a URL like:

http://doublyaimless-en-us-foundation-alice.googlecode.com

By default Google code just uses Doubly’s email identfier (doublyaimless) and appends it to the original project name (aiml-en-us-foundation-alice).  It is possible to choose other names, however they will start with the email identifier (doublyaimless in this case).


### 3. Make a local copy ###

Now Doubly downloads a local copy of the clone of his newly established repository onto his computer:


### A. Store the password ###

To save himself the trouble of typing a password each time he downloads changes,  he first performs a one-time edit to his mercurial.ini file located in:

%userprofile%\mercurial.ini  (Windows)
> (Mac - where?)

by adding these lines

[auth](auth.md)
gc.prefix =  https://doublyaimless-aiml-en-us-foundation-alice.googlecode.com/hg/
gc.username = doublyaimless@gmail.com
gc.password = doubly’s-password

Doubly finds his password: doubly’s-password, in his Google Code Profile under “Settings”.  Note the password is associated with the user, not the project.


### B. Create the local copy on your computer ###

Doubly uses hg to make a local copy.  He decides to make a project in a directory called c:\doubly.  On his local comuter Doubly runs the following commands to create the directory, navigate to it, and get the clone:

Doubly accesses the command prompt through
Start-->All Programs-->Accessories-->Command Prompt

cd c:
mkdir doubly
cd doubly
hg clone https://doubly.aimless@doublyaimless-aiml-en-us-foundation-alice.googlecode.com/hg/

doublyaimless-aiml-en-us-foundation0-alice


The last two lines are really one line with a space between the “../hg/” and “doublyaimless...” parts.  The output from hg indicates that the hg command was successful.  Not only does Doubly get a copy of all the files, he also gets a copy of all the changes (“Changesets”) for those files up to the point where he created the clone:


### 4. Make some changes to the AIML ###

Doubly edits the file update.aiml and adds a category



&lt;category&gt;




&lt;pattern&gt;

CAN YOU MAKE COFFEE

&lt;/pattern&gt;




&lt;template&gt;

Yes, if I have a filter, ground coffee and hot water.


&lt;/template&gt;




&lt;/category&gt;




### 5. Commit the changes ###

By issuing the hg commit command, Doubly tells his repository that he wants to include his changes in the AIML set.

hg commit -u doublyaimless “added one category to update.aiml”


### 6. Push the changes to the Google Code clone ###

To make the changes available to the public, Doubly uses the hg push command.  This synchonizes the repository on the server side with the repository on his local computer.

hg push
The hg push command asks for Doubly’s password, but it is not needed because Doubly already edited his mercurial.ini in step 3.


### 7. Request Review ###

Now Doubly contacts the owner (Dr. Wallace) and asks him to review the changes.  He could contact the owner by phone, email, or through the Google Code Code Review feature.


### 8. Owner reviews ###




**A. Pull the changes**

First, Dr. Wallace pulls Doubly’s changes down to the local repository on his computer:


hg pull https://doublyaimless-aiml-en-us-foundation-alice.googlecode.com/hg/


**B.  Merge the local repository**

Then he merges  the changes into the  repository on his local computer:

hg merge

what happens if there is a conflict?

There are 3 possibilities when Dr. Wallace runs hg merge (i, ii and iii):

i. There is nothing to merge, in that case hg says use hg update

The hg merge command may respond with “There is nothing to merge -- use hg update instead.”  In that case, use

hg update

However, even if there are no conflicts, the project owner may want to review the changes.

In that case, he runs hg diff (see Review the Changes below)

ii. There are no conflicts, then merge works automatically

Dr. Wallace may also want to run hg diff in this case, to review the changes.

He runs,

hg diff

and sees the specific changes Doubly made.


The + and - symbols in the output of the hg diff command highlight the change Doubly made.
Noticing that the change is unacceptable, Dr Wallace runs

hg log

to see that the last changeset before the unacceptable change, was number 3.

hg revert -r 3 wallace.aiml

and his clone reverts to the previous changeset, number 3.  Doubly’s changes have been logged, but they do not become part of the main trunk of aiml-en-us-foundation-alice.


iii. There are conflicts, hg launches the kdiff3 tool to merge the files

Conflicts occur when two or more contributors edit the same parts of the same files.





**C. Push the changes**

Finally, if the changes are acceptable, Dr. Wallace pushes the changes to the Development Snapshot Repsitory.  Note that under some circumstances, Doubly might have requested the changes be pushed to an earlier Official Production Repository.   This might be because Doubly had been working with version v1-0 for example, and wanted to submit his changes to this earlier release.

In either case Dr. Wallace runs the command

hg push

and now the changes have been made available to the community through the Google Code project.




Notes:

If you try hg merge and get a response like “abort: outstanding uncommitted merges”, it means the directory is in some kind of confused state.  To fix this, use

hg update -C

and then repeat the hg merge.








---




### References ###

http://hginit.com/01.html

http://mercurial.aragost.com/kick-start/en/basic/#installation-configuration

http://code.google.com/p/jugevents/wiki/MercurialRepositoryGuidelines