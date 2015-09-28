The AIML files need to be installed in the correct order


# Using the infoTabby AIML files #

The aiml-en-us-ovrp-infotabby files contain a number of categories with duplicate patterns. Depending on the AIML interpreter used, duplicates are handled differently.

On Pandorabots the rule is: The files are loaded in order from the top of the list (under the "AIML Files" section) to the bottom. When a category is loaded that has the same pattern path (i.e. same input pattern, that pattern and topic pattern--remember that `<that>` and `<topic>` are set to implicitly), then Pandorabots discards the earlier category and selects the response template from the most recently loaded category.

To give an example: Suppose a file A.aiml has a category
```
<category> 
<pattern>TEST</pattern> 
<template>This is the response from file A.</template> 
</category>
```
and a file B.aiml has a category
```
<category> 
<pattern>TEST</pattern> 
<template>This is the response from file B.</template> </category>
```

Provided that the files are loaded in alphabetical order, the A.aiml loaded before the B.aiml, then the response to the input "Test" should be "This is the response from file B."

# infoTabby AIML File Order #

The AIML files in aiml-en-us-ovrp-infotabby should be loaded in the following order:

**•First, load:**

reduction0.safe.aiml,

reduction1.safe.aiml,

reduction2.safe.aiml,

reduction3.safe.aiml,

reduction4.safe.aiml,

reductions-update.aiml,

atomic-categories0.aiml.

**•Second, load:**

client\_profile.aiml,

salutations.aiml,

yesno.aiml

**•Then load all remaining AIML files.**

•Pandorabots will always load the file update.aiml as the last file.