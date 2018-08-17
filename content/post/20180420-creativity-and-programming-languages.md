---
title: "Creativity and programming languages"
date: 2018-01-28
image: img/cage-creativity.jpg
categories: ["science","code"]
tags: ["podcast","code","creativity","La horde du contrevent"]
---

Since the second half of the 20th century, we know that every language in which we can write a Turing Machine is a language with which we can write every single possible algorithm ever possible to write. Another way to say it is that since many years we know that all the programming language are equivalent, no one is able of more than any other, end of the story.

![Drop mic](/img/dropmic.gif)

As a consequence we could live happy in a world where every programmer is using the same language to talk to machines but it's absolutely not the case. [According to Wikipedia](https://en.wikipedia.org/wiki/List_of_programming_languages), there is more than 700 languages (and with no doubt all programming language ever created is not in this page). And it's only the _programming languages_, we can add libraries that sometimes modify so much a programming language that you can't recognize it.

![Timeline of programming languages](/img/programminglang-timeline.jpg)

Programming languages are actually the hidden place of a huge creativity. I love art, cinema, theater and it's in this particular field that I've been the most surprised by all the new idea we can discover.

If you don't believe me, this post is for you, I'll try to answer to these three questions : 

> Why do we still create new languages?
> 
> Are they really different?
> 
> Why is it a creative activity?

## The ultimate programming language

