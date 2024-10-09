# VS Code Setup

Visual Studio Code is a versatile, cross-platform source code editor that boasts an array of robust development tools. It features IntelliSense for seamless code completion, comprehensive debugging capabilities, integrated Git support, and an inline terminal for enhanced productivity.

<br />

## Learn VS Code

* To begin your journey with Visual Studio Code, explore their extensive [documentation](https://code.visualstudio.com/docs/).
* [Click here](https://www.youtube.com/watch?v=iLmQ52IIrvM) to learn how VSCode Workspaces works.
* [Emmet](https://code.visualstudio.com/docs/editor/emmet) has been integrated into VS Code. [Click here](https://youtu.be/V8vizNQKtx0?si=Nb51inVxUKyDhgyJ) to learn how to use Emmet, and its shortcuts by visiting this [cheat sheet link](https://docs.emmet.io/cheat-sheet/).
* [Click here](https://youtu.be/_VpuYH3HU9s?si=mf2K4SgRA6INbtg7) to learn how to view markdown preview in VS Code.

<br />

## Tweaks

The following adjustments will enhance the efficiency of VS Code.

- [ ] Open VSC from [terminal](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line)
- [ ] Change tab [spacing to 2](https://stackoverflow.com/questions/29972396/how-can-i-customize-the-tab-to-space-conversion-factor-in-vs-code)
- [ ] [Auto save](https://www.youtube.com/watch?v=nBsukFTnGf8) file changes in VS Code
- [ ] Enable a Visual Studio editor word-wrap
- [ ] Prevent the Visual Studio editor from scrolling past the bottom of a file.
Disable scrollBeyondLastLine option in the settings.
- [ ] Resolve the VS Code [path error](https://stackoverflow.com/a/47530455) to php executable.
Add the following path to resolve the error:

```
"php.executablePath": "/Applications/MAMP/bin/php/php8.2.0/bin/php" 
```

<br />

## User Settings

The user settings hold the VS Code preferences tailored for each individual.

To access the User Settings:

Launch the command palette by pressing <kbd>⌘ Command</kbd> + <kbd>⇧ Shift</kbd> + <kbd>P</kbd> and enter "Open User Settings (JSON)."

Next, simply paste the following settings into the JSON file:

```json
{
  "security.workspace.trust.untrustedFiles": "open",
  "workbench.startupEditor": "none",
  "editor.minimap.enabled": false,
  "editor.wordWrap": "on",
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.detectIndentation": false,
  "liveServer.settings.donotShowInfoMsg": true,
  "files.autoSave": "afterDelay",
  "workbench.colorTheme": "Palenight Theme",
  "php.validate.executablePath": "/Applications/MAMP/bin/php/php8.2.0/bin/php"
}
```

![VSCode user setting json](/images/user-setting-json.png "VSCode user setting json")

<br />

## Extensions

The goal is to install minimal extensions while maximising the use of native VS Code features. Below is a curated list of extensions designed to help you get the most out of your VS Code experience.

- [ ] [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [ ] [px to rem](https://marketplace.visualstudio.com/items?itemName=sainoba.px-to-rem), there is an excellent tutorial on using rem units instead of pixels to enhance component accessibility.
- [ ] [Palenight Theme](https://marketplace.visualstudio.com/items?itemName=whizkydee.material-palenight-theme)
- [ ] [Minify](https://marketplace.visualstudio.com/items?itemName=HookyQR.minify)
- [ ] [Beautify](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify) 
- [ ] [SSH FS](https://marketplace.visualstudio.com/items?itemName=Kelvin.vscode-sshfs)
- [ ] [Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks)
- [ ] [BEM Helper](https://marketplace.visualstudio.com/items?itemName=Box-Of-Hats.bemhelper)
- [ ] [TODO Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)
- [ ] [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

<br />

## AI Assistants

Here is a collection of extensions designed to enhance your coding experience.

- [ ] [Cody](https://marketplace.visualstudio.com/items?itemName=sourcegraph.cody-ai)
- [ ] [Codeium](https://marketplace.visualstudio.com/items?itemName=Codeium.codeium)
- [ ] [Fitten](https://marketplace.visualstudio.com/items?itemName=FittenTech.Fitten-Code)
- [ ] [Snyk](https://marketplace.visualstudio.com/items?itemName=snyk-security.snyk-vulnerability-scanner-vs)
- [ ] [Pieces](https://marketplace.visualstudio.com/items?itemName=MeshIntelligentTechnologiesInc.pieces-vscode)