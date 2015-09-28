# Connecting infoTabby with your catalog #

infoTabby can pass searches to your catalog and to other online resources. The results of these searches will display as a new window or tab, depending on the browser settings.

This is done using a combination of aiml and custom html.

### AIML side ###
The search argument ("searcharg") and the kind of search (author, title, keyword, etc.) are set in an aiml category:

```

<category>
<pattern>LKUP</pattern>
<template>I can look things up for you in our catalog. 
Enter the author or the title or the topic; please use the fewest possible words.
<think>
<set name="topic">LKUP</set>
</think>
</template>
</category>

<topic name="LKUP">
<category>
<pattern> * </pattern>
<that>ENTER EITHER THE AUTHOR * FEWEST POSSIBLE WORDS</that>
<template>Let's see what's in our catalog. If you don't see the results, you'll need to turn off your pop up
blocker and ask me again.
<think>
<set name="searcharg"><star/></set>
<set name="search">catkey</set>
</think>
</template>
</category>
</topic>

```


In the second category above, the search argument is set by
**`<set name="searcharg"><star/></set>`** and the kind of search is set by **`<set name="search">catkey</set>`**. ("catkey" in this case is a keyword search through all formats and locations.)

Many of these categories are have already been written and are in the **guidedsearch.aiml** and **newsearching.aiml** files. You can add or edit these as you wish, but they will provide a good basis for your bot.

### Custom HTML side ###
So how does this get passed to the catalog? By using some conditions embedded in the custom html files:

```

<condition name="search" value="catauth">
<script language="JavaScript">var myWindow =window.open
'http://catalog.mentorpl.org/search/a?SEARCH=<get name="searcharg"/>');
</script>
</condition>

<condition name="search" value="catcall">
<script language="JavaScript">var myWindow =window.open
('http://catalog.mentorpl.org/search/c?SEARCH=<get name="searcharg"/>');
</script>
</condition>

<condition name="search" value="catisbn">
<script language="JavaScript">var myWindow =window.open
('http://catalog.mentorpl.org/search/i?SEARCH=<get name="searcharg"/>');
</script>
</condition>

<condition name="search" value="catkey">
<script language="JavaScript">var myWindow =window.open
('http://catalog.mentorpl.org/search/X?SEARCH=<get name="searcharg"/>');
</script>
</condition>

<condition name="search" value="catsubj">
<script language="JavaScript">var myWindow =window.open
('http://catalog.mentorpl.org/search/d?SEARCH=<get name="searcharg"/>');
</script>
</condition>
```

You will need to replace **`http://catalog.mentorpl.org/search/d?SEARCH=`** with your own catalog's URL and scoping in the conditions in the **input.html** file.

### Important note ###

We have become aware of an issue when using browsers other than IE. Using ampersands to formulate more specific searches will function correctly in IE, but not in Chrome, Firefox, or Safari. For example:

```
<condition name="search" value="dvdtitle">
<script language="JavaScript">var myWindow =window.open
('https://catalog.mentorpl.org/search/?searchtype=t&amp;SORT=D&amp;searcharg=<get name="searcharg"/>&amp;searchscope=2');
</script>
</condition>
```

can be used to find a DVD title. The results will display correctly in IE, but will yield an error message in other browsers. We are working to correct this issue.