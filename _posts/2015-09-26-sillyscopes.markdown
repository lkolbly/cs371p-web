---
layout: post
title: "Sillyscopes!"
date: 2015-09-26
categories:
---
Our good friend Glenn Downing (who also happens to teach this class) read my previous post on this blog and pointed to:
[http://codeforces.com]
and
[https://www.hackerrank.com]

He teaches a competitive programming course which uses codeforces.com, and that website looked pretty cool.

We venture forward to this most recent week. This week we got our running grades for the semester back.

Most classes would give you just a single number, your average score. That number usually ends up being meaningless anyways because they're averaged poorly or because of curves.

In this class we got not only our points, but our Z-score in the class (standard deviations above or below the mean) as well as our class rank.

There are 78 people who are better than me. It was 77 this morning, but then someone got another point or something. Oddly there weren't any grades entered, that I'm aware of. One wonders.

This is a class where the rich get richer, and the poor get poorer, because the rich prey on the poor.

There are those who can write beautiful code right out of the box. Their code is modular, short, relatively clear, and works. When they write test cases, they cover the corners. Their code is bullet-proof.

Then there are those who... maybe aren't quite there yet. Their code is cobbled together and has a few bugs. Maybe they didn't quite think of everything in their tests.

This class has a system where your program is run against the acceptance test of a randomly chosen student. If your program fails, you lose two points and they gain two points. This is repeated 5 times (you can lose or gain up to 10 points).

The people at the top will be more likely to get points than those at the bottom. This is fine, but it's very cutthroat (which is why I dislike competitive programming).

I got two points from this system. I like having more points. But along the way I put down 5 people (1 person lost 2 points because of me, and I passed ~4 people in the class rank).

Personally, I feel like directly transferring points from worse students to better students works against the goal. The goal is for everyone to learn - and ideally everyone helps everyone learn. With this point system now we have a reason to not help (nay, mislead) our fellow students. With a class this big (~170 people), people are faceless and it's hard to feel guilty.

Tip of the Week: Keep track of why you do things.

I'm in CS378 Embedded Systems with Dr. Oshana, which is the best class ever and you should totally ditch OOP and go for it [1], but this week we're doing a project wherein we have to write a command line interpreter for an embedded system (via UART). Somebody on the class discussion forum was getting an error code which I vaguely recognized. I looked at what I had done and noticed this line:

```
         console_printf("%s ", g_command_line.prompt);
-    } else if (c == '\b') {
+    } else if (c == '\b' || c == 127) {
        if (g_command_line.buffer_cursor > g_command_line.buffer) {
```

So I must have changed something about backslash. But for the life of me, I don't remember what I changed or why.

And that's no use to anybody else.

So, use version control and issue tracking. It'll save you from having to remember.

[1] I might be biased because I like C and robots and I don't like C++. One class has C and robots (well, a smart car) and the other has C++. My biases should be obvious.
