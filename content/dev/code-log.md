---
comments: false
date: "2018-08-20"
draft: false
noauthor: false
share: false
title: "Code log"
type: "page"
weight: 111
---


This is just a code log, where I put code discoveries, problems, etc.


# Augusgt 17th, 2O18

The happiness of Javascript and dates. First, months in Javascript start at 0 : 

```javascript
new Date(2018,1,1) // this is the 1st of February...
```

Next there is no week number available, you need to build your own.

```javascript
// Returns the ISO week of the date.
Date.prototype.getWeek = function() {
  var date = new Date(this.getTime());
   date.setHours(0, 0, 0, 0);
  // Thursday in current week decides the year.
  date.setDate(date.getDate() + 3 - (date.getDay() + 6) % 7);
  // January 4 is always in week 1.
  var week1 = new Date(date.getFullYear(), 0, 4);
  // Adjust to Thursday in week 1 and count number of weeks from date to week1.
  return 1 + Math.round(((date.getTime() - week1.getTime()) / 86400000
                        - 3 + (week1.getDay() + 6) % 7) / 7);
}
```
(found [on weeknumber.net](https://weeknumber.net/how-to/javascript))

And this week management made me discover how special is 2018, since the 1st of January is a monday, **if you start your week on monday or on sunday**, your week number _is not the same_... Who starts a week a sunday (except MongoDB database btw)?

