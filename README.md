# Set up web development environment for new Macbook (mavericks)

	I am still editing this post, welcome to give me some advices on anything :D

## 1. Install [Homebrew](http://brew.sh)

	ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go/install)"
	
It will install 'command line developer tools' at begining, so you don't need to download Xcode.

	brew doctor

Your terminal should give you this message:

> Your system is ready to brew.

## 1.5 Install Xcode

Install Xcode from Apple [app store](https://developer.apple.com/xcode/).


## 2. Install [RVM](https://rvm.io) and Ruby
Install RVM with a Rby

	\curl -L https://get.rvm.io | bash -s stable
	
**Turn off all termimals and reopen a new one**, then your RVM is already installed. You can use this commend to see the version of RVM you installed:

	rvm -v


## 3. Install Ruby(s)
List all ruby version you could install on your computer:

	rvm list known
	
Use this commend to install different versions of ruby:

	rvm install 1.9.3 --with-gcc=clang
	
It will automatically install all required packages: autoconf, automake, libtool, pkg-config, gcc46, libyaml, readline, libksba, openssl.

Install ruby 2.0:

	rvm install 2.0.0
	
Check installed rubies on your computer:

	rvm list
	
You can set ruby 2.0.0 as default ruby by using this:

	rvm use 2.0.0 --default
	
Check it again, see any difference?
	
	rvm list
	
## 3.5 Set up git

Now that you have Git installed, it's time to configure your settings. Follow this good [toturial](https://help.github.com/articles/set-up-git) from github.

Set up your default name and email address for github:

	git config --global user.name "Your Name Here"
	
	git config --global user.email "your_email@example.com"

Set up your [SSH Keys](https://help.github.com/articles/generating-ssh-keys), and then you don't need to type password every time.

	ssh-keygen -t rsa -C "your_email@example.com"
	
And then go to [SSH Key manager](https://github.com/settings/ssh), add generated hash to your github.

Run this commend on your terminal to test git set up corrently or not:

	ssh -T git@github.com
	
If you can see your username, then it means you got git on your Macbook.

> Hight recommend: [Tower](http://www.git-tower.com/) to be your Github GUI, it's so good. Bens proved.

## 4. Install [ClipMenu](http://www.clipmenu.com) - optional
Go to <http://www.clipmenu.com> and download ClipMenu, which stores clipboard histories such as plain text, rich texts format, PDF, PICT, and TIFF image. You can access in the menubar or by using hot key.

After drag application to a folder, you need to run it at least one time to activate it. 

If you Have this error:
> “ClipMenu” can’t be opened because it is from an unidentified developer

Please go to "System perferences" - "Security & Privacy" - Allow apps downloading from 'Anywhere', then run app again.


## 5. Install [SubLime 2](http://www.sublimetext.com/2)

Download Sublime 2 from: <http://www.sublimetext.com/2>

install [package control](https://sublime.wbond.net/installation) for sublime 2:

The simplest method of installation is through the Sublime Text console. The console is accessed via the **ctrl+`** shortcut or **the View > Show Console menu**. Once open, paste the appropriate Python code for your version of Sublime Text into the console.

	import urllib2,os; pf='Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler( ))); open( os.path.join( ipp, pf), 'wb' ).write( urllib2.urlopen( 'http://sublime.wbond.net/' +pf.replace( ' ','%20' )).read()); print( 'Please restart Sublime Text to finish installation')
	
Add sublime to commend line:

	ln -s /Applications/Sublime\ Text\ 2.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl
	
Try this to see your commend line for sublime is all set or not:

	subl .

## 4.5 Install Oh-My-Zsh

A community-driven framework for managing your zsh configuration. Includes 120+ optional plugins (rails, git, OSX, hub, capistrano, brew, ant, macports, etc), over 120 themes to spice up your morning, and an auto-update tool so that makes it easy to keep up with the latest updates from the community. <https://github.com/robbyrussell/oh-my-zsh>

	curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
	
You might need to restart your terminal. Let's make our terminal look better. Open config file:
	
	subl ~/.zshrc

Change theme to arrow, I personally like this theme:

	ZSH_THEME="arrow"
	
Add these plugins:
	
	plugins=(git rails sublime ruby)

## 4.6 Install tomorrow theme
