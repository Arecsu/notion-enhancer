# changelog

**potential future features (not confirmed)**

- [groupy-like tabbing](https://www.npmjs.com/package/electron-tabs)
- [improved responsiveness](https://chrome.google.com/webstore/detail/notion%20%20-responsiveness-f/leadcilhbmibbkgbnjgmmnfgnnhmeddk)
- [highlight/mark viewer](https://chrome.google.com/webstore/detail/notion%2B-mark-manager/hipgmnlpnimedfepbfbfiaobohhffcfc)
- [advanced math editor](https://github.com/Manueloccorso/NotionMathEditor_BrowserExtension)
- re-orderable extensions

### v0.9.1 (2020-09-26)

- bugfix: font chooser will continue iterating through fonts after encountering a blank option.
- bugfix: block indents are no longer overriden.
- bugfix: neutral does not force full width pages.
- bugfix: bypass preview extension works with the back/forward arrows.
- bugfix: check all views on a page for a weekly calendar.
- bugfix: emoji sets no longer modifies the user agent = doesn't break hotkeys.

> 📥 `npm i -g notion-enhancer@0.9.1`

### v0.9.0 (2020-09-20)

a feature and cleanup update.

- improved: halved the number of css rules used -> much better performance.
- improved: font imports must be define in the `mod.js` so that they can also be used in
  the enhancements menu.
- improved: tiling window-manager support (can hide titlebars entirely without dragarea/buttons).
- improved: extensions menu search is now case insensitive and includes options, inputs and versions.
  the search box can also for focused with `CMD/CTRL+F`.
- improved: extensions menu filters shown either a ✓ or × to help understand the current state.
- improved: added individual text-colour rules for different background colours.
- improved: added variables for callout colouring.
- improved: replaced with `helpers.getNotion()` with the constant `helpers.__notion` to reduce
  repeated function calls.
- improved: added variables for page width.
- improved/bugfix: emoji sets extension should now work on macOS and will change user agent to use
  real emojis instead of downloading images when system default is selected.
- bugfix: enhancer settings should no longer reset on update (though this will not have
  effect until the release after this one).
- bugfix: blue select tags are no longer purple.
- bugfix: page titles now respond to small-text mode.
- bugfix: weekly calendar view height is now sized correctly according to its contents.
- bugfix: made the open enhancements menu hotkey configurable and changed the default to `ALT+E`.
  to remove conflict with the inline code highlight shortcut.
- bugfix: update property-layout to match notion changes again.
- bugfix: updated some of the tweak styling to match notion changes.
- bugfix: block-level text colours are now changed properly.
- bugfix: do not require data folder during installation, to prevent `sudo` attempting to
  create it in `/var/root/`.
- bugfix: bullet points/checkboxes will now align properly in the right-to-left extension.
- themes: "littlepig" (light + dark) = monospaced themes using emojis and colourful text.
- extension: "font chooser" = customize fonts. for each option, type in the name of the font you would like to use,
  or leave it blank to not change anything.
- extension: "always on top" = add an arrow/button to show the notion window on top of other windows
  even if it's not focused.
- extension: "calendar scroll" = add a button to scroll down to the current week in fullpage/infinite-scroll calendars.
- extension: "hide help button" = hide the help button if you don't need it.
- extension: "bypass preview" = go straight to the normal full view when opening a page.
- extension: "word counter" = add page details: word/character/sentence/block count & speaking/reading times.

notion-deb-builder has been discovered to not generate an app.asar and so is no longer supported.

> 📥 `npm i -g notion-enhancer@0.9.0`

### v0.8.5 (2020-08-29)

- bugfix: separate text highlight and select tag variables.
- bugfix: bypass CSP for the `enhancement://` protocol - was failing on some platforms?

> 📥 `npm i -g notion-enhancer@0.8.5`

### v0.8.4 (2020-08-29)

- bugfix: property-layout now works consistently with or without a banner.

> 📥 `npm i -g notion-enhancer@0.8.4`

### v0.8.3 (2020-08-29)

previous release was a mistake: it did as intended on linux, but broke windows.
this should achieve the same thing in a more compatible way.

> 📥 `npm i -g notion-enhancer@0.8.3`

### v0.8.2 (2020-08-28)

some things you just can't test until production... fixed the auto-installer
to use `./bin.js` instead of `notion-enhancer`

> 📥 `npm i -g notion-enhancer@0.8.2`

### v0.8.1 (2020-08-28)

a clarity and stability update.

- improved: more informative cli error messages (original ones can be accessed with the `-d/--dev` flag).
- bugfix: gallery variable didn't apply on fullpage.
- bugfix: date picker hid current date number.
- bugfix: small-text pages should now work as expected.
- bugfix: padding issues in page previews.
- bugfix: property-layout extension had been broken by internal notion changes.
- bugfix: linux installer path typo.
- bugfix: caret-color was being mistaken for color and block-level text colouring was broken.
- improved: auto-application on install.

> 📥 `npm i -g notion-enhancer@0.8.1`

### v0.8.0 (2020-08-27)

complete rewrite with node.js.

- new: simpler cli installation system (inc. commands: `apply`, `remove`, and `check`).
- new: mod loading system (easier to create new mods, adds to notion rather than overwriting).
- new: mod configuration menu.
- improved: more theming variable coverage - inc. light theme and sizing/spacing.
- bugfix: non-reproducable errors with python.
- bugfix: better launcher patching on linux.
- bugfix: fix frameless window issue introduced by notion desktop 2.0.9.
- extension: "custom inserts" = link files for small client-side tweaks.
- extension: "bracketed links" = render links surrounded with \[\[brackets]] instead of underlined.
- extension: "focus mode" = hide the titlebar/menubar if the sidebar is closed (will be shown on hover).
- theme: "dark+" = a vivid-colour near-black theme.
- theme: "neutral" = smoother colours and fonts, designed to be more pleasing to the eye.
- theme: "gameish" = a purple, "gamer-styled" theme with a blocky-font.
- theme: "pastel dark" = a smooth-transition true dark theme with a hint of pastel.
- extension: "emoji sets" = pick from a variety of emoji styles to use.
- extension: "night shift" = sync dark/light theme with the system (overrides normal theme setting).
- extension: "right-to-left" = enables auto rtl/ltr text direction detection. (ported from [github.com/obahareth/notion-rtl](https://github.com/obahareth/notion-rtl).)
- extension: "weekly view" = calendar views named "weekly" will show only the 7 days of this week. (ported from [github.com/adihd/notionweeklyview](https://github.com/adihd/notionweeklyview).)]
- extension: "property layout" = auto-collapse page properties that usually push down page content. (ported from [github.com/alexander-kazakov/notion-layout-extension](https://github.com/alexander-kazakov/notion-layout-extension).)

> 📥 `npm i -g notion-enhancer@0.8.0`

### v0.7.0 (2020-07-09)

- new: tray option to use system default emojis (instead of twitter's emojiset).
- new: mac support (identical functionality to other platforms with the
  exception of the native minimise/maximise/close buttons being kept, as they integrate
  better with the OS while not being out-of-place in notion).
- new: notion-deb-builder support for linux.
- new: an alert will be shown if there is an update available for the enhancer.
- improved: replaced button symbols with svgs for multi-platform support.
- improved: window close button is now red on hover (thanks to [@torchatlas](https://github.com/torchatlas)).
- bugfix: `cleaner.py` patched for linux.
- bugfix: tray now operates as expected on linux.
- bugfix: odd mix of `\\` and `/` being used for windows filepaths.
- bugfix: app no longer crashes when sidebar is toggled.

> 📥 [notion-enhancer.v0.7.0.zip](https://github.com/dragonwocky/notion-enhancer/archive/v0.7.0.zip)

### v0.6.0 (2020-06-30)

- style: custom fonts.
- style: font resizing.
- style: hide discussions (thanks to [u/Roosmaryn](https://www.reddit.com/user/Roosmaryn/)).
- new: custom colour theming, demonstrated via the dark+ theme.
- new: linux support (thanks to [@Blacksuan19](https://github.com/Blacksuan19)).
- improved: if hotkey is pressed while notion is unfocused, it will bring it to the front rather than hiding it.
- improved: stop window buttons breaking at smaller widths.
- improved: more obviously visible drag area.
- bugfix: specify UTF-8 encoding to prevent multibyte/gbk codec errors (thanks to [@etnperlong](https://github.com/etnperlong)).

> 📥 [notion-enhancer.v0.6.0.zip](https://github.com/dragonwocky/notion-enhancer/archive/v0.6.0.zip)

### v0.5.0 (2020-05-23)

- new: running from the wsl.
- new: reload window with f5.
- improved: code has been refactored and cleaned up,
  inc. file renaming and a `customiser.py` that doesn't require
  a run of `cleaner.py` to build modifications.
  improved: scrollbar colours that fit better with notion's theming.
- bugfix: un-break having multiple notion windows open.

> 📥 [notion-enhancer.v0.5.0.zip](https://github.com/dragonwocky/notion-enhancer/archive/v0.5.0.zip)

**development here taken over by [@dragonwocky](https://github.com/dragonwocky).**

**the ~~crossed out~~ features below are no longer features included by default,**
**but can still easily be added as [custom tweaks](TWEAKS.md).**

### v0.4.1 (2020-02-13)

- bugfix: wider table & the "+" button not working in database pages.

> 📥 [notion-enhancer.v4.1.zip](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d239a3cf-d553-4ef3-ab04-8b47892d9f9a/Notion_Customization_v4.1.zip)

### v0.4.0

- new: tray icon.
- new: app startup options (+ saving).
- new: `Reset.py`
- improved: better output from `Customization Patcher.py`.
- bugfix: wider tables in "short page" mode.
- bugfix: unclickable buttons/draggable area (of titlebar).

### v0.3.0

- new: show/hide window hotkey.
- new: app startup options.
- ~~style: smaller table icons.~~

> 📥 [notion-enhancer.v3.zip](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b01aa446-5727-476a-a25e-395472bfb1be/NotionScriptsV3.zip)

### v0.2.0

- new: light/dark theme support for window control buttons + scrollbars.
- new: custom styles directly linked to the enhancer resources + compatible with web version.
- ~~improved: making table column width go below 100px.~~

### v0.1.0

- new: custom window control buttons.
- removed: default titlebar/menubar.
- ~~removed: huge padding of board view.~~
- ~~removed: huge padding of table view.~~
- ~~optional: making table column width go below 100px.~~
- ~~style: thinner cover image + higher content block.~~
- style: scrollbars.
