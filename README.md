# Development References

I’m using this wiki as a references informations of various development related subject.

There’s nothing secret in there and as a developer I thought it may be useful for other developers too. If writing code is what you do all day long, (or all night long for others), you will probably find something interesting in there at some point. 

This is a Wiki build using [Gollum](https://github.com/gollum/gollum) written in [Markdown](http://en.wikipedia.org/wiki/Markdown).

## Installation
```
$ git clone https://github.com/jpsirois/references-development.git
$ cd references-development
$ bundle install
```

## Usage
```
$ gollum
```

There’s also a nice live-preview option to gollum for editing you can use by launching it like this:
```
$ gollum --live-preview
```

Once launched your Git powered Wiki is running at `http://0.0.0.0:4567/` with [Puma](https://github.com/puma/puma).

## Why Gollum
I decided to use directly use the Gollum engine instead of built-in version in GitHub to be able to enjoy more all the features provided by GitHub, issues refecencing in commit, inline comments, pull-request, fork, better Git history stats, etc…

## License
© 2014 licensed under a [MIT license](http://jpsirois.mit-license.org/license.html).
