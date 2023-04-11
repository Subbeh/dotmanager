# Dotfile Manager

This is a bash script that manages your dotfiles by creating a git repository in your home directory and storing your dotfiles in it. It then creates symbolic links to the original files in your home directory. You can move your dotfiles to the repository and manage them with git commands.

The script uses the `stow` utility to manage the symbolic links and requires `git` to access the dotfile repository.

## Installation

1. Clone the repository:

```bash
git clone https://github.com/<username>/dotfile-manager.git ~/.dotfile-manager
```

2. Copy the script to your home directory:

```bash
cp ~/.dotfile-manager/dotfile-manager.sh ~/dotfile-manager.sh
```

3. Make the script executable:

```bash
chmod +x ~/dotfile-manager.sh
```

4. Add an alias to your .bashrc or .zshrc file:

```bash
alias dot='~/dotfile-manager.sh'
```

## Usage
### Commands

- `dot status`: Show the status of the git repository and any submodules.
- `dot link -d [<app-name>] [<object(s)>]`: Move files to the repository and create symbolic links to the original location.
- `dot load [-g | -p <profile-name(s)> | [<app-names>]]`: Create and update symbolic links from the repository.
  - `-g`: update submodules within the repository
  - `-p`: use a profile from profiles.dot

### Examples

- `dot status`: Show the status of the git repository and any submodules.
- `dot link -d vim .vimrc`: Move .vimrc file to the repository and create symbolic link to the original location.
- `dot validate vim`: Validate if .vimrc file already exists before trying to create a symlink to the same location.
- `dot load vim`: Recreate and update symbolic links for the vim app.
- `dot load -p dev server`: Recreate and update symbolic links for all apps in the dev and server profiles.
- `dot load -g`: Update submodules within the repository before recreating and updating symbolic links.

# Contributing

Contributions are welcome! Feel free to open a pull request or an issue on the GitHub repository.
