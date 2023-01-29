---
title: "Version 20.03"
date: 2020-03-19T04:41:43+02:00
draft: false
aliases:
  - /downloads/binaries/changelog
---
For the release 20.03, we provide a changelog hereby about what has changed since 17.12 (to download the change log, a link is provided at the bottom of this page):

## General UI/SDK changes:

 * **UI**: Add information about the wxWidgets library being used in Help -> About dialog
 * **UI**: Fix two asserts for incorrect use of wxALIGN_LEFT when opening the Project -> Properties dialog
 * **wx3**: Fix assertion when removing last virtual target (ticket #892)
 * **UI**: Add logging of execution time to various places in the code
 * **UI**: Add compiler ID to Help -> About dialog (ticket #870)
 * **UI**: Make Plugin manager to have resizeable plugin info control
 * **UI**: Fix Toolbars corruption when saving perspective (ticket #846)
 * Fix crash with batch build on linux by moving the build process out of OnInit() when using wx>=30
 * **UI**: Improve child window placement. Introduce 3 options: center-on-parent (default), center-on-display and leave to OS/ Window manager.
 * **UI**: Make sure pressing escape works correctly in the Reorder targets dialog
 * **UI**: Fix the parents of various child dialogs in the Build -> Properties
 * **UI**: Make sure we call PlaceWindow for the dialog for selecting platform for targets
 * **UI**: Make sure the correct parent is set when showing the project dependencies dialog
 * **UI**: Fix possible assert when the language selection is invalid
 * **UI**: Make data paths more resilient to changes to the current directory
 * **UI**: Make pressing Escape in scope "Code Refactoring" dialog to close it
 * **UI**: Adjust borders for the Find/Replace dialog
 * **UI**: Fix corruption of toolbars when saving perspective (ticket #846)
 * **UI**: Fix assert that a bitmap is already selected in a DC on Windows
 * **UI**: Fix crash if the list in Settings->Scripting is empty (ticket 842)
 * **UI**: Show only one message box if a project could not be loaded while loading a workspace (ticket #809)
 * **scintilla-wx**: Remove double buffering for wxGTK (it doesn't fix the flickering problem)
 * **UI**: Select the correct language in the menu shown from the language button in the status bar
 * **scintilla-wx**: Cherry-pick changes from wx-master (Better support for passing images from wx to scintilla)
 * **UI**: Some places in the code were trying to load images from file system and not from resources.zip (ticket #826)
 * **UI**: Replace the wxComboBox with wxChoice in Project->Properties->Build targets->Type
 * **UI**: Make the layout of Environment Settings -> View a bit more compact
 * **UI**: Replace the radio buttons for images sizes in Env Settings -> View with wxChoice controls
 * **UI**: Use better looking icon for the "Select text" button in the Incremental search toolbar
 * **UI**: Fix layout issue in the environment settings dialog
 * **UI**: Print config file path as the first line in the list ctrl for the main log
 * **UI**: Fit toolbars on every load
 * **UI**: Make MainFrame::DoFixToolbarsLayout to really work when toolbar size changes
 * **UI**: Make it possible to assign a keyboard shortcut to Build -> Select target -> Select target...
 * **sdk**: Fix memory leak when showing the "choose compiler" dialog, because the current compiler is not available
 * **UI**: Log the info message to the main log
 * **UI**: Avoid crash or assert when application is closed via OS's TaskBar
 * **UI**: Fix a warning emitted by wxWidgets about incorrect use of wxALIGN_CENTER_HORIZONTAL in the EditPath dialog
 * **UI**: Treat editor and project files as modified when altered outside of Code::Blocks and not reloaded (ticket #492)
 * **wx30**: Do no call LoadResource for plugins which don't have xrc files in their zip archives
 * **wx30**: Fix assert that all images added to an image list must have the same size
 * **batch build**: Fix segmentation fault after batch build (ticket #738)
 * **UI**: Fix crash in GotoFile::BuildContent(74)
 * **SDK**: Fix memory leak when loading new workspace
 * **UI**: Fix a memory leak of Page objects on application shutdown
 * **UI**: Fixes to the auto-sizing feature of the GotoFile dialog (see r11468)
 * **UI**: Make the Goto File window to resize itself when the content of the list ctrl doesn't fit
 * **UI**: Make opening containing folder work when the path contains whitespace (ticket #734)
 * **wx3-stl**: Make almost everything (wxSmith doens't) to build with wxWidgets in STL mode
 * **sdk**: Remove duplicated calls to AddBuildTarget for generated files
 * **sdk**: Make sure we don't add the same file twice if it is stored with different relative path in the project file
 * **sdk**: Make CompilerFactory::GetCompiler using an id faster
 * **sdk**: Small optimization in cbProject::addFile (don't call wxFileName::GetExt multiple times)
 * **sdk**: Small optimizations in MacrosManager
 * **sdk**: Don't save empty extension tags in the project file
 * **sdk**: Sort extensions just before saving the project
 * **sdk**: Add $PLATFORM macro that expands to "msw" on windows and "unix" on linux and mac
 * **sdk**: Path delimiters in the .cbp file aren't Unix-normalized when saving project on Windows (ticket #705)
 * **UI**: Print a message in the log when the application is ended because another instance is detected
 * **UI**: Fix a crash/assert on shutdown when the CallAfter is executed after the managers have been shutdown
 * **UI**: Print an error in the log if opening a file fails
 * **UI**: Make sure passing --file=path/to/file.ext without line number works, too
 * **ProjectManagerUI**: Implement both external and internal wxTreeCtrl Drag and Drop for the project manager tree
 * **ProjectManagerUI**: Temporary disable external drag and drop from project manager wxTreeCntrl. External and Internal drag and drop are incompatible.
 * **UI**: Remove double dollar signs (ticket #653)
 * **wx30**: Fix de-serializing wxStrings when doing DDE
 * **UI**: Prevent the splash screen from staying on top from the compiler selector dialog
 * Fix possible null pointer dereference in plugins management (ticket #673)
 * **UI**: Set the focus to the OK button in the Multi Select dialog (used when adding files to a project)
 * **UI**: Make sure that the file path control in the EditPath is larger, so longer paths could be reviewed
 * **UI**: DefaultMimeHandler: Set min size for the selection dialog
 * **UI**: Fix crash when reloading multiple projects in a workspace and they have dependencies
 * **wx3-gtk3**: Fix crash when doing Control-A, Control-V (ticket #629)
 * **UI**: Make sure the current project is always visible in the project tree while moving it up/down (ticket #617)
 * **UI**: Show the scintilla version in about dialog
 * **wx30**: Fix editor redraw problems on Windows (workaround, related to status bar)
 * **UI**: Make return to select the filtered option in the Goto File, Goto Function and Select Target dialogs on Windows

## HiDPI improvements:

 * Log the actual scaling factor (makes sense for gtk2/3)
 * Add new versions of the select-target images
 * Update 16x16 in src/resources to look like their bigger versions
 * Update images for ThreadSearch
 * Use the new updated tree icons
 * Add missing rc-file* images to the main resources
 * New 16x16 images for infopane and help plugin
 * Make the abbreviation plugin HiDPI aware
 * Create a missing icon in the toolbar if the requested icon couldn't be loaded
 * Make the SpellChecker icons in the status bar to be HiDPI aware
 * Use toolbar art providers for main, compiler and debugger toolbars
 * Move select_target.png to sdk/resources
 * Make it possible to use the cbArtProvider with toolbars
 * Make button images (zoom in/out) in the help plugin panel to be HiDPI aware
 * Apply scale factor to the toolbar size
 * Make icons in various dialogs to be HiDPI aware
 * Fix browse buttons in Project -> Properties to look good on HiDPI monitors
 * Make the icons for the buttons in IncrementSearch to be HiDPI aware
 * Make the icon in scope "Code Refactoring" dialog to be HiDPI aware
 * Add support for bitmap buttons to the cbArtProvider
 * Fix scaling of menu images created with the cbArtProvider on macOS
 * **help plugin**: Fix bigger icons in the Help menu on Windows
 * **IncrementalSearch**: Fix the menu icon to use the menu size and scaling (HiDPI aware)
 * **DoxyBlocks**: Make the Module menu images to be HiDPI aware
 * Make the readonly icon used in editor's notebook to be HiDPI aware
 * Try to make Notebook icons in 'Logs and Others' look non-blurry on GTK3+GDK_SCALE=2
 * Make all loggers in 'Log & Others' to provide HiDPI aware icons
 * Make the OpenFilesList plugin HiDPI aware
 * Better support for creating the image list on GTK3 when scaling factor is 2
 * Modify cbProjectTreeImages::MakeImageList to add a red image in the generate image list when a file fails to load
 * Make the tree images in project tree and file manager trees to be HiDPI aware
 * Use the scaling factor detection to select the image size for menu images
 * Fix debug log message about ClientToScreen failures coming from the call to wxDisplay::GetFromWindow
 * Update icons from the cb-icons repo (compiler and incremental search pluigns)
 * Move images to codecompletion.zip instead storing them on the file system and fix all build systems
 * Implement sizeable images in the auto completion list produced by the CC plugin
 * Remove wrong warning message in the log from the cbArtProvider
 * Fix the icon size in Breakpoints dialog on HiDPI windows builds
 * Make the list images in Breakpoints dialog to look good on scaled GTK+3 build (scaling factor 2 or more)
 * Make images in the Build menu (compiler plugin) to be DPI aware
 * Make the IncrementalSearch menu image to be DPI aware
 * Make the DoxyBlocks menu images to be DPI aware
 * Make the images in the debugger menu to be DPI aware
 * Make all images defined in main_menu.xrc to be DPI aware
 * Add additional image sizes which would be used for the main menu
 * Make the icons in the Breakpoints dialog to be DPI aware
 * Remove toolbar images with size 22x22
 * Print the resource id of the toolbar when there are problems loading a bitmap
 * Add 20x20, 24x24, 28x28, 40x40, 48x48, 56x56 and 64x64 for contrib plugins
 * Add 20x20, 24x24, 28x28, 40x40, 48x48, 56x56 and 64x64 for core stuff
 * Add more options for the sizes of the toolbar icons
 * Print log message when loading an image for a toolbar fails
 * Fix asserts in the wxBitmap c-tor when the image file cannot be found on this
 * Print a warning when changing the size of toolbar images
 * Make the wx31 builds to be system dpiAware
 * Fix missing image after the move of 22x22 images to a separate folder
 * Do not use scalingFactor on Windows
 * Add wrapper for wxWindow::GetContentScaleFactor to make it easier to use this call
 * Make toolbar images for DoxyBlocks work correctly when using GTK+3 on HiDPI (scale >= 2) monitor
 * Make toolbars on wx3.1 and GTK3 to almost look sharp
 * Print scaling factor for the main frame during startup
 * Do not call Realize toolbars for every disabled tool in a xrc file
 * Reenable the dpi aware flag on windows
 * Add 32x32 images for the rest of plugins which create toolbars
 * Make toolbars work on retina mac machines
 * Add the possibility to select toolbars which are 32x32 big
 * Add 32x32 images for main and debugger toolbars
 * Print warning message when a toolbar image requires resizing
 * Make the xrc wxToolbarAddon handler to be able to remap bitmap paths

## SDK new/changed APIs:

 * **sdk**: Implement cbProject::operator= so it is possible to copy projects
 * **sdk**: Change the return type of cbWatch::GetDebugString (ABI break)
 * **sdk**: Remove cbWatchesDlg::UpdateWatches, because it is no longer used
 * **sdk**: Add cbEVT_DEBUGGER_CONTINUED event for debugger
 * **UI**: Try to place child windows always on a valid display (ticket #770)
 * **sdk**: Make cbAssert to send SIGINT instead of SIGTERM
 * **SDK**: Make cbResolveSymLinkedDirPath a bit more robust
 * **sdk**: Add function which could be used to get the rect of the monitor where a window is placed (extracted from PlaceWindow)
 * **sdk**: Add API for sorting menu items in the editor's context menu (modify all plugins to use it)
 * **UI**: Use sorted container to provide a more stable iteration when building the module menu
 * **UI**: Use the setting for caret line to show it in the syntax highlight settings

## Performance improvements:

 * **UI**: Minimize the time needed to open the file/replace dialog for the LLVM project
 * **SDK**: Call the virtual function GetTitle just once inside loops in cbProject::RemoveBuildTarget

## Syntax Hightlight UI improvements:

 * **UI**: Make it possible to type in the syntax highlight preview
 * **wx30**: Fix assert introduced with rev 9667 (reading null color for syntax highlight)

## Editor:

 * Try to fix flicker when moving the cursor with keyboard/mouse (ticket #890)
 * Disable middle-mouse button paste until user sets Settings -> Editor -> Other editor setting -> Enable marked text paste with middle mouse click (on Windows)
 * Fix non-latin keys to work in shortcuts in the editor on Linux
 * Add controls for selecting the technology and font quality
 * Auto-size marker margin column and switch to breakpoint image with the correct size
 * Make the width of the change bar to change with the zoom
 * Add an option which can be used to disable the save-to-temp-and-move operation we use by default
 * Add menu item 'Copy full path' in the editor tab context menu
 * Implement 'Fold current block' to work when the cursor is inside the block (ticket #700)
 * Fix the feature which restores editor folds when the project/editor is reloaded
 * Make it possible to set the white-space mode to "Only indent"
 * Enable pasting when there are multiple cursors and typing with them is enabled
 * Group all find related items together at the top of the context menu in the editor
 * Move the Code Refactoring -> Rename symbols menu item to the Insert submenu
 * Move Properties to the bottom of the editor's context menu
 * Remove excessive separators from the editor's context menu
 * Remove menu items from editor's context menu which are duplicated in the editor's tab
 * Move Copy/Cut/Paste from a submenu Edit to the main context menu of the editor
 * Add 'Close to the left' and 'Close to the right' menu items in the context menu for the editor's notebook
 * Implement caret buffer in the editor (up to now we have it implemented in the EditorTweaks plugin). UI in the Settings -> Editor -> General -> Other editor settings
 * Do not mess the editor with brace selection completion when there are multiple cursors
 * Pass a theme object to editors created for new files (ticket #100)
 * Make the line for the current position during debugging to use the same colour as the caret line (ticket #659)

## Lexers:

 * Add syntax highlighting for Nim (ticket #657)
 * Add WAVE keyword to Windows resource lexer (ticket #834)
 * Improve C/C++ lexer (ticket #741)
 * Add YAML lexer, make sure to always use spaces when editing YAML files
 * Add option to change the colour of the indentation guides for all lexers not only for the ObjC lexer
 * Add selection, active line, matching brace and no matching brace style options using code
 * Add lexer for plaintext files
 * Add lexer for Markdown (ticket #640)
 * Update doxygen keywords in the C/C++ lexer
 * Update keywords for the new Fortran standard (ticket #683)
 * Update GLSL lexer to v4.60 Standard (ticket #588)

## Script bindings:

 * Bind SetLinkerExecutable and GetLinkerExecutable in CompileOptionsBase
 * Make it possible to examine and modify the Extension XML nodes in the project files
 * Save the old print function and restore it after executing the script in ScriptingManager::LoadBufferRedirectOutput (ticket #817)
 * Make it possible to use relative paths when including squirrel scripts (ticket #812)

## Library updates:

 * Scintilla to 3.7.5; Sync wx files with the same files in wxWidgets' master
 * Exchndl crash handler to v0.9.1
 * Hunspell on Windows from v1.3.3 to v1.7.0
 * Astyle to v3.1
 * wxPDFDoc to v0.9.8 (used in SourceExporter plugin)

## Astyle:

 * Finally make Mozilla-style/example work
 * Add new options, remove obsolete options

## Code completion plugin:

 * Take the zoom of the current editor into account when deciding if to use a buffered auto completion list
 * Fixed annoying bug that the compiler calls fail due to missing dependencies (DLLs)
 * Fix parsing of function declaration which returns enum type (partial fix for ticket #127)
 * Fix parsing of enums whose underlying types are specified (in C++11) (ticket #176)
 * Fix parsing of when the result of function is cast to void (ticket #25)
 * Fix parsing of struct instances declared on same statement (ticket #762)
 * Fix parsing of multi-line #if defined() (ticket #761)
 * Fix parsing of 'for' loops with empty declaration block. Handle the case where the first token is a semicolon
 * Fix parsing of #defined \ macros (ticket #693)
 * Fix crash caused by accessing array with out of bound index.
 * Do not start system header thread if the list of directories is empty (ticket #780)
 * Improve the logic for starting/stopping system header threads
 * Fix crash when the project has files with invalid targets and the user tries to do header completion
 * Ignore attribute((whatever)) in typedef definition (ticket #759)
 * Support function declaration lists (ticket #724)
 * Handle comma as terminator for function declarations
 * Fix leaks of SystemHeadersThread objects when shutting down the application
 * Log how much time traversing a directory to find headers takes
 * Do not traverse root folders for drives
 * Use better method for detecting file system loops
 * Do not block the UI when showing the list of include completions while a thread is traversing
 * Fix assertion when clicking on "Find references of:" (ticket #633)

## Compiler plugin:

 * Add an option to targets which allows the user to select the linker executable to be used for the target
 * Make the LinkerExecutableOption::AutoDetect work as advertised
 * Cleaned up obsolete interim C/C++ standards that are now properly supported by GCC (i.e. C++11/14/17; C17)
 * Print Build banner at command preBuild step, else they appear to belong to previous target
 * Fix assert about RecalcSizes (ticket #857)
 * Expand CodeBlocks variables for non-ttCommandsOnly targets also
 * Fix potential crash if the choice control is removed from the toolbar
 * Print a log message that we are modifying the dll search path before running an executable
 * Adjust the regexp for detecting the compiler version to support double digit numbers
 * Do not switch to the build log when the workspace is closed
 * Fix a crash introduced in r11465 (ticket #582)
 * Clear target specific variables from the MacroManager on every recalculation (ticket #582)
 * Remove duplicated compiler option
 * Clear logs when the workspace is closed (ticket #656)
 * Make sure the goto prev/next build error goes only on errors
 * Show the build message when the user requests goto prev/next error
 * Add support for -std=c++17 flag
 * Don't show a log message when the wxKill command fails to kill children, because they've finished already
 * Hide process output when the process is stopped/killed
 * Fix double send of cbEVT_COMPILER_FINISHED when the executable is closed after run
 * Make the abort button work again (ticket #104). Kill the started process and all children instead of using wxSIGTERM

## Debugger plugin:

 * Make sure we always store remote debugging project options sorted by target
 * Rework the plugin to not use ProjectLoaderHooks
 * Fix crash when trying to attach when there is no loaded project (ticket #879)
 * Fix regression when executing additional commands before
 * Make sure we don't save empty serial baud attributes in the debugger extension
 * Improve UI of Debugger project options panel
 * Check additional shell commands when deciding if the remote settings for target/projects need to be saved
 * Rework the UI for the "Remote connection" tab in the project opions to look a bit more pleasant
 * Improve the IsPointerType to detect restrict and const volatile types as pointers correctly
 * **sdk**: Add another parameter to cbDebuggerPlugin::AddWatch to make it similar to AddMemoryRangeWatch
 * **sdk**: Make it possible to delay the update of memory range watches (possible massive breakage)
 * **sdk**: Add event which will be used to notify debug windows that data is ready
 * Initial implementation of Memory Range Watches
 * Set the plugin value of the event when sending EVT_DEBUGGER_UPDATED
 * Send CURSOR_CHANGED event when the debugger has stopped on a breakpoint/signal
 * Fix the disassembly view with newer GDBs
 * Make it possible to evaluate expression in wxSmith code blocks
 * Improvements for Fortran (ticket #717)
 * Put the recent entered command in the position 0 of the wxComboBox list.
 * Remove gdb_types.script because it is not longer used (the scripting support has been removed from the debugger)
 * Make sure to quit correctly when attaching to process fails
 * Make it possible to attach to a process using the command line (This commit adds --dbg-attach and --dbg-config command line options)
 * Prevent warning for invalid current directory when attaching to process
 * Make sure to set the SHELL variable before starting GDB

## OccurrenceHighlighting plugin:

 * Update the permanent occurrence highlights when editor is split
 * Handle editor open events to highlight all words that match the set for permanent highlights
 * Make it possible to set the plugin to override the text colour

## Scripting wizard:

 * Fix wxWidgets script on windows (ticket #676)
 * Print better message when the xrc file fails to load
 * Change extension for files added to Fortran projects to f90 (ticket #605)

## Browse tracker plugin:

 * Create default.Browsetracker.ini from old Browsetracker.ini (only once) when personality == default
 * Fix deprecated wxFont usage in config panel
 * Honor Toolbar activation/deactivation from View/Toolbars; Change config toolbar setting to "Show Toolbar Always"
 * Fix crash in JumpTracker when the editor object is nullptr
 * Internationalize the configuration panel
 * Fix shutdown assert on linux when using wx3.x
 * Unregister hooks/sinks to prevent crashes when uninstalled

## Code snippets plugin:

 * Let user know that attempt to edit file failed
 * Adds DnD to ProjectManagerUI, removes it from the plugin, and fixes asserts
 * Fix assert (ticket #631)

## Drag scroll plugin:

 * Add user config option to reverse mouse wheel zoom
 * Fix right mouse click in project window. See https://forums.codeblocks.org/index.php/topic,22863.new.html
 * Don't move cursor when using right mouse key (wx3.x)

## Environment variables plugin:

 * Crash when closing Environment settings dialog (ticket #877)
 * Rework the plugin to not use ProjectLoaderHooks
 * Incorrect variables could be set or variables could be lost when using the configuration dialog (ticket #641)

## File manager plugin:

 * Slow down caused by incorrect fix in rev 11463 (ticket #722)
 * Fix assert when clicking the 'goto parent directory' button beyond the root (ticket #713)
 * Fix wrong use of stl-containers (erasing invalidates iterators) (ticket #722)

## Key binder plugin:

 * Fix warning for Ctrl-P being duplicated
 * Introduce version 2.0 using CodeLight key binding methods; allowing future ability to dynamically set menu and global accelerators to any frame
 * Sort cbKeybinder20.conf file and remove old (duplicate) bindings
 * Use correct file separator on Linux for .config/cbKeyBinder10.ini
 * If there is no <personality>.cbKeyBinder10.ini file try to load cbKeybinder10.ini
 * Add overridden menu accelerators to global table for Linux
 * Obtain correct config folder on linux (ticket 840)
 * Freeze config panel while updating
 * Avoid 'Wheres the event handler gone' asserts when modifying shortcuts
 * Fix F2, Shift-F2 and allow linux to handle any View menu check items (ticket #273)

## Nassi-Shneiderman plugin:

 * Convert the toolbar images from xpm buffers defined in code to using pngs stored in a zip
 * Fix crashes during drag n drop of bricks
 * Use wxBRUSHSTYLE_ constants to get rid of depricated-warnings from wx31
 * Remove wxALIGN_CENTER_HORIZONTAL|wxALIGN_CENTER_VERTICAL for expanded item. Avoids assert from wxWidgets 3.1

## Project options manipulator plugin:

 * Replace all options in one go (partial fix for ticket #868)
 * Report success after changing the compiler options (ticket #470)
 * Fix the UI layout of main dialog (ticket #607)

## RndGen plugin:

 * Some code cleanup (ticket #736)
 * Add the plugin to the builds on linux/macos (ticket #728)
 * Better explanation of the purpose and usage of the plugin (ticket #648)

## SpellChecker plugin:

 * Highlight error only if the cursor is away from the word. Simplify special character handling.
 * Fix wrong white space handling on windows by using the scintilla word finding functions
 * Speedup by moving code out of loop and advancing the position of the parser
 * Add Spanish flag images (ticket #881)
 * Make the popup menu to show when pressing the left button

## Thread search plugin:

 * Use file filter mask for all search options, not only for search in directories
 * Fix overwriting of search mask on windows
 * Don't prefix tilde to search word when doing Context menu -> Find occurrences of (ticket #742)
 * Prepare the plugin to support more than two resolutions of UI images
 * Make the images in plugin's toolbar to work correctly on GTK+ 3 and scaling of 2x
 * Remove almost all places in the plugin which used the /environment/toolbar_size instead of GetImagePrefix

## wxSmith plugin:

 * Fix use of an icon resources.zip
 * Add new style wxFLP_SMALL to wxFilePickerCtrl in wxWidgets 3.x (ticket #880)
 * Add new style wxFD_SHOW_HIDDEN to wxFileDialog in wxWidgets >= 3.1.3 (ticket #887)
 * Fix assertion because of missing default style for wxListView (ticket #884)
 * Add wxDIRP_SMALL flag for wxDirPickerCtrl (ticket #861)
 * Fix wrong grouping of radio boxes in the wxSmith settings dialog (ticket #875)
 * Fix image editor layout for wxWidgets >= 3.1.0 and rename dialog to image picker. (ticket #862)
 * Make wxParentProperty read only in wxsChart (ticket #853)
 * Limit field number in wxsStatusBar (ticket #847)
 * Better support for wxGLCanvas for wxWidgets 3.x (ticket #702)
 * Fix assert for adding windows to wxAUI manager (part of ticket #789)
 * Make the dialog for editing the items of wxChoice control to be resizable
 * Handle the default color in the color property class the same in both wxWidgets 3.x and wxWidgets 2.8 (ticket #815)
 * Fix "dangling" frames which prevent Code::Blocks's process from exiting correctly
 * Fix wxImagePanel preview error if an empty image is used
 * Do not generate code if user specifies no image in wxImagePanel
 * Fix a crash caused by uninitialized wxPen in wxMathPlot control
 * Make the wxImagePanel control support a image filename
 * Change wx*_BORDER styles to the new wxBORDER_* which are used in wxWidgets 3.x
 * Fix assert when using the wxGridBagSizer (ticket #664)
 * Fix use-after-free error when moving a control in a sizer
 * Add Radio as possible wxAuiToolBarItem item kind (ticket #15)
 * Fix assert after inserting wxListCtrl (ticket #671)
 * Set sensible defaults for initial and increment properties in wxSpinCtrlDouble
 * Add wxSpinCtrlDouble supported only for wxWidgets 3.x builds (ticket #616)

## Other plugins:

 * **Astyle**: Fix argument bug (ticket #698)
 * **AutoSave**: Add option to save log rotated backup files in a sub-folder (ticket #132)
 * **ClassWizard**: Remember file extensions for header and source files
 * **CppCheck**: Fix crash when the generated xml is missing
 * **CScope**: Add configuration dialog to select the cscope executable. Also add a link to the help page in the settings dialog.
 * **EditorConfig**: Rework the plugin to not use ProjectLoaderHooks
 * **EditorConfig**: Allow to use global editor settings for EOL (ticket #577)
 * **EditorTweaks**: Remove caret buffer code, because it was added to the core editor
 * **Help**: Fix bug in man2html (ticket #626)
 * **IncrementalSearch**: Try to have better/simpler history in the choice control (ticket #740)
 * **IncrementalSearch**: Make it possible to get focus by clicking (ticket 625)
 * **MouseSap**: Remove all direct GTK calls. Fix Shift-MiddleMouse key pasting to avoid overwriting Primary clipboard.
 * **OpenFileList**: Fix crash when disable/enable the plugin in the plugin manager dialog (ticket #774)
 * **OpenFileList**: Fix memory leak when unloading the plugin
 * **ReopenEditor**: Fix memory leaks
 * **SmartIndent**: Improve brace completion for Fortran (ticket #667)
 * **ToDo plugin**: Fix memory corruption due to splash screen (ticket #635)

# Summary, for download

Download the full changelog here: https://sourceforge.net/projects/codeblocks/files/Binaries/20.03/changelog

## Older Changelogs

See [Changelog for 17.12](/changelogs/17.12)

See [Changelog for 16.01](/changelogs/16.01)

See [Changelog for 13.12](/changelogs/13.12)

See [Changelog for 12.11](/changelogs/12.11)

## Special thanks

Special thanks for their (continuous) support go to:

 * Alatar
 * Artem VL
 * blauzahn
 * Christophe Marc BERTONCINI
 * Commaster
 * darmar
 * drzacek
 * Eran Ifrah
 * Fabián Inostroza
 * Gérard Durand (gd_on)
 * Gokul Krishnan
 * Hayleyfire
 * homertp
 * Jacques Laffont
 * Juan Manuel Fernández Muñoz
 * LETARTARE
 * Martin Strunz
 * Miguel Gimenez
 * ouch
 * sodev
 * Specialmart
 * stahta01
 * Xaviou
 * Zheng Fan
