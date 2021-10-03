# Linux commands cheetsheet:

## Basic commands for working with text:
 *  Ctrl + A => move cursor in the front of text
 *  Ctrl + E => move cursor in the end of text
 *  Ctrl + U => remove(crop) the word from cursor till start of the word
 *  Ctrl + K => remove(crop) the word from cursor till end of word
 *  Ctrl + Y => Paste cropped text
 *  Ctrl + Shift + C => Copy text to clipboard
 *  Ctrl + Shift + P => Paste text to clipboard

## Commands for files and folder:
 *  ~ : Represents users home directory. 
   `
   cd ~ => return to users home directory.
   `
 *  pwd => Represents your absolute path of current working directory.
 *  .  => Represents current directory.
 *  cd => change directory
 *  cd .. => moves one directory backwards
 *  cd ../../ => moves two directory backwards
 *  cd => return to users home directory
 *  mkdir dir-name => create new directory if does not exist.
 *  rmdir dir-name => removes directory if exists
 *  cp file1 file2 => copies content of file1 to file2
 *  mv ./file1 ../ => Move file1 from current directory to backward directory
 *  rm file1.txt => remove file1.txt
 *  rm -r dummy  => removes recursively all files and directory from dummy directory
 *  ls => List all files and directories within your current working directory.
 *  touch file-name => Will creat a file with provided file-name.

## Commands for changing file/directory permissions:
 
 `drwxrwxrwx : d => directory, r => read, w => write, x => excute, - => no permission 
    if d is blank then, its a file (-rwxr-xr-x)
    first group(drwx) - represents owner( who created the file)
    second(rwx) - represents user group (user groups other than owner, who has access to file)
    third(rwx) - represents others
    
    Numerical value for permisiions r, w ,x:
    r - 4
    w - 2
    x - 1
 `
 *  chmod XXX : this is used to change the permission associated with file/directory. It's called change mode. 
 X denotes permission number for an group(owner, user-group, other).
 
 `
    ex: chmod 644 - will assign read write to owner and read to both user group and other group.
    The default permission is 644.
    permission 777 - means all users(owner, user, others) have got full permission(rwx) on file/directory.
 `

 *  chown user fileName: change ownership of a file or directory
 
 `
    ex:  chown user:group filename
 `

## Commands to create hard and soft links for file:
 
 ` Link => A link in UNIX are pointers pointing to a file or a directory. Links allow more than one file name to refer to the same file, elsewhere. `
 
 Two ways to create symlinks:
 -------------------------------
 *  ln -s file1 file 2 => This will create a soft link file2 for refering file1.
 Soft links break if the source file(file1) is moved or moved.
 *  ln file 1 file 2 => This will create a hard link file2 for refering file1.
Hard links work even if then source(file1) is moved.


## Commands for searching/displaying text:
 *  grep -n “the” file1.txt => searches "the" in file1.txt with numbered line.

 *  cat file-name => Displays the content of file.

 *  | => Pipe is used to send the result of one command to next command after pipe to excute on it.
 
 `  
    ex
    cat file.txt | wc : here result of cat command is send to wc command for futher processing.
 `
 *  head filename => Display first 10 lines of a file.
 
 `head file.txt => Displays first 10 lines of file.txt `
 
 `head -n5 file.txt => Displays first 5 lines of file.txt`
 
 * tail filename => Display last 10 lines of a file.

 `tail file.txt => Displays last 10 lines of file.txt`
 
 `tail -n5 file.txt => Displays last 5 lines of file.txt`
 
 `cat file.txt | tail -n5 | cat -n => This displays the last 5 lines of the file.txt numbered as 1, 2, 3, 4, 5.`
 
 * less filename => Less will open the entire file but shows you the part of file then user can navigate in the file. Displays the content of file page by page. 


## Redirection of Inputs/Outputs/Stderr:

 #### File Descriptor and their representations:
 *  stdin  =>  0  => Input from the console
 *  stdout =>  1  => Output to console
 *  stderr =>  2  => Error to console

 #### Redirection:
 *  ' > ' => output of command1 is redirected to file.txt/stdout (Output Redirection).
 *  ' >> ' => output of command1 is appended to file.txt/stdout (Output Redirection).
 *  ' < ' => command 1 reads its input from file.txt/stdin (Input Redirection).

## RAM CPU and Disk Info:
*  free -h => Displays available and used RAM(memory).
*  cat /proc/cpuinfo => Displays information about cpu like cores etc.
*  df -h => Displays information about available and used Disks.
-h here is used to display the information in human readable format

## Other useful Command:
*  man option command => Displays manual page for a command.
*  help command => Display help information related to a command.
*  uname -a => Displays information about linux system on your machine.
*  hostname => Display the hostname and ip in the network for your machine.
`hostname -I => Will Display the ip of the system in network.`

*  ping => To test the reachablity of the system in network.
`ping google.com => Will ping to google.com and if that avaialble in network it will return th packets` 
