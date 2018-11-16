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

### Plugins in detail

#### AutoTag Rename

[AutoTag Rename](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)

This one you have to be careful with. The documentation states you can edit a closing tag and it updates the correct opening tag. But I have found that to be not correct 100% of the time. Especially if things are nested pretty deep. So, my general rule of thumb that has worked out for me often is, edit the opening tag to replace both tags.

#### Babel

[Babel](https://marketplace.visualstudio.com/items?itemName=mgmcdermott.vscode-language-babel)

If you want to utilize the newer features or up coming features, this plugin will provide you proper syntax hinting and highlighting.

The JavaScript gets transpiled as part of the Gulp build process. What gets converted is depended on your `.babelrc` file. I recommend utilize at minimum the `babel env` preset as that will allow you to target browsers based on a set of rules, and transpile only the things that are necessary. Here is my current set up.

```JSON
{
  "presets": ["@babel/preset-env"],
  "plugins": [
    "@babel/plugin-proposal-optional-chaining",
    "@babel/plugin-proposal-object-rest-spread"
  ]
}
```

> Remember to include the preset and plugins in the the package.json and is installed before use.

#### Better Comments

[Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments)

This is extremely useful for reading big chunks of comments.

#### Bracket Pair Colorizer

[Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)

Then things get deeply nested, either object or code logic, it can get hard to know what is closing what and where. This tool colorizes the parenthesis and brackets for a quick easy visualizer of what you code is doing.

#### Code Spell Checker

[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

Because, we all can use a little help spelling things better.

#### Color Highlight

[Color Highlight](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)

Often times, I don't know the color scheme of the project or forget over time. I personally cannot visualize what the hex numbers, hsla, rgba, or lab colors represent to. This tool gives you a preview of the actual color where the color is defined and utilized. ( Does not move over to CSS or Sass variables yet )

#### Editor Config

[Editor Config](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)

When working with a team it's important to code in a similar style. Whatever way that style is for you and your team, is up to you and your team. But, put an editor config in place and never argue about it again. Here is my `.editorconfig`.

```Yaml
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
max_line_length = 120
quote_type = double
spaces_around_operators = true
spaces_around_brackets = true
```

#### ESLint

[ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

The same argument for the Editor Config applies here. Add and remove as your team sees fit. Here is my `.eslint` file.

```JSON
{
  "env": {
    "browser": true,
    "jquery": true,
    "es6": true,
    "amd": false,
    "commonjs": true
  },
  "extends": "eslint:recommended",
  "globals": { ... },
  "parserOptions": {
    "ecmaVersion": 2018,
    "sourceType": "module"
  },
  "rules": {
    "indent": ["error", 2],
    "linebreak-style": ["error", "unix"],
    "quotes": ["error", "double"],
    "semi": ["error", "always"]
  }
}
```

> My globals are all about GSAP and more will be added later. But these are super specific to my needs. Check the actual file if you are looking for full details.

#### GitLens

[GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)

Just a super useful tool for seeing important information about your Git repo. ( I need to do more digging on this one, but on its surface I have gotten a lot of benefit )

#### Highlight Matching Tag

[Highlight Matching Tag](https://marketplace.visualstudio.com/items?itemName=vincaslt.highlight-matching-tag#user-content-styling-options)

I like this to understand the shape of my HTML better. It's just a nice visualizer to see if anything has been formatted incorrectly. Here are the settings that I have changed to work with the theme I am using.

```JSON
"highlight-matching-tag.highlightSelfClosing": true,
"highlight-matching-tag.styles": {
  "opening": {
    "full": {
    "highlight": "#be1985",
    "name": "#000"
    }
  }
}
```

#### Indenticator

[Indenticator](https://marketplace.visualstudio.com/items?itemName=SirTori.indenticator)

Another useful tool to understand where you are in your code. I find the default options are perfect, though they are configurable.

#### Material Icon Theme

[Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)

I find these icons to be bountiful and prettier, in addition to customizable. Here are my settings for default folder icons and theme.

```JSON
"material-icon-theme.folders.theme": "specific",
"material-icon-theme.folders.color": "#ffc600",
```

#### npm

[npm](https://marketplace.visualstudio.com/items?itemName=eg2.vscode-npm-script)

A nice to have. It's good to know when something has an update available.

#### npm Intellisense

[npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)

Including things from the `node_modules` folder is no longer a PITA. This tool provides intellisense and helpful suggestions.

#### Path Intellisense

[Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)

This tool provides intellisense and helpful suggestions for completing your files paths.

#### Polacode

[Polacode](https://marketplace.visualstudio.com/items?itemName=pnp.polacode)

Sometimes I want to show off some code, but it's hard to get an decent looking snapshot. This tool solves that problem with ease.

#### Prettier

[Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

For all the formatting needs that is not automatically taken care of by the `.editorconfig` and `.eslint` files.

#### Quokka.js

[Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode)

Quokka.js is a rapid prototyping playground for JavaScript and TypeScript. It runs your code immediately as you type and displays various execution results in your code editor. How can this not be useful?

#### Scss Formatter

[Scss Formatter](https://marketplace.visualstudio.com/items?itemName=sibiraj-s.vscode-scss-formatter)

Sass and Scss are special files that need special attention to formatting. This tool takes care of the Scss specific formatting.

#### Scss IntelliSense

[Scss IntelliSense](https://marketplace.visualstudio.com/items?itemName=mrmlnc.vscode-scss)

When working on a large project with a lot of mixin's and variables, it's hard to remember all of them. This tool provides you useful auto-complete suggestions.

#### VS Live Share

[VS Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)

When you are working on a project and need help. It can be difficult to debug over screen share where the outside party has to tell you what to look at and what to write and where to write it. This tool provides a tunnel to your code base that can be edited by the outside party. Giving them the ability to debug the way they know how.

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
