---
title: "Version 12.11"
date: 2012-11-25T12:22:17+02:00
draft: false
aliases:
  - /downloads/31
---
For the release 12.11, we provide a top-level changelog hereby about what has changed since 10.05 (to download this or a full change log, links are provided at the bottom of this page):

## General:

- Better support for dark themes in Linux
- Support open file's containing folder using the context menu of the file
- Context menu item to show file in project tree
- Improved lexers for various languages
- Added the ability to show tooltips on cbAuiNotebook tabs - show full filename and project in tooltip for editor tabs
- Added the ability to maximize editors with double-click on tab
- Add ability to hide the editor tabs, can be toggled with "View -> Hide editor tabs" or "Ctrl+H"
- Select file from all projects in the workspace (Search->Goto file)
- Some accessibility improvements - more things are accessible only with a keyboard
- Lots of improvements to the Marcos support in the options - more options support macro expansion and there are more variables
- Added per language override for the 'use tabs' setting. Currently only for Python files (always use spaces) and for Makefiles (always use tabs)
- Use gtk-notebook as default notebook on systems using wxGTK, so the notebook-tabs integrate more smooth into the systems theme
- Active project no longer stored in workspace but in dedicated layout file for the workspace,
- Speed up scrolling in wxScintilla
- Harmonised find and replace dialogues
- Added power user support for units glob feature. These are directory paths that can be specified, and all files in there will be considered as sources for the project. This can be based on a wild-card for the file types, and can be recursive. When no wild-card is specified (empty) the default CB wild-card for adding files is used
- Made the localization to be off by default, hopefully this will minimize the number of people getting the right-to-left text issue
- Add predefined settings for the terminals on Linux

## Compiler:

- Support GCC up to version 4.7
- Improved Fortran/D support
- Improved resource compilation with MinGW resource compiler
- Automatically re-link a project when a dependant static library has been changes
- Switched full command line logging to be the default option for all compilers
- Fixed Cygwin Compiler auto-detection

## Code Completion:

- **Calltip improvements**: cleaned it up (strip duplicates), refined the calltip window position, "Pretty Print" each function names
- Fixed showing the Call tip for consturctors and destructors
- Optimised the Symbols browser by avoid unnecessary updates
- Fixed some bug when saving/loading the Code completion options
- Made 'Find implementation' and 'Find declaration' to be more precise (goto to line and column)
- Fixed some bugs with the refresh of the Code completion toolbar
- Fixed many bugs in the parser (crashes, deadlocks and parsing errors)
- Added support to the parser for handling conditional preprocessor directives (only for file scope, included files aren't expanded)
- Improved the Macro replacement and added macro replacement for GCC/MSVC build-ins
- Made the parser more robust and improved the thread safety
- **Introduce two major options for the operation of the Code completion plugin**: one parser for all workspace or a parser per project
- Improved the parsing of Class inheritance, now it is better and faster
- Improved parsing of C++ template constructs, typedef statements, operator overloading
- Added macro expansion for some code patterns (e.g. wxWidgets's event handling table/entry macros)
- Added None/Null parser for parsing files not included in any C::B project.
- Adding code with auto-completion follows the active indentation and EOL style
- Support auto-completion for include header file names and preprocessor directives
- Automatically append the text if the prefix word already exists before the caret(after the user hit Enter on the suggestion list)
- Support auto-completion for member variable initialisation
- **Added some tools for simple refactoring tasks**: find references, rename a symbol (not 100% precise)

* Not implemented (TODO) - parsing of multiple template arguments

## Debugger:

- Reworked the plugin API and made it easier to implement different debugger plugins (currently there are at least 3 plugins in progress)
- Reimplemented the watches window to be easier to use* using wxPropertyGrid control. Now adding, removing, editing watches should be easier
- Reimplemented the UI used for the 'Evaluate expression under cursor' feature, it is similar to the new watches window
- Fixed some problems in the callstack window - switching to the selected frame should work 99% of the time
- There were many improvement to the disassembly window
- The debugger options have been extracted in Settings->Debugger. Multiple configurations are supported for every different plugin
- Made it possible to run the host application for a DLL project in a terminal
- The GDB plugin is way more robust and reliable now, GDB 7.5 is supported
- The CDB plugin is vastly improved
- Remote debugging works better
- Made it possible to use marco replacement variables in many places

* The local variables and function arguments features have not been reimplemented, because of complexities in the UI design, reliability issues and performance

## New plugins:

- **Abbreviatons (extracted from the core)**: provides auto-completion (note that this has nothing to do with code completion): http://wiki.codeblocks.org/index.php?title=Abbreviations_plugin
- **Cscope**: integrates the source code searching features of Cscope: http://wiki.codeblocks.org/index.php?title=Cscope_plugin
- **DoxyBlocks**: support for doxygen inline documentation: http://wiki.codeblocks.org/index.php?title=DoxyBlocks_plugin
- **EditorConfig**: http://forums.codeblocks.org/index.php/topic,16512.0.html
- **EditorTweaks**: make one off changes to active editor (EOL mode, wrap etc) and code alignment tool: http://wiki.codeblocks.org/index.php?title=Editor_Tweaks_plugin
- **FileManager**: tree view of the file system with support for basic file management operations in the management pane: http://wiki.codeblocks.org/index.php?title=File_Manager_plugin
- **NassiShneiderman**: creation of Nassi Shneiderman diagrams: http://wiki.codeblocks.org/index.php?title=NassiShneiderman_plugin
- **ReopenEditor**: reopens last closed editor(s) via hotkey (Ctrl+Shift+t) or menu-item
- **SmartIndent (extracted from the core)**: multi-language support for automatic indenting of code to match typical indentation styles
- **SpellChecker**: check spelling in comments and strings using hunspell: http://wiki.codeblocks.org/index.php?title=SpellChecker_plugin
- **ToolsPlus**: creation and management of custom tools: http://wiki.codeblocks.org/index.php?title=Tools%2B_plugin

## Improved plugins:

- **Abbreviations**: added support for autocompletion and automatic conversion of tab/space and eol style of the editor
- **AStyle**: add brackets option, delete empty lines option, other new features from moving to astyle 2.02
- **AutoSave**: new option to autosave entire workspace, bug fix for timer UI
- **AutoVersion**: improved svn support (legacy versions, git-svn), bug fixes
- **BrowseTracker**: jump tracker now ignores line 1 activations
- **CppCheck**: configuration UI, bug fixes
- **CodeSnippets**: bug fix (crasher)
- **CodeStatistics**: stats for project or entire workspace
- **DragScroll**: bug fix (gtk crasher)
- **Header Fix-up**: STL and C library bindings
- **Help**: support for windows help collections, fixes crash on exit
- **HexEditor**: crash fix
- **KeyBinder**: remove Ctrl-C/V/X (copy/paste/cut) from menu keybinder table to allow native behavior, other fixto play more nicely with OS
- **Profiler**: autoselect active target,fix for rare crash
- **Project Importer**: new support for MSVC 7, 10
- **ThreadSearch**: UI improvements
- **ToDo**: more language independent, fixes annoying UI bugs
- **Valgrind**: added configuration panel, works better with CB projects, more output handling and support for valgrind features
- **wxSmith**: support for many new widgets (including KWIC, ImagePanel, GridBagSizer), internationalization support, duplicate IDs are allowed, tons of bug fixes

# Summary, for download

Download the short (this) changelog here: http://sourceforge.net/projects/codeblocks/files/Binaries/12.11/changelog

Download the full changelog here: http://sourceforge.net/projects/codeblocks/files/Binaries/12.11/changelog_fullgg
