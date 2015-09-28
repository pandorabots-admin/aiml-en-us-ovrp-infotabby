# Teaching your bot to tell time #

The hours.aiml file uses a formatted date tag that makes the bot aware of the time, day of the week, and date. Editing this file will be easier if you understand how it works.

When a patron asks the bot a question like, "Are you open today?" or "What are your hours?" the query goes through a number of steps to reach an answer.

1. The formatted date tag generates the date which is checked against a list of holidays. If the date matches a holiday, the user is told that the library is open or closed depending on the holiday. [on line 506](starting.md)

2. If the date does not match a holiday, the date tag generates the weekday and time (in hours, 0-23) which are matched against another list that invokes a response appropriate for that weekday and hour. [on line 659](starting.md)

3. If the question is posed after midnight, the bot will respond with the time when the library will reopen. [line 854](starting.md)


A similar process is used for users asking if the library will be open tomorrow [line 1009](starting.md) or yesterday [line 1173](starting.md).

Daily hours are set in categories starting at line 1338.

This file makes extensive use of the `<srai>` and `<topic>` tags.