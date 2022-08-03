---
title: "Using Bash Scripts in Pipes"
slug: dirac-bash-command-line-using-bash-scripts-pipes
teaching: 25 
exercises: 10
questions:
- "Can I use scripts I write in pipes as well?"
objectives:
- "Use a Bash script we've written within a pipe."
- "Create a Bash script that reads input from other commands within a pipe."
keypoints:
- "You can include your own Bash scripts in pipes."
- "A common and useful pattern in Bash shell is to run a program or script that generates potentially a lot of output, then use pipes to filter out what you're really after."
---

Note that this pattern is quite a common one with the Bash shell: we're running a program that gives us potentially a lot of output, and we're filtering out in some way just what we're interested in.

> ## Simple is Good
> 
> Wherever possible, we should always try to simplify the code we write, removing any extraneous use of scripts or code that isn't needed. This enhances readability and makes our code easier to understand.
> 
> We've written a script that filters out output that ends in `0`. Instead of using `./filter.sh` in our pipe, what could we replace it with that would accomplish the same thing?
> 
> > ## Solution
> > 
> > ~~~
> > $ ./loop.sh | grep "dmel" | head -n 1
> > ~~~
> > {: .language-bash}
> > 
> > By using the `grep` directly in the pipe, we've removed the need for a separate script, simplifying the pipe.
> >
> 
{: .solution}

{: .challenge}
