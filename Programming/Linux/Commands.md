# Commands

**Help**   
`man`: Unix man pages, for help  
]`-k`: search for command by keywords  
`apropos`: *man -k*  
`whatis`: simpler explanation

## General

`passwd`: changes CSE password  
`whoami`: finds out who you are  
`id`: finds out more detailed information  about who you are  
`users`: finds out who else is logged into the system  
`who`: finds out more detailed information about logged-in users  
`w`: finds out who is logged in and what they are doing  
`date`: gets current date  
`exit` or `logout`: *always remember to log out*  

**up-arrow**: see previously entered commands  
**tab**: autocomplete commands  
**ctrl d**: exit out of editing  

## Files

### Navigating files

- Unix uses a hierarchical file system
- Top is called the **root directory**, displayed as `/`

`ls`: display contents of root directory
]`-a`: see hidden files
]`-Fa`
`.`: current directory
`..`: parent directory
`~`: home directory
`env`: displays user environment
`echo $...`: list values of user environments
`pwd`: tells current directory
`cd`: changes directory

/ - folder  
\* -  program
@ - symbolic link (pointer to another file or directory)

Common directories

/bin - all binaries were stored here in early Unix (now in /sbin and /uss/bin)
/dev - device stored drivers  
/etc - place for administrative files  
/lib - used to store code libraries shared by programs  
/lost+found - recovered files  
/mnt - eternal hardware  
/sys - files related to system information  
/tmp - temporary files  
/user - assortment of files  
/boot - files needed to boot Unix  
/home - home directory for all users  
/net - shortcuts to other computers on network  
...

Absolute
- *Exact* location of a file
- Starts with '/'

Relative
- *Relative* location to some given location

Hidden files
- Usually preference files
- Uses a '.' in front of file name

User environment
- HOME: home directory for storing files
- SHELL: program used for shell
- PATH: directories searched through when typing a command
- MAIL: directory where mail is stored
- LOGNAME: username
- TZ: time zone

### Listing files

`ls -...`  
]`s`: blocks of memory being used  
]`F`: appends information  
]`m`: printed as comma-separated values  
]`C`: multiple columns
]`1`: displayed in a single column  
]`l`: detailed information about the files/directories such as size, date, ownership, and permissions  
]`x`: sorted alphabetically, left-to-right  
]`t`: reverses order of results  
]`R`: recursively lists all files/directories of all subdirectories
]`lg`: group file belongs to

*Can put multiple flags in a row without dashes*

Flags
- `ls`...

### Creating files

`touch`: when used, changes the date it was accessed  
- When used on a file that doesn't exist, it creates a file  

### Managing disk space

`du`: check disk space used  
]`h`: human friendly description  
]`s`: total size  
]`a`: space used by files  
`df`: check space free  
]`h`: human readable  

Compressing

`gzip`: compressing/shrinking big files  
`bzip`  
]`v`: see how much space was saved  
`gunzip`: uncompressing a file   
`bunzup2` 

### Ownership and permissions

- Owner, group, everyone else(world or others)
  - Read: ability to open a file or see filenames inside of a directory
  - Write: ability to change a file or write inside of a directory
  - Execute: ability to launch a program file or access file information/content only if the file name is known

- Owner of a file can alter the permissions for their own permissions as well as the permissions of the other user types
- The other user types cannot change permissions

`ls -`
]`l`: view information about the permissions of a file/directory

Type: (d/-)  
Owner: (r/-)(w/-)(x/-)  
Group: (r/-)(w/-)(x/-)  
Everyone: (r/-)(w/-)(x/-)
- r: read
- w: write
- x: execute

`chmod`: (*change mode*) change file/directory permissions  
`unmask`: setting default file/directory permissions - permissions you *don't* want to allow  
`chown`: change owner/group of a file/directory

Symbolic notation: pick one or more of the user types, pick one of the options to change the permission, and pick one or more of the permissions options
- u: user
- g: group
- o: others
- a: all
- +: add permissions
- -: remove permissions
- =: set permissions
- r/w/x

