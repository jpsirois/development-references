# Development References

I’m using this wiki as a references informations of various development related subject.

There’s nothing secret in there and as a developer I thought it may be useful for other developers too. If writing code is what you do all day long, (or all night long for others), you will probably find something interesting in there at some point.

## Softwares I use _(in-progress)_

* [Zsh](http://www.zsh.org/)
* [iTerm2](http://www.iterm2.com/#/section/home)
* [Sublime Text](http://www.sublimetext.com/)
* [MacVim](https://github.com/b4winckler/macvim)
  * I highly recommande using [Vundle](https://github.com/gmarik/vundle) as a bundle manager. It’s based on git repository and work really well.

## CSS
* [Ultimate Gradient Generator](http://www.colorzilla.com/gradient-editor/)

## Simple, Cheap & Efficient Development project management _(in-progress)_

* VCS: [GitHub](https://github.com/features) (nothing to say)
* Tasks & Issues: [GitHub Issues](https://github.com/blog/831-issues-2-0-the-next-generation) (free and powerful, fully-integrated in our workflow)
  * Use [ghi](https://github.com/stephencelis/ghi) for easy command-line Issues operations  
* Kanban boards: [ZenHub.io](http://www.zenhub.io) (free, integrated into GitHub with a Chrome extension)
* Documentation: [GitHub Wiki](https://github.com/blog/774-git-powered-wikis-improved) (a free .git repos, added to project repos as sub-module for easy access)
  * It is powered with [Gollum](https://github.com/gollum/gollum/wiki)
* Team Chat: [HipChat](https://www.hipchat.com/) (free for 5 users)
* Dashboard: [Dashing](http://shopify.github.io/dashing/) (if needed)
* Error tracking: [Errbit](https://github.com/errbit/errbit) (free self-hosted on [Heroku](https://www.heroku.com/))
* Uptime tracking: [Node uptime](http://redotheweb.com/uptime/) (free self-hosted on [Heroku](https://www.heroku.com/))
* Monitoring: [Cabot](http://cabotapp.com/) ???

## Guardfile files using [guard-shell](https://github.com/guard/guard-shell) & [terminal-notifier](https://github.com/alloy/terminal-notifier)
Using guard-shell allow more control. I used this for some quick and simple static websites or templates creation.

```ruby
guard 'shell' do
  watch(/(^src\/haml\/(.+)\.haml)/) do |match|
    puts match[0] + " changed at " + Time.now.strftime("%H:%M:%S") +". Re-generating HTML from HAML"
    `haml #{match[1]} #{match[2]}.html`
    `terminal-notifier -group 'haml' -title 'Regenerating Coffeescript' -message '#{match[0]}'`
  end

  watch(/(^src\/sass\/.+)/) do |match|
    puts match[0] + " changed at " + Time.now.strftime("%H:%M:%S") +". Re-generating CSS from SASS."
    `Compass compile`
    `terminal-notifier -group 'compass' -title 'Regenerating Compass' -message '#{match[0]}'`
  end

  watch(/(^src\/coffeescript\/.+)/) do |match|
    puts match[0] + " changed at " + Time.now.strftime("%H:%M:%S") +". Re-generating JS from CoffeeScript"
    `coffee -c -o assets/javascripts src/coffeescript`
    `terminal-notifier -group 'coffeescript' -title 'Regenerating Coffeescript' -message '#{match[0]}'`
  end
end
```

## Git
- [Emojis to shorten your git commit messages](https://gist.github.com/jpsirois/9238420)

## License
© 2014 licensed under a [MIT license](http://jpsirois.mit-license.org/license.html).
