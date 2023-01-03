What's new in v1.1.9

Released December 23, 2022

The Installer has been updated to use Electron v21 (requires downloading the latest Installer from [https://obsidian.md](https://obsidian.md/)).

## No longer broken

-   The page preview popover no longer shows file names twice.
-   Canvas: Fixed "reload page" menu item not working consistently.
-   File recovery now supports canvas files.
-   Prevent `obsidian://new` URIs from creating folders outside of the vault.
-   Prevent external websites embedded in canvas and plugins from opening URI links.

What's new in v1.1.8

Released December 20, 2022

## Improved

-   Canvas: YouTube embeds are now shown at 16:9 instead of square.
-   Canvas: Added a "privacy" toggle to the export modal. This will allow you to share the canvas while masking all the text on the cards.
-   Canvas: Added a command to export your canvas as an image.

## No longer broken

-   Canvas: Auto-resizing file cards now works more reliably.
-   Canvas: Fixed bug where pressing undo (`Ctrl/Cmd + Z`) would undo the file rename in addition to undoing an action on the Canvas.
-   Canvas: Fixed issue where creating a new text card does not always zoom in to edit automatically.
-   Canvas: Fixed crash when opening a modal while an iframe was focused.

What's new in v1.1.7

Released December 19, 2022

## Improved

-   Canvas: Added new alignment options to justify content horizontally or vertically.
-   Canvas: the drag handles has been removed from connection lines. Now you can drag from anywhere on the line to move it.

## No longer broken

-   Canvas: fixed extra spacing being added to the top of cards.
-   Fixed duplicate titles appearing for embedded notes (i.e. `![[some note]]`).
-   Fixed hotkeys acting inconsistently across pop-out windows when a modal was visible.
-   Canvas: fixed group label getting truncated while editing.
-   Canvas: fixed bug where the file title would stay selected after updating the title. This caused some unexpected behavior when pressing undo (`Ctrl/Cmd + Z`) or paste (`Ctrl/Cmd + V`).

What's new in v1.1.6

Released December 16, 2022

## Improved

-   Canvas: Inline titles now render in file cards when enabled.
-   Canvas: Replaced the "Copy screenshot" canvas menu item with a new "export as image" menu option. This will allow you to export either the current viewport or a full high resolution PNG of your canvas.
-   Canvas: Embedded canvases now show the connection lines in addition to the card boxes.

## No longer broken

-   Renaming a file will no longer cause the current scroll position to be lost.
-   Canvas: File-specific options have been removed file card's context menu if the card is narrowed to a specific heading.
-   Canvas: Dragging a nested group will no longer try to snap to itself. This was causing some jittering.
-   Canvas: fixed "Replace" command not working in canvas file cards.
-   Canvas: Fixed an issue where following links from the canvas would prevent editor-specific hotkeys from firing.
-   Canvas: Fixed loading a website in a pop-out window causes Obsidian to crash on boot.

What's new in v1.1.5

Released December 14, 2022

## Improved

-   Embedded canvases now render a diagram of the underlying canvas. This works for canvases embedded within markdown files (i.e. `![[daily_notes.canvas]]`) or embedded on another canvas.
-   Canvas: Add new options to distribute vertically/horizontally, stack vertically/horizontally, and auto-organize cards into grid.
-   Canvas: The Find/replace menu (`Ctrl/Cmd+F`) now works inside cards embedded in the canvas.
-   Canvas: Web pages now has a menu to open in the browser, you can also `Ctrl/Cmd`-click the card label.
-   Canvas: Slight performance improvements when interacting with larger canvases.
-   Canvas: Added "Go to source" and "Go to target" menu items on the connection context menu to quickly jump to nodes.
-   Canvas: `Ctrl/Cmd` + Drag now shows a menu to quickly add a card or create a group where your selection is.
-   Canvas: Images, websites, videos, and audio will now always render instead of becoming a grey box when zoomed out.
-   Sync: When merging during a sync conflict, the original local version is now stored in File Recovery (if enabled).

## No longer broken

-   Fixed bug preventing hotkeys from being set if there is no default hotkey.
-   Canvas: Links and embeds inside text cards will now properly get updated when the target files are renamed.
-   Canvas: Fixed duplicating groups not copying their children cards.
-   Canvas: Fixed bug where opening a new canvas in a hidden tab would occasionally go blank and crash.
-   Canvas: Fixed bug causing some websites to crash when moving a canvas view to a popout window.
-   Canvas: Fixed issue where websites could not be interacted with in a popout window.
-   Canvas: PDFs should be slightly less blurry.
-   Canvas: Fixed bug where cards are unable to resize when an adjacent card is touching.

What's new in v1.1.4

Released December 12, 2022

## Shiny new things

-   Canvas: Added "Groups" to canvas. Groups can be thought of as placemats for your cards. They always render below cards and dragging the group label will move all notes in the group at once. To create a group, select multiple cards then right-click and choose 'Create group.'

## Improved

-   Canvas: Improved performance when interacting with large canvases.
-   Canvas: On Windows and Linux, you now hold `Ctrl` to duplicate the selection instead of `Alt`. On macOS, this is still `Option+Drag`.
-   Canvas: Added right-click and drag to pan around the viewport.
-   Canvas: Added 'copy screenshot' menu item.
-   Canvas: Added 'reset zoom' button.
-   Canvas: Double-clicking the bottom of a card now auto expands it to the size of the contents.
-   Canvas: The canvas will always zoom to fit on open.
-   Canvas: PDFs and iframes that have been interacted with will stay loaded even when zoomed out.
-   Canvas: text cards now have dynamic padding so they shouldn't appear with scrollbars on small sizes.
-   Canvas: Web pages now have a label with the site title.
-   Canvas: Right-clicking on web pages now gives the option to copy the URL or reload the page.

## No longer broken

-   Canvas: The connection menu will exclude embeds.
-   Canvas: Fixed issue where deleted cards and connections would sometimes reappear and be un-selectable.
-   Adding a hotkey to a default hotkey no longer results in the default hotkey being removed.

## Developers

-   Canvas files are now multi-line formatted when saved. This should make the diffs more human-readable when stored in version control.

What's new in v1.1.3

Released December 9, 2022

## Improved

-   Live Preview has been tweaked to avoid flashes of "unstyled" content while scrolling through larger documents.
-   Canvas: We have updated how colors work inside of Canvas. The six colors in the color palette are now themeable. There is a new 7th slot with a color picker.
-   Canvas: Added a new menu item to paste in a web URL. Right clicking on an existing web page in Canvas now shows an option to change the URL.
-   Canvas: YouTube links will now automatically get inserted as Youtube's embed version.
-   Canvas: There's a new 'help' button to view all the currently hotkeys available for Canvas.
-   Canvas: Dragging a connection line from a file card now shows a menu with all outgoing links to quickly add them as connections.
-   Canvas: Added a new 'Narrow...' menu option to file cards. This will narrow the card contents to only the selected heading.

## No longer broken

-   The frontmatter YAML will now always be hidden in reading mode. The "Show frontmatter" toggle now toggles the metadata section.
-   macOS: Fixed bug in Canvas where cards would drag when ctrl-clicking.
-   Fixed issue when using multiple cursors where an extra cursor would appear in the top right.
-   .canvas files now show in the editor link suggest.
-   Linux: middle-clicking on the canvas will no longer trigger 'paste.'

## Developers

-   Added a notice when opening a Canvas that fails to parse.

What's new in v1.1.2

Released December 8, 2022

## No longer broken

-   Canvas: fixed bug where text nodes don't always save their content.

What's new in v1.1.1

Released December 8, 2022

## Improved

-   Canvas: 'delete' has been renamed to 'remove' to avoid confusion.
-   Canvas: cards can now be dragged by the filename label.
-   Canvas: `Ctrl/Command`-clicking on a filename label will open that file in a new tab.
-   Other plugin views should now properly respond to selecting a card in the Canvas. This includes the Outline pane, the Backlinks pane, etc.
-   Templates core plugin properly inserts into the canvas editor.
-   The viewport will now pan while dragging nodes close to the edge of the screen.
-   Pressing `Shift-enter` inside the file select modal in canvas will now create a file based on your current input (same as the quick switcher behavior).
-   Improved appearance of file name modal when using "Convert to file..." Canvas action.
-   Increased the max zoom distance in Canvas.

## No longer broken

-   Sync: canvas files will now sync between devices (oops!)
-   Canvas: fixed bug causing editor to occasionally lose track of inserted text and cursor position when typing quickly.
-   Canvas: connections cannot be drawn from a card back to itself.
-   Canvas: fixed issue where shift-clicking on a card would cause the editor to appear in an unfocused card.
-   Canvas: fixed text suggest menu not closing when clicking outside of a card.
-   Canvas: Fixed dragging links from cards into their own cards.
-   Canvas: Fixed dragging links from the embedded canvas editor.
-   File explorer: added back missing 'Open in new window' command to the context menu.

## Developers

_See v1.1.1 in the [Developer CHANGELOG](https://github.com/obsidianmd/obsidian-api/blob/master/CHANGELOG.md#v111-2022-12-8--insider-build)_.

What's new in v1.1.0

Released December 5, 2022

## New shiny things

-   Introducing the **Canvas** core plugin. You can now lay your notes out in an infinite, spatial canvas.

![canvas-promo](https://user-images.githubusercontent.com/693981/205718501-d9fe405b-6684-41c8-a3b3-eb5da73777d2.png)

## Improved

-   Ribbon items can now be rearranged (drag & drop) or hidden (right click on the ribbon for options). Configuration is also available in Settings (`Appearance › Ribbon menu`). Note: if you are using an existing plugin to manage the ribbon, this might interfere.
-   Plugins can now be sorted by "Recently updated."
-   Added theme version information to the debug modal.
-   Added "Close window" command (`Ctrl/Command + Shift + W`).
-   Pressing `Shift + Enter` in the editor Find Dialog will find the previous instance.

## No longer broken

-   Linux: fixed middle-click to paste.
-   'Split' commands will now focus the newly created tab group.
-   Fixed issue where File explorer would not always select the right items when using shift-clicking.
-   Popout windows will now open with the same zoom level as the main window
-   Fixed `Home` behavior in task lists.
-   Moving folders to the Obsidian trash (`.trash`) will no longer add a trailing `.`
-   Fix ordered lists showing as bullets.
-   Plugin gallery will no longer cache the results if there's no internet connection.
-   macOS: fixed issue with spell check replacing the wrong word on the same line.
-   Improved styling of text when the accent color is lighter than a certain threshold.
-   Fixed "Fold more" and "Fold less" commands not working properly on list items.
-   The File explorer will no longer capture arrow key events when modifier keys are used. This was breaking hotkeys such as `Ctrl + Shift + →`.
-   Fixed issue with folds in Reading mode getting unfolded when creating a new tab.

## Developers

-   We have added a [Developer CHANGELOG](https://github.com/obsidianmd/obsidian-api/blob/master/CHANGELOG.md) to our API repo. Moving forward, we will keep developer-facing changes catalogued here.
-   Added new metadata APIs
-   Added macOS calendar entitlements
-   Added support for `fundingUrl` in the plugin manifest. The donation URL will be shown in the plugin gallery entry.

---

# What's new in v1.1

Released December 20, 2022

This update unlocks even more flexibility into how you work in Obsidian. Some of the highlights include:

-   [Canvas plugin](app://obsidian.md/index.html#canvas) — A brand new core plugin for Obsidian. Arrange your notes in an infinite canvas.
-   [Customizable ribbon](app://obsidian.md/index.html#customizable-ribbon) — Control what items appear in your ribbon and the order they appear in.
-   [Some quality of life improvements for plugin developers](app://obsidian.md/index.html#developer-improvements) — A new metadata API, a way to configure a donation URL, and a changelog for the Obsidian API.

## Canvas

Canvas is a new core plugin for Obsidian. It allows you to lay out your notes on an infinite, spatial canvas.

![canvas-promo](https://user-images.githubusercontent.com/693981/205718501-d9fe405b-6684-41c8-a3b3-eb5da73777d2.png)

Canvas can be a place to synthesize your notes, a dashboard for navigating your second brain, or your new Obsidian workstation.

We’ve outlined some of the basic Canvas features in [our Help Vault](https://help.obsidian.md/Plugins/Canvas). For more advanced usage, check out our [collection of Protips](https://obsidian.md/canvas#protips).

Then press the "Create new canvas" button on the left-side ribbon to jump right in!

## Customizable Ribbon

Ribbon items can now be rearranged (drag & drop) or hidden (right click on the ribbon for options). Configuration is also available in Settings (`Appearance › Ribbon menu`).

![ribbon-drag-and-drop](https://user-images.githubusercontent.com/693981/208676459-7a94bbc3-a16d-4d19-8d71-64e901ed3607.png)

**Note:** if you are using an existing plugin to manage the ribbon, this might interfere.

## Developer Improvements

### Developer Changelog

We have added a [Developer Changelog](https://github.com/obsidianmd/obsidian-api/blob/master/CHANGELOG.md) to our API repo. Moving forward, we will keep developer-facing changes catalogued here.

### Metadata API

We've added a new metadata API for easily adding and updating frontmatter. For more basic usage information, check out [the guide in the changelog](https://github.com/obsidianmd/obsidian-api/blob/master/CHANGELOG.md#v110-2022-12-05--insider-build).

### In-App Improvements

The community plugins list can now be sorted by "recently updated." This should improve plugin discovery for more actively developed plugins as well as help users identify which plugins are still actively maintained.

![sort-recently-released](https://user-images.githubusercontent.com/693981/208675825-87fb6a93-c502-42e8-bffa-c3152b4aac7f.png)

For theme developers, we've also added theme information to the debug modal. When users submit theme related issues, now you can ask them to send the debug modal information to accelerate the information-gathering phase.

Finally, you can choose to include a `fundingUrl` in your plugin manifest. Users will be shown a link in-app to donate to you. You can put your Buy Me A Coffee links or Ko-fi here.

## Additional Improvements & Bug Fixes

-   Linux: fixed middle-click to paste.
-   'Split' commands will now focus the newly created tab group.
-   Fixed issue where File explorer would not always select the right items when using shift-clicking.
-   Popout windows will now open with the same zoom level as the main window
-   Fixed `Home` behavior in task lists.
-   Moving folders to the Obsidian trash (`.trash`) will no longer add a trailing `.`
-   Fix ordered lists showing as bullets.
-   Plugin gallery will no longer cache the results if there's no internet connection.
-   macOS: fixed issue with spell check replacing the wrong word on the same line.
-   Improved styling of text when the accent color is lighter than a certain threshold.
-   Fixed "Fold more" and "Fold less" commands not working properly on list items.
-   The File Explorer will no longer capture arrow key events when modifier keys are used. This was breaking hotkeys such as `Ctrl + Shift + →`.
-   Fixed issue with folds in Reading mode getting unfolded when creating a new tab.
-   The frontmatter YAML will now always be hidden in reading mode. The "Show frontmatter" toggle now toggles the metadata section.

---

## FAQ

**Q.** Is Canvas going to be available on mobile?

> Yes! _Eventually._ The mobile version is still in development and won't be available until the new year. Canvas is one of our most ambitious undertakings to date, so it will take some time to properly adapt it to the mobile experience. We appreciate your patience.

**Q.** Why don't Canvas files show up in Search or Backlinks?

> These features are both planned and will be introduced in a later release.

**Q.** What is a `.canvas` file? Is the format open-source?

> Canvas stores its data as JSON files with a special `.canvas` file extension. The JSON format is defined in [an open source spec](https://github.com/obsidianmd/obsidian-api/blob/master/canvas.d.ts) licensed with an MIT license.

---

A complete list of previous changes can be found on [our forum](https://forum.obsidian.md/c/announcements/13).