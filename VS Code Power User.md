# VS Code Power User

I am always searching for a environment that works with me and not against me. Finding Visual Studio Code has been a big win for productivity. I have been using this for more than a year at the time of this check in and I figured it was time to evaluate all the plugins I have installed and settings I have in place. There are lot of great options out there for themes and plugins, some better than others. With that in mind, it can be hard to pick out which ones are worth the install. Sometimes popularity is a bad indicator of quality. Here is my list of plugins that I use on a daily basis and think are necessities for new environment set up. I purposefully left out language specific plugins, excluding JavaScript and Scss, as well as frame works. I might update this documentation in the future to include frame work or language specific plugins once I have personally tested them. Without further ado, here is my list of must have plugins and settings I have turned on to optimize my work flow.

> This is intended as a starter guide. I encourage you to question my settings, figure out what works for you and your team, enhance your work flow with plugins that makes sense to your project, and set up linting rules that work for you.\*

### Packages

- [AutoTag Rename](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
- [Babel](https://marketplace.visualstudio.com/items?itemName=mgmcdermott.vscode-language-babel)
- [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments)
- [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)
- [Color Highlight](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)
- [Editor Config](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Highlight Matching Tag](https://marketplace.visualstudio.com/items?itemName=vincaslt.highlight-matching-tag#user-content-styling-options)
- [Indenticator](https://marketplace.visualstudio.com/items?itemName=SirTori.indenticator)
- [Intellisense for CSS, Scss for HTML](https://marketplace.visualstudio.com/items?itemName=gencer.html-slim-scss-css-class-completion)
- [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)
- [npm](https://marketplace.visualstudio.com/items?itemName=eg2.vscode-npm-script)
- [npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)
- [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
- [Polacode](https://marketplace.visualstudio.com/items?itemName=pnp.polacode)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode)
- [Scss Formatter](https://marketplace.visualstudio.com/items?itemName=sibiraj-s.vscode-scss-formatter)
- [Scss IntelliSense](https://marketplace.visualstudio.com/items?itemName=mrmlnc.vscode-scss)
- [VS Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)

### Theme

- [Cobalt2 Official](https://marketplace.visualstudio.com/items?itemName=wesbos.theme-cobalt2)

### Fonts

- [FiraCode](https://github.com/tonsky/FiraCode)
  - Specific instructions for VS Code can be found [here](https://github.com/tonsky/FiraCode/wiki/VS-Code-Instructions).

### Settings

If you just want my settings here they are.

```JSON
{
  "editor.mouseWheelZoom": true,
  "terminal.external.windowsExec": "C:\\Windows\\System32\\bash.exe",
  "terminal.integrated.shell.windows": "C:\\Windows\\System32\\bash.exe",
  "editor.fontLigatures": true,
  "editor.fontFamily": "Fira Code",
  "editor.formatOnSave": true,
  "editor.fontWeight": "100",
  "editor.lineHeight": 22,
  "editor.letterSpacing": 0.5,
  "editor.renderLineHighlight": "all",
  "emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "vue-html": "html",
    "plaintext": "jade",
    "cshtml": "cshtml"
  },
  "files.exclude": {
    "**/.git": true,
    "**/.svn": true,
    "**/.hg": true,
    "**/CVS": true,
    "**/.DS_Store": true,
    "**/node_modules": true
  },
  "eslint.autoFixOnSave": true,
  "workbench.colorTheme": "Cobalt2",
  "extensions.ignoreRecommendations": true,
  "extensions.showRecommendationsOnlyOnDemand": true,
  "editor.cursorBlinking": "smooth",
  "editor.cursorStyle": "line-thin",
  "workbench.iconTheme": "material-icon-theme",
  "material-icon-theme.folders.theme": "specific",
  "material-icon-theme.folders.color": "#ffc600",
  "terminal.integrated.letterSpacing": 0.5,
  "breadcrumbs.enabled": false,
  "highlight-matching-tag.highlightSelfClosing": true,
  "highlight-matching-tag.styles": {
    "opening": {
      "full": {
        "highlight": "#be1985",
        "name": "#000"
      }
    }
  }
}
```
