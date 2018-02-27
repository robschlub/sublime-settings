# sublime-settings

This reposity helps with the setup of sublime for Python and JS development. 


## Install Sublime and Pacakage Manager

### Install Sublime
Download from https://www.sublimetext.com


### Install package manager
* Open Sublime
* ctrl+"`" (or View->Show Console)
* Paste the following into the sublime console:
  * `import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)`


### Install settings files
* Close Sublime if open
* `git clone https://github.com/robschlub/sublime-settings`
* `mv sublime-settings/.git ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User`
* `cd ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User`
* `git pull reset --hard`

On sublime text resart, all packages will be installed automatically



## Install Dependencies Globally for linting

### Python

At the console type:
`pip3 install -r python-requirements.txt`



### Javascript 

At the console type:
* `npm install -g eslint`
* `npm install -g eslint-plugin-import`
* `npm install -g eslint-config-airbnb-base`
* `cd PROJECT_FOLDER`: 
  * `npm init`
  * ln -s ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User/ProjectFiles/.eslintrc.json PROJECT_FOLDER/.eslintrc.json



### CSS
`npm install -g csslint`
* In project folder: 

  * ln -s ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User/ProjectFiles/.csslintrc PROJECT_FOLDER/.csslintrc
  * Create symbolic links in every folder that has a css


