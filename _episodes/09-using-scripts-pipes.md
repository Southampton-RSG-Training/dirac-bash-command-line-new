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

~~~
$ ./loop.sh | grep "dmel" | head -n 1
~~~
{: .language-bash}

> ## Simple is Good
> 
> Wherever possible, we should always try to simplify the code we write, removing any extraneous use of scripts or code that isn't needed. This enhances readability and makes our code easier to understand.
> 
> We've written a script that filters out output that ends in 0. Instead of using ./filter.sh in our pipe, what could we replace it with that would accomplish the same thing?
> 
> > ## Solution
> > 
> > ~~~ bash
> > $ ./loop.sh | grep "dmel" | head -n 1
> > ~~~
> > {: .language-bash}
> > 
> > By using the grep directly in the pipe, we've removed the need for a separate script, simplifying the pipe.
> >
>{: .solution}
{: .challenge}

> ## Exploring More `ls` Arguments
>
> What does the command `ls` do when used with the `-l` and `-h` arguments?
>
> Some of its output is about properties that we do not cover in this lesson
> (such as file permissions and ownership), but the rest should be useful
> nevertheless.
>
> > ## Solution
> >
> > The `-l` arguments makes `ls` use a **l**ong listing format, showing not
> > only the file/directory names but also additional information such as the
> > file size and the time of its last modification. The `-h` argument makes
> > the file size "**h**uman readable", i.e. display something like `5.3K`
> > instead of `5369`.
> 
{: .solution}

{: .challenge}

> ## Differences between remote and local system
>
> It's important to be able to distinguish whether you're on your local machine or a remote
> machine, and if you're connecting from either a Linux or Mac terminal it can be easy to forget!
> 
> If you're on either of these machines, open a second terminal window on your local computer
> and run the `ls` command without logging in remotely. What differences do you see?
>
> > ## Solution
> >
> > You would likely see something more like this:
> >
> > ~~~ python
> > Applications Documents    Library      Music        Public
> > Desktop      Downloads    Movies       Pictures
> > ~~~
> > {: .language-python}
> >
> > In addition, you should also note that the preamble before the prompt (`$`)
> > is different. This is very important for making sure you know what system
> > you are issuing commands on when in the shell.
>{: .solution}
{: .challenge}

