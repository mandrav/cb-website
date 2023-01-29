---
title: "Version 17.12"
date: 2017-12-30T16:42:01+02:00
draft: false
aliases:
  - /downloads/48
---
For the release 17.12, we provide a changelog hereby about what has changed since 16.01 (to download the change log, a link is provided at the bottom of this page):

## SDK

 * **autotools**: Try to fix building with newer boost
 * Prevent sending EVT_MOUSE_CAPTURE_LOST while opening a context menu in wxScintilla
 * Allow the user to discard old config file if it fails to load
 * Return false if there are errors reading a xml file with tinyxml
 * Fix crash when reading truncated config file
 * Make sure we show an error message box when we cannot save the config file
 * Move the wizard files to the correct folder when making bundle
 * Fix blurryness when making a bundle
 * **autotools**: Add OSX bundle making support (ticket #562, thanks Dave Murphy)
 * **autotools**: Fix compilation using autotools on OSX
 * Fix ProjFile::Rename to correctly add the new file to m_ProjectFilesMap (thanks homertp, ticket #521)
 * **script bindings**: Don't crash when trying to add wxString and something that is not a wxString
 * Speed up project loading for large projects (projects with many files or many targets)
 * **FileManager**: Write directly to symlinked files (wx30 only, ticket #276)
 * **autotools**: Modernize our build system (ticket 349, thanks David Seifert)
 * **osx**: Build all plugins as dynamic libraries (ticket #275, thanks Franko F)
 * **osx**: Fix plugins location (ticket #275)
 * Remove homemade static_assert and use the real thing
 * Add additional tests to MacrosManager to determine if a newer project has been activated.
 * **Linux (autofoo)**: Try to use system provided squirrel, astyle, tinyxml (based on Fedoras unbundle-patch)
 * Fix issue #358 - Remove additional flags from pkg-config files (thanks Vincent C and Alexander GQ Gerasiov)
 * **c++11**: Use unique_ptr instead of auto_ptr (ticket 349 applied partially, thanks David Seifert)
 * **c++11**: Remove our nullptr implementation and some other tr1 classes
 * **osx**: Fix launching in terminal when the executable path contains characters that need to be escaped (thanks Easior Lars)
 * **batch**: Fix crash when batch building, because the autofitting accesses null pointer
 * **c++11**: Code::Blocks now requires a C++11 capable compiler
 * Use more proper types in some places (thanks frithjofh)
 * **script binding**: Log messages with any buffer size (hack, patch by unknown person)
 * Do not add a cmd.exe in front of NUL when replacing macros
 * Remove all breakpoint related functions from EditorBase
 * Remove all bookmark functions from EditorBase - they are not needed there, just in cbEditor
 * applied patch to remove and sync macro prefixes (thanks White-Tiger)
 * Fix a bug in configmanager.cpp which can lead to undefined behaviour. Wrong combination of std::map::erase and iterators (thanks to frithjofh).

## Core / UI

 * Remove ads extension when saving newly created files on wxGTK (ticket #571)
 * Fix status bar flickering when scrolling the editors
 * Make sure that menu items in the Project menu are correctly disabled
 * Notify the user that there is running compilation during quit and ask if he/she wants to stop it
 * Make sure that menu items in the context menu in Projects tab are correctly enabled/disabled
 * Clean up the UpdateUI behaviour of the File menu items
 * Remove 'Save All', 'Save all projects' and 'Close all project' menu items from the File menu
 * Add update ui processing for the File -> Properties menu item
 * Add 'Enable both' and 'Disable both' menu items in the Options submenu for the files in the project tree
 * Replace the cbMessageBox with AnnoyingDialog shown when there is config write error. This makes it possible to retry the saving of the config file
 * Do not loose changes when clicking twice the same target in ProjectOption dialog (ticket #547, thanks homertp)
 * **lexer**: Add PowerShell script support
 * Fix redraw problem on ubuntu because freeze/thaw are used in a wrong way
 * Move the open containing folder setting to the environment dialog (ticket #419)
 * Fix open containing folder on linux (ticket #419)
 * **editor**: Fix middle click copy/pasting when using wx2.8
 * **editor**: Revert some commits related to copy and pasting on wxGTK (9420, 6883, 5185) (ticket #524)
 * Update the info window after a plugin is uninstalled
 * **editor**: Insert new line below and above current line without indentation (ticket #180, thanks scarphin)
 * Do not loose settings when re-ordering targets in the project options dialog (ticket #534, thanks  homertp)
 * When removing files from a project, sort the files in the selection dialog. (thanks Miguel Gimenez)
 * Always hide the "auto generated" text for files that do not belong to a project
 * Make it possible to edit all targets in the Select Target dialog (thanks homertp, ticket #522)
 * **editor**: Select word at cursor if there is nothing selected and the 'Select next occurrence' command is executed
 * **editor**: Make the UpdateUI behaviour for 'Select next occurrence' and 'Select skip to next occurrence' to be a bit more logical
 * **editor**: Fix bug in the Select Skip Next command when using it on the first selection
 * Add the current position of the cursor in the status bar (thanks frithjofh)
 * Preserve open editors per target/project (ticket #182 thanks scarphin)
 * **lexer**: Added few new keywords to Fortran lexer (thanks darmar, ticket #500)
 * Fix crashes at startup due to undefined behaviour in wxPropGrid (ticket #489)
 * Remove explicit sizing and leave that to the sizers for controls in CodeStat settings, DoxyBlocks settings and Editor settings (thanks blauzahn)
 * **printing**: Fix printing splitted windows and improve the restoration of gutter and line numbers (thanks LETARTARE)
 * Limit the number of targets visible in the menu to lower number to try to fit them on screen (ticket #478)
 * Implement Select target menu item that shows an incremental select dialog (#ticket 478)
 * Fix read-after-the-end-of-array bug when a project has more than MAX_TARGETS number of targets in it (ticket #478)
 * Use separate up/down buttons for the search dirs tab instead of a spin buttin (ticket #477)
 * Use separate up/down buttons for the linker libs list instead of a spinbutton (ticket #477)
 * Make the GotoFile to try calculate a column width based on its content, so everything fits in the column
 * **GotoFunction**: Make the dialog re-sizable
 * Set the focus to the cancel button in the about dialog to enable closing with escape to work on wx28 on linux
 * Add configuration option to make focusing the first build error an option (ticket #473, thanks yvesdm3000)
 * Make env settings dialog resizeable on Windows (thanks mgimenez)
 * **GotoFile**: New goto file dialog which uses virtual list which makes it possible to have 50-100k elements in it without visible slowdowns
 * Replace case insensitive with case sensitive checking when the user changes a virtual target name (ticket #468 thanks bluehazzard)
 * Speed up goto file opening for large projects (ticket #325)
 * Make editor and environment settings resize correctly (fixes ticket #467)
 * Better align widgets vertically in the EditPath dialog
 * Use wxStdButtonSizer to make buttons more consistent (ticket #421)
 * Sort the elements in the tree, so they are consistent (ticket #421)
 * Fix an out-of-bounds read in the new GetUserVariableDialog (ticket #421)
 * Specify min size for the text ctrl in the EditPath dialog, so it is a bit more user friendly (ticket #421)
 * Use bitmap buttons for buttons in the EditPath dialog (ticket #421)
 * Replace flexgridsize with simpler boxsize in edit path dialog and fix the control expansion (ticket #421)
 * Set HiDPI aware to false for C::B on Windows with HiDPI monitors (HiDPI support in wx starts from wx31+), should resolve some layout issues
 * Allow macros in project notes. Press J to do the replacement (patch by unknown person)
 * Properly restore the line number settings in the editor after printing
 * Add dialog for global variables to "Edit Path" dialog (ticket #421, thanks bluehazzard)
 * Fix incorrect usage of size_t (ticket #66)
 * Add multiple select in the "Copy to..." dialog in Search Directories (ticket #410)
 * Disable the Copy to buttons in the Build options dialog if nothing in the list is selected, because these operations do nothing in this case
 * Add multiple select in the "Copy selected to" dialogue (ticket #410, thanks bluehazzard)
 * Fix default buttons in most dialog broken after the change to use wxStdDialogButtonSizer (ticket #368)
 * Fix SF Ticket #386 Parallel builds arbitrarily limited to 100.
 * Apply modified SF ticket #66 Patch for "Goto Function" enhancement. Thanks Bat.
 * **editor**: Enable folding for newly created files (partly fixes ticket #366)
 * **editor**: Enable switching between header and implementation for templates (.tpp;.tcc . <-> .h;.hpp).
 * Use a listbox instead of choice for the list of variables in the global variables dialog (ticket #346, thanks bluehazzard)
 * Updated the cc tooltip colours after the settings have changed
 * Fix sorting of virtual folders when there is an empty one (thanks earlgrey)
 * Clarify the menu item names for splitting the editor
 * show project/workspace file name and target title in title of batch window
 * **lexer**: Added autotools, cu and inno setup lexers (patch by unknown person)
 * **editor**: Apply patch #71 - Wrap around when reaching the last bookmark in an editor (thanks beja)
 * Correct template title not to use illegal characters (patch by unknown person)
 * Allow to rename virtual folders via menu (patch by unknown person)
 * Select highlighting scheme from status bar for convenience (patch by unknown person)
 * Apply patch #80 - prevent asking for closing the workspace in batch builds (thanks Bat)
 * Applied patch by frithjofh w/ some refactoring for the search/replace dialog (see https://forums.codeblocks.org/index.php/topic,20849.msg142364.html#msg142364)
 * Remove (new) from the name of the watches window
 * fixed wrong message in batch builds on errors
 * Use the app window in cbGetSingleChoiceIndex and cbGetTextFromUser as parent when nullptr is passed
 * Replace calls to wxGetTextFromUser with a custom function that allows sizing and proper placement (also add missing PlaceWindow calls when the wxTextEntryDialog is used)
 * Replace calls to wxGetSingleChoiceIndex with a custom function that allows sizing and proper placement
 * Limit the vertical resizing of the EditPath dialog
 * Use a std dialog button sizer in the GDB's breakpoints dialog
 * Remove strangely looking SetSize call, remove the static line widget from Compiler flags dialog
 * Rename the OK button to Close in the configure tools dialog
 * Remove a panel and a flexgridsizer from the compiler flags dialog
 * Make the edit path sizable
 * Replace box sizers with std dialog button sizers where possible, also expand the sizers
 * Expand the std button sizers in order to make the dialogs look better on wxGTK
 * Show file in the project tree command should show the Management tab if it is closed
 * disable saving / loading editor layout by default (due to a bug)
 * make loading/restoring project/editor layout an option
 * Replace '&amp;' with '__' in the xrc file for the edit tools dialog (fixes ticket #321)
 * Change description of $$(macros) to $(macros) in the configure add dialog

## Code-Completion

 * Fix crash when showing the call tip
 * Fix doxygen spelling in the settings panel
 * Make the size of toolbar controls configurable in the settings (ticket #303)
 * Fix an issue that Code Completion list got hidden after shown up
 * Fix assert on generate ctor implementation
 * Fix possible inconsistency caused by bad usage of cbAssert - the expression must not have side effects, because in some builds they might not be executed
 * Fix default colours for code call tips (thanks darmar)
 * Send proper events for 'Autoselect single match'
 * Automatically test for doxygen document. (thanks White-Tiger)
 * Fix a bug that we have forget adding the doxygen documents for macro
 * Fix a endless loop crash bug when parsing C99 designated initializer
 * Fix ticket #278 and ticket #393 (thanks White-Tiger)
 * Fix ticket #351
 * Try to fix issue #14 for real this time (high memory consumption due to recursive symbolic links)
 * show an error to the user if expression could not be resolved
 * Fix a parsing std namespace bug.

## Compiler

 * Make it possible to utilize more than 16 CPU threads while building (ticket #327)
 * Make Code::Blocks work better with current SDCC (ticket #567, #371, thanks Philipp Klaus Krause)
 * Clean up the clang flags a bit and add the common sort options
 * Add -std=c++14 and -std=gnu++14 to the list of C++ only flags (format the file to be a bit more readable)
 * Try to improve the invalid compiler message we're printing
 * Add button to compiler toolbar to show the select target dialog
 * Improve clang log parsing (parse the file and line for notes)
 * Use the correct flag to the linker when building windows gui applications with clang (ticket #51, thanks edison)
 * Fix the AVR GCC compiler on linux to not add invalid include and linker paths
 * Remove deprecated cygwin only flag (ticket #526, thanks Jannick)
 * Corrected "defines" switch for Gfortran (thanks darmar, ticket #499)
 * Improvement of parsing of Gfortran compiler output (thanks darmar, ticket #497)
 * Updated output parser for VS2015 (thanks sodev, ticket #496)
 * Add -std=c11 to default compiler options
 * Batch mode doesn't work on MacOS (ticket #425, thanks Franko F for the original patch)
 * Save the other resource settings in the Compiler options dialog
 * **Add support for the following options **: -std==c++1y and -std=c++1z
 * Fix description of "-ansi" compiler-flag in "options_common_warnings.xml".
 * Expand backtick expression when doing clean for makefile projects (fixes #326)
 * Switch to build log when compiling single file (ticket #222, thanks Sergey Bezgodov)
 * Remove the limit on the number of processors and change the default to use all available in the machine (fixes #327)
 * Don't compile the regexes for the compiler until they are really needed (speeps up startup)
 * **Support for new compilers**: android-GCC MW, powerpc-EABI (patch by unknown person)
 * Added more common options to clang, gcc, msvc
 * parsing Gfortran v5.* compiler messages in new v5.* format; option -fopenmp should be applied at compiler and linker command line (thanks darmar)
 * Applied patch to make Cygwin compiler work with recent Cygwin installations (thanks stahta01)

## Debugger

 * Mark the GDB attach to process command to be a continue command
 * Remove squirrel based pretty printers - users are supposed to use the gdb-python-pretty-printers
 * Disable the Examine memory menu item for child or special (function args and local variables) watches (ticket #408)
 * Make it possible to examine the memory of non-pointer variables like structs (ticket #408)
 * Make it possible to examine the memory of a watched variable using the contect menu in the watches window (ticket #408, thanks bluehazzard)
 * Truncate the value when displaying the watches tooltip (ticket #85, thanks Bat)
 * Fix crash in the disassembly windows (ticket #506 and #503, thanks bluehazzard)
 * Fix parsing of shortened strings
 * Make the source code in mixed mode to be treated as comments by the asm lexer
 * Save the Mixed mode setting from the Disassembly dialog (thanks bluehazzard, ticket #503)
 * Examine memory dialog remembers the size to dump (ticket #503)
 * Fix parsing of backtrace produced by newer CDB's (ticket #430 thanks debugfanchin)
 * Make if possible to debug 32bit program with CDB 64bit (ticket #429, thanks debugfanchin)
 * Don't call EditorLinesAddedOrRemoved twice for split editors
 * Don't print a warning when the current compiler is set to "No compiler" and the active debugger is set to "Target's default"
 * Set print elements limit to the default for gdb, using unlimited has proven to be dangerous
 * Fix gdb watch parsing error when there is a repeating sequence just before a closing brace '}'
 * Fix issue #254 - make it possible to use the stop button for the CDB debugger (thanks maras420)

## Scripted Wizard

 * Apply YWX additions (GetWizardScriptFolder, FillContainerWithSelectCompilers,AppendContainerWithSelectCompilers,FillContainerWithChoices,AppendContainerWithChoices)
 * Improve Code::Blocks plugin wizard (ticket #481, thanks bluehazzard)
 * Add support for 3.1 in the WxWidgets wizard (thanks New Pagodi)
 * Fix images to be 32x32 and be transparent (fixes ticket #314)
 * Added FLUID and SDL2 templates (patch by unknown person)
 * Add new templates to automake build-system
 * Added Java wizards for fun
 * Added qt5 and improved qt4 wizard (patch by unknown person)
 * Added arduino and msp430 wizards (patch by unknown person)
 * Added SDL2 wizard (patch by unknown person)
 * Added wizard for D language (patch by unknown person)
 * **Applied (modified) patch by stahta01 to relax wizards when searching for library files to link against, see**: https://forums.codeblocks.org/index.php/topic,20730.msg142215.html#msg142215

## Spell Checker

 * Add (Fedora-)path for dictionaries.
 * Support Unicode path names (thanks White-Tiger)
 * Better support short forms like "doesn't" (thanks White-Tiger)
 * Pumped hunspell lib to more recent version to allow adding additional / multiple dictionaries
 * Some status messages to the user to track down if something goes wrong

## ProjectOptionsManipulator

 * **Added modified/bug-fixed patch by bluehazzard**: Add possibility to change compiler
 * Bug-fix for erroneous message when user cancels dialog
 * Bug-fix for some UI logic (enabling/disabling applicable controls)
 * Query the user to save all projects at end for convenience
 * Show summary of operation done at end
 * Mark project files modified if they are changed

## Astyle

 * Fix config option label - swapped of and #
 * **pump**: update of ASTYLE plugin to fix bug #493 AStyle crashes in svn build rev 11033
 * make Mozilla style preview work correctly
 * Fix bug in settings dialog "Break logical conditions..." (ticket #450, thanks bluehazzard)
 * Fix a typo in the setting dialog.
 * Fix spelling - parentheses is the correct word
 * Fix issue #352 (thanks sodev)

## CppCheck

 * Support for XML log file format v1 and v2 (v1 will be obsolete soon)
 * Allow macros in command line parameters provided through settings
 * Added support for Vera++ (https://bitbucket.org/verateam/vera)
 * Add PATH to cppcheck executable if required before the call

## wxSmith

 * Add wxSpinCtrl alignment styles
 * Fix drawing artefacts when built with wx3.0
 * Don't write \0 characters in generated/altered files when C::B is built with wx3.x
 * **Fix crash, when closing wxs-file and a sub-property is selected; see**: https://forums.codeblocks.org/index.php/topic,21893.0.html
 * Improve compatibility with wx3.x by adding some new events and removing events that aren't supported (thanks mgimenez)
 * Sort generated includes and forward declartion to prevent random changes to the source files when the hash function changes
 * Fix the resizing of the ArrayStringEditor dialog
 * Make it handle minsize corretly for wxSplitter (ticket #465, thanks Volker Meyer)
 * fix assert with wx3.0, due to doubled properties in some sizeritems.
 * introduced settings wrt to controlling translation and style of translation code (wxT(), _T()...) globally
 * move wxMathPlot and it's counterpart wxSmithPlot in wxContribItems and wxSmithContribItems.

## Other Plugins

 * **abbreviations**: Applied patch to fix abbreviations target is missing in some project files (thanks stahta01)
 * **abbreviations**: Fixed bug in with non-alpha-numeric character abbreviations (thanks BlueHazzard)
 * **cb_share_config**: Added simple "export all" functionality for easy backup of all config stubs to a backup folder
 * **cbp2make**: Added (further improved) cbp2make by mirai-computing due to project seems dead otherwise
 * **CodeStat**: Fix assert in the progress update (thanks blauzahn)
 * **cscope**: Fix hang of cscope when given a missing file (ticket #448 Robert Morin)
 * **help**: allow to search for keywords also on CPlusPlus.com
 * **DoxyBlocks**: Clean up the UI a bit
 * **DoxyBlocks**: Filter out comment strings in the parameter documentation (thanks Yves De Muyter)
 * **HexEditor**: Change the label of the OK button to Find
 * **HexEditor**: Limit vertical resizing of the search dialog
 * **HexEditor**: Fix text misalignment when selecting numbers in the editor
 * **IncrementalSearch**: wx3 compatibility-fix
 * **ProjectImporter**: Better handling for more recent VC workspaces / project files (patch by unknown person)
 * **SourceExporter/NassiShneiderman**: Make sure only one File -> Export menu is created no matter which plugin is created first
 * **SourceExporter**: Fix undefined behaviour
 * **ThreadSearch**: Add option to disable/enable the autosizing of log columns (fixes #324, thanks  Sergey Bezgodov)
 * **ThreadSearch**: Fix infinite filesystem traversal when there are cyclic symlinks present
 * **todo**: Display count of list item (ticket #452 Sergey Bezgodov)
 * **todolist plugin**: some code improvements by frithjofh
 * **Valgrind**: Quote the path to the xml file if needed - makes the plugin work when the project is located in a path with spaces

## Updated 3rd party libs

 * move astyle (plugin) out of beta into v3.0 release
 * updated exchndl (crash handler) to v0.8.2
 * updated exception handler to v0.8.1
 * updated wxPDFDoc library to recent GIT version to resolve licensing issues
 * updated exchndl (crash handler) DLL to v0.8.0
 * updated library to v0.9.5 for better wx30 compatibility

## Misc (targeting wx3)

 * Fix assert when loading files and the global enconding setting is set to default (ticket #305)
 * Fix assert when closing the application during long compilation
 * Memory dump window has wrong proportion on windows (ticket #557, thanks bluehazzard)
 * Fix assert when executing Build -> Errors -> Next error and there is no error in the list
 * Fix the highlight language button in the status bar
 * Fix assert when pressing the auto-detect button in the compiler settings
 * Always disable symbol browser in such builds to prevent crashes (ticket #225)
 * Fix compilation with latest wx master (thanks blauzahn)
 * Fix assert on startup in IncrementalSearch (ticket #405, thanks bluehazzard)
 * Fix assert due to the same labeled property added to the wxSmith's property grid for wxStdDialogButtonSizer
 * Fix some alignment asserts reported for some of the dialogs
 * Fix assert when calling wxSetWorkingDirectory with an empty path
 * Fix two asserts in the AVR wizard
 * Fix lots of asserts when batch building (there are some left though)
 * Fix assert when the current target uses "No compiler" (fixes ticket #315)
 * Fix asserts when wizard icons are no 32x32 pixels big (fixes ticket #314)
 * Fix an assert in ToDo plugin (thanks blauzahn)
 * Fix assert when deleting a compiler
 * Fix assert when the search mask in the Find/Replace dialog is empty (fix formatting of the code around)
 * Fix the ValueTooltip autosizing. It was disabled for wx29, but should work in all wx3.0, because my patch should be in them

# Summary, for download

Download the full changelog here: https://sourceforge.net/projects/codeblocks/files/Binaries/17.12/changelog

## Older Changelogs

See [Changelog for 16.01](/changelogs/16.01)

See [Changelog for 13.12](/changelogs/13.12)

See [Changelog for 12.11](/changelogs/12.11)

## Special thanks

Special thanks for their (continuous) support go to:

 * frithjofh
 * stahta01
 * White-Tiger
 * maras420
 * darmar
 * Bat
 * beja
 * BlueHazzard
 * gd_on
 * blauzahn
 * Easior Lars
 * earlgrey
 * Sergey Bezgodov
 * David Seifert
 * sodev
 * Vincent C
 * Alexander GQ Gerasiov
 * debugfanchin
 * Franko F
 * Yves De Muyter
 * Robert Morin
 * Volker Meyer
 * LETARTARE
 * scarphin
 * homertp
 * Jannick
 * Miguel Gimenez
 * Bat
 * edison
 * YWX
 * Dave Murphy
 * Philipp Klaus Krause

