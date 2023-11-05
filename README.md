# Alias for copying the commit hash string

## Introduction

This alias pipes the hash string from your **last** commit to clipboard.<br>
The command adds the alias into your global git profile, which is pc specific. You can safely remove it later, if you wish so.<br>

Usage example: `git getlog`<br>
Git profile location: `~/.gitconfig`

### Edit the profile (if needed)

Windows (powershell):

- Type: `notepad ~\.gitconfig` + tab, (only press enter after hitting the "tab" -key).<br>
- Or: `notepad $env:USERPROFILE\.gitconfig`

Mac / Linux: `nano ~/.gitconfig`<br>
You can replace notepad / nano with the text editor of your choice..

## Add alias into your git profile

You can also replace the alias `getlog` with another word.

### Windows

`git config --global --add alias.getlog '!git log -1 --pretty=format:%H | clip'`

### Linux

Requires xclip<br>
-r = no newline, '-sel clip' = '-selection clipboard'.<br>
`git config --global --add alias.getlog '!git log -1 --pretty=format:%H | xclip -r -sel clip'`

### Mac (requires confirmation)

`git config --global --add alias.getlog '!git log -1 --pretty=format:%H | pbcopy'`
