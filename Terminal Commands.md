# Terminal Commands

## Navigate folders

Navigate folder structure you use the `cd` command. Example : 

`cd /cygdrive/c/Users/USERNAME`

A cool thing you can do is tab complete the path name. For example, you type `cd cy` and hit tab it will fill out `cydrive` ( assuming there is a folder or file with those first 2 letters)

If you run into a situation where there are multiple files with those first couple of letters, then a list of them will show up under the current command. In Babun, you will be able to tab select the items or use the arrow keys to select correct folder. 

## List Directories

If you want to see what is listed in the folder you can use the `ls` command. If you want more information on the files and folders `ls -l`

## Open folder

When you are in the folder you want to be in, you can type `open .` and that will open a new window.

## Make a New Folder

To make a new folder `mkdir FOLDERNAME` replace foldername with what you want to call it.

## Remove Folder or File

`rm -r FOLDERNAME` **USE WITH CAUTION.** This will remove all files and folders inside the folder you point it at. CANNOT BE UNDONE. 



# Node Commands

## Install Packages

`npm install <package name>` This is the basic syntax of how to install packages. Typically speaking you will save a package locally ( to your project ) or globally ( to your machine ). 

`npm install --save <package name>` the 'dash dash save' is the flag that saves the item to your `package.json` as a dependency. If you need something as a dev dependency you add 'dash dev' to your save statement. `npm install --save-dev <package name>` 

All of this can be shortened if you install a lot. The `install` can be shortened to `i`. The `--save` and `--save-dev` can be shortened to `-S` and `-D` respectively. 

## List Global Packages

What to see what global packages you have installed? Run `npm list -g --depth=0` in your command line and see what's there.

## Kill all Node processes

Open process can be an issue. So, to kill all open processes run `taskkill /F /IM node.exe` in your bash.