---
title: "Version 13.12"
date: 2012-11-25T12:23:47+02:00
draft: false
aliases:
  - /downloads/38
---
For the release 13.12, we provide a top-level changelog hereby about what has changed since 12.11 (to download this or a full change log, links are provided at the bottom of this page):

## General:

- Provide a UI, where almost all color settings can be changed. Allow more colors to be customized.
- Improve the UI for editing "Editor syntax highlight themes".
- Improve multi monitor support for the info window popup.
- Several bug fixed with the Global compiler variables.
- Fix bug "Ticking any checkbox in the File properties dialog cause the file to be made read-only".
- Allow more strings to be translated.
- Improvements/bugfixes to the Find/Replace feature.
- Improvements to the annoying dialog.
- **Add two more terminal presets**: xfce_terminal and terminology.
- Improvements/bugfixes for "Start here page".
- Improvements to the editor - new commands, fixes to old commands, etc.
- Make strip trailing blanks to preserve active line of active editor (fix bug #18845) .
- Try to make visible all toolbars, when a toolbar is shown/hidden and add menu option to fit and optimize the toolbars.
- Improve "swap header/source" command by adding a case-insensitive search as fallback.

## Compiler:

- All default compiler options (flag checkboxes, regexes, file extensions, etc) are stored in XML.
- (Optional) warning messages if multiple compiler options are unwise to use together (but still legal).
- Automatic disabling of mutually exclusive compiler options.
- Options to add, edit, and remove compiler flag checkboxes through the GUI.
- Compiler options are saved back to XML if they are modified (in <user_data>/CodeBlocks/compilers); the resulting files can be shared.
- Dynamic loading of pure XML defined compilers (simple auto-detection routines available).
- Automatically filter C and C++ exclusive flags.
- **New compiler interfaces defined for**: LLVM Clang, IAR ARM, Keil C51, and IAR ICC8051.
- Add registry based autodetection of TDM-GCC.
- Make the gcc compiler be a bit more robust, when making static libraries.
- Don't clear logs before run.

## Code Completion:

- Fix several crashes.
- Fix several parsing bugs.
- Add pseudo semantic highlight feature - recognises class members and styles them differently (disabled by default).
- Don't place the calltip outside of the editor window (this should be modified to not place it outside the monitor, instead).
- Don't place the calltip over the cursor.

## Debugger:

- The locals and function arguments have been reimplemented.
- Bug fixes for parsing watches.
- Allow the user to control which watches should be updated automatically and which shouldn't.
- Allow breakpoints to work, when using C::B under Wine

## Updated third party components:

- pumped astyle lib to v2.0.4 final
- pumped (wx)scintilla to v3.3.5
- pumped wxPDFDoc to 0.9.4 (includes many changes related to wx29)
- pumped underlying squirrel scripting lib from v2.2.4 to v2.2.5 (stable)

## Plugins:

- **Abbreviations**: Add support for multiple languages, fixed some bugs.
- **AStyle**: Applied patch #3478: Add line breaking option to AStyle
- **DoxyBlocks**: Support projects located in path with spaces or other strange characters. Bug fixes.
- **EditorTweaks**: Bug fixes, add features
- **Header Fixup**: Fixed issue reported here: https://forums.codeblocks.org/index.php/topic,17095.0.html
- **Incremental Search**: Avoid conflict in indicators. Add search history with configurable length.
(New) - Occurrence Highlighting: Move occurrence highlighting code from cbEditor into a plugin. (refer here: https://forums.codeblocks.org/index.php/topic,18207.0.html)
- **Smart Indent**: Enable on entire C-language family.
- **Spell Checker**: Fixed bugs. Improve handling of missing dictionaries.
- **Thread Search**: Fixed bugs. Improvements to the UI.
- **ToDo**: Several improvements.

# Summary, for download

Download the short (this) changelog here: https://sourceforge.net/projects/codeblocks/files/Binaries/13.12/changelog

Download the full changelog here: https://sourceforge.net/projects/codeblocks/files/Binaries/13.12/changelog_full

## Older Changelogs

See [Changelog for 12.11](/changelogs/12.11)
