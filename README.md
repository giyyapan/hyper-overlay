<div align="center">
  <p>
  <a href="https://favware.tech"><img src="https://raw.githubusercontent.com/Favna/hyper-overlay/master/assets/traystatic.png" height="200" alt="logo"/></a>
  </p>

  <p>
<h1> Hyper Overlay </h1>
<h3> Elegant way to have your hyper terminal at your fingers anywhere, anytime</h3>
  </p>

<p>
<img src="https://cloud.githubusercontent.com/assets/924158/17121698/d122bcaa-52ab-11e6-876c-25a267d00e89.gif" title="homeMacOS" alt="homeMacOS" width="430" align="middle"/><img src="https://raw.githubusercontent.com/Favna/hyper-overlay/master/assets/home.gif" title="homeWin" alt="homeWin" width="430" align="middle"/>
</p>
</div>

---

**Project Status**

[![GitHub](https://img.shields.io/github/license/favna/hyper-overlay?logo=github&style=flat-square)](https://github.com/favna/hyper-overlay/blob/master/LICENSE.md)

**Bundle Sizes**

[![npm bundle size](https://img.shields.io/bundlephobia/min/hyper-overlay?label=hyper-overlay%20-%20minified&logo=webpack&style=flat-square)](https://bundlephobia.com/result?p=hyper-overlay)
[![npm bundle size](https://img.shields.io/bundlephobia/minzip/hyper-overlay?label=hyper-overlay%20-%20minzipped&logo=webpack&style=flat-square)](https://bundlephobia.com/result?p=hyper-overlay)
[![npm](https://img.shields.io/npm/v/hyper-overlay?color=crimson&label=hyper-overlay%20version&logo=npm&style=flat-square)](https://www.npmjs.com/package/hyper-overlay)

**Social Media and Donations**

[![Join Discord server](https://img.shields.io/discord/512303595966824458?color=697EC4&label=Join%20Discord%20Server&logo=discord&logoColor=FDFEFE&style=flat-square)](https://favware.tech/redirect/server)
[![Twitter Follow](https://img.shields.io/twitter/follow/favna_?label=Follow%20@Favna_&logo=twitter&colorB=1DA1F2&style=flat-square)](https://twitter.com/Favna_/follow)
[![Patreon Donate](https://img.shields.io/badge/patreon-donate-brightgreen.svg?label=Donate%20with%20Patreon&logo=patreon&colorB=F96854&style=flat-square&link=https://www.patreon.com/bePatron?u=9336537)](https://www.patreon.com/bePatron?u=9336537)
[![PayPal Donate](https://img.shields.io/badge/paypal-donate-brightgreen.svg?label=Donate%20with%20Paypal&logo=paypal&colorB=00457C&style=flat-square&link=https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=XMAYCF9SDHZ34)](https://www.patreon.com/bePatron?u=9336537)

---

# Fork Note

Frok from [Favna/hyper-overlay](https://github.com/Favna/hyper-overlay) and fixed the issue that focus is not switching back to previous application after hide the overlay window.

Using solution from PR https://github.com/rickgbw/hyperterm-overlay/pull/39.

Related issues:
- https://github.com/rickgbw/hyperterm-overlay/issues/38

The tweaked package is published in npm: [giyyapan-hyper-overlay](https://www.npmjs.com/package/giyyapan-hyper-overlay).

---

Notes below are from the original repo:

---

# PLEASE NOTE

This project should be considered stale. I do not have time nor enough knowledge of Electron and Hyper to support it the current time. I cannot guarantee that I will ever invesst enough time in either the framework or the application to support it. While it *may* work it should be expected to have bugs, and they will not be fixed.

---

A complete and customizable solution for a permanent / dropdown / hotkey / overlay window in your Hyper Terminal, accessible via hotkeys and/or toolbar icon (tray).

Open your overlay with `Option + Space` on MacOS or `Control + Space` on Windows / Linux or by clicking the tray icon. `Escape` is the hotkey for hiding the overlay, or you can press `X` , `-` , or click the tray icon again.

This has been forked from [hyperterm-overlay](https://github.com/rickgbw/hyperterm-overlay) which appears to have been deserted and aims to fix some of the issues on that GitHub repository.

**Important:** Designed for Hyper >= 2.0.0

## Install

Option 1 (using hyper's package manager):

Use `hyper i hyper-overlay` 

Option 2 (manual):

Edit your `~/.hyper.js` ( `Cmd|Control+,` ) and insert the `hyper-overlay` in your `plugins` array:

``` js
plugins: [
    'hyper-overlay'
],
```

## Configuration

Add `overlay` in your `~/.hyper.js` config.
The configuration below shows all possibilities with their respective default values.

``` js
module.exports = {
    config: {
        // other configs...
        overlay: {
            alwaysOnTop: true,
            animate: true,
            hasShadow: false,
            hideDock: false,
            hideOnBlur: false,
            hotkeys: {
                open: ['Control+Space'], // On MacOS hotkey is default to Option + Space!
                close: ['Shift+Escape'], // On MacOS hotkey is default to Option + Escape!
            },
            position: 'top',
            primaryDisplay: false,
            resizable: true,
            size: {
                width: 0.4,
                height: 0.4
            },
            startAlone: false,
            startup: false,
            tray: true,
            unique: false
        }
    },
    // ...
};
```

### alwaysOnTop

* Value: true or false
* Default: true
* Makes Hyper Overlay window stay always on top.

### animate

* Value: true or false
* Default: true
* Enable animation when show and hide the window.

### hasShadow

* Value: true or false
* Default: false
* Controls the default macOS window shadows.

### hideOnBlur

* Value: true or false
* Default: false
* Hides the Hyper Overlay when it loses focus.

### hideDock

* Value: true or false
* Default: false
* Removes the Hyper dock icon. It works only when the `unique` option is activated.

### hotkeys

#### Open

* Value: array of hotkey strings
* Default: ['Option+Space'] on MacOS or ['Control+Space'] on Windows / Linux
* Specify one or more hotkeys to show and hide the Hyper Overlay (see: [ `Accelerator` ](https://github.com/electron/electron/blob/master/docs/api/accelerator.md))

#### Close (hide)

* Value: array of hotkey strings
* Default: ['Option+Escape'] on MacOS or ['Shift+Escape'] on Windows / Linux
* Specify one or more hotkeys to hide the Hyper Overlay (see: [ `Accelerator` ](https://github.com/electron/electron/blob/master/docs/api/accelerator.md))

### position

* Value: `top` , `bottom` , `left` , `right` , `topRight` , `topLeft` , `bottomRight` , `bottomLeft` , `center` 
* Default: 'top'
* Choose where Hyper Overlay will be positioned

### primaryDisplay

* Value: true or false
* Default: false
* Show Hyper Overlay only on primary display.

### resizable

* Value: true or false
* Default: true
* Allow the Hyper Overlay be resizable.

<div align="center">
  <p>

    <img src="https://cloud.githubusercontent.com/assets/924158/17121469/5281a916-52aa-11e6-92f5-fa1c3dff75c8.gif" title="resizeMacOS" alt="resizeMacOS" width="430" align="middle" /><img src="https://raw.githubusercontent.com/Favna/hyper-overlay/master/assets/resize.gif" title="resizeWin" alt="resizeWin" width="430" align="middle" />

  </p>
</div>

### size

#### width

* Value: A value between 0.1 and 1
* Default: 0.4
* The width of Hyper Overlay when it is showing.

#### height

* Value: A value between 0.1 and 1
* Default: 0.4
* The height of Hyper Overlay when it is showing.

#### visibleOnAllWorkspaces

* Value: true or false
* Default: false
* Let Hyper window be visible in all workspaces

### startAlone

* Value: true or false
* Default: false
* Makes Hyper Overlay the unique window displayed when started.
* Other windows started will be default Hyper windows.

### startup

* Value: true or false
* Default: true
* Open Hyper Overlay on Hyper startup.

### tray

* Value: true or false
* Default: true
* Add icon to the system notification area, for access Hyper Overlay.

<div align="center">
  <p>

    <img src="https://cloud.githubusercontent.com/assets/924158/17121470/5294b02e-52aa-11e6-9bca-9d70f186c60b.gif" title="trayMacOS" alt="trayMacOS" width="430" align="middle" /><img src="https://raw.githubusercontent.com/Favna/hyper-overlay/master/assets/hideonblur.gif" title="trayWin" alt="trayWin" width="430" align="middle" />

  </p>
</div>

### unique

* Value: true or false
* Default: false
* Makes Hyper Overlay the unique window of Hyper. Any other window will be removed.

## Other plugins in gifs

[hyper-material-theme](https://www.npmjs.com/package/hyper-material-theme)

[hyper-tab-icons](https://www.npmjs.com/package/hyper-tab-icons)

[hyper2-border](https://www.npmjs.com/package/hyper2-border)

### License

Copyright © 2019, [Favware](https://github.com/favware).
Released under the [MIT License](LICENSE).

### Buy us a donut

Favware projects are open source and always will be, even if there are no donations. That said, we also know there are people out there that may still want to donate just to show their appreciation so this is for you guys. Thanks in advance!

We accept donations through PayPal, BitCoin, Ethereum and LiteCoin. You can use the buttons below to donate through your method of choice

|Donate With|QR|Address|
|:---:|:---:|:---:|
<a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=XMAYCF9SDHZ34"><img src="https://storage.googleapis.com/data-sunlight-146313.appspot.com/ribbon/paypaldonate.png"></a>|<a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=XMAYCF9SDHZ34"><img src="https://storage.googleapis.com/data-sunlight-146313.appspot.com/ribbon/paypalqr.png" width="128"></a>|[Donate with PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=XMAYCF9SDHZ34)|
<img src="https://storage.googleapis.com/data-sunlight-146313.appspot.com/ribbon/bitcoindonate.png">|<img src="https://storage.googleapis.com/data-sunlight-146313.appspot.com/ribbon/bitcoinqr.png" width="128">|<a href="bitcoin:1E643TNif2MTh75rugepmXuq35Tck4TnE5?amount=0.01&label=favware%27%20Ribbon%20Discord%20Bot">1E643TNif2MTh75rugepmXuq35Tck4TnE5</a>|
<img src="https://storage.googleapis.com/data-sunlight-146313.appspot.com/ribbon/ethereumdonate.png">|<img src="https://storage.googleapis.com/data-sunlight-146313.appspot.com/ribbon/ethereumqr.png" width="128">|<a href="ethereum:0xF653F666903cd8739030D2721bF01095896F5D6E?amount=0.01&label=favware%27%20Ribbon%20Discord%20Bot">0xF653F666903cd8739030D2721bF01095896F5D6E</a>|
<img src="https://storage.googleapis.com/data-sunlight-146313.appspot.com/ribbon/litecoindonate.png">|<img src="https://storage.googleapis.com/data-sunlight-146313.appspot.com/ribbon/litecoinqr.png" width="128">|<a href="litecoin: LZHvBkaJqKJRa8N7Dyu41Jd1PDBAofCik6?amount=0.01&label=favware%27%20Ribbon%20Discord%20Bot">LZHvBkaJqKJRa8N7Dyu41Jd1PDBAofCik6</a>|

