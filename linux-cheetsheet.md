## Linux commands cheetsheet:

# Basic commands for working with text:
 *  Ctrl + A => move cursor in the front of text
 *  Ctrl + E => move cursor in the end of text
 *  Ctrl + U => remove(crop) the word from cursor till start of the word
 *  Ctrl + K => remove(crop) the word from cursor till end of word
 *  Ctrl + Y => Paste cropped text
 *  Ctrl + Shift + C => Copy text to clipboard
 *  Ctrl + Shift + P => Paste text to clipboard

# Commands for files and folder:
 *  ~ : Represents users home directory. 
   `
   cd ~ => return to users home directory.
   `
 *  .  => Represents current directory.
 *  cd => change director
 *  cd .. => moves one director backwards
 *  cd ../../ => moves two director backwards
 *  cd => return to users home directory
 *  mkdir <dir-name> => create new director if does not exist.
 *  rmdir <dir-name> => removes directory if exists
 *  cp file1 file2 => copies content of file1 to file2
 *  mv ./file1 ../ => Move file1 from current directory to backward directory
 *  rm file1.txt => remove file1.txt
 *  rm -rf dummy  => removes recursively all files and directory from dummy directory
 
# Commands for changing file/directory permissions:
 `
    drwxrwxrwx : d => directory, r => read, w => write, x => excute, - => no permission 
    if d is blank then, its a file (-rwxr-xr-x)
    first group(drwx) - represents onwer( who created the file)
    second(rwx) - represents user group (user groups other than owner, who has access to file)
    third(rwx) - represents others
    Numberical value of permisiions:
    r - 4
    w - 2
    x - 1
 `
 *  chmod <permission number> : this is used to change the permission associated with file. It's called change mode.
 `
    ex: chmod 644 - will assign rw to owner and read to both user group and other group.
    The default permission is 644.
 `

 *  chown <user fileName>: change ownership of a file or directory
 `
    ex:  chown user:group filename
 `

# Commands to create hard and soft links for file:
 link => A link in UNIX are pointers pointing to a file or a directory. Links allow more than one file name to refer to the same file, elsewhere. 
 Two ways to create symlinks:
 -------------------------------
 *  ln -s file1 file 2 => This will create a soft link file2 for refering file1.
 Soft links break if the source file(file1) is moved or moved.
 *  ln file 1 file 2 => This will create a hard link file2 for refering file1.
Hard links work even if then source(file1) is moved.


# Commands related to searching text:
 *  grep -n “the” file1.txt => searches "the" in file1.txt with numbered line.

# Pipe Commands:
 *  | => Pipe is used to send the result of one command to next command after pipe to excute on it.
 `  
    ex
    cat file.txt | wc : here result of cat command is send to wc command for futher processing.
 `
 *  head <filename> => Display first 10 lines of a file.
 `
    ex:
    head file.txt => Displays first 10 lines of file.txt
    head -n5 file.txt => Displays first 5 lines of file.txt
 `
 * tail <filename> => Display last 10 lines of a file.
`
    ex:
    tail file.txt => Displays last 10 lines of file.txt
    tail -n5 file.txt => Displays last 5 lines of file.txt
    cat file.txt | tail -n5 | cat -n => This displays the last 5 lines of the file.txt numbered as 1, 2, 3, 4, 5.
 `
 * less <filename> => Less will open the entire file but shows you the part of file then user can navigate in the file. Displays the content of file page by page. 


# Redirection of Inputs/Outputs/Stderr:
 ### File Descriptor and their representations:
 *  stdin  =>  0  => Input from the console
 *  stdout =>  1  => Output to console
 *  stderr =>  2  => Error to console

 ### Redirection:
 * ' > ' => output of command1 is redirected to file.txt/stdout (Output Redirection).
 * ' >> ' => output of command1 is appended to file.txt/stdout (Output Redirection).
 * ' < ' => command 1 reads its input from file.txt/stdin (Input Redirection).

# RAM and Disk Info:
* free -h => Displays available and used RAM 
* cat /proc/cpuinfo => Displays information about cpu like cores etc.
* df -h => Displays information about available and used Disks.

# Other useful Command:
* man <option> <command-name> => Displays user manual of command. 
* help <command> => Display help information related to command.