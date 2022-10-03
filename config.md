GIT OPTIONS
===========

___

| Command | Description |
| ------- | ---------   | 
| `--replace-all` | Default behavior is to replace at most one line. This replaces all lines matching the key (and optionally the value-pattern). | 
| `--add`   | Adds a new line to the option without altering any existing values. This is the same as providing ^$ as the value-pattern in --replace-all. |
| `--get`   | Get the value for a given key (optionally filtered by a regex matching the value).Returns error code 1 if the key was not found and the last value if multiple key values were found. | 
| `--get-all` | Like get, but returns all values for a multi-valued key. |
| `--get-regexp` | Like --get-all, but interprets the name as a regular expression and writes out the key names. Regular expression matching is currently case-sensitive and done against a canonicalized version of the key in which section and variable names are lowercased, but subsection names are not. |
| `--get-urlmatch <name> <URL>` | When given a two-part name section.key, the value for section.<URL>.key whose <URL> part matches the best to the given URL is returned (if no such key exists, the value for section.key is used as a fallback). When given just the section as name, do so for all the keys in the section and list them. Returns error code 1 if no value is found. |
| `--global` | For writing options: write to global ~/.gitconfig file rather than the repository .git/config, write to $XDG_CONFIG_HOME/git/config file if this file exists and the ~/.gitconfig file doesn’t. |
|          | For reading options: read only from global ~/.gitconfig and from $XDG_CONFIG_HOME/git/config rather than from all available files. |
| `--system` | For writing options: write to system-wide $(prefix)/etc/gitconfig rather than the repository .git/config. |
|          | For reading options: read only from system-wide $(prefix)/etc/gitconfig rather than from all available files. |
| `--local` | For writing options: write to the repository .git/config file. This is the default behavior. |
|         | For reading options: read only from the repository .git/config rather than from all available files. |
| `--worktree` | Similar to --local except that $GIT_DIR/config.worktree is read from or written to if extensions.worktreeConfig is enabled. If not it’s the same as --local. Note that $GIT_DIR is equal to $GIT_COMMON_DIR for the main working tree, but is of the form $GIT_DIR/worktrees/<id>/ for other working trees. See git-worktree[1] to learn how to enable extensions.worktreeConfig. |
| `-f <config-file> or  --file <config-file>` | For writing options: write to the specified file rather than the repository .git/config. |
|         | For reading options: read only from the specified file rather than from all available files. |
| `--blob <blob>` | Similar to --file but use the given blob instead of a file. E.g. you can use master:.gitmodules to read values from the file .gitmodules in the master branch. See "SPECIFYING REVISIONS" section in gitrevisions[7] for a more complete list of ways to spell blob names. |
| `--remove-section` | Remove the given section from the configuration file. |
| `--rename-section` | Rename the given section to a new name. |
| `--unset` | Remove the line matching the key from config file. |  
| `--unset-all` | Remove all lines matching the key from config file. | 
| `-l or --list` | List all variables set in config file, along with their values. |
| `--fixed-value` | When used with the value-pattern argument, treat value-pattern as an exact string instead of a regular expression. This will restrict the name/value pairs that are matched to only those where the value is exactly equal to the value-pattern. |
| `--type <type>` | git config will ensure that any input or output is valid under the given type constraint(s), and will canonicalize outgoing values in <type>'s canonical form. |
