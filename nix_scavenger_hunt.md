# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*

/Users/Xeifer/Documents/Web Dev/GitHub/wats1030-intro-to-unix

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*

LICENSE nix_scavenger_hunt.md
README.md nix_scavenger_hunt_stretch.md
challenge_files

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*

total 56
drwxr-xr-x    9 Xeifer  staff   306B Apr  6 17:32 .
drwxr-xr-x    4 Xeifer  staff   136B Apr  6 18:39 ..
-rw-r--r--@   1 Xeifer  staff   6.0K Apr  6 17:49 .DS_Store
drwxr-xr-x   13 Xeifer  staff   442B Apr  6 18:39 .git
-rw-r--r--    1 Xeifer  staff   1.1K Apr  6 16:06 LICENSE
-rw-r--r--    1 Xeifer  staff   1.3K Apr  6 16:06 README.md
drwxr-xr-x  111 Xeifer  staff   3.7K Apr  6 16:06 challenge_files
-rw-r--r--    1 Xeifer  staff   5.4K Apr  6 16:06 nix_scavenger_hunt.md
-rw-r--r--    1 Xeifer  staff   317B Apr  6 16:06 nix_scavenger_hunt_stretch.md

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/)Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*

NAME
     ls -- list directory contents

SYNOPSIS
     ls [-ABCFGHLOPRSTUW@abcdefghiklmnopqrstuwx1] [file ...]

DESCRIPTION
     For each operand that names a file of a type other than directory, ls
     displays its name as well as any requested, associated information.  For
     each operand that names a file of type directory, ls displays the names
     of files contained within that directory, as well as any requested, asso-
     ciated information.

     If no operands are given, the contents of the current directory are dis-
     played.  If more than one operand is given, non-directory operands are
     displayed first; directory and non-directory operands are sorted sepa-
     rately and in lexicographical order.

     The following options are available:

     -a      Include directory entries whose names begin with a dot (.).

     -l      (The lowercase letter ``ell''.)  List in long format.  (See
             below.)  If the output is to a terminal, a total sum for all the
             file sizes is output on a line before the long listing.

     -h      When used with the -l option, use unit suffixes: Byte, Kilobyte,
             Megabyte, Gigabyte, Terabyte and Petabyte in order to reduce the
             number of digits to three or less using base 2 for sizes.

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*

Applications dev
Data etc
Incompatible Software home
Library installer.failurerequests
Network net
System opt
User Guides And Information private
Users sbin
Volumes tmp
bin usr
cores var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*

/

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*

/Users/Xeifer

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*

-rw-r--r--    1 Xeifer  staff     0B Apr  6 16:06 2015_special_stuff.demo
-rw-r--r--    1 Xeifer  staff     0B Apr  6 16:06 cloaked-wookie.demo
-rw-r--r--    1 Xeifer  staff     0B Apr  6 16:06 scooter-double-mamba.demo

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*

/Users/Xeifer/Documents/Web Dev/GitHub/wats1030-intro-to-unix

* Press the up arrow on your keyboard. *What just happened?*

- terminal scrolled to previous command
—> Citadel:wats1030-intro-to-unix Xeifer$ cd -

* Press the up arrow a few more times. *What do you see?*

- terminal is scrolling through command history

* Run the `history` command. *What do you see?*

- I see a giant list of all previous commands

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*

Xeifer

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*

Xeifer   console  Apr  6 12:50
Xeifer   ttys000  Apr  6 19:21

* How long has your system been running? Use `uptime` to see, and *paste the result here:*

19:29  up  6:40, 2 users, load averages: 1.79 1.91 1.72

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*

- This appears to be process hisotry  It lists software updates, apps used such as spotlight, what time they were used, etc.

DESCRIPTION
     The ps utility displays a header line, followed by lines containing
     information about all of your processes that have controlling terminals.

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.)

*How do you interpret what you see here?*

- This appears to be an overview of the system processes/CPU usage as it shows current processes, running, threads, etc.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*

- 2 files found
credit_cards.txt
credit_cards2.txt

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*

Last updated: 01-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*

./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*

- None, this is the command I used:
Citadel:challenge_files Xeifer$ grep WA .
grep: .: Is a directory

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*

./Britt-Erdman.user:O'Harachester, WA 37261
./Lissie-Strosin.user:Jewessfurt, WA 00816-7241

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*

01
2015_special_stuff.demo
Afton-Jast.user
Aimee-Maggio.user
Alfonso-Gottlieb.user
Allen-Kemmer.user
Almina-Cormier.user
Alta-Lemke.user
Amina-McGlynn.user
Anabel-Hammes.user
Ancel-Conn.user
Anjali-Halvorson.user
Ardath-Kuvalis.user
Avah-Dickinson.user
Ayaan-Stiedemann.user
Aylin-Grant.user
Bedford-Sipes.user
Benita-King.user
Benito-Stoltenberg.user
Beverlee-Moen.user
Brad-Thiel.user
Brayan-Douglas.user
Bria-Satterfield.user
Bridgette-Reichel.user
Britt-Erdman.user
Britta-Hammes.user
Bryant-Kuhic.user
Bryton-Aufderhar.user
Caitlin-Grady.user
Carroll-Hartmann.user
Claudie-McClure.user
Clemente-Haley.user
Cleo-VonRueden.user
Codie-Romaguera.user
Cooper-Reynolds.user
Corrie-Bogisich.user
Dannielle-Green.user
Deedee-Jacobson.user
Desiree-Marks.user
Deven-Rutherford.user
Doyle-Jones.user
Dustyn-O'Connell.user
Elza-Mraz.user
Emory-Crona.user
Erin-Walker.user
Estela-Schultz.user
Fernanda-Tromp.user
Fletcher-Rice.user
Fred-Ryan.user
Genie-Abshire.user
Grace-Tromp.user
Grant-Cronin.user
Hali-Roob.user
Harland-Schoen.user
Harrell-Quitzon.user
Hillard-Ziemann.user
Isadora-Leffler.user
Jaxen-Gleichner.user
Jayme-Rodriguez.user
Jenni-O'Connell.user
Johny-Borer.user
Kassandra-Barrows.user
Keely-Hilpert.user
Kenyatta-Hickle.user
Kiana-Kulas.user
Kirstin-Hoppe.user
Kwame-Schmitt.user
Ladonna-Lueilwitz.user
Lala-Will.user
Leia-Hudson.user
Leia-Ziemann.user
Lillard-Purdy.user
Lilly-Kohler.user
Lissie-Strosin.user
Mannie-Ritchie.user
Masako-Lind.user
Melisa-Yundt.user
Michelina-Kuphal.user
Minnie-Jacobi.user
Murdock-Leffler.user
Mychal-Corkery.user
Nakita-Nader.user
Nayely-Dare.user
Nicholas-Strosin.user
Niles-Runte.user
Nina-Sporer.user
Noreta-Steuber.user
Ovid-Bogan.user
Randell-Sauer.user
Remy-Renner.user
Ronna-Hermann.user
Rosalind-Wisozk.user
Rosena-Simonis.user
Sandie-Balistreri.user
Sharen-Hansen.user
Sherrill-Russel.user
Sherwin-Kovacek.user
Sherwood-Rath.user
Shyheim-Murazik.user
Siobhan-Kirlin.user
Tomas-Kutch.user
cloaked-wookie.demo
credit_cards.txt
credit_cards2.txt
files.txt
scooter-double-mamba.demo
serial-numbers
test2
tmp
wow

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*

- Terminal breaks the results down into a sequence of pages

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

Xeifer           4468   0.0  0.0  2423376    208 s000  R+    8:28PM   0:00.00 grep xeifer