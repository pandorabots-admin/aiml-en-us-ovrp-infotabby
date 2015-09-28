## How Chatbot Knowledge is Maintained and Shared ##


### Introduction ###

Pandorabots uses Google Code to distribute and maintain the AIML (Artificial Intelligence Markup Language) files making up the chatbot’s “brain.” These files are collected into AIML sets which you may download and use on Pandorabots. You can also edit these sets, write new AIML files, and share your work with other libraries. Because many people are modifying the files or adding new ones, the AIML sets are kept up to date with a version control system known as Mercurial (or hg for short).

As a librarian, you may not be interested in learning the details of version control, so we’ve outlined some basics to get you started. We have links to additional information if you’d like to learn more.

### AIML Projects ###

AIML sets are gathered into AIML projects. Since there are numerous AIML projects, we use a convention for naming them that makes them easy to identify.  This is called a Namespace.   You can think if it as being roughly analogous to Dewey Decimal Classification.

AIML Project namespaces follow the pattern:

aiml-language-country-botmaster-botname

Here are some examples:

aiml-en-us-pandorabots-alice            … an American English Language version of Alice

aiml-en-us-ovrp-infotabby                       … an American English Language Librarian from the Ohio
> Virtual reference project




You can find an AIML project on Google code by using the namespace in the URL:

aiml-en-us-foundation-alice.googlecode.com

or

code.google.com/p/aiml-en-us-foundation-alice (alternative format)

aiml-en-us-ovrp-infotabby.googlecode.com

etc.


### Repositories ###

Each AIML Project holds a collection of repositories.   Each repository in a project basically represents a version of a bot.  In particular, an individual repository is a collection of code and downloads associated with a particular release or version of a bot.

AIML projects include:

1. A Development Snapshot Repository that includes the latest changes to the AIML set
2. A set of Official Production Repositories that include the current “official” release as well as earlier releases.


The Development Snapshot is not assigned a version number, but the Official Production Repository has a version number starting with 1-0.

Over time, you will see evolving versions:
v1-1.aiml-en-us-ovrp-infotabby,
v1-2.aiml-en-us-ovrp-infotabby,
v1-3.aiml-en-us-ovrp-infotabby,
and so on, whenever there is a new production release.

Some librarians may wish to use and/or modify the earlier production versions, while others may wish to access the “latest and greatest” changes available in the Development Snapshot.

A single zip file is associated with both the Development Snapshot and with each Production release.  The zip file consists of the AIML files in that repository as well as any associated custom HTML files, bot property files or other documentation.

You can simply download the single zip file consisting of all the AIML files in a set, and safely avoid learning the details of the version control system. If you’d like to share the changes you make with other librarians, read below:


### Sharing your work using Google Code ###

There are a number of ways to share your work using Google Code.  We use a version control system called Mercurial.  The program that implements Mercurial is called TortoiseHG (HG is the chemical symbol for Mercury).   You will need to download Mercurial in order to work with code sharing on Google code.  We’ve prepared a document that shows how to download and install Mercurial:

### Downloading and Installing TortoiseHG ###

Then, consider each of the following scenarios and decide which one matches your situation, then follow the associated link to the next document.


●     I want to create a bot using the aiml-en-us-ovrp-infotabby set (but for now I’ll keep any changes to myself) See Google Code 1: Creating a Library Reference Bot with Pandorabots

●   I want to get started with version control on Google Code. Google Code 2: Introduction to using Mercurial with Google Code

●     I want to get a copy of an AIML project and I might later want to make changes to the AIML and offer them back to the project. (I want to work on and add to the aiml-en-us-ovrp-infotabby set and offer these changes back to the project) See Google Code 3: Contributing changes to the free A.L.I.C.E. AIML set

●     I have an existing collection of AIML code, already under version control, and I want to create a Mercurial repository for this code as a project on Google Code  (work in progress -- briefly, export the files if it is svn, erase the .hg file if it is under mercurial.)




### Glossary ###


AIML: Artificial Intelligence Markup Language -  AIML is an open standard markup language.
AIML Set:   All the files containing knowledge for a particular bot or other set of free AIML files (such as a set of utilities.
Mercurial: A specific version control system compatible with Google Code.
Google Code: Google’s site for developers to maintain code under version control and share it with others.
hg, HG: Other terms for Mercurial, also the name of the Mercurial command line program.
version control system:  a mechanism to manage changes to documents, programs, and other information stored as computer files.
Namespace: A systematic hierarchical way to name programs, data or files
Major-Minor version: A release of an AIML set specified by a major release number X and a minor release number Y in the form X-Y, such as 1-0, 1-3, 2-0 etc.
Download: a zip file containing of all the AIML files in a set.
AIML set: a collection of AIML files that may belong to a single bot, or any other natural grouping of AIML files (such as utilities, games, etc.)  The AIML set may also contain auxiliary non-AIML files such as custom HTML files, configuration files, and Readme documents.
Wiki: the wiki associaed with the Google Code Project
Project: A project on Google code.
Respository: A container for files or data being managed by version control.




### Feedback ###

Please send corrections and suggestions for improvement to info@pandorabots