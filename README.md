# Notes From Reading the Vim Manual
## Intro
### Vim
I have been using vim for some years now. It is only recently, when I started
working I started to seriously look into it. Vim is a very powerful and
opinionated editor. I want to learn a lot about it. OK now it's time to ditch
this document if you don't agree with me, we are still friends and everything
is still fine.

### Vim manuals
I knew the most basic ways to use vim before I started reading the
[manuals][manual]. I am not sure how suitable this will be for a person who is
just starting to learn vim. I will try to explain where I am referencing stuff
if I find it necessary.

The manual for vim is not the easiest way to start vim. It is very vim style.
For me, the experience has been: I wanna learn vim -> I read manual -> I start
reading some instructions how to read the vim manual. Then we can go backwards
to learn vim. :) We can go to the vim manual by typing `:help` in vim's command
mode. The **home** page for vim's manual consists of three sections:

- BASIC
- USER MANUAL
  - Getting Started
  - Editing Effectively
  - ...
- REFERENCE MANUAL
  - General Subjects

The sections are meant to be suitable for different use cases. If we compare
the level of advanceness, we would have BASIC `<` USER MANUAL `<` REFERENCE
MANUAL. This does not mean that the things covered are mutually exclusive
between the sections.

I am going to write about some of the useful commands I learned while digging
through the manuals. quickref.txt

## User manual
### 04.1 Motions
"e" moves the curser to the end of the work you are currently at. If you
specify a number `n` before "e", vim jumps to the end of the `n`th word.

The difference between "d2w" and "d2e",
```
You need a computer.
    ^
```

After "d2w",
```
You computer.
    ^
```

After "d2e",
```
You  computer.
    ^
```

"$" moves the curser to the end of the line. The use case for this is simple,
after "d$" (note that "$" in inclusive)
```
You
   ^
```

## 04.2 Changing text
When it comes to "c" command, which is the changing text character, it does not
matter if you use "c2e" or "c2w" to replace two words. Let's start with the
good old example,

```
You need a computer.
    ^
```

After "c2w",
```
You computer.
```

After "c2e",
```
You computer.
```

## 04.3 Now repeat
How to use "."? We need to embrace its power and make most use out of it!
So what is it for? It repeats the last command you ran. Looking the example
from the manual, we want to remove the \<B\> tags from the line,

```
To <B>generate</B> a table of <B>contents.
```
We can do "/<", "df>", "n", ".", "n", "." on the line.

## 04.4 Visual mode
In block visual mode, try out "o" and find something exciting!

In line visual mode, while having something selected, you can press "o" to jump
to the other end of your selected words, while keeping your text selected.
When is this going to be useful? I need to try this out and come back to
this section after I find something exciting!

SWAPPING TWO CHARACTERS

Frequently when you are typing, your fingers get ahead of your brain (or the
other way around?).  The result is a typo such as "teh" for "the".  Vim
makes it easy to correct such problems.  Just put the cursor on the e of "teh"
and execute the command "xp".  This works as follows: "x" deletes the
character e and places it in a register.  "p" puts the text after the cursor,
which is after the h.

```
teh     th     the
 x       p
```

## 04.8 Text objects
Ever find yourself in the middle of a word and want to delete that word? Use
"daw" which stands for "Delete A word"!

Ever find yourself in the middle of a sentence and want to delete the whole
sentence? Use "dis" which stands for "Delete A Sentence"!

For more text objects see motion.txt:6. Text object selection.
