# cmd

run cmd in a specific folder

    cmd /K "cd /d the-path-of-the-folder"

Windows command	| Unix command	| Notes
|--|--|--|
arp	|arp||	
assign	| ln |	Create a file link
assign	| ln -s	|On Unix, a directory may not have multiple links, so instead a symbolic link must be created with ln -s.
assoc |	file	|
at	|at batch cron	|
attrib	| chown chmod	|Sets ownership on files and directories
cd	|cd	|On Windows, cd alone prints the current directory, but on Unix cd alone returns the user to his home directory.
cd	| pwd |	On Windows, cd alone prints the current directory.
chkdsk|	fsck|	Checks filesystem and repairs filesystem corruption on hard drives.
cls	|clear|	Clear the terminal screen
copy|	cp|	
date| time	date	|Date on Unix prints the current date and time. Date and time on Windows print the date and time respectively, and prompt for a new date or time.
del	|rm	|
deltree	|rm -r|	Recursively deletes entire directory tree
dir	|ls|	“dir” also works on some versions of Unix.
doskey /h F7 key|	history|	The Unix history is part of the Bash shell.
edit|	vi emacs etc.|	edit brings up a simple text editor in Windows. On Unix, the environment variable EDITOR should be set to the user’s preferred editor.
exit|	exit Control-D|	On Unix, pressing the control key and D simultaneously logs the user out of the shell.
explorer |	nautilus etc.|	The command explorer brings up the file browser on Windows.
fc|	diff|	
find|	grep|	
ftp	|ftp|	
help|	man |	“help” by itself prints all the commands
hostname|	hostname|	
ipconfig /all|	ifconfig -a|	The /all option lets you get the MAC address of the Windows PC
mem|	top|	Shows system status
mkdir	|mkdir|	
more	|more less	
move	|mv|	
net |	w
session	|who
net statistics |	uptime	
nslookup	|nslookup	
ping	|ping	
print	|lpr|	Send a file to a printer.
reboot shutdown -r	| shutdown -r	
regedit	|edit /etc/*|	The Unix equivalent of the Windows registry are the files under /etc and /usr/local/etc. These are edited with a text editor rather than with a special-purpose editing program.
rmdir|	rmdir	|
rmdir /s |	rm -r|	Windows has a y/n prompt. To get the prompt with Unix, use rm -i. The i means “interactive”.
set	env|	Set| on Windows prints a list of all environment variables. For individual environment variables, set <variable> is the same as echo $<variable> on Unix.
set Path	|echo $PATH |	Print the value of the environment variable using set in Windows.
shutdown	|shutdown|	Without an option, the Windows version produces a help message
shutdown -s|	shutdown -h	|Also need -f option to Windows if logged in remotely
sort|	sort	|
start|	&|	On Unix, to start a job in the background, use command &. On Windows, the equivalent is start command. See How to run a Windows command as a background job like Unix ?.
systeminfo|	uname -a|	
tasklist|	ps	|“tasklist” is not available on some versions of Windows. See also this article on getting a list of processes in Windows using Perl
title	|?|	In Unix, changing the title of the terminal window is possible but complicated. Search for “change title xterm”.
tracert	|traceroute	|
tree|	find ls -R	|On Windows, use tree | find “string”
type|	cat|	
ver	|uname -a	|
xcopy |	cp -R|	Recursively copy a directory tree