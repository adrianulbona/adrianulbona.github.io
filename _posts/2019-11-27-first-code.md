--- 
layout: post
title: First Lines of Code
---

![omar](https://media0.giphy.com/media/OVtqvymKkkcTu/source.gif)

A few days ago I was thinking about how I ended up being a Software Engineer. I think it started with me asking my parents to visit on Sundays an aunt that was doing accounting and had a computer (around '97-'98) ... probably I was looking to play games. 

Soon after, I remember that one friend told me that there is place (club) in the nearby town where they have computers and you can play games. I was the _Children's Club/Palace_ (a quite neat leftover from the communist times for after-school activities). Told my dad about this and next autumn I got enrolled, I had no clue it was actually a programming class, I was just thinking about the games. It must have been '99 (3rd year of the primary). 

But there was a trick ... from the 2 hours of class, the first part learning how to code and only afterwards games. I remember that we started with [BASIC](https://en.wikipedia.org/wiki/BASIC) and after a while we switched to [PASCAL](https://en.wikipedia.org/wiki/Pascal_(programming_language)). One of the oldest files I could find is from 2000 and it looks like this: 

```pascal
program Fibonacci;
uses crt;
var x: array[1..30] of integer;
    n, i: integer;

begin
  clrscr;
  write('Pozitia in sirul lui Fibonacci: ');
  read(n);
  x[1]:=1;
  x[2]:=1;
  for i:=3 to n do
    x[i]:=x[i-2]+x[i-1];
  write('Elementul de pe pozitia ',n,' din sir este ',x[n]);
repeat until keypressed;
end.
```

I have to admit that I had a thing for intentation from back then. 

Funny, now that I reflect on how I actually started programming, it looks kind of ... random. How did you start coding? 
