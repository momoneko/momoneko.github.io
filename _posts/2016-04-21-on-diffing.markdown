---
layout: post
title:  "Write diffable code"
date:   2016-04-21
categories: programming cheats
---

For a long timeI have been suspicious of diffing two source code. Never
understood how diffing two files help you to understand what exactly has
changed unless you actually know the code and can see almost at a glance what
happens and you don't really need diffing any longer. (Obviously, diffing is
very useful for patching, but that's not for human consumption).

Now I have understood its power and how awesome it is. I did not understand
diffing because I was writing my code in a bad way. I did not try to separate
it into what happens and what I shouldn't care about. After a long time
learning all that I have come to appreciate diffs. And now I can look at a
diff and not care about the codebase. If it's good code, the diff will make it
all clear.

It's dumb making this public. But this is a reminder for myself. Write diffable
code. You won't need the rest if all you want is the difference.
