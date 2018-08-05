---
title: Language expressiveness versus code maintainability
description: How different programming languages lead to different software maintenance challenges
layout: hh
tags: code maintenance
image: http://hilton.org.uk/blog/factory2.jpg
---

[![A factory - where real maintenance happens](factory3.jpg)](https://unsplash.com/photos/NGsBU5d-qxQ)

<a style="background-color:#ccc;color:white;text-decoration:none;padding:4px 6px;font-family:-apple-system, sans-serif;font-size:12px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px" href="https://unsplash.com/photos/XUEdfpPIhXg" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Crystal Kwok"><span style="display:inline-block;padding:2px 3px"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-1px;fill:white" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M20.8 18.1c0 2.7-2.2 4.8-4.8 4.8s-4.8-2.1-4.8-4.8c0-2.7 2.2-4.8 4.8-4.8 2.7.1 4.8 2.2 4.8 4.8zm11.2-7.4v14.9c0 2.3-1.9 4.3-4.3 4.3h-23.4c-2.4 0-4.3-1.9-4.3-4.3v-15c0-2.3 1.9-4.3 4.3-4.3h3.7l.8-2.3c.4-1.1 1.7-2 2.9-2h8.6c1.2 0 2.5.9 2.9 2l.8 2.4h3.7c2.4 0 4.3 1.9 4.3 4.3zm-8.6 7.5c0-4.1-3.3-7.5-7.5-7.5-4.1 0-7.5 3.4-7.5 7.5s3.3 7.5 7.5 7.5c4.2-.1 7.5-3.4 7.5-7.5z"></path></svg></span><span style="display:inline-block;padding:2px 3px">Crystal Kwok</span></a>

Some programming languages, such as Scala and Perl, aim to be as expressive as possible, giving you maximum flexibility in how you write your code.
Other languages, such as Java and Go, prefer or even force a single coding style, giving you more consistency.
On top of all of the other pros and cons of these two approaches, these choices affect code maintainability.

The good news is that neither programming language style makes it much harder than the other to write maintainable code.
The bad news is that both coding styles give you significant maintainability issues.
This article considers the trade-offs.

## Smaller code is more maintainable

The most effective way to write maintainable code is to write less of it.
Functional languages do well at maintaining code more concise, and anyone who has ported Java code to Scala will know what the most striking change is the reduction in the number of lines of code.

Other things being equal, more concise code is easier to browse and easier to change, and there are several ways to make your code more concise.
However, other things aren’t equal, so making your code more concise may end up making it less maintainable.

## Non-standard annotations harder to learn

Although Java developers have a long history of reducing repetitive lines of code, by introducing annotation-based libraries such as [Project Lombok](https://projectlombok.org).
The result is less verbose code in a non-standard dialect.

Non-standard coding idioms give you a trade-off between long-term coding efficiency and the short-term cost of teaching the style to new team members.
The choice for the most maintainable code therefore depends on how fast the team rotates.
This is hard to predict, but easier to observe: if you use a non-standard dialect, and all of your code has a consistent style, then you don’t have a problem keeping up with team rotation.
If you have code in different styles then it isn’t working.

Non-standard libraries and language extensions, such as Java annotation libraries, and JavaScript variants, such as CoffeeScript, aren’t the only way to end up with team-specific coding styles.
Some languages give you that out-of-the-box.

## Team-specific coding styles hard to preserve

The old Perl motto that [There’s more than one way to do it](https://en.wikipedia.org/wiki/There%27s_more_than_one_way_to_do_it) is both Perl’s blessing and curse.
Like Perl, Scala simultaneously supports more than one coding idiom.
This isn’t a code maintenance issue until you have more than one programmer on your team.

<blockquote class="big solid-one">
<p>Half of the Scala developers are just writing Java code.
The other half are writing Haskell.</p>
</blockquote>

You can, of course, solve this by adopting a team coding style that suits your situation.
However, these team coding styles are hard to preserve.
Over time, team members will follow different interests and grow in different directions.
With functional programming languages, in particular, it’s hard to preserve a consistent style when half (rather than all or none) of the team are also learning Haskell or a Lisp.

## Cross language styles require double the background

Multi-paradigm languages such as Scala offer the best of two worlds - object-oriented programming and functional programming.
To write maintainable code, you need to avoid the worst of both worlds.

Object-oriented programming is hard to do well.
After all, most Java code is really just procedural code in classes.
Functional programming is also hard to do well, no matter now many monad tutorials we write.
Being good at both at the same time, as a team, is even harder because there are two paradigms to learn.

C++ offers another example of a diverse language, which probably has more language versions than there are members of your development team.
Pick one.

## Team-specific approach wins

You need a team-specific coding style to achieve consistent maintainable code.
A language like Go helps you do this by [dictating what that style is](https://golang.org/doc/effective_go.html#introduction), and offering relatively little language flexibility.
Programmers learning Scala, on the other hand, frequently ask for guidance on what idiomatic Scala code looks like.
Answers are of course available, but don’t all agree with each other.

Python seems to occupy space in between: more language flexibility but with such a strong community tradition of what idiomatic Python code looks like that it has its own term - [Pythonic](https://blog.startifact.com/posts/older/what-is-pythonic.html).

## Conclusion

Languages that let you write the most concise code have the potential to be most maintainable, because brevity is a big advantage.
However, this potential advantage is all for nothing if you fail to achieve a consistent coding style, or fall prey to [naming smells](naming-smells).

The practical difficulty of writing maintainable code in more expressive languages is no doubt the secret to Java and Go’s success.
Personally, although I’d rather write Scala code than Java, I’d also rather maintain someone else’s Java code than someone else’s Scala.

_When you need help thinking through software maintenance, [contact Peter Hilton](../contact) for training in [How to write maintainable code](../training/maintainable-code)._