# 🐧 Linux Commands Notes

## date
   - It is used to display the current system date and time.

## ls
   - It is used to display the files and directories present in the current directory.

## ls -l
   - It is used to display files and directories in a detailed (long listing) format.
   - Output: Shows file permissions, number of links, owner, group, file size, modification date, and file name.

## ls -a
   - It is used to display all files and directories, including hidden files (those starting with .).
   - . means Hidden files;
   - Output: Shows all files and folders, including hidden files like .bashrc and .profile.

## ls -la
   - It is used to display all files and directories, including hidden files, in a detailed (long listing) format.
   - Output: Shows file permissions, owner, group, size, modification date, and file name for all files and directories, including hidden ones.

## clear
   - clear is used to clear the terminal screen and remove previously displayed commands and output.
   - 💡 Tip: The shortcut Ctrl + L performs the same action as the clear command in most Linux terminals.

## mkdir
   - It is used to is used to create a new directory (folder) in Linux.
   - mkdir foldername

## pwd
   - (Print Working Directory) is used to display the full path of the current directory.
   - /home/anshika/Documents ( This shows the current directory where you are working.)

## touch
   - It is used to create a new empty file or update the timestamp of an existing file.
   - Example: touch notes.txt
   - Output: Creates an empty file named notes.txt if it does not already exist.
   - Note: If the file already exists, touch updates its last modified timestamp instead of creating a new file.

## echo
   - echo is used to display text or variables on the terminal.
   - Syntax: ```echo "text"```
   - Example: ```echo "Hello Linux"```
   - Output: Hello Linux
   - 💡 Tip: You can also use echo to write text into a file:
   - ```echo "Hello World" > file.txt```
   - This creates (or overwrites) file.txt with the text Hello World.

## cat 
   - cat (Concatenate) is used to display, create, and combine the contents of files.
   - Syntax: ```cat filename```
   - Example: ```cat notes.txt```
   - Output: This is my Linux notes file
   - 💡 Common Uses:
        - Display file content:
        - ```cat file.txt```
        - Create a file: ```cat > file.txt```
        - Combine files: ```cat file1.txt file2.txt```

## cd 
   - cd (Change Directory) is used to navigate from one directory to another in Linux.
   - Syntax: ```cd directory_name```
   - Example: ```cd Documents```
   - Output: Changes the current working directory to Documents
   - 💡 Common Uses:
        - Go to a specific directory:  ```cd Downloads```
        - Go back one directory:  ```cd ..```
        - Go to the home directory:  ```cd ~```
        - Go to the previous directory:  ```cd -```

## mv
   - mv is used to move a file or directory from one location to another, or to rename it.
   - Syntax: ```mv source destination```
   - Example: ```mv file.txt Documents/```
   - Output: Moves file.txt to the Documents directory.
   - Rename Example: ```mv oldfile.txt newfile.txt```
   - Output: Renames oldfile.txt to newfile.txt.


## rm
   - (Remove) is used to delete files and directories in Linux.
   - Syntax: ```rm filename```
   - Example: ```rm file.txt```
   - Output: Deletes the file file.txt
   - 💡 Common Uses:
        - Delete a file: ```rm notes.txt```
        - Delete multiple files: ```rm file1.txt file2.txt```
        - Delete an empty directory:  ```rm -d myfolder or rmdir```
        - Delete a directory and its contents: ```rm -r myfolder```
        - Force delete without confirmation:  ```rm -f file.txt```
        - ⚠️ Warning: rm permanently deletes files. There is no recycle bin/trash by default.

## cp
   - cp (Copy) is used to copy files and directories from one location to another.
   - Syntax: ```cp source destination```
   - Example: ```cp file.txt backup.txt```
   - Output: Creates a copy of file.txt named backup.txt
   - 💡 Common Uses:
        - Copy a file:  ```cp file.txt Documents/```
        - Copy multiple files:  ```cp file1.txt file2.txt Documents/```
        - Copy a directory:  ```cp -r myfolder Backup/```
        - Note: ```-r ```(recursive) is required when copying directories.

