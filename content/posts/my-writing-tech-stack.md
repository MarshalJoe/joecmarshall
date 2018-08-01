---
title: "My Writing Tech Stack"
date: 2018-07-31T18:56:18-05:00
draft: false
---

All writers have their own workflows for writing: Many people use Word, Google Docs, or Libre Office - George R.R. Martin famously uses [WordStar](http://www.slate.com/blogs/future_tense/2014/05/14/george_r_r_martin_writes_on_dos_based_wordstar_4_0_software_from_the_1980s.html), a DOS-based text-processing system from the mid-80s. As long as your personal productivity is juiced and you're comfortable, you can be as idiosyncratic as you want. Somewhere a hardcore cypherpunk is writing the next crytographic epic in vim.

In that spirit, I've evolved my own writing process over time as I've looked for a workflow that minimized application overhead, allowed me to translate documents between formats, provided robust version tracking, integrated well with other tools, and worked offline. There are several parts to the stack.

## Markdown for Everything
I'm am big fan of Markdown, which is [insanely easy to learn](https://joecmarshall.com/posts/1-minute-markdown/). Pegging my rich text formatting to Commonmark (e.g. Github) Markdown allows me to write a single plain text document (which can be transmitted anywhere you can send plain text, which is to say everywhere) and then make it an HTML document, PDF, doc, rtf, or any other file format I can dream up. Critically, this means that I can use the same text formatting system *anywhere* and never have to lose productivity to a learning curve. Considering I can also use Commonmark on Github (my professional platform where I do most of my work) and other major technical apps, it's the single system that gives me the greatest interopability between content outlets. And it's *fast*. Being able to write with an extended punctuation, instead of manually highlighting text and using a WYSIWYG menu to choose a style, is a much cleaner, nmore seamless experience.

## Sublime Text Processing
For text processing, I love Sublime Text 3. I already use it for a lot of coding and there are several Markdown-themed packages (like `MarkdownPreview` and `MarkdownExtended`) that not only give me a nice text processing experience, where *italics*, **bold**, and other types of formatting are automatically applied as I write, but that also allow me to preview Markdown documents in-browser and generate HTML from my Markdown document. 

## Versioning and Resiliency
Everything I've described is just plain text - why not keep it in a repo and apply `git` to keep it versioned and backed-up to a redundant remote? This is a workflow I already use a professional developer, and all the advantages that acrue to a versioned codebase apply here: versioning allows for individual changes to be isolated and makes it easier to understand how the project has evolved over time; it allows for easy scripting and integration with other tools (like Sublime); and makes it trivial to push the contents of the repo to multiple, independent, stores. For example, if a project is particularly important, or it's something more sensitive like my personal notes, I can push the repo to both my Github and Bitbucket accounts.

## Integrations With Other Tools
Unix is all about plain text! There are several stock CLI tools you can use to get things like word count, character count, and other basic info. Here's a short wrapper I wrote around `wc` to print out the word count of all the `txt` files within the directory where the script is called:

```
#!/bin/sh

total=0

for FILE in `find . -type f -name "*.txt"`

do
    wc -w $FILE
    words=`wc -w < $FILE | tr -d ' '`
    total=$(($total + $words))
done

printf "%'d" $total

echo " words"%
```

I use the convention of keeping files that I want to track as `txt` files, so that if I'm working on a book or large project, I can get the aggregated word count for everything ending in `txt`. If I have personal or "scratch" notes, or something to otherwise exclude I can just create it as a `md` file and still leverage the common tool suite. What did I name this script? `txt.sh` of course!

## And It Works Everywhere
I can write anywhere because Sublime Text doesn't need much to run. I own a license for Sublime, but could just as easily use the free version, and never need to worry about whether I have an Office license that can decode a proprietary Microsoft file extension. I can also do without Sublime (I'm used to seeing the Markdown as written, with the punctuation formatting included) and simply write it anywhere I can write plain text: In an email draft, in my personal Slack notes, or anywhere else a text field is available.

Those are just some of the reasons that I really enjoy a Markdown-heavy, plain text-for-everything, git-versioned workflow that piggybacks on tooling meant for code. 

Being able to [write an entire book in Markdown](https://leanpub.com/), pushing new builds on a branch update, or getting a clear and expressive formatting system for low-overheard high-availability applications like static site generators - at this point, they're just a welcome bonus to adopting an already-empowering workflow. 

This workflow has served me well as a professional writer, including for my upcoming first book about penetration testing, [Hands-On Bug Bounties For Penetration Testers](https://www.amazon.com/gp/product/1789344204/ref=as_li_tl?ie=UTF8&tag=bughunt-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=1789344204&linkId=d0166c1e6990155b2e00db633c3e27d3). I'd be lost without it.
