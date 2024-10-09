# Terminal Commands

The terminal commands allows you to automate tasks, access system features, troubleshoot issues, and perform operations more efficiently than with the graphical interface. It also provides greater control over your system and enhances problem-solving skills.

[Click here](http://ss64.com/osx/) to access the comprehensive macOS terminal command reference.

<br />

## Terminal

| Key/Command                                 | Description      |
| --------                                    | --------         |
| <kbd>⇥ Tab</kbd>                            | Auto-complete files and folder names                           |
| <kbd>⌃ Control</kbd> + <kbd>A</kbd>         | Go to the beginning of the line you are currently typing on    |
| <kbd>⌃ Control</kbd> + <kbd>E</kbd>	        | Go to the end of the line you are currently typing on          |
| <kbd>⌃ Control</kbd> + <kbd>U</kbd>	        | Clear the line before the cursor                               |
| <kbd>⌃ Control</kbd> + <kbd>K</kbd>	        | Clear the line after the cursor                                |
| <kbd>⌃ Control</kbd> + <kbd>W</kbd>	        | Delete the word before the cursor                              |
| <kbd>⌃ Control</kbd> + <kbd>T</kbd>	        | Swap the last two characters before the cursor                 |
| <kbd>⌃ Control</kbd> + <kbd>R</kbd>	        | Lets you search through previously used commands               |
| <kbd>⌃ Control</kbd> + <kbd>L</kbd>	        | Clears the Screen                                              |
| <kbd>⌘ Command</kbd> + <kbd>K</kbd>	        | Clears the Screen                                              |
| <kbd>⌃ Control</kbd> + <kbd>C</kbd>	        | Kill whatever you are running                                  |
| <kbd>⌃ Control</kbd> + <kbd>D</kbd>	        | Exit the current shell                                         |
| <kbd>⎋ Escape</kbd> + <kbd>T</kbd>	        | Swap the last two words before the cursor                      |

<br />

## Core Commands

| Key/Command                                 | Description      |
| --------                                    | --------         |
| CD                                          | Home directory                                                 |
| CD [folder]                                 | Change directory                                               |
| CD ~                                        | Home directory, e.g. 'cd ~/folder/'                            |
| CD /                                        | Root of drive                                                  |
| LS                                          | Short listing                                                  |
| LS -R                                       | Long listing                                                   |
| LS -A                                       | Listing incl. hidden files                                     |
| LS -LH                                      | Long listing with Human readable file sizes files              |
| LS -R                                       | Entire content of folder recursively                           |
| Sudo [Command]                   | Run command with the security privileges of the superuser (Super User DO) |
| Open [file]                                 | Opens a file                                                   |
| Open .                                      | Opens the directory                                            |
| Top                                         | Displays active processes. Press q to quit                     |
| Nano [file]                                 | Opens the Terminal it's editor                                 |
| Pico [file]                                 | Opens the Terminal it's editor                                 |
| <kbd>Q</kbd>                                | Exit                                                           |
| Clear                                       | Clear screen                                                   |

<br />

## Command History

| Key/Command                                 | Description      |
| --------                                    | --------         |
| History <kbd>N</kbd>                        | Shows the stuff typed - add a number to limit the last n items |
| <kbd>⌃ Control</kbd> + <kbd>R</kbd>         | Interactively search through previously typed commands         |
| <kbd>!</kbd>[value]                         | Execute the last command typed that starts with 'value'        |
| <kbd>!!</kbd>                               | Execute the last command typed                                 |

<br />

## File Management

| Key/Command                                 | Description      |
| --------                                    | --------         |
| Touch [file]                                | Create new file                                                |
| Pwd                                         | Full path to working directory                                 |
| ..                                          | Parent/enclosing directory, e.g.                               |
| LS -L ..                                    | Long listing of parent directory                               |
| CD ../../	                                  | Move 2 levels up                                               |
| .	                                          | Current folder                                                 |
| CAT	                                        | Concatenate to screen                                          |
| RM [file]	                                  | Remove a file, e.g. rm [file] [file]                           |
| RM -I [file]	                              | Remove with confirmation                                       |
| RM -R [dir]	                                | Remove a directory and contents                                |
| RM -F [file]	                              | Force removal without confirmation                             |
| RM -I [file]	                              | Will display prompt before                                     |
| Sudo RM -RF ~/.Trash/*	                    | Empty trash                                                    |
| CP [file] [newfile]	                        | Copy file to file                                              |
| CP [file] [dir]   	                        | Copy file to directory                                         |
| MV [file] [new filename]   	                | Move/Rename, e.g. mv -v /home/user/oldname /home/user/newname  |
| CHMOD 600 [file]   	                        | Set file/directory permission, e.g. chmod 600 [dir] / [file]   |
| MDFIND [file]	   	                          | Find full path of the file                                     |

<br />

## Directory Management

| Key/Command                                 | Description      |
| --------                                    | --------         |
| MKDIR [dir]                                 | Create new directory                                           |
| MKDIR -P [dir]/[dir]                        | Create nested directories                                      |
| RKDIR [dir]                                 | Remove directory (only operates on empty directories)          |
| RM -R [dir]                                 | Remove directory and contents                                  |
| RM -RF [dir]                                | Delete a whole folder and its content recursively              |
| RM -RF*           | Delete all files/folders in the current directory, without deleting the directory itself |

<br />

## Pipes - Allows to combine multiple commands that generate output

| Key/Command                                 | Description      |
| --------                                    | --------         |
| MORE                                        | Output content delivered in screensize chunks                  |
| > [file]                                    | Push output to file, keep in mind it will get overwritten      |
| >> [file]                                   | Append output to existing file                                 |
| <                                           | Tell command to read content from a file                       |

<br />

## Help

| Key/Command                                 | Description      |
| --------                                    | --------         |
| [command] -h                                | Offers help                                                    |
| [command] --help                            | Offers help                                                    |
| [command] help                              | Offers help                                                    |
| reset                                       | Resets the terminal display                                    |
| MAN [command]                               | Show the help for 'command'                                    |
| WHATIS [command]                            | Gives a one-line description of 'command'                      |
