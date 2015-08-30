---
layout: post
title: "First Post"
date: 2015-08-30
categories:
---
Welcome to the class.

They say that a first impression is the strongest impression. I'm currently reading the book "Blink", by Malcolm Gladwell (author of "The Tipping Point"), which speaks only of this phenomenon for 300 pages. A good read, actually, I highly recommend it, though it does come off a little bit like Stephan Wolfram's book "A New Kind of Science" (which is also worth reading).

I digress. What does this have to do with Professor Downing's class, CS 371P (Object Oriented Programming) at UT?

Glenn Downing is an award-winning teacher. He's worked at JPL, Los Alamos, and MCC, he's won three teaching awards, and he holds a patent in a "System and method for initializing variables in an object-oriented program". He has a daughter that he's very proud of, he seems like a great guy to be around, your typical case for teacher of the year.

Except that he's wrong.

I have a personal bias against C++, and I have a personal bias against people who put their curly braces after their return statement:
```
int main() {
   cout << "Hello, world!" << endl;
   return 0;}
```
How can I trust someone who does that?

But on a serious note, putting code into a header file is wrong. It leads to multiple dependency errors in large projects, in the case where you have 2 C++ files, each of which includes the same header, and then the two C++ files are later linked together.

In the particular case of the class, it only became an issue because of the way gcov aggregates its statistics on a per-file basis, and the makefile for the class was checking the C++ file for the coverage statistics of the function in question, not the header file:
```
$ gcov -b ./Coverage2.c++ | grep -A 5 "File 'Coverage2.c++'"
instead of:
$ gcov -b ./Coverage2.c++ | grep -A 5 "File 'Collatz2.h'"
```

On the other hand, Professor Downing does the unique practice of calling on people in class. I think this practice is wonderful and should be in all classes - it forces a student to think, on the spot, about a problem, like triage. I'm not a fan of competitive coding, hackathons, or that type of thing, because I find them too stressful of a hobby (if you want me to be stressed, you have to pay me, and a prize is not money in the bank). But one thing that they teach is the ability to triage a situation and go in a direction, and not freeze or over-analyze.

I should speak some words also about how this class seems to be emphasizing the tools more than the programming itself. Namely, Github, Travis CI, gcov, doxygen, etc. Personally I think any programmer worth their weight in gold [1] should be able to pick up these tools in any given weekend, so a class is pointless.

So what I see is that I have issues with the material presented in class, but the material is well-taught. I opened talking about first impressions - we've only had two classes so far, and no homework or projects, so I'm going to keep an open mind and we'll see how this next project goes.


[1] $16,524/LB at time of writing, $3.2 million for the average male and $2.7 million for the average female, which coincidentally matches the lifetime earnings of a male or female ($3.5 million and $2.9 million, respectively) with a PhD, according to [a 2009 report by the Georgetown University Center on Education and the Workforce](https://www2.ed.gov/policy/highered/reg/hearulemaking/2011/collegepayoff.pdf) page 10. New theory: Women are not discriminated against because of their gender, but because of their weight.
