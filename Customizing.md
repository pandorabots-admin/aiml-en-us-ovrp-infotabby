# Customizing the infoTabby aiml set #

infoTabby runs user input through a series of categories to arrive at a meaningful response. You only need to edit five files to configure the bot to respond with your own library's information and/or policies.

When you unzip infoTabby, you'll find the following subfolders: **Custom html**, **Files you need to customize**, **infoTabby**, **Reductions**, and **Searching**.

Open the **Reductions** folder and load the seven files **in this order**:


**reduction0.safe.aiml**

**reduction1.safe.aiml**

**reduction2.safe.aiml**

**reduction3.safe.aiml**

**reduction4.safe.aiml**

**reductions-update.aiml**

**atomic-categories0.aiml**

File loading order is very important! You can go ahead and load the rest of the infoTabby files now.

Don't worry about the files in the **Custom html** or **Searching** folders for now; they allow your bot to pass searches to your catalog and should be loaded last.


## Customizing the library information files ##

Open the **files you need to customize** folder. Inside you'll find four files:

**contact.aiml**

**hours.aiml**

**library\_info.aiml**

**localinfo.aiml**

**material\_type\_attributes.aiml**


These are the files you need to edit. Lets start with the largest and easiest to edit.

### 1. library\_info.aiml ###

This file contains responses for most library information. The information it contains has been organized by topic, i.e. account info, bestsellers info, etc. These sections are indicated with comments,

<!--ACCOUNT INFO-->

<!--BESTSELLERS INFO--> etc.

Editing this file is simple, just change the information between the `<template></template>` tags in each category.


Here is the first category you'll see in this file:

```
<category>
<pattern>ABOUTACCTS</pattern>
<template>You may get a card, open an acccount, at the Main Library Circulation Desk or at either Branch. You can also get a <a href="https://catalog.xxxx.xxxxx/selfreg" target="_blank"><b>temporary card online</b></a>. There is no charge to get a card.
You must present identification showing your current address. Any YOUR STATE resident can get a card, you do not need to live in YOUR TOWN. What is your question about accounts?
</template>
</category>
```

Do not edit the patterns, just the information between the
`<template></template>` tags.


### 2. material\_type\_attributes.aiml ###

This file allows you to set loan periods, fines, renewal limts and other information for material types, books, CDs, DVDs, etc.

For example:

```
<topic name="BOOK ATTRIBUTES">
<category>
<pattern>BKS</pattern>
<template>
<think>
<set name="itype">Books</set>
<set name="co limit">any many as you wish. No limit.</set>
<set name="lper">two weeks</set>
<set name="fine">$0.10 per day</set>
<set name="rlimit">four</set>
<set name="material type attr">BOOK ATTRIBUTES</set>
</think>
<srai>MTSORT</srai>
</template>
</category>
</topic>
```

The lines you need to edit for each material type are:

```
<set name="itype">item type, i.e. Books, CDs, DVDs, etc</set>
<set name="co limit">Number of this item that may be checked out</set>
<set name="lper">loan period</set>
<set name="fine">daily fine</set>
<set name="rlimit">number of renewals allowed</set>
```


### 3. localinfo.aiml ###

Optional. Edit this file if you want to include local news, history, etc.

### 4. contact.aiml ###

Library contact info. Configuration is like material\_type\_attributes.aiml. Add your own names, positions, deptartments, emails, etc. to the file.


### 5. hours.aiml ###

This file is somewhat complex and contains information about your hours of operation. [Follow this link](Hoursaiml.md) to learn how to customize the **hours.aiml** file.


## Bot personality and miscellaneous fun stuff: ##

These govern your bot's personality. You may include or exclude any of them as you desire.

**about\_the\_bot.aiml** (info about the bot)

**cathaiku.aiml** (infoTabby can recite cat haiku)

**chat.aiml** (misc. chat)

**controversy.aiml** (infoTabby's views on controversial topics)

**cowboypoetrygenerator.aiml** (infoTabby can generate powerful and gloomy evocations of the Old West)

**personality.aiml** (bot personality)

**miscfun.aiml** (just like it sounds, misc. fun stuff)

**pineapples.aiml** (infoTabby has some interesting thoughts on pineapples and fishsticks)

**religion.aiml** (bot views on religion)


## Passing searches to your catalog ##

infoTabby can pass searches to your catalog and to other online resources using a combination of AIML and html. The AIML files in the **Searching** folder do not need to be edited for infoTabby to pass searches; you'll need to change some URLs in the **Custom html** for this to operate correctly. [Here's how to do it!](PassingSearches.md)

The AIML files related to passing searches are:

**search0intake.aiml**

**search1udc.aiml**

**search2catalog.aiml**

**search2info.aiml**

**search3additlq.aiml**

**search4concl.aiml**