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

# September 25th, 2018

Let's play with the fantastics `pipe` and `alias` commands.

For example if you want to look for `something` in your command line history, you can use the command :

```
history | grep something
```

Remarks on this syntax : 
- `history` is the first command, this gives you your command line history
- `|` is a special operator called "pipe" that can join input and output of commands. Here he will transmit the history to the input of `grep` which will do a research on this text.
- And `grep` will look for the word you asked in the text

Even better, since as programmers we are lazy, we probably don't want to type all that to just do a research. That's where we need `alias`. An alias is a word that will be replaced by a given code snippet.

For example with : 

```
alias hg='history | grep' 
```

When you'll now type `hg something`, it will actually execute `history | grep something`.

And if you want to keep your alias for next sessions, you have to store it in your terminal config file. If you use Zsh, it's the file `~/.zshrc`


# August 21st, 2018

Chrome insist to stay on `https` when you've been on https once... To make him understand you don't want him to force `https` you need to : 

- go to [chrome://net-internals/#hsts](chrome://net-internals/#hsts)
- In the part "Delete domain security policies" enter your domain name
- click on delete


# August 17th, 2O18

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

