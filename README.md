# Fresh MacOS Setup
Setting up macOS for front-end development and product design can be streamlined and organised.

If you're using an older machine and wish to reinstall macOS, follow the instructions in the "[Reinstall macOS](#reinstall-macOS)" section. However, if you're working with a fresh machine, feel free to skip this part and proceed directly to the "[Fresh Installation](#fresh-installation)" section.

<br />

## Reinstall macOS

Before you proceed with the reinstallation of macOS, it's crucial to back up any personal configurations you wish to retain. This includes your custom zsh scripts, aliases, git aliases, profile settings, terminal color profiles, browser bookmarks, and any other important configurations.

To reinstall macOS, ensure you have a wireless internet connection.

Start by restarting your computer. As soon as you hear the Mac startup chime, press and hold <kbd>⌘ Command</kbd> + <kbd>R</kbd> to enter the Mac recovery system. Then, follow the instructions provided on the [Apple website](https://support.apple.com/en-gb/HT204904) for further guidance.

<br />

## Fresh Installation

Make sure everything is up to date in the App Store.

### Install Xcode

Before installing Homebrew or any other dependencies, installing the Xcode command line tools is essential. You can easily do this by visiting the [App Store](http://itunes.apple.com/us/app/xcode/id497799835).

Alternatively, if you favour using the terminal, you can install Xcode by entering this command:

```
bash xcode-select --install
```

A prompt will appear, requesting you to install the command line developer tools. Just select **Install** to proceed.

Once Xcode is installed, you'll need to accept the Xcode license agreement. You can accomplish this by running the following command:

```
sudo xcodebuild -license
```

### Install [Homebrew](https://brew.sh/)

To begin the Homebrew installation, launch the terminal and enter the following command:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Here are the directories where Homebrew has been installed. Familiarising yourself with these locations can be beneficial for future reference.

```
/usr/local/bin/brew
/usr/local/Library/...
/usr/local/share/man/man1/brew.1

==> The following directories will be made group writable:
/usr/local/.

==> The following directories will have their group set to admin:
/usr/local/.
```

To ensure a smooth installation process, please execute the following command prior to installing any packages through Homebrew and adhere to the prompts provided.

To verify that Homebrew is installed correctly and to check its version

```
brew --version
```

If you're experiencing issues with Homebrew, execute the command below:

```
brew doctor
```

The latest MacBook equipped with the M chip comes with Zsh pre-installed. Execute the following command to verify if Zsh is present on your device.

```
zsh --version
```

After confirming that zsh is installed on your system, include its path in your .zshrc file.

```
echo 'export PATH="/usr/local/sbin:$PATH"' >> ~/.zshrc
```

<br />

## Terminal Improvements

Developers spend most of their time in the terminal, yet the default Mac Terminal can often seem dull and restrictive regarding customisation. To fully elevate your terminal experience, installing the Oh My Zsh framework is crucial. It streamlines the management of configurations, plugins, and themes, transforming your terminal into a more vibrant and personalised workspace. With this powerful tool, you can enjoy enhanced flexibility and address all the shortcomings of the standard Terminal, creating a dynamic and tailored workflow.

### Install [Warp](https://www.warp.dev/) Terminal

Warp revolutionises the terminal experience by integrating AI and your development team's knowledge seamlessly. It boasts auto-suggestions, syntax highlighting, and advanced features often lacking in other terminals or require cumbersome plugins to install.

[Click here](https://app.warp.dev/get_warp?package=dmg) to download Warp to elevate your terminal experience or if you prefer the command line, install it using Homebrew.

```
brew install --cask warp
```

I really like the default Warp "Dracula" theme, but you can also download or create a custom theme by following the guide available on their [website](https://docs.warp.dev/appearance/custom-themes).

### Install [Starship](https://starship.rs/) Prompt

The Starship is a fast, customizable prompt for any shell with minimal setup.

Starship can be installed using either Shell or Homebrew.

Shell:

```
curl -sS https://starship.rs/install.sh | sh
```

Homebrew:

```
brew install starship
```

Add the Starship init script to the end of ~/.zshrc:

```
eval "$(starship init zsh)"
```

Then reload the Warp:

```
source ~/.zshrc
```

Once Warp has been reloaded, modify the following Warp settings:

```
Appearance > Prompt > Select "Honor custom user prompt (PS1)"
```

![Warp prompt selection](/images/warp-select-prompt.png "Warp prompt selection")

#### Customise Starship

To get started configuring starship, create the following file: ~/.config/starship.toml.

```
mkdir -p ~/.config && touch ~/.config/starship.toml
```

My favourite Starship theme is [Gruvbox Rainbow](https://starship.rs/presets/gruvbox-rainbow), and its installation is straightforward.

To enjoy the full experience of "Gruvbox Rainbow," you'll need to install Nerd Font, which is essential for displaying icons associated with files and folders.

You can either visit the [Nerd Fonts website](https://www.nerdfonts.com/) to download and install the fonts directly or if you prefer using the command line, follow the commands below.

To display all nerd fonts

```
brew search nerd-font
```

Install Hack Nert Font

```
brew install --cask font-hack-nerd-font
```

Reload the Warp, and modify the following Warp settings:

```
Appearance > Text > Terminal font > Hack Nerd Font Mono
```

![Warp font selection](/images/warp-select-font.png "Warp font selection")

To add "Gruvbox Rainbow" to your Starship configuration, use the following command:

```
starship preset gruvbox-rainbow -o ~/.config/starship.toml
```

### Install [Eza](https://eza.rocks/)

An Eza is a modern, colourful 'ls' replacement with better defaults and features.

To install Eza, please execute the command below:

```
brew install eza
```

Add the following Eza aliases in your .zshrc file:

```
# Eza for ls command
# ------------------------------------------------------------------------------
alias l="eza --icons"
alias ls="eza --icons"
alias ll="eza -lg --icons"
alias la="eza -lag --icons"
alias lt="eza -lTg --icons"
alias lt1="eza -lTg --level=1 --icons"
alias lt2="eza -lTg --level=2 --icons"
alias lt3="eza -lTg --level=3 --icons"
alias lta="eza -lTag --icons"
alias lta1="eza -lTag --level=1 --icons"
alias lta2="eza -lTag --level=2 --icons"
alias lta3="eza -lTag --level=3 --icons"
```

<br />

## Dotfiles

I have compiled the dotfiles that are available for download in the appropriate directories.

* Git: [GitConfig](git/.gitconfig) and [GitIgnore](git/.gitignore)
* Zsh: [Zshrc](zshrc/.zshrc)

<br />

## Install Softwares

There are three effective methods for installing software on macOS:

1. Use the App Store to download and install apps.
2. Visit individual app websites to install them one by one.
3. Utilise Homebrew via the command line for installation.

The choice of method depends entirely on your personal preference. Regardless of the approach you take, the outcome will remain same.

The list below includes frequently used packages; however, they are not mandatory. Please install only those that are essential for your specific application.

Note: You can discover the compatibility of Homebrew packages with your macOS version by [clicking here](https://formulae.brew.sh/).

### Essentials

- [ ] App Store: [Website](https://www.apple.com/uk/app-store/)

```
brew install mas
```

- [ ] Git: [Website](https://git-scm.com/) | [Mac](https://git-scm.com/download/mac) | [Windows](https://git-scm.com/download/win) | [Linux](https://git-scm.com/download/linux)

```
brew install git
```

- [ ] Wget: [Website](https://www.gnu.org/software/wget/) | [Windows](https://ftp.gnu.org/gnu/wget/)

```
brew install wget
```


### Utitlies

- [ ] Resize This: [Mac](https://itunes.apple.com/gb/app/resize-this/id614530344)

```
mas install 614530344
```

- [ ] Funter: [Website](https://nektony.com/funter) | [Mac](https://nektony.com/funter)

```
brew install --cask funter
```

- [ ] Gemini 2: [Website](https://macpaw.com/gemini) | [Mac](https://macpaw.com/gemini)

```
brew install --cask gemini
```

- [ ] Rocket 💲: [Website](https://matthewpalmer.net/rocket/) | [Mac](https://matthewpalmer.net/rocket/)

```
brew install --cask rocket
```
- [ ] Magnet 💲: [Website](https://magnet.crowdcafe.com/index.html) | [Mac](https://apps.apple.com/gb/app/magnet/id441258766?mt=12)

```
mas install 441258766
```

- [ ] PixelSnap 2 💲: [Website](https://getpixelsnap.com/) | [Mac](https://getpixelsnap.com/)

```
brew install --cask pixelsnap
```

- [ ] Caffeinated 💲: [Website](https://caffeinated.app/) | [Mac](https://apps.apple.com/gb/app/caffeinated-anti-sleep-app/id1362171212?mt=12)

```
mas install 1362171212
```

- [ ] Disk Sensei 💲: [Website](https://cindori.com/sensei) | [Mac](https://cdn.cindori.com/apps/sensei/Sensei.dmg)
- [ ] BlueHarvest 💲: [Website](http://www.zeroonetwenty.com/blueharvest/) | [Mac](https://apps.apple.com/gb/app/blueharvest/id739483376?mt=12)

```
brew install --cask blueharvest
```

- [ ] The Unarchiver: [Website](https://theunarchiver.com/) | [Mac](https://apps.apple.com/gb/app/the-unarchiver/id425424353?mt=12)

```
brew install --cask the-unarchiver
```

- [ ] LG onScreen Control: [Website](https://www.lg.com/us/support/help-library/lg-monitor-how-to-use-on-screen-control-CT30017683-20153186454352)

```
brew install --cask lg-onscreen-control
```

- [ ] LG Calibration Studio: [Website](https://www.lg.com/ca_en/support/product-help/CT20098114-20153004876369)
* CleanMyMac X 💲: [Website](https://macpaw.com/cleanmymac) | [Mac](https://macpaw.com/cleanmymac)

```
brew install --cask cleanmymac
```

- [ ] Feedly: [Website](https://feedly.com/) | [iPhone](https://apps.apple.com/us/app/feedly-smart-news-reader/id396069556) | [Android](https://play.google.com/store/apps/details?id=com.devhd.feedly)
* Kaleidoscope 💲: [Website](https://kaleidoscope.app/) | [Mac v2](https://kaleidoscope.app/support)

```
brew install --cask kaleidoscope@2
```

- [ ] SYC 2 💲: [Website](https://softorino.com/softorino-youtube-converter/) | [Mac](https://softorino.com/youtube-downloader-mac/download/) | [Windows](https://softorino.com/)
* NTFS for Mac 💲: [Website](https://www.paragon-software.com/home/ntfs-mac/) | [Mac v15](https://www.paragon-software.com/home/ntfs-mac/)

```
brew install --cask paragon-ntfs
```

- [ ] Waltr 2 💲: [Website](https://softorino.com/legacy/waltr/) | [Mac](https://softorino.com/legacy/waltr/download/) | [Windows](https://softorino.com/waltr/)

```
brew install --cask waltr
```

- [ ] Wallpaper Wizard 2 💲: [Website](https://wallwiz.com/) | [Mac](https://apps.apple.com/gb/app/wallpaper-wizard-2/id1266674560?mt=12)

```
brew install --cask wallpaper-wizard
```

- [ ] ChatGPT: [Website](https://chatgpt.com/) | [Mac](https://persistent.oaistatic.com/sidekick/public/ChatGPT.dmg) | [iPhone](https://apps.apple.com/us/app/chatgpt/id6448311069) | [Android](https://play.google.com/store/apps/details?id=com.openai.chatgpt&pcampaignid=web_share)

```
brew install --cask chatgpt
```

- [ ] Softorino YouTube Converter 2 💲: [Website](https://softorino.com/softorino-youtube-converter/)

```
brew install --cask softorino-youtube-converter
```

- [ ] WALTR HEIC Converter: [Website](https://softorino.com/heic-converter/) | [Mac](https://softorino.com/heic-converter/) | [Windows](https://softorino.com/heic-converter/)

```
brew install --cask waltr-heic-converter
```

- [ ] Kindle: [Website](https://www.amazon.co.uk/kindle-dbs/storefront?storeType=browse&node=341689031&ref_=topnav_storetab_kindlebooks_store) | [Mac](https://apps.apple.com/gb/app/kindle/id405399194?mt=12) | [Windows](https://www.amazon.co.uk/gp/browse.html?node=21568507031&ref=kcp_fd_hz) | [iPhone](https://apps.apple.com/us/app/amazon-kindle/id302584613) | [Android](https://play.google.com/store/apps/details?id=com.amazon.kindle&hl=en&gl=US)

```
mas install 302584613
```

- [ ] Spotify: [Website](https://www.spotify.com/) | [Mac](https://www.spotify.com/us/download/mac/) | [Windows](https://www.spotify.com/de-en/download/windows/) | [iPhone](https://spotify.link/h5TbcGLLkhb?label=sp_cid%3Aa6b2e28d-37d6-413e-8ec6-73e3c6a6dc89) | [Android](https://spotify.link/T1vKH6Kr9ib?label=sp_cid%3Aa6b2e28d-37d6-413e-8ec6-73e3c6a6dc89)
- [ ] PDF Expert 💲: [Website](https://pdfexpert.com/) | [Mac v3.4](https://pdfexpert.com/downloads) | [iPhone](https://apps.apple.com/gb/app/pdf-expert-editor-reader/id743974925) | [Android](https://play.google.com/store/apps/details?id=com.pdfexpert.advancedpdfmaker)

```
brew install --cask pdf-expert
```

- [ ] LocalSend: [Website](https://localsend.org/) | [Mac](https://localsend.org/download) | [Windows](https://localsend.org/download) | [iPhone](https://localsend.org/download) | [Android](https://localsend.org/download)

```
brew install --cask localsend
```

- [ ] UpNote 💲: [Website](https://getupnote.com/) | [Mac](https://itunes.apple.com/us/app/upnote-an-elegant-note-app/id1398373917?ls=1&mt=12) | [Windows](https://www.microsoft.com/en-us/p/upnote/9mv7690m8f5n?activetab=pivot:overviewtab) | [iPhone](https://itunes.apple.com/us/app/upnote-elegant-note-app/id1389634515) | [Android](https://play.google.com/store/apps/details?id=com.getupnote.android) | [Linux](https://snapcraft.io/upnote)

```
mas install 1398373917
```

- [ ] 1Password 💲: [Website](https://1password.com/) | [Mac](https://app-updates.agilebits.com/) | [iPhone](https://apps.apple.com/app/id1511601750?mt=8) | [Android](https://play.google.com/store/apps/details?id=com.onepassword.android&hl=en&gl=US) | [Chrome](https://chromewebstore.google.com/detail/1password-%E2%80%93-password-mana/aeblfdkhhhdcdjpifhhbdiojplfjncoa)

```
brew install --cask 1password
```

- [ ] Boom 2 💲: [Website](https://www.globaldelight.com/) | [Mac](https://www.globaldelight.com/boom/) | [Windows](https://www.globaldelight.com/boom/) | [iPhone](https://apps.apple.com/us/app/boom-music-player-equalizer/id1065511007) | [Android](https://play.google.com/store/apps/details?id=com.globaldelight.boom&hl=en) | [Chrome](https://chrome.google.com/webstore/detail/boom3d-51-surround-for-ne/ndjhebiohmanieefhnhcmlbflfljmhdn?hl=en&authuser=0)

```
brew install --cask boom
```

- [ ] Grammarly: [Website](https://grammarly.com/) | [Mac](https://www.grammarly.com/desktop/mac) | [Windows](https://www.grammarly.com/desktop/windows) | [iPhone](https://apps.apple.com/us/app/grammarly-keyboard-editor/id1158877342) | [Android](https://play.google.com/store/apps/details?id=com.grammarly.android.keyboard&hl=en_GB&gl=US) | [Chrome](https://chrome.google.com/webstore/detail/grammarly-grammar-checker/kbfnbcaeplbcioakkpcpgfkobkghlhen)

```
brew install --cask grammarly-desktop
```

### VPN

- [ ] Windscribe: [Website](https://windscribe.com/) | [Mac](https://windscribe.com/download) | [iPhone](https://apps.apple.com/us/app/windscribe-vpn/id1129435228) | [Android](https://play.google.com/store/apps/details?id=com.windscribe.vpn&hl=en) | [Chrome](https://windscribe.com/download)

```
brew install --cask windscribe
```

- [ ] CyberGhost VPN 💲: [Website](https://www.cyberghostvpn.com/en_US/) | [Mac](https://www.cyberghostvpn.com/en_US/apps) | [Windows](https://www.cyberghostvpn.com/en_US/apps) | [iPhone](https://apps.apple.com/gb/app/vpn-by-cyberghost-wifi-proxy/id583009522) | [Android](https://play.google.com/store/apps/details?id=de.mobileconcepts.cyberghost&hl=en&gl=US) | [Chrome](https://chrome.google.com/webstore/detail/stay-secure-with-cybergho/ffbkglfijbcbgblgflchnbphjdllaogb)

```
brew install --cask cyberghost-vpn
```

- [ ] Private Internet Access 💲: [Website](https://www.privateinternetaccess.com/) | [Mac](https://www.privateinternetaccess.com/download/mac-vpn) | [Windows](https://www.privateinternetaccess.com/download/windows-vpn) | [iPhone](https://apps.apple.com/us/app/private-internet-access-anonymous/id955626407) | [Android](https://play.google.com/store/apps/details?id=com.privateinternetaccess.android&hl=en) | [Chrome](https://chrome.google.com/webstore/detail/private-internet-access/jplnlifepflhkbkgonidnobkakhmpnmh)

```
brew install --cask private-internet-access
```

### Browsers

- [ ] Arc: [Website](https://arc.net/) | [Mac](https://releases.arc.net/release/Arc-latest.dmg) | [Windows](https://releases.arc.net/windows/ArcInstaller.exe)

```
brew install --cask arc
```

- [ ] Edge: [Website](https://www.microsoft.com/en-us/edge?form=MA13FJ) | [Mac](https://www.microsoft.com/en-us/edge?form=MA13FJ) | [iPhone](https://apps.apple.com/us/app/microsoft-edge-web-browser/id1288723196) | [Android](https://play.google.com/store/apps/details?id=com.microsoft.emmx&hl=en_GB&gl=US)

```
brew install --cask microsoft-edge
```

- [ ] Brave: [Website](https://brave.com/) | [Mac](https://brave.com/download/) | [iPhone](https://apps.apple.com/gb/app/brave-private-web-browser/id1052879175?uo=4&mt=8) | [Android](https://play.google.com/store/apps/details?id=com.brave.browser&hl=en_GB&gl=US)

```
brew install --cask brave-browser
```

- [ ] Opera: [Website](https://www.opera.com/browsers/opera) | [Mac](https://www.opera.com/) | [iPhone](https://apps.apple.com/us/app/opera-browser-with-vpn-and-ai/id1411869974) | [Android](https://play.google.com/store/apps/details?id=com.opera.browser&hl=en_GB&gl=US)

```
brew install --cask opera
```

- [ ] Firefox: [Website](https://www.mozilla.org/en-GB/firefox/) | [Mac](https://www.mozilla.org/en-GB/firefox/new/) | [iPhone](https://apps.apple.com/gb/app/firefox-private-safe-browser/id989804926) | [Android](https://play.google.com/store/apps/details?id=org.mozilla.firefox&pcampaignid=web_share)

```
brew install --cask firefox
```

- [ ] Chrome: [Website](https://www.google.com/intl/en_uk/chrome/) | [Mac](https://www.google.com/intl/en_uk/chrome/) | [iPhone](https://apps.apple.com/us/app/google-chrome/id535886823) | [Android](https://play.google.com/store/apps/details?id=com.android.chrome&hl=en_GB&gl=US)

```
brew install --cask google-chrome
```

- [ ] Vivaldi: [Website](https://arc.net/) | [Mac](https://vivaldi.com/desktop/) | [Windows](https://vivaldi.com/desktop/) | [iPhone](https://apps.apple.com/app/vivaldi-browser/id1633234600) | [Android](https://play.google.com/store/apps/details?id=com.vivaldi.browser)

```
brew install --cask vivaldi
```

### Web Development Tools

- [ ] HackMD: [Website](https://hackmd.io/)
- [ ] Webpack: [Website](https://webpack.js.org/)

```
brew install webpack
```
- [ ] MD Editor: [Website](https://pandao.github.io/editor.md/en.html)
- [ ] Watchman: [Website](https://facebook.github.io/watchman/)

```
brew install watchman
```

- [ ] Kbd Generator: [Website](https://kbd.hsuan.xyz/)
- [ ] OrbStack: [Website](https://orbstack.dev/) | [Mac](https://orbstack.dev/download/stable/latest/arm64)

```
brew install orbstack
```

- [ ] Codekit 💲: [Website](https://codekitapp.com/) | [Mac](https://codekitapp.com/binaries/codekit.zip)

```
brew install --cask codekit
```

- [ ] Transmit 💲: [Website](https://panic.com/transmit/) | [Mac v5.9.2](https://panic.com/transmit/#download)

```
brew install --cask transmit
```

- [ ] Prepros: [Website](https://prepros.io/) | [Mac](https://prepros.io/downloads/stable/mac) | [Windows](https://prepros.io/downloads/stable/windows)

```
brew install --cask prepros
```

- [ ] VSCode: [Website](https://code.visualstudio.com/) | [Mac](https://code.visualstudio.com/download) | [Windows](https://https://code.visualstudio.com/download)

```
brew install --cask visual-studio-code
```

- [ ] Charles: [Website](https://www.charlesproxy.com/) | [Mac](https://www.charlesproxy.com/download/latest-release/) | [Windows](https://www.charlesproxy.com/download/latest-release/)

```
brew install --cask charles
```

- [ ] Proxyman: [Website](https://proxyman.io/) | [Mac](https://proxyman.io/release/osx/Proxyman_latest.dmg) | [Windows](https://proxyman.io/release/windows/Proxyman_latest.dmg)

```
brew install --cask proxyman
```

- [ ] Neovim: [Website](https://neovim.io/) | [Mac](https://github.com/neovim/neovim/releases/latest/download/nvim-macos-arm64.tar.gz) | [Windows](https://github.com/neovim/neovim/releases/latest/download/nvim-win64.msi) | [Linux](https://github.com/neovim/neovim/releases/latest/download/nvim-linux64.tar.gz)

```
brew install neovim
```

- [ ] MAMP PRO 💲: [Website](https://www.mamp.info/en/mamp-pro/mac/) | [Mac v6.8](https://www.mamp.info/en/downloads/) | [Windows](https://www.mamp.info/en/downloads/)

```
brew install --cask mamp
```

### Database Clients

- [ ] Sequel Pro: [Website](http://www.sequelpro.com/) | [Mac](https://sequelpro.com/download#auto-start)
- [ ] Navicat Premium: [Website](http://navicat.com/products/navicat-premium) | [Mac](http://navicat.com/products/navicat-premium)

```
brew install --cask navicat-for-mysql
```

### Version Control

- [ ] Fork: [Website](https://git-fork.com/) | [Mac](https://git-fork.com/) | [Windows](https://git-fork.com/)

```
brew install --cask fork
```

- [ ] Sourcetree: [Website](https://www.sourcetreeapp.com/) | [Mac](https://www.sourcetreeapp.com/) | [Windows](https://www.sourcetreeapp.com/)

```
brew install --cask sourcetree
```

- [ ] Tower 2 💲: [Website](https://www.git-tower.com/) | [Mac](https://www.git-tower.com/download/mac) | [Windows](https://www.git-tower.com/download/windows)

```
brew install --cask tower
```

- [ ] GitHub Desktop: [Website](https://github.com/apps/desktop) | [Mac](https://desktop.github.com/download/) | [Windows](https://desktop.github.com/download/) | [iPhone](https://apps.apple.com/us/app/github/id1477376905) | [Android](https://play.google.com/store/apps/details?id=com.github.android&pcampaignid=web_share)

```
brew install --cask github
```

### Design & Mockups

- [ ] Sketch 💲: [Website](https://www.sketch.com/) | [Mac](https://www.sketch.com/downloads/mac/)

```
brew install --cask sketch
```

- [ ] Sketch Mightnight 💲: [Website](https://midnightsketch.com/) | [Mac](https://midnightsketch.com/)
- [ ] Sketch Confetti Plugin 💲: [Website](https://sketchconfetti.com/) | [Mac](https://sketchconfetti.com/)
- [ ] Pixelmator Pro 💲: [Website](https://www.pixelmator.com/pro/) | [Mac](https://apps.apple.com/gb/app/pixelmator-pro/id1289583905?mt=12) | [iPhone](https://apps.apple.com/us/app/pixelmator/id924695435?ign-mpt=uo%3D4)

```
mas install 1289583905
```

- [ ] Balsamiq Mockup: [Website](https://balsamiq.com/) | [Mac](https://balsamiq.com/buy/#d) | [Windows](https://balsamiq.com/buy/#d)

```
brew install --cask balsamiq-wireframes
```

- [ ] Squash 3 for Mac 💲: [Website](https://www.realmacsoftware.com/squash/) | [Mac](https://www.realmacsoftware.com/squash/) | [App store](https://apps.apple.com/gb/app/squash-3/id1545179668?mt=12)

```
brew install --cask squash
```

- [ ] Sketch Text Styles Manager 💲: [Website](https://peerjollux.gumroad.com/l/sketch-text-styles-manager) | [Mac](https://peerjollux.gumroad.com/l/sketch-text-styles-manager)
- [ ] Sketch symbols manager plugin 💲: [Website](https://peerjollux.gumroad.com/l/sketch-symbols-manager) | [Mac](https://peerjollux.gumroad.com/l/sketch-symbols-manager)
- [ ] Figma 💲: [Website](https://www.figma.com/) | [Mac](https://www.figma.com/downloads/) | [Windows](https://www.figma.com/downloads/) | [iPhone](https://apps.apple.com/app/figma-mirror/id1152747299) | [Android](https://play.google.com/store/apps/details?id=com.figma.mirror)

```
brew install --cask figma
```

- [ ] Miro 💲: [Website](https://miro.com/) | [Mac](https://miro.com/apps/) | [Windows](https://miro.com/apps/) | [iPhone](https://apps.apple.com/us/app/miro-collaborative-whiteboard/id1180074773) | [Android](https://play.google.com/store/apps/details?id=com.realtimeboard) | [Chrome](https://chrome.google.com/webstore/detail/miro-web-clipper/ecfnenchgjbicgaooadfdmcojkcmjblk)

```
brew install --cask miro
```

### Video Editing

- [ ] Adapter: [Website](https://www.macroplant.com/adapter) | [Mac](https://macroplant.com/adapter) | [Windows](https://macroplant.com/adapter)

```
brew install --cask adapter
```

- [ ] HandBrake: [Website](https://handbrake.fr/) | [Mac](https://handbrake.fr/downloads.php) | [Windows](https://handbrake.fr/downloads.php)

```
brew install handbrake
```

- [ ] Cisdem Video Player: [Website](https://www.cisdem.com/video-player.html) | [Mac](https://www.cisdem.com/video-player.html) | [Windows](https://www.cisdem.com/video-player.html)
- [ ] Capcut: [Website](https://www.capcut.com/) | [Mac](https://www.capcut.com/download-guidance) | [Windows](https://www.capcut.com/download-guidance) | [iPhone](https://apps.apple.com/us/app/capcut/id1500855883) | [Android](https://play.google.com/store/apps/details)

```
brew install --cask capcut
```

- [ ] Plex media server: [Website](https://www.plex.tv/) | [Mac](https://www.plex.tv/media-server-downloads/) | [Windows](https://www.plex.tv/media-server-downloads/) | [iPhone](https://apps.apple.com/us/app/plex-stream-movies-tv/id383457673) | [Android](https://play.google.com/store/apps/details?id=com.plexapp.android&hl=en_GB&gl=US)

```
brew install --cask plex-media-server
```

- [ ] Wondershare Filmora 13 💲: [Website](https://filmora.wondershare.com/) | [Mac](https://filmora.wondershare.com/) | [Windows](https://filmora.wondershare.com/) | [iPhone](https://apps.apple.com/app/apple-store/id1459336970) | [Android](https://play.google.com/store/apps/details?id=com.wondershare.filmorago&pcampaignid=web_share)

```
brew install --cask wondershare-filmora
```

### Project Management

- [ ] Teamcamp: [Website](https://www.teamcamp.app/) | [iPhone](https://apps.apple.com/in/app/teamcamp/id1671489765) | [Android](https://play.google.com/store/apps/details?id=com.teamcamp&hl=en)

### Screen Recording

- [ ] Kap: [Website](https://getkap.co/) | [Mac](https://getkap.co/api/download/arm64)

```
brew install --cask kap
```

- [ ] ScreenFlow: [Website](http://www.telestream.net/screenflow) | [Mac](https://www.telestream.net/telestream-support/screen-flow/support.htm#download)

```
brew install --cask screenflow
```

- [ ] CleanShot X 💲: [Website](https://cleanshot.com/) | [Mac](https://cleanshot.com/)

```
brew install --cask cleanshot
```

- [ ] FocuSee 💲: [Website](https://gemoo.com/focusee/) | [Mac](https://gemoo.com/focusee/) | [Windows](https://gemoo.com/focusee/)
- [ ] Movavi Screen Recorder: [Website](https://www.movavi.com/screen-recorder/) | [Mac](https://www.movavi.com/screen-recorder/) | [Windows](https://www.movavi.com/screen-recorder/)
- [ ] LICEcap: [Website](https://www.cockos.com/licecap/) | [Mac](https://www.cockos.com/licecap/) | [Windows](https://www.cockos.com/licecap/) | [Customise icon](https://github.com/t32k/licecap-icon)

```
brew install --cask licecap
```

### Screen Sharing

- [ ] Teamviewer: [Website](http://www.teamviewer.com/) | [Mac](http://www.teamviewer.com/en/download/mac.aspx) | [Windows](https://www.teamviewer.com/en/download/windows/) | [iPhone](https://www.teamviewer.com/en/download/ios/) | [Android](https://www.teamviewer.com/en/download/android/)

```
brew install --cask teamviewer
```

### Email Clients

- [ ] Edison Mail: [Website](https://www.edisonmail.com/) | [Mac](https://apps.apple.com/gb/app/edison-mail-email/id1489591003?mt=12) | [iPhone](https://apps.apple.com/us/app/email-edison-mail/id922793622?ppid=eb424e3b-2db1-4b53-b3c1-d02f6030878b) | [Android](https://play.google.com/store/apps/details?id=com.easilydo.mail&listing=edisonmailwebsite)

```
mas install 1489591003
```

- [ ] Spark: [Website](https://sparkmailapp.com/) | [Mac](https://apps.apple.com/gb/app/spark-classic-email-app/id1176895641?mt=12) | [Windows](https://sparkmailapp.com/windows) | [iPhone](https://apps.apple.com/us/app/spark-mail-ai-email-inbox/id997102246) | [Android](https://play.google.com/store/apps/details?id=com.readdle.spark&pcampaignid=web_share)

```
brew install --cask readdle-spark
```

- [ ] Outlook 💲: [Website](https://www.microsoft.com/en-gb/microsoft-365/outlook/email-and-calendar-software-microsoft-outlook) | [Mac](https://apps.apple.com/gb/app/microsoft-outlook/id985367838?mt=12) | [Windows](https://apps.microsoft.com/detail/9NRX63209R7B?hl=en-gb&gl=US) | [iPhone](https://apps.apple.com/us/app/microsoft-outlook/id951937596) | [Android](https://play.google.com/store/apps/details?id=com.readdle.spark&hl=en&gl=US)

```
brew install --cask microsoft-outlook
```

### Communication

- [ ] Teams: [Website](https://www.microsoft.com/en-gb/microsoft-teams/group-chat-software) | [Mac](https://www.microsoft.com/en-gb/microsoft-teams/download-app) | [iPhone](https://apps.apple.com/ph/app/microsoft-teams/id1113153706) | [Android](https://play.google.com/store/apps/details?id=com.microsoft.teams&hl=en_GB&gl=US)

```
brew install --cask microsoft-teams
```

- [ ] WhatsApp Business: [Website](https://business.whatsapp.com/) | [iPhone](https://apps.apple.com/app/apple-store/id1386412985) | [Android](https://play.google.com/store/apps/details?id=com.whatsapp.w4b)
- [ ] Slack: [Website](https://slack.com/intl/en-gb) | [Mac](https://slack.com/intl/en-gb/downloads/mac?geocode=en-gb) | [iPhone](https://apps.apple.com/us/app/slack/id618783545) | [Android](https://play.google.com/store/apps/details?id=com.Slack) | [Chrome](https://chrome.google.com/webstore/detail/slack/jeogkiiogjbmhklcnbgkdcjoioegiknm)

```
brew install --cask slack
```

- [ ] Skype: [Website](https://www.skype.com/en/) | [Mac](https://www.skype.com/en/get-skype/) | [iPhone](https://apps.apple.com/us/app/skype/id304878510) | [Android](https://play.google.com/store/apps/details?id=com.skype.raider&hl=en_GB&gl=US) | [Chrome](https://chrome.google.com/webstore/detail/skype/lifbcibllhkdhoafpjfnlhfpfgnpldfl)

```
brew install --cask skype
```

- [ ] Signal: [Website](https://signal.org/) | [Mac](https://signal.org/download/) | [Windows](https://signal.org/download/) | [iPhone](https://apps.apple.com/us/app/signal-private-messenger/id874139669) | [Android](https://play.google.com/store/apps/details?id=org.thoughtcrime.securesms&pcampaignid=web_share)

```
brew install --cask signal
```

- [ ] Discord: [Website](https://discord.com/) | [Mac](https://discord.com/download) | [Windows](https://discord.com/download) | [iPhone](https://apps.apple.com/us/app/discord-talk-play-hang-out/id985746746) | [Android](https://play.google.com/store/apps/details?id=com.discord&pcampaignid=web_share)

```
brew install --cask discord
```

- [ ] Skype for Business: [Website](https://www.microsoft.com/en-gb/microsoft-365/previous-versions/skype-for-business-online) | [Mac](https://support.microsoft.com/en-gb/office/install-skype-for-business-8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) | [iPhone](https://apps.apple.com/us/app/skype-for-business/id605841731) | [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.lync15&hl=en&gl=US)

```
brew install --cask skype-for-business
```

- [ ] Keybase: [Website](https://keybase.io/) | [Mac](https://keybase.io/docs/the_app/install_macos) | [Windows](https://keybase.io/docs/the_app/install_windows) | [Linux](https://keybase.io/docs/the_app/install_linux) | [iPhone](https://keybase.io/_/download/keybase-for-ios) | [Android](https://keybase.io/_/download/keybase-for-android)

```
brew install --cask keybase
```

- [ ] Zoom: [Website](https://zoom.us/) | [Mac](https://zoom.us/download#client_4meeting) | [Windows](https://zoom.us/download#client_4meeting) | [iPhone](https://apps.apple.com/us/app/id546505307) | [Android](https://play.google.com/store/apps/details?id=us.zoom.videomeetings) | [Chrome](https://chrome.google.com/webstore/detail/zoom-chrome-extension/kgjfgplpablkjnlkjmjdecgdpfankdle?hl=en&gl=US&authuser=1)

```
brew install --cask zoom
```

- [ ] Telegram: [Website](https://telegram.org/) | [Mac](https://apps.apple.com/gb/app/telegram/id747648890?mt=12) | [Windows](https://telegram.org/apps) | [iPhone](https://apps.apple.com/app/telegram-messenger/id686449807) | [Android](https://telegram.org/android) | [Chrome](https://chrome.google.com/webstore/detail/telegram/clhhggbfdinjmjhajaheehoeibfljjno)

```
brew install --cask telegram
```

- [ ] WhatsApp: [Website](https://www.whatsapp.com/) | [Mac](https://www.whatsapp.com/download) | [Windows](https://www.whatsapp.com/download) | [iPhone](https://apps.apple.com/us/app/whatsapp-messenger/id310633997) | [Android](https://play.google.com/store/apps/details?id=com.whatsapp&pcampaignid=web_share) | [Chrome](https://chrome.google.com/webstore/detail/web-for-whatsapp/agelpmkaibloibilkiakjbpcknocomeo)

```
brew install --cask whatsapp
```

### Cloud Drive Mounter

- [ ] CloudMounter: [Website](http://mac.eltima.com/mount-cloud-drive.html) | [Mac](https://mac.eltima.com/download-cloud-mount.html)

```
brew install --cask cloudmounter
```

- [ ] ExpanDrive: [Website](https://www.expandrive.com/) | [Mac](https://www.expandrive.com/download-expandrive) | [Windows](https://www.expandrive.com/download-expandrive)

```
brew install --cask expandrive
```

- [ ] Mountain Duck: [Website](https://mountainduck.io/) | [Mac](https://dist.mountainduck.io/Mountain%20Duck-4.16.3.22374.zip) | [Windows](https://dist.mountainduck.io/Mountain%20Duck%20Installer-4.16.3.22374.exe)

```
brew install --cask mountain-duck
```

### File sharing

- [ ] Dropbox: [Website](https://www.dropbox.com/en_GB/) | [Mac](https://www.dropbox.com/desktop) | [Windows](https://www.dropbox.com/desktop) | [iPhone](https://apps.apple.com/gb/app/dropbox/id327630330) | [Android](https://play.google.com/store/apps/details?id=com.dropbox.android&hl=en_GB) | [Chrome](https://chrome.google.com/webstore/detail/dropbox/ioekoebejdcmnlefjiknokhhafglcjdl)

```
brew install --cask dropbox
```

- [ ] OneDrive💲: [Website](https://www.microsoft.com/en-gb/microsoft-365/onedrive/online-cloud-storage) | [Mac](https://www.microsoft.com/en-gb/microsoft-365/onedrive/download) | [Windows](https://www.microsoft.com/en-gb/microsoft-365/onedrive/download) | [iPhone](https://apps.apple.com/us/app/microsoft-onedrive/id477537958) | [Android](https://play.google.com/store/apps/details?id=com.microsoft.skydrive&hl=en_GB&gl=US) | [Chrome](https://chrome.google.com/webstore/detail/onedrive/nffchahhjecejoiigmnhhicpoabngedk)

```
brew install onedrive
```

### Privacy

- [ ] Little Snitch: [Website](https://www.obdev.at/products/littlesnitch/index.html) | [Mac](https://www.obdev.at/products/littlesnitch/download.html)

```
brew install --cask little-snitch
```

- [ ] Radio Silence 💲: [Website](https://radiosilenceapp.com/) | [Mac](https://radiosilenceapp.com/download)

```
brew install --cask radio-silence
```

### Website Audit and SEO

- [ ] Website Auditor 💲: [Website](https://www.link-assistant.com/website-auditor/) | [Mac](https://www.link-assistant.com/website-auditor/) | [Windows](https://www.link-assistant.com/website-auditor/)
- [ ] Screaming Frog SEO Spider: [Website](https://www.screamingfrog.co.uk/seo-spider/) | [Mac](https://www.screamingfrog.co.uk/seo-spider/) | [Windows](https://www.screamingfrog.co.uk/seo-spider/)

```
brew install --cask screaming-frog-seo-spider
```

<br />

## Optional Mac modifications

Here are a few Mac modifications that I truly enjoy, and I thought you might appreciate them too.

Add separators to dockbar

```
defaults write com.apple.dock persistent-apps -array-add '{ "tile-type" = "spacer-tile"; }'; Killall Dock
```

![Mac dock](/images/mac-dock.png "Mac dock")

Add recent files stack to dockbar

```
defaults write com.apple.dock persistent-others -array-add '{ "tile-data" = { "list-type" = 1; }; "tile-type" = "recents-tile"; }'; Killall Dock
```

How to make TextEdit open with a blank file by default?

```
System Prefrences > iCloud > iCloud Drive ( Options ) > uncheck textEdit
```