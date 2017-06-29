# data1030.github.io


## Contributing
To start working with this project in OS X, install Hugo and then checkout the source branch.

### Getting started
```bash
  brew install hugo
  git clone https://github.com/data1030/data1030.github.io.git
  cd data1030.github.io
```

To run a local server, use the command

```
hugo server
```

### Editing the course website
To push changes to the the course website you will need to update the `docs` folder and push that subdirectory to
the `master` branch. *This is a workaround to an unfixable problem.*

Run the following to do so
```
  hugo # Generates the files in the docs folder
  . # Make your commit here
  .
  .
  git subtree --prefix=docs push origin master
```

### File Organization

The course schedule on the homepage can be edited by modifying the HTML files in the `layouts/modules` directory.
This is suboptimal and should be changed in the future.
All other files should be added to the contents folder.

See https://gohugo.io for more information.



  