Numeric notation: same idea, but numbers stand for the various permission changes
- Binary representation of each permission converted to decimal

### Managing files

`touch`: create a new file  
`cp <file> <copy`: copy but don't delete original  
`mv <file> <directory>`: move file  
`mv <file> <file name>`: rename file  
`rm <file> [<file> <file> <file>]`: delete a file - **most dangerous command**  
]`-i`: show confirmation  
]`-r`: **extremely dangerous** recursive deleting of files

### Managing directories

`mkdir`: creates a new directory at specified location  
`cp -r`: copy/create directory
- Must use '-r'
- If the directory exists, the contents are copied
- If it doesn't exist, the entire directory is copied with the location and name of the second  
`mv`: used for moving and renaming a directory  
`rm -r <dir> <dir> <dir>`: **most dangerous** command  

]`-i`

### Viewing files

`file`: view kind of information in file
}`*`: run on all files in directory

Pieces of files  
`head`: view beginning of files  
`tail`: view end of file  
]`-<num>`: number of lines  

Entire files  
`cat`: display entire contents of file  
]`-n`: numbers each line  
]`-v`: showing non-printable characters  
`more`: display entire contents of file, allowing movement through the file  
]`-s`: suppress multiple blank lines  
]`+n`: open the file at the nth line  
]`+/<text>`: jump to line containing some text  
`less`: same as *more* but with commands for going backwards

More  
`[Space]`: display next screen of text  
`n[Return]`: display next n lines of text  
`h`: display a list of commands available  
`d`: scroll down half a page  
`q`: quit  
`ns`: skip forward n lines  
`nf`: skip forward n screen full  
`b` or `Control]b`: go backward a screen  
`=`: display current line number  
`/<text>`: search for occurrence of text  
- `n`: search for next occurrence

### Pipes and filters

File redirection    
`>`: writes date from the source on the left to the file on the right, *overwriting* an previous data in file  
`<`: reads data from file on right and uses it as input to the command on the left  
`>>`: writes data from the source on the left to the file on the right *appending* data rather than overwriting  

Pipes  
`|`: pipe, used to redirect output of one command to be used in another

*Example*  
`head -<y> files | tail -<y-x+1>`: view lines x-y

Counting lines, words, and characters  
`wc`: counts number of lines, words, or characters  
]`-l`: lines  
]`-w`: words  
]`-c`: characters  

Filters
- Designed to be in the middle of a pipeline

`sort`: sorts alphabetically  
]`-b`: ignore blanks  
]`-d`: sort in dictionary order  
]`-f`: ignore case of words  
]`-n`: sorting numerically  
]`-r`: reversing results  

`uniq`: removes duplicate lines in data  
]`-c`: see how many duplicate lines were removed  

*Examples*  
`ls -1D | sort -f`: sort output of ls
`sort < <file>`: sort lines of a file  
`cat <file> | sort -d | uniq -c | echo`: sort lines of a file using dictionary order, remove duplicates, show number of lines removed, and display

### Wildcards and regular expressions

Wildcards  
`*`: acts as a match for any number and sequence of characters  
`?`: acts as a match for any single character  

Regular expressions  
- Pattern to perform advanced searching

`grep`
]`<expression>`

Rules
- A single character matches itself
- String matches itself
- `\c` forces character 'c' to be read as a letter
- `^` stands for beginning of a line while `$` is the end
- `.` any single character
- `[abd]` means any one character in the set can be used
  - `[a-zA-Z]`
- `[^abc]` means any one character not in the set can be used
- `x*` means that zero of more occurences of the character in front of the character can be used

`egrep`  
]`<expression>`

Rules
- Every rule for `grep`
- `(` and `)` can be used to group pieces of an expression
- `|` means *or* and can match either the expression on the left, the expression on the right, or both
- `+` is similar to `*`, but means *one or more* instead of *zero or more*
- `?` is similar to both `*` and `+`, but means *zero or one occurrences exactly*