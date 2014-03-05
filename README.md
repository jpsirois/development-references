# Development References

I’m using this wiki as a references informations of various development related subject.

There’s nothing secret in there and as a developer I thought it may be useful for other developers too. If writing code is what you do all day long, (or all night long for others), you will probably find something interesting in there at some point.

## Development Softwares I use _(in-progress)_

* [Zsh](http://www.zsh.org/)
* [iTerm2](http://www.iterm2.com/#/section/home)
* [Sublime Text](http://www.sublimetext.com/)
* [MacVim](https://github.com/b4winckler/macvim)
  * I highly recommand using [Vundle](https://github.com/gmarik/vundle) as a bundle manager. It’s based on git repository and work really well.


## Development Chrome Extensions I use

* [Always Clear Downloads](https://chrome.google.com/webstore/detail/always-clear-downloads/cpbmgiffkljiglnpdbljhlenaikojapc)
* [Backbone Debugger](https://github.com/Maluen/Backbone-Debugger)
* [Chromoji](https://chrome.google.com/webstore/detail/chromoji-emoji-for-google/cahedbegdkagmcjfolhdlechbkeaieki?hl=en-GB) (configure it at 1.25 size to have it similar to what Safari render)
* [Ember Inspector](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi?hl=en)
* [Google Analytics Debugger](https://chrome.google.com/webstore/detail/google-analytics-debugger/jnkmfdileelhofjcijamephohjechhna?hl=en)
* [jQuery Audit](https://github.com/zertosh/jquery-audit)
* [JS Runtime Inspector](https://chrome.google.com/webstore/detail/js-runtime-inspector/iilpjebedgohcmlffhnkhbjhabkdhfmn?hl=en-US)
* [LiveReload](https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei)
* [MultiLogin](https://chrome.google.com/webstore/detail/multilogin/nccllfnllopfpcbjdgjdlfmomnfgnnbk?hl=en)
* [Postman - REST Client](https://chrome.google.com/webstore/detail/postman-rest-client/fdmmgilgnpjigdojojpjoooidkmcomcm?hl=en)
* [React Developer Tools](http://facebook.github.io/react/blog/2014/01/02/react-chrome-developer-tools.html)
* [Responsive Inspector](https://chrome.google.com/webstore/detail/responsive-inspector/memcdolmmnmnleeiodllgpibdjlkbpim?hl=en)
* [Web Developer](https://chrome.google.com/webstore/detail/web-developer/bfbameneiokkgbdmiekhjnmfkcnldhhm?hl=en-US)
* [YSlow](https://chrome.google.com/webstore/detail/yslow/ninejjcohidippngpapiilnmkgllmakh)
* [ZenHub for GitHub](https://www.zenhub.io/)



## CSS
* [Ultimate Gradient Generator](http://www.colorzilla.com/gradient-editor/)

## Web Developer Tools
* [console.log wrapper](https://github.com/patik/console.log-wrapper)

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

## Git

### Emojis to shorten your git commit messages
- Fix: 🔧 or 🔨
- Add: ➕ or +
- Remove: ➖ or - or ❌
- Split: ➗
- Security: 🔒
- Security breach: 🔓
- Deploy: 🚀
- Money: 💵 or 💰
- Credit Card: 💳
- Mobile: 📱
- Desktop: 💻
- Audio: 🎵
- Video: 🎥
- Energy: 🔋
- Search: 🔍
- Time: ⌛️ or ⏰ or 🕒 
- Reuse: ♻️
- Date: 📅
- Bug: 🐛 or 🐞
- Link: 🔗
- Image: 🎑 or 🌅
- Email: ✉️
- Analytics or Chart: 📊 or 📈 or 📉
- Package or Plugin: 📦
- Warning: 🚨
- Clean: 🚿 or 🛁
- User: 👤

## License
© 2014 licensed under a [MIT license](http://jpsirois.mit-license.org/license.html).
