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

# October 18th, 2018

I wanted to transform in a JSON in complex cases with nested elements. And surprisingly I couldn't find a method to do that on Google. Here is the method I used.

## The problem

Thanks to JQuery `serializeArray` method, I have a list of key values, for example : 

```javascript
data = [
    {name: "key1", value: "value1"},
    {name: "key2[key3][key4]", value: "value2"},
    {name: "key2[key3][key5]", value: "value3"},
    {name: "key6[key7]", value: "value4"}
]
```

and I want to convert that in a proper JSON : 

```javascript
{
    "key1":"value1",
    "key2":{
        "key3":{
            "key4":"value2",
            "key5":"value3"
        }
    },
    "key6":{
        "key7":"value4"
    }
}
```

## The solution

This kind of nested problems can be solved thanks to recurrency and the fact that modifiying a javascript object anywhere modify the object still. 

```javascript
magicparser = function(cur_output,el){
    // try a match of the type key[key2]...
    m = el.name.match(/([^\[]+)\[([^\]]+)\](.*)/) 
    if(m === null){
      // it's a direct key->val : "key"
      cur_output[el.name] = el.value;
    }else{
      // it's a key with nested key : "key[key2]..."
      if(cur_output[m[1]] === undefined)
        // so we create the entry
        cur_output[m[1]] = {}
      // and we go deeper
      magicparser(cur_output[m[1]],{name: m[2]+m[3], value: el.value})
    }
  }

output = {}
data.forEach(function(el){
  magicparser(output,el)
})
```

# October 16th, 2018

In Pandas I finally found something I'm dreaming of to vizualize data. Imagine you have a dataframe with 3 columns : 

- Money : Your money
- Year : The year you earned this money
- Product : With product generated the income

We very often want to just plot `Money` against `Year` with 3 curves and a different color for each one and a beautiful legend.

I used to do a loop for that but it's actually super easy with Pandas and the magic method `unstack` : 

```python
df.groupby(['Year','Product']).sum().unstack()['Money'].plot()
```


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