The ultimate programming language has been tried long ago and it didn't stop the creation of new ones. Every programmer has his favorite language so this is not to start a war, I'm talking of an _ultimate programming language_ as a perfect idea that the language [LISP](https://en.wikipedia.org/wiki/Lisp_(programming_language)) illustrate perfectly in my opinion. This language is born in 1958 and as so is one of the first programming language ever created (14 years before [C](https://en.wikipedia.org/wiki/The_C_Programming_Language) and 32 years before [Python](https://en.wikipedia.org/wiki/Python_(programming_language)) that you probably know for example). Its syntax is very simple, parenthesis, functions arguments... and that's all!

```lisp
(fonction arg1 arg2 arg3)
```

People think LISP is an ultimate language because some of his core concepts come directly from the dreams of [Ada Lovelace](https://en.wikipedia.org/wiki/Ada_Lovelace) : There are no differences between the data (inputs of our algorithms) and the language in which we process these inputs (the code we write). To put it in another way, we can use this language to modify its own behavior and adapt it to every problem.

LISP, created in 1958 can not only do everything (you can code a Turing pachine) but it is also possible to modify its syntax as you need to adapt to your problem. Why would we need new languages after this one?

For reasons that are very similar to why it is powerful : LISP is hard to read, hard to use, hard to master and not necessarly the most efficient language for every application.

We must not judge a programming language only by what it can do or by its efficiency to do it but also by its ability to communicate an idea, an algorithm, to a computer. And, as it's sometimes forgot, to communicate these algorithms to others humans!

> Believing that we need only one programming language is like believing only one art form is sufficient to communicate any idea. It's believing we should stop making movies, tv shows, comics, music because we already have books and it's good enough.

## The best way

[Godel, Escher & Bach](https://www.amazon.com/G%C3%B6del-Escher-Bach-Eternal-Golden/dp/0465026567/ref=sr_1_1?ie=UTF8&qid=1534543794&sr=8-1&keywords=godel+escher) is a famous book which try to connect the mathematician Godel, the artist Escher and the musician Bach. In the introduction to the french version, written by the author, Douglas Hofstadter explain that this french version is not an inferior version, neither a copy of the original version that would have lost some concepts during the process. No, he worked with the translators to make the same book, but in french. He presents this version as another projection of his ideas and that probably by reading the two version (if ever you are fluent in the two languages) you would get closer to the idea he wanted to trasnmit.

A book or any work of art is only the transmission, as good as possible of what was of a mind of an artist. And sometimes some bugs occurs : When Sam Ramy presents his horror movie [Evil Dead](https://www.youtube.com/watch?v=dtsK7skqk9U) and the public laugh in some scenes where it was supposed to be scared, it's a bug (that will be used a lot in the following episodes).

Many work of art appears nowadays in several formats, sometimes freely adpated. [The Martian](https://www.amazon.com/Martian-Young-Readers-ANDY-WEIR/dp/1785034677/ref=sr_1_8?ie=UTF8&qid=1534544231&sr=8-8&keywords=the+martian) first a book is getting stressful and addictive as an audiobook when the main character is telling us, day by day what happen to him. And of course the movie presents incredible sight seeings.

Some other work of art seem to be stuck to one specific format. In [Flowers for Algernon](https://www.amazon.com/Flowers-Algernon-Daniel-Keyes/dp/015603008X/ref=sr_1_1?ie=UTF8&qid=1534544373&sr=8-1&keywords=flowers+for+algernon), we read the journal of a retarted person who is having a treatment to enhance his IQ. In the begining of the book the writing is very hard to follow and as we turn the pages, the writing evolve with the narrator IQ.

Some writers use their medium to the limit. As if limited by their own language, they invent a new one. In [La horde du contrevent](https://www.amazon.com/Horde-Contrevent-Sc-Fiction-French-ebook/dp/B01A6X03EI/ref=sr_1_1?ie=UTF8&qid=1534544565&sr=8-1&keywords=damasio+horde), Alain Damasio invent a syntax to describe the wind. With commas, parenthesis and other signs we can see the wind move, hit and kill on the pages of the book.

![La horde du contrevent](/img/horde.jpg)

Artists have in every epoch ask the question a programmer starts with : what is the best way to tell my story? 

> If programming was only about communicating to a computer, no programmer would invent new syntax, new language to describe what he is doing to his peers. A computer doesn't care about that, it's a machine after all.

## Think different

This far you must understand that there are several languages but, after all, what can make all these languages different? It's still some cooking recipies, a list of instruction, some operation that we repeat, other done if some conditions are validated, etc. 

So of course you can write 


```javascript
if(condition){action1();}
```

or

```ruby
action1() if condition
```

but it's maybe not a good justification for such a post...

If the only differences between languages were this kind of small syntaxic changes, it would be pointless. But developers are way more creative.

Let's take an example : How to color a map with France, Belgium, Switzerland and Germany with 3 colors (Red, Blue, Green) without having two adjacent regions with the same color?

Writing a _cooking recipe_ to solve this problem would be quite long as we would do what we are doing by hand : We try a color for the first country, use a différent one for the next one, etc. If at one point it's impossible, we go back and we change the colors.

Another way to solve this problem is to use a _declarative language_. For example, with [Prolog](https://en.wikipedia.org/wiki/Prolog), we can write the following code  : 

- First we describe the fact that our colors are not the same

```prolog
different(red,green). different(red,blue).
different(green,red). different(green,blue).
different(blue,red). different(blue,green).
```

- Next, we describe which are the neighbouring countries

```prolog
coloring(France,Belgique,Suisse,Allemagne):-
different(France,Belgique),
different(France,Suisse),
different(France,Allemagne),
different(Belgique,Allemagne),
different(Suisse,Allemagne)
```

- Finally, we ask for the solution

```prolog
coloring(France,Belgique,Suisse,Allemagne)
```

Where is the algorithm? That's exactly what seems magic with this way of programming : the algorithm **is** the description of the problem! We call this kind of language _declarative_, we declare some rules and after that we can ask questions. One of the most popular declarative language is [SQL](https://en.wikipedia.org/wiki/SQL), a language use by most of the databases.

There is no restriction on how should work a programming language. The only limits are the programmers imagination. For example in the programming language [Haskell](https://www.haskell.org/), we can define infinite lists! Of course a computer can't display all the elements of the list and crash if we ask for it but the programming language is _lazy_, as far as we don't ask, he doesn't try.

There are also programming language that are real exercice of style like the _Shakespeare Programming Language_ where we code as if we were writing a Shakespeare play. For example this program writes "Hello World".

```
[Romeo](https://en.wikipedia.org/wiki/Romeo "Romeo"), a young man with a remarkable patience.
[Juliet](https://en.wikipedia.org/wiki/Juliet "Juliet"), a likewise young woman of remarkable grace.
[Ophelia](https://en.wikipedia.org/wiki/Ophelia "Ophelia"), a remarkable woman much in dispute with Hamlet.
[Hamlet](https://en.wikipedia.org/wiki/Prince_Hamlet "Prince Hamlet"), the flatterer of Andersen Insulting A/S.

Act I: Hamlet's insults and flattery.
Scene I: The insulting of Romeo.
[Enter Hamlet and Romeo]
Hamlet:
You lying stupid fatherless big smelly half-witted coward! You are as
stupid as the difference between a handsome rich brave hero and thyself!
Speak your mind!
You are as brave as the sum of your fat little stuffed misused dusty
old rotten codpiece and a beautiful fair warm peaceful sunny summer's
day. You are as healthy as the difference between the sum of the
sweetest reddest rose and my father and yourself! Speak your mind!
You are as cowardly as the sum of yourself and the difference
between a big mighty proud kingdom and a horse. Speak your mind.
Speak your mind!
[Exit Romeo]
Scene II: The praising of Juliet.
[Enter Juliet]
Hamlet:
Thou art as sweet as the sum of the sum of Romeo and his horse and his
black cat! Speak thy mind!
[Exit Juliet]
Scene III: The praising of Ophelia.
[Enter Ophelia]
Hamlet:
Thou art as lovely as the product of a large rural town and my amazing
bottomless embroidered purse. Speak thy mind!
Thou art as loving as the product of the bluest clearest sweetest sky
and the sum of a squirrel and a white horse. Thou art as beautiful as
the difference between Juliet and thyself. Speak thy mind!
[Exeunt Ophelia and Hamlet]

Act II: Behind Hamlet's back.
Scene I: Romeo and Juliet's conversation.
[Enter Romeo and Juliet]
Romeo:
Speak your mind. You are as worried as the sum of yourself and the
difference between my small smooth hamster and my nose. Speak your
mind!
Juliet:
Speak YOUR mind! You are as bad as Hamlet! You are as small as the
difference between the square of the difference between my little pony
and your big hairy hound and the cube of your sorry little
codpiece. Speak your mind!
[Exit Romeo]
Scene II: Juliet and Ophelia's conversation.
[Enter Ophelia]
Juliet:
Thou art as good as the quotient between Romeo and the sum of a small
furry animal and a leech. Speak your mind!
Ophelia:
Thou art as disgusting as the quotient between Romeo and twice the
difference between a mistletoe and an oozing infected blister! Speak
your mind!
[Exeunt]
```


And, as strange as it is, this language is powerful enough to write a Turing machine, and as a consequence any algorithm can be written with it. Yes, Microsoft World can be written in Shakespeare Programming Language, and it would be quite amazing.


## Human communication

There are a lot of differences in programming languages as the previous one. And if you can find a lot of programming languages that's partly because of these kind of design choices. It even seems that some paradigms of programming languages have the same roots as the cultural differences in human communication.

In the book [The Culture Map](https://www.amazon.com/Culture-Map-Breaking-Invisible-Boundaries/dp/1610392507/ref=sr_1_1?ie=UTF8&qid=1534546316&sr=8-1&keywords=the+culture+map), Erin Meyer presents 7 criterias to analyse cultural differences : 

- **communication :** is the context very important or not
- **feedback :** direct or indirect negative feedback
- **leading :** egalitarian or hierarchical
- **deciding :** consesual or top down
- **trusting :** according to what is done or via our relationships
- **disagreeing :** controntation or avoiding confrontation
- **time management :** linear or non-linear

These criterias seems to correspond also to important programming designs.

For example, some libraries use a _high context_. In [Ruby on Rails](https://rubyonrails.org/), only writing `has_many :friends` in a file named `user.rb` is enough for the tool to understand that we have a database named `Users` and another one `Friends` and that the database `Friends` will store a reference to the `Users` database for each entry. So with only a small line of code we avoid lines of descriptions. And as human communication, this kind of high context suppose that everyone is sharing the same context or some problems will occur quickly.

How to make feedback is also a classical difference between languages. _Variables_ have what we call a _type_. For example `1` is an integer and `"1"` a string. Some programming languages are nice, you can write `1+"1"` and the language will convert the string in integer to do the sum. Other will be more strict and crash because they can't add a string and an integer.

More interesting even is the time management. As a cooking recipe, we can think as a programming language as a linear time algorithm where we do the operations line by line in order. But some languages start the next line without waiting for the previous one to finish, they are asynchronous.

These are only some examples of the differences between languages. Creating a language follow most of the time a need of communicate something in a particular way. We can find the same with books, some authors create a new world full of imaginary creatures to tell their story.

What is surprising with programming language is that other people will use these weird creations and make it their main tool, even if it requires a lot of adpatation. If very few world created by authors are used by others, for programming language it's very common. Most of the programmers can use several languages and adapt their choice to their needs. It's as if a writer decided to use Italian to write his romance and switched to english for his thriller.

## Communicate with machines

New languages are of course created also to make execution by machines more efficient. 

With the internet and the Web, it's rarely only one computer which is processing the data but way more in parallel. As a consequence, these last years programming language have been created to make this task easier.


As a conclusion, there are a lot of programming languages and there will probably be a lot more in the future. Because culture changes, because habits change, because needs change, because it's intersting, because it's entertaining, because it's one of the way humans have found to express their creativity.






### Notes

This is a translation of [Podcast Science 319](https://www.podcastscience.fm/dossiers/2018/04/20/creativite-et-langages-de-programmation-2/), a weekly popular science podcast in french.


### Références
- [A lot of different syntaxes to do the same thing](https://en.wikipedia.org/wiki/Semantics#Computer_science )
- [Programming languages comparison](https://en.wikipedia.org/wiki/Comparison_of_programming_languages)
- [Seven languages in seven weeks](https://www.amazon.fr/Seven-Languages-Weeks-Bruce-Tate/dp/193435659X/ref=sr_1_1?ie=UTF8&qid=1524127105&sr=8-1&keywords=seven+languages+in+seven+weeks)