## wc
   - wc (Word Count) is used to count the number of lines, words, and characters in a file.
   - Syntax: ```wc filename```
   - Example: ```wc notes.txt```
   - Output: 5 20 120 notes.txt
        - This means: 5 → Lines, 20 → Words, 120 → Characters
   - 💡 Common Uses:
        - Count lines only:  ```wc -l notes.txt```
        - Count words only:  ```wc -w notes.txt```  `  
        - Count characters only:  ```wc -c notes.txt```

## cut -b
   - It is used to extract specific bytes (characters) from each line of a file or text.
   - Syntax: ```cut -b position filename```
   - Example: "Extract first character" ```echo "Linux" | cut -b 1```
   - Output: L
   - "Extract first 3 characters" ```echo "Linux" | cut -b 1-3```
   - Output: Lin
   - "Extract specific characters" ```echo "Linux" | cut -b 2,4```
   - Output: iu (2nd and 4th characters)
   - Extract from a file
   - Suppose names.txt contains: Anshika Rahul Priya
   - Command: ```cut -b 1-3 names.txt```
   - Output: Ans Rah Pri
   - ```cut -b``` extracts specific bytes (characters) from each line of a file or text.

## tee
   - It is used to display output on the terminal and save it to a file at the same time.
   - Syntax: ```command | tee filename```
   - Example: "Extract first character" ```echo "Hello Linux" | tee file.txt```
   - Output: Hello Linux
   - Saved in file.txt: Hello Linux
   - Example 2: Save Command Output ```ls | tee files.txt```
   - This:
        - Displays the list of files on the screen
        - Saves the same output to files.txt
   - Append to a File -> Use -a option: ```echo "New Line" | tee -a file.txt```
        - This adds content to the end of the file instead of overwriting it.

## sort
   - sort is used to arrange lines of text in alphabetical or numerical order.
   - Syntax: ```sort filename```
   - Example: Alphabetical Sorting
       - Suppose names.txt contains:
          - Rahul
          - Anshika
          - Priya
   - Command: ```sort names.txt```
   - Output: Anshika
             Priya
             Rahul 
  - | Command | Purpose |
    |---------|---------|
    | `sort file.txt` | Sort alphabetically |
    | `sort -n file.txt` | Sort numerically |
    | `sort -r file.txt` | Reverse order |
    | `sort -u file.txt` | Remove duplicate lines |


## diff
   - Compares two files line by line and shows the differences.
   - Syntax: ```diff [options] file1 file2```
   - Example: ```diff file1.txt file2.txt```
   - Sample Output Meaning: ```2c2
                           < Hello
                             ---
                           > Hello World
                             - ```
   - ```2c2``` → line 2 changed
   - ```<``` → content from first file
   - ```>``` → content from second file
   - Useful Options:
        - ```-u``` → unified format (easy to read)
        - ```-i``` → ignore case differences
        - ```-w``` → ignore whitespace


## vi or vim
   - A terminal-based text editor used to create and edit files in Linux.
   - Syntax: ```vi file_name``` or ```vim file_name```
   - Example: ```vi notes.txt```
   - Basic Modes:
       - Normal Mode → Default mode (navigation, commands)
       - Insert Mode → Type/edit text (```press i```)
       - Command Mode → ```Save/quit``` (press Esc then use commands)
   - Common Commands:
       - ```i``` → Enter insert mode
       - ```Esc``` → Back to normal mode
       - ```:w``` → Save file
       - ```:q``` → Quit
       - ```:wq``` → Save and quit
       - ```:q!``` → Quit without saving

## df
   - Shows disk space usage of file systems (used, available, and total space).
   - Syntax: ```df [options] [file_system]```
   - Example: ```df -h```
   - Sample Output (simplified):
         ```Filesystem      Size  Used  Avail  Use%  Mounted on
              /dev/sda1        50G   20G   28G    42%   / ```
   - Useful Options:
       - ```-h``` → Human-readable format (KB, MB, GB) ✅
       - ```-T``` → Display file system type
       - ```-a``` → Show all file systems


## less
   - Displays file content one screen at a time (scrollable viewer).
   - Syntax: ```less file_name```
   - Example: ```less log.txt```
   - Basic Navigation:
        - ```↑ / ↓``` → Move line by line
        - ```Space``` → Next page
        - ```b``` → Previous page
        - ```/text``` → Search for text
        - ```q``` → Quit
   - Useful Options:
       - ```-N``` → Show line numbers
       - ```-i``` → Ignore case in search
   - less = view large files easily with scrolling and search

## more
   - Displays file content one screen at a time (scrollable viewer).
   - Syntax: ```less file_name```
   - Example: ```less log.txt```
   - Basic Navigation:
        - ```↑ / ↓``` → Move line by line
        - ```Space``` → Next page
        - ```b``` → Previous page
        - ```/text``` → Search for text
        - ```q``` → Quit
   - Useful Options:
       - ```-N``` → Show line numbers
       - ```-i``` → Ignore case in search
   - less = view large files easily with scrolling and search

## zcat
   - Displays the contents of a compressed .gz file without extracting it.
   - Syntax: ```zcat file_name.gz```
   - Example: ```zcat logs.gz```
   - How It Works:
        - Reads .gz (gzip) compressed files
        - Outputs content directly to terminal

## tail
   - Displays the last part (end) of a file.
   - Syntax: ```tail [options] file_name```
   - Example: ```tail log.txt```
   - Sample Output (last 10 lines by default): line 91 t0 100
   - Useful Options:
        - ```-n 5``` → Show last 5 lines -> ```tail -n 5 log.txt```
        - ```-f``` → Follow file in real-time (useful for logs) -> ```tail -f log.txt```

## head
   - Displays the first part (beginning) of a file.
   - Syntax: ```head [options] file_name```
   - Example: ```head file.txt```
   - Sample Output (first 10 lines by default): line 1 t0 10
   - Useful Options:
        - ```-n 5``` → Show first 5 lines -> ```head -n 5 log.txt```

## softlink
   - A soft link is a shortcut (reference) to another file or directory.
   - Syntax: ```ln -s target_file link_name```
   - Example: ```ln -s file.txt shortcut.txt``` -> ```shortcut.txt``` now points to ```file.txt```
   - Key Points:
        - Works like a shortcut 
        - Can link across different file systems
        - If original file is deleted → link becomes broken
   - Check Soft Link: ```ls -l```
   - Output shows -> indicating link: ```shortcut.txt -> file.txt```

## hardlink

ssh

top

q

ps

fuser

kill

free

nohup

head -n

vmstat

vmstat -a




   
  



