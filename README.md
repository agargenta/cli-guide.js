# CLI Guide jQuery Plugin

[GSoC 2015 Project](http://www.google-melange.com/gsoc/project/details/google/gsoc2015/marti1125/5757334940811264)

A Javascript library for creating interactive command line tutorials that run in your web browser.

Necessary Files
-----------------

### Libs

* [jQuery](https://jquery.com/download/)
* [Prism](http://prismjs.com/download.html)

### Fonts

* [Segoe UI Symbol Regular](http://openfontlibrary.org/en/font/segoe-ui-symbol)
* [Code New Roman Regular](http://openfontlibrary.org/en/font/code-new-roman)


Demos
-----

* [Apache Aurora](http://twitter.github.io/cli-guide.js/demo/aurora.html)


Documentation
-------------

#### Example

    $('#stepsdiv').cliguide({
        nameOfTheProject: 'Apache Aurora'
    }).cli({
        stepsFile: 'templates/apache_aurora.json',
        commandStepsFile: 'templates/apache_aurora_commands.json',
        preloadfile: 'templates/apache_aurora_files.json'
    }, function(){
        //Codes in here will be runned after CLI functions run
    });

#### Options

| Property | Description | Required |
|---|---|---|
| nameOfTheProject | name of the project | X |
| stepsFile        | a .json file | X |
| commandStepsFile | a .json file | X |
| preloadfile | a .json file | optional |

#### The structure of .json files

#### stepsFile

    [
      {
        "step": "0",
        "content": {
            "title": "Setup: Install Aurora 0",
            "content": [
                " You use the Aurora client and web UI to interact with Aurora jobs. ",
                " To install it locally, see vagrant.md. The remainder of this Tutorial ",
                " assumes you are running Aurora using Vagrant. Unless otherwise stated, ",
                " all commands are to be run from the root of the aurora repository clone."
            ],
            "tips": "You can run $ <i>aurora</i> for see all commands"
        }
      }
    ]

#### commandStepsFile

    [
      {
    	  "command":"hello world!",
    	  "result": "test...."
      }
    ]

#### preloadfile

    [
     {
       "name":"test.txt",
       "content": "Hello World!"
     },
     {
       "name":"hello.py",
       "content": "print(\"Hello World!\")"
     }
    ]

Components
-------------

#### Terminal

![terminal](https://raw.github.com/twitter/cli-guide.js/master/terminal.gif)

#### Nano Editor

![nano editor](https://raw.github.com/twitter/cli-guide.js/master/nano.gif)

Build
-------------
    $ npm install
    $ gulp


License
-------

Copyright 2015 Twitter, Inc.

Licensed under the MIT License
