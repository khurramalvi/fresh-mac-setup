# Terminal Commands

The terminal commands allows you to automate tasks, access system features, troubleshoot issues, and perform operations more efficiently than with the graphical interface. It also provides greater control over your system and enhances problem-solving skills.

[Click here](http://ss64.com/osx/) to access the comprehensive macOS terminal command reference.

<br />

## Shortcuts

| Key                                         | Description      |
| --------                                    | --------         |
| <kbd>⇥ Tab</kbd>                            | Auto-complete files and folder names  |
| <kbd>⌃ Control</kbd> + <kbd>A</kbd>         | Go to the beginning of the line you are currently typing on. This also works for most text input fields system wide. Netbeans being one exception |
| <kbd>⌃ Control</kbd> + <kbd>E</kbd>         | Go to the end of the line you are currently typing on. This also works for most text input fields system wide. Netbeans being one exception |
| <kbd>⌃ Control</kbd> + <kbd>L</kbd>         | Clears the screen |
| <kbd>⌘ Command</kbd> + <kbd>K</kbd>         | Clears the Screen |
| <kbd>⌃ Control</kbd> + <kbd>U</kbd>         | Cut everything backwards to beginning of line |
| <kbd>⌃ Control</kbd> + <kbd>K</kbd>         | Cut everything forward to end of line |
| <kbd>⌃ Control</kbd> + <kbd>W</kbd>         | Cut one word backwards using white space as delimiter |
| <kbd>⌃ Control</kbd> + <kbd>Y</kbd>         | Paste whatever was cut by the last cut command |
| <kbd>⌃ Control</kbd> + <kbd>H</kbd>         | Same as backspace |
| <kbd>⌃ Control</kbd> + <kbd>C</kbd>         | Kill whatever you are running. Also clears everything on current line |
| <kbd>⌃ Control</kbd> + <kbd>D</kbd>         | Exit the current shell when no process is running, or send EOF to a the running process |
| <kbd>⌃ Control</kbd> + <kbd>Z</kbd>         | Puts whatever you are running into a suspended background process. fg restores it |
| <kbd>⌃ Control</kbd> + <kbd>_</kbd>         | Undo the last command. (Underscore. So it's actually <kbd>⌃ Control</kbd> + <kbd>⇧ Shift</kbd> + <kbd>-</kbd>) |
| <kbd>⌃ Control</kbd> + <kbd>T</kbd>         | Swap the last two characters before the cursor |
| <kbd>⌃ Control</kbd> + <kbd>F</kbd>         | Move cursor one character forward |
| <kbd>⌃ Control</kbd> + <kbd>B</kbd>         | Move cursor one character backward |
| <kbd>⌥ Option</kbd> + <kbd>→</kbd>          | Move cursor one word forward |
| <kbd>⌥ Option</kbd> + <kbd>←</kbd>          | Move cursor one word backward |
| <kbd>⎋ Escape</kbd> + <kbd>T</kbd>          | Swap the last two words before the cursor |
| <kbd>⎋ Escape</kbd> + <kbd>⌫ Delete</kbd>   | Cut one word backwards using none alphabetic characters as delimiters |

<br />

## Essentials

| Command                                     | Description      |
| --------                                    | --------         |
| cd [folder]                                 | Change directory e.g. 'cd Documents' |
| cd                                          | Home directory |
| cd ~                                        |  Home directory |
| cd /                                        | Root of drive |
| cd -                                        | Previous directory |
| ls                                          | Short listing |
| ls -l                                       | Long listing |
| ls -a                                       | Listing incl. hidden files |
| ls -lh                                      | Long listing with Human readable file sizes |
| ls -R                                       | Entire content of folder recursively |
| sudo [command]                              | Run command with the security privileges of the superuser (Super User DO) |
| open [file]                                 | Opens a file ( as if you double clicked it ) |
| top                                         | Displays active processes. Press q to quit |
| nano [file]                                 | Opens the file using the nano editor |
| vim [file]                                  | Opens the file using the vim editor |
| clear                                       |  Clears the screen |
| reset                                       |  Resets the terminal display |

<br />

## Chaining

| Command                                     | Description      |
| --------                                    | --------         |
| [command-a]; [command-b]                    | Run command A and then B, regardless of success of A |
| [command-a] && [command-b]                  | Run command B if A succeeded |
| [command-a] \|\| [command-b]                | Run command B if A failed |
| [command-a] &                               | Run command A in background |

<br />

## Piping

| Command                                     | Description      |
| --------                                    | --------         |
| [command-a] \| [command-b]                  | Run command A and then pass the result to command B e.g ps auxwww \| grep google |

<br />

## History

| Command                                     | Description      |
| --------                                    | --------         |
| history n                                   |  Shows the stuff typed - add a number to limit the last n items |
| Ctrl + r                                    | Interactively search through previously typed commands |
| ![value]                                    |  Execute the last command typed that starts with 'value' |
| ![value]:p                                  |  Print to the console the last command typed that starts with 'value' |
| !!                                          |  Execute the last command typed |
| !!:p                                        |  Print to the console the last command typed |

<br />

## File Management

| Command                                     | Description      |
| --------                                    | --------         |
| touch [file]                                |   Create a new file |
| pwd                                         | Full path to working directory |
| .                                           |  Current folder, e.g. 'ls .' |
| ..                                          | Parent/enclosing directory, e.g. 'ls ..' |
| ls -l ..                                    | Long listing of parent directory |
| cd ../../                                   | Move 2 levels up |
| cat                                         | Concatenate to screen |
| rm [file]                                   |  Remove a file, e.g. 'rm data.tmp' |
| rm -i [file]                                | Remove with confirmation |
| rm -r [dir]                                 | Remove a directory and contents |
| rm -f [file]                                | Force removal without confirmation |
| cp [file] [newfile]                         | Copy file to file |
| cp [file] [dir]                             | Copy file to directory |
| mv [file] [new filename]                    |  Move/Rename, e.g. 'mv file1.ad /tmp' |
| pbcopy < [file]                             | Copies file contents to clipboard |
| pbpaste                                     | Paste clipboard contents |
| pbpaste > [file]                            | Paste clipboard contents into file, 'pbpaste > paste-test.txt' |

<br />

## Directory Management

| Command                                     | Description      |
| --------                                    | --------         |
| mkdir [dir]                                 | Create new directory |
| mkdir -p [dir]/[dir]                        |  Create nested directories |
| rmdir [dir]                                 | Remove directory ( only operates on empty directories ) |
| rm -R [dir]                                 | Remove directory and contents |
| less [file]                                 |  Output file content delivered in screensize chunks |
| [command] > [file]                          |  Push output to file, keep in mind it will get overwritten |
| [command] >> [file]                         | Append output to existing file |
| [command] < [file]                          |  Tell command to read content from a file |

<br />

## Search

| Command                                     | Description      |
| --------                                    | --------         |
| find [dir] -name [search_pattern]           | Search for files, e.g. 'find /Users -name "file.txt"' |
| grep [search_pattern] [file]                | Search for all lines that contain the pattern, e.g. 'grep "Tom" file.txt' |
| grep -r [search_pattern] [dir]              | Recursively search in all files in specified directory for all lines that contain the pattern |
| grep -v [search_pattern] [file]             | Search for all lines that do NOT contain the pattern |
| grep -i [search_pattern] [file]             | Search for all lines that contain the case-insensitive pattern |
| mdfind [search_pattern]                     | Spotlight search for files (names, content, other metadata), e.g. 'mdfind skateboard' |
| mdfind -onlyin [dir] -name [pattern]        | Spotlight search for files named like pattern in the given directory |

<br />

## Help

| Command                                     | Description      |
| --------                                    | --------         |
| [command] -h                                |  Offers help |
| [command] --help                            | Offers help |
| info [command]                              | Offers help |
| man [command]                               |  Show the help manual for [command] |
| whatis [command]                            | Gives a one-line description of [command] |
| apropos [search-pattern]                    | Searches for command with keywords in description |