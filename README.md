# data1030.github.io

## Contributing
To start working with this project in OS X, install Hugo and then checkout the source branch.

### Installation
Run the following commands to install Hugo and the source code.
```bash
  brew install hugo
  git clone https://github.com/data1030/data1030.github.io.git
  cd data1030.github.io
```

To run the site on a local server, run the command

```
hugo server
```

### Editing Quick Start
If you want to edit the home page, go to `content/_index.md`
If you want to edit individual assignment pages, go to `contents/assignments`
If you want to edit the layout of the pages, go to `layouts/_default/`
If you want to edit the CSS, go to `static/style.css`

### Pushing edits
To push changes to the the course website you will need to update the `docs` folder by first running the command `hugo` and then push `docs` to the `master` branch. *This is just a problem with how Github Pages for users/organizations works.*

Run the following to do so
```
  hugo # Generates the files in the docs folder
  git add .
  git commit -m "<YOUR MESSAGE>"
  git push origin source # Update all the code
  git subtree --prefix=docs push origin master # Update the docs folder
```

### File Organization

The course schedule on the homepage can be edited by modifying `content/_index.md`.
Examples of assignments, documents, and notes are available in the subdirectories in the `content`
folder as well.

Just add a yaml header in the following format and then add your markdown.

```
---
title: Plotting
date: 2017-06-30T13:51:17+08:00 # Due date or release date of the page
draft: true # Set this to false for the page to be 
category: notes # Set this to the type of page you are creating
---

## Motivation
...

```


A helpful command is

```
hugo new blog/test.md
```

This generates a basic empty markdown file called `test.md` in `content/blog`.

See https://gohugo.io for more information.


### Todo

* Integrate with MathJax to enable LaTex support
* Licensing
* Brown domain name


  
