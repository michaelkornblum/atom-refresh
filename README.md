# atom-refresh

Has Atom's slow performance got you down? It could be the plugins your using. Bear in mind that every plugin that you have installed on your machine adds to your startup time. Additionally, updating plugins may also leave behind some cruft from prior installations. So, how do you fix this?

## The Nuke and Pave Method
Deleting the configuration directory in Atom for MacOS and Linux-based systems is easy, and makes Atom run as if it's a fresh install. However, taking this step also permanently deletes every plugin in your work environment. Before taking this drastic step, create a text file. This text file can be named anything you want, provided that it ends in a .txt extension. Inside this text file, list each and every plugin that you currently have installed. For example:

```
// atom-packages.txt

file-icons
platformio-ide-terminal
emmet
atom-live-server
todo
minimap
highlight-selected
pigments
git-plus
autocomplete-module-import
linter-eslint
linter-jscs
linter-htmlhint
linter-stylint
```

To get a full list of plugins that are installed in your dev environment, go to the terminal and enter the following:

```bash
ls .atom/packages
```

Copy the names of the plugins you wish to keep from the terminal output into your text file, and save the document.

Now for the nuke and pave.

Close Atom if it is running and from the command-line, enter:

```bash
sudo rm -r .atom
```

This command will delete your entire Atom configuration directory. But don't worry, a fresh version of the directory will respawn when you restart Atom. Once Atom is restarted, open your terminal and enter the following command:

```bash
apm install --packages-file atom-packages.txt
```

After awhile, apm, Atom's package manager will pull down and install the newest versions of your atom packages. This soluton is one way to speed up you Atom experience, however you may also want to ask yourself why you have so many packages in the first place. While looking through your package list, ask youself "Are there plugins I no longer need or use?" If the answer is "no", then by all means delete them.
