---
layout: post
title: "The Minority Report"
date: 2015-10-04
categories:
---
The creator of C++ (Bjarne Stroustrup) once said: "There are only two kinds of languages: the ones people complain about and the ones nobody uses."

This week we covered more about templates and we started covering lambda functions.

I personally like lambda functions. Sometimes, it is handy to have a full function that you can toss around to different functions. The C++ standard library's accumulat() and all_of() functions both take a function as a parameter. In a language like Python that lambda would be restricted to a single statement, and scoping becomes a little less clear. C++ fixes these problems and allows arbitrarily sized lambdas with clearly scoped variables.

Unfortunately, lambdas went the way of templates, and maybe could've had a little more thought put into them:

```
#include <iostream>
#include <functional>

using namespace std;

function<int(int)> foo()
{
  int i = 2;
  return [&i] (int x) -> int {return i+x+1;};
}

int main(int argc, char **argv)
{
  function<int(int)> fn = foo();
  cout << fn(5) << endl;
  return 0;
}
```

Prints out 6 on my machine. There are many camps on language design. The camp I belong to believes that the language should protect the coder in a case like this, using what JavaScript does with closures or Python with reference counting.

This blog is about the class, not the language, so I shall tie it together: This class is making me think about language design more than any other class I've taken. I don't like C++. But the professor makes an argument for it, and it makes me think hard about what it is that I like and don't like in languages.

Tip of the Week: Have experience writing big projects from scratch (>2000 lines, and multiple files). Most classes value good code but don't teach architecture, but having a good architecture is more important. Good architecture leads to good code. Bad architecture leads to code that has to work around the program it's living in, and it becomes more of a headache the further you get down the line.
