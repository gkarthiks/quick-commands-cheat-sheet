

| Operator | Usage | How to |
|----------|-------|---------|
| @ | Sets the display of command statements in Batch files. | `@echo off` |
| &	| Executes commands in sequence irrespective of the previous command's result. | `command1 & command2` |
| && | Executes commands in sequence only if the previous command is successfully executed. | `command1 && command2` |
| ¦¦ | Executes the second command only if the first command fails. | `command1 ¦¦ command2` |
| > | Prints output of the command to a named file. If file does not exist, it creates one otherwise overwrites existing file | `command > file.txt` |
| >> | Prints the output of the command to an existing file. If file doesn't exist will create one. |	`command >> file_name` |
| <	| Takes the given file data as input to the command. | `command < somefile` |
| ¦	| Push the putput of first command as input to the proceeding commands. | `command1 ¦ command2` |
