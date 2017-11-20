

# SublimeText Bootstrap

I teach a class and wanted a fast way to install Sublime Text with all my preferred settings.

I forked this [agnadassaf's repo](https://github.com/ahmadassaf/sublime-text-bootstrap) that was a fork of [evanplaice's repo](https://github.com/evanplaice/sublime-text-seed)

I wanted the install to be as quick as possible and this is way faster than manually doing it but there are some manual steps involved.

## Steps for Sublime Text Installation
1. Fork the repo
2. Clone the repo to your machine
3. `$ cd YOURFORKEDREPO`
4. Run the install file

```bash
$ ./setup.py
```

**note** Don't type `$` it is just there to let you know that this is something you type in the terminal.

5. Make any adjustments to the packages you want to use, the key bindings you are used to and the personal sublime text settings you use.

## Install node
`$ brew install node` (this program installs homebrew for you)

## `sublime` symlink
* This program installs `sublime` symlink so you can open sublime from the Command Line by just typing `sublime`

Sublime Text configuration exists at those locations depended on your operating system:

 - **OSX**: `/Library/Application Support/Sublime Text 3`
 - **Linux**: `~/.config/sublime-text-3`

Those configurations mainly consists of following:

 - `Packages/` folder where all your installed plugins and setting files lie (shortcut into this available through preferences menu)
 - `Packages/User/` folder where are the files specific to your configuration (other folders in Packages/ folder are pristine plugin files and should not be directly edited)
 - `Local/Session.sublime_session` stores all the information about projects, workspaces, etc.
 - `Packages/User/Preferences.sublime-settings` stores the preferences you have changed (main settings for Sublime Text)
 - `Packages/User/Package Control.sublime-settings` contains the list of installed addons

> If you have any custom packages, color schemes or themes then you can drop those in the `Packages/User/` folder

To batch install packages (plugins, themes, etc.), a `Package Control.sublime-settings` file needs to be placed into the `Packages/User/` folder. Inside of the settings file should be a JSON object with the key "installed_packages" that references a list of package names. When Package Control starts, if any of those packages are not present, the will be automatically downloaded and installed.

### Manual Part
**note** I'm sure the python script can be modified to do this part but until I figure it out or someone enlightens me, I'll show you the manual way.

#### Add all your packages
Copy the `Package\ Control.sublime-settings` in `Packages/User/` (after you made the changes that you want)

`$ cp -R Package\ Control.sublime-settings ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User/`

**important** Shutdown Sublime Text and reopen it. Package Control will read this file and automatically install all your packages inside this file. Pretty cool, huh?

**note** You may have to manually install jsprettier as it was not installing automatically.
**note** You will get a loop error but you can disregard that as it will still install the packages

#### Add your keybindings
Copy the `Default (OSX).sublime-keymap` in `Packages/User/` (after you made the changes that you want)

**note** Make sure you are inside the `user-settings` directory in your cloned repo on your machine

`$ cp -R Default\ \(OSX\).sublime-keymap ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User/`

#### Add your User Settings
Copy the `Preferences.sublime-settings` in `Packages/User/` (after you made the changes that you want)

`$ cp -R Preferences.sublime-settings ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User/`

### Update it as your workflow evolves
Since you forked your code you can update Github with it as your workflow changes.

### Extras
#### Eslint
* For Eslint and Sublinter to work install it globally
* Requires Node installed

`$ npm install -g eslint`

#### Markdown
Copy the `Markdown.sublime-settings` in `Packages/User/` (after you made the changes that you want)

`$ cp -R Markdown.sublime-settings ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User/`

#### Prettier
* Make your JavaScript look pretty
*
`$ npm install -g prettier`

It used to take me 20 minutes to setup Sublime Text how I like it and now I can do it in 4 minutes or less. Thanks to the shoulders of giants on stood on to make this small contribution.

