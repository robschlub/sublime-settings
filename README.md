# sublime-settings

This reposity helps with the setup of Sublime Text 3 for Python and JS development on Mac OS X. 


## Install Sublime and Pacakage Manager

### Install Sublime
Download and install Sublime Text 3 from https://www.sublimetext.com


### Install package manager
* Open Sublime
* ctrl+"`" (or View->Show Console)
* Paste the following into the sublime console:
  * `import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)`


### Install settings files
* Close Sublime if open, and clone this repository to the Sublime package user settings directory
* `git clone https://github.com/robschlub/sublime-settings`
* `mv sublime-settings/.git ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User`
* `cd ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User`
* `git pull reset --hard`

On sublime text resart, all packages listed in `Package Control.sublime-settings` will be installed automatically.


## Install Dependencies Globally for linting

### Python

At the console type:
`pip3 install -r python-requirements.txt`

Restart Sublime Text 3 and open a python file to confirm linting errors/warnings are being displayed

Command line output of linter can be obtained by: 
* `ln -s ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User/ProjectFiles/.flake8 PROJECT_FOLDER/.flake8`
* `PROJECT_FOLDER/flake8`
>> Note: The rules in `ProjectFiles/.flake8` and `SublimeLinter.sublime-settings` need to be manually kept in sync

>> More Information:
>>
>> Flake8: http://flake8.pycqa.org/en/latest/index.html

### Javascript 

At the console type:
* `npm install -g eslint`
* `npm install -g eslint-plugin-import`
* `npm install -g eslint-config-airbnb-base`
* `cd PROJECT_FOLDER`: 
  * `npm init`
  * `ln -s ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User/ProjectFiles/.eslintrc.json PROJECT_FOLDER/.eslintrc.json`
Restart Sublime Text 3 and open a javascript file to confirm linting errors/warnings are being displayed

Command line output of linter can be obtained by: `PROJECT_FOLDER/eslint FILE_TO_TEST`

>> More information:
>>
>> SublimeLinter ESLint: https://github.com/SublimeLinter/SublimeLinter-eslint
>>
>> ESLint Installation: https://eslint.org/docs/user-guide/getting-started
>>
>> ESLint Rules: https://eslint.org/docs/rules/ 
>>
>> ESLint Airbnb project: https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb
>>
>> Airbnb javascript style guide: https://github.com/airbnb/javascript


### CSS
`npm install -g csslint`
* In project folder: 

  * `ln -s ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User/ProjectFiles/.csslintrc PROJECT_FOLDER/.csslintrc`
  * Create symbolic links in every folder that has a css
Restart Sublime Text 3 and open a css file to confirm linting errors/warnings are being displayed

Command line output of linter can be obtained by: `PROJECT_FOLDER/csslint FILE_TO_TEST`

>> More information:
>> 
>> SublimeLinter CSSLint: https://github.com/SublimeLinter/SublimeLinter-eslint
>>
>> CSSLint: https://github.com/CSSLint/csslint
>>
>> CSSLint Rules: https://github.com/CSSLint/csslint/wiki/Rules


