_If you don’t already have a Google account, create one and go to
http://code.google.com/p/aiml-en-us-ovrp-infotabby/
Add this project to your Favorites._

### Download and install TortoiseHG ###
TortoiseHG is a Mercurial client.  Mercurial is a system that allows multiple developers to work on the same project, and then merge the results of their independent work into a unified result.

Download from: http://mercurial.selenic.com/downloads/

For Windows 7 choose
TortoiseHg 2.0.5 with Mercurial 1.8.4 - x64 Windows

TortoiseHG includes both a Graphical User Interface (GUI) and a command-line version of the Mercurial client.   For this project we are using the command-line version.

After installing the program TortoiseHG, we will be able to use the command line version called ‘hg’.  However if you try to open a command prompt and run ‘hg’ the system may say ‘command not recognized’.   The simplest way to make the system recognize the ‘hg’ command is to reboot your computer.   To troubleshoot any problems, see the Sidebar called TortoiseHG and the Path Environment Variable.

Sidebar: TortoiseHG and the Path Environment Variable

Note: The install process should modify the environment variable called Path.

To see the value of Path, right click on Computer and choose Properties.



<a href='https://picasaweb.google.com/lh/photo/iWR2iqOpAnzNOVPlhPGC3w?feat=embedwebsite'><img src='https://lh3.googleusercontent.com/-ZO9UVqAWPg0/TkgAdErGm-I/AAAAAAAAAMY/6xDIdYRYtqU/s800/scsh1.png' height='519' width='566' /></a>


By clicking on Properties, you will see


<a href='https://picasaweb.google.com/lh/photo/zme5vH3ZzXulsA8prGD_uw?feat=embedwebsite'><img src='https://lh3.googleusercontent.com/-7F82NLKy3o0/Tkf1qoZZsMI/AAAAAAAAAKE/tk1yVr2x_pY/s800/scsh2.png' height='291' width='624' /></a>

Choose Advanced System Settings and you will see this dialog:

<a href='https://picasaweb.google.com/lh/photo/M6YFgsuXAn_RqHR-WN8CDg?feat=embedwebsite'><img src='https://lh5.googleusercontent.com/-OwaCtK3twJQ/Tkf1xj2jiCI/AAAAAAAAAKU/udI_njBfNp4/s800/scsh3.png' height='486' width='443' /></a>

Select Environment Variables and you should see this dialog:

<a href='https://picasaweb.google.com/lh/photo/1yuoFs2-9rcc4SFWzvlZ4g?feat=embedwebsite'><img src='https://lh4.googleusercontent.com/-W_sqr8YTefk/Tkf14OYwbhI/AAAAAAAAAKk/SiKCg-wN1sY/s800/scsh4.png' height='447' width='408' /></a>

Under System Variables, click on Path and you will see this Edit System Variables dialog:

<a href='https://picasaweb.google.com/lh/photo/7U1GD9fSuPHCkA38406bQA?feat=embedwebsite'><img src='https://lh4.googleusercontent.com/-2vluOXjIlnM/Tk7DiB_hFEI/AAAAAAAAAMo/zaqwAMvCiAU/s800/scsh5.png' height='164' width='368' /></a>


The value of Path should be something like
C:\Program Files\Common Files\Microsoft Shared\Windows Live;...;C:\Program Files\TortoiseHg\

In other words, you should see “C:\Program Files\TortoiseHg\” at the end.
However under Windows 7 for this change to take effect, you may need to reboot your machine.



To test that the install of TortoiseHG was successful, open a command Prompt.  If this is not already on your Start Menu, then go to Start-->All Programs-->Accessories-->Command Prompt

<a href='https://picasaweb.google.com/lh/photo/sP2QxlrMnyhW0NO6ypFKrw?feat=embedwebsite'><img src='https://lh4.googleusercontent.com/-rhVVu8xyPW0/Tkf2fd4LCPI/AAAAAAAAAK8/qU1dgWUJjK4/s800/scsh6.png' height='558' width='413' /></a>


In the command prompt type

**hg**

If TortoiseHG installed correctly you should see something like this:


<a href='https://picasaweb.google.com/lh/photo/cS9_MkYrnaC33ToEGiD_fQ?feat=embedwebsite'><img src='https://lh4.googleusercontent.com/-p6TxE6FiNvA/Tkf2mIykGTI/AAAAAAAAALM/3DMudg0SNbg/s800/scsh7.png' height='378' width='677' /></a>


Now you want to make a clone of the Refbot repository from Google Code, to do this type the following commands:



**mkdir Projects**

**cd Project**

**mkdir http://code.google.com/p/aiml-en-us-ovrp-infotabby/***

Now you are in a directory called c:\users\<your name>\Projects\ which has a subfoder called http://code.google.com/p/aiml-en-us-ovrp-infotabby/.
To make this subdirectory a clone of the Google code repository, type the the hg command as follows:

**hg clone http://code.google.com/p/aiml-en-us-ovrp-infotabby/ aiml-en-us-ovrp-infotabby**

Now if you look in the subdirectory

**aiml-en-us-ovrp-infotabby**

you will see your copy of the Infotabby AIML files from the project.

### Next Step - Making your own [Infotabby Clone](https://docs.google.com/document/pub?id=1_UkFmFVGoSu2wCkI2vPwJXyJ2sFEjYG5TQV6Ng-cYhE) ###