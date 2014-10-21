A python script to keep track of information which cannot be tracked by
git.

It's designed to work only on *nix systems. It will track the following
information:
* empty directories
* device files and named pipes
* file/directory ownership and permissions

# System Requirement
A not so old python interpreter.

Yes, that's it. The script was tested under python 2.6 & python 2.7,
older version like 2.5 probably will work too.

# Install
Copy the script "anykeeper" to anywhere you like, including system PATH
like /usr/bin. You can even put it directly into your own project.

# License
This project can be redistributed under the
[2-clause BSD license](http://en.wikipedia.org/wiki/BSD_licenses#2-clause_license_.28.22Simplified_BSD_License.22_or_.22FreeBSD_License.22.29)
which is quite permissive, see COPYING for more details.

# Getting Started
First make sure your working copy is clean, if not, commit or revert your
changes. Then execute command "anykeeper init" inside your project to
initialize anykeeper. This command will create two regular files
(.anykeeper.conf, .anykeeper.meta) and a git hook (.git/hooks/pre-commit).
If the git hook already exists, you have to edit it manually to execute the
command. Finally commit the two newly created file .anykeeper.conf &
.anykeeper.meta.

From now on, after every git command that would change the contents of your
working copy, for example, checkout/pull, you have to run command
"anykeeper init" to restore the information git doesn't track. The git
pre-commit hook will take care of everything else.
