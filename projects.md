---
layout: page
title: Projects 
permalink: /projects/

---

|Name|Description|
|---|---|
[chord-quiz](#chord-quiz)| A musical quiz app written in React.
[extinction]($extinction)| Species gone extinct in your lifetime, written in React.
[todo-list](#todo-list)| A simple, yet responsive todo app.
[bibliotik.py](#bibliotik)| An e-book downloading tool.
[trim](#trim)| An `ffmpeg` interface for video cutting.

<a name="chord-quiz"/>

## chord-quiz
Go [here](https://amascii.github.io/chord-quiz) to see it in action :).

<a name="extinction"/>

## extinction
Go [here](https://amascii.github.io/extinction) to see it in action :).

<a name="todo-list">

## todo-list
Go [here](https://amascii.github.io/todo-list) to  see it in action :).

<a name="bibliotik">

## bibliotik
`bibliotik.py` is a nice tool written in Python that helps you download books from an open directory. There are hundreds of thousands of books in said directory and searching for them is painfully slow. This tool makes it easy to search and download the titles you want. It uses BeautifulSoup to scrape the directory and generate an index file.

A test run:
```
> python3 bibliotik.py

Welcome to Bibliotik!
Search for: iliad robert fagles
0 1991 Homer - The Iliad[Transl Robert Fagles][Penguin Classics]_Rcl.azw3
1 1991 Homer - The Iliad[Transl Robert Fagles][Penguin Classics]_Rcl.pdf
2 An Iliad (Overlook) - Homer, (transl. Robert Fagles), (adapts.) Lisa Peterson, Denis O'Hare (retail).epub

Enter file #(s) to download: 0 1
1991 Homer - The I 100%[===============>]   1.45M  1.97MB/s    in 0.7s
1991 Homer - The I 100%[===============>]   9.20M  5.65MB/s    in 1.6s
Done!
Press ENTER to continue
```
Files are downloaded into the current directory.

Check it out [here](https://github.com/amascii/bibliotik).
<a name="trim">

## trim
Have you ever used `ffmpeg`?
It is a very powerful tool for handling video and audio.
However, it isn't very easy to use at first and some simple actions require a rather verbose command.
`trim.py` aims to make the process of video cutting easier.
Under the hood it still uses `ffmpeg`, but makes arguments much more intuitive.

Take the following example:
```
> trim.py in.ts out1 1:00 1:15 out2 1:30 2:00
> ls
in-out1.ts in-out2.ts in.ts
```
`in.ts` is split into two files: `in-out1.ts` and `in-out2.ts`.
The first is a 15 second cut from 1:00 to 1:15 of the original file.
Likewise, the latter is a 30 second cut from 1:30 to 2:00.
An infinite amount of cuts can be specified with `[out] [start] [end]` triplets after the input file.
Doing this with ffmpeg would look like:
```
ffmpeg -ss 1:00 -i in.ts -t 15 -c copy in-out1.ts
ffmpeg -ss 1:30 -i in.ts -t 30 -c copy in-out2.ts
```
A bit cumbersome, in my opinion.

Check it out [here](https://github.com/amascii/MiScripts/blob/master/trim.py).

