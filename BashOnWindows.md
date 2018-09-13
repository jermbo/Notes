# Bash on Windows

## Developer Mode

First thing you need to do is turn on Developer Mode for Windows.
`Settings -> Update and Security -> For Developers` and change `Sideload apps` setting to `Developer Mode`.
This might take a minute or two.

## Install Ubuntu

Once the developer mode is done, you need to get Ubuntu. Go to the Windows Store and search Ubuntu. ( Download the Ubuntu with nothing extra in the title, just Ubuntu).

Once that is done installing, click the blue Launch button. This will prompt you to make a username and password.

## Update and Upgrade

With the window open, it's a good idea to update and upgrade. ( Not sure if that order is important but that's what I read everywhere )

`sudo apt update`

`sudo apt upgrade`

This process will take a few minutes.

## Install Node and NPM

Now we need Node. Referencing their [documentation](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions) you can install via the command line.

`curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -`
`sudo apt-get install -y nodejs`

Replace the `8.x` with whatever version you want. Maybe, `14.x` is more accurate when you read this. I don't know what future time you are reading this.

Then, NPM is next.

`sudo apt-get install npm`

I had run the echo statement below to get `npm` command to be recognized.

`echo 'export PATH=$HOME/bin:/usr/local/bin:$PATH' >> ~/.bashrc`

## Git

This one is pretty straight forward.

`sudo apt-get git`

Done. The only thing I have not figured out yet is the global config, so I will update this when I figure that out.

## Oh-My-ZSH

[Instal Oh-My-ZSH!!](https://evdokimovm.github.io/windows/zsh/shell/syntax/highlighting/ohmyzsh/hyper/terminal/2017/02/24/how-to-install-zsh-and-oh-my-zsh-on-windows-10.html)

## VS Code Integration

Open your settings and find `Terminal Integrated Shell Windows` and update the path to `C:\Windows\System32\bash.exe`

## Random

If you notice a box with a question mark at the beginning of the line, it's probably a font issue. Check out this [GitHub Issue](https://github.com/robbyrussell/oh-my-zsh/issues/5444#issuecomment-413647264) for a possible fix.
