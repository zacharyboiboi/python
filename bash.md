# DAY 1: BASH
  
  ### Bash information:
    ```
    -Bash stands for Bourne Again.
    -Unix shell to interact with operating system.
    -Bash widely used on linux
    -command line environment for excuting scripting tasks.
    -supports job control, command-line editing, and command history
    -writenn similar 
    
   #### Linux Command and Switches:
        
        ```
        history:
        !<his number> to reference command 
        history | egrep <command> <---------searcheshistory when used command
        ```
        
  **reverse i search in bash ctrl + r  and type char**
        
        
        
   **ctrl + a takes you to beganning of command** 
   
   
   
   ### Getting help man:
   ```
   
   -man bash bash man page
   -man find opens man page for finf command 
   -G end of page
   -g start of man page
   -/pattern search forward for (N-th) matching line
   -&pattern Seach backward for (N-th) matching line
   n or shift+n moves between search results 
   b to go up
   q    Quit man
   
   ```
   
   ### Online resources:
   
      
      
   Additional Links for Research:
    ```
    -https://linux.die.net/man - Online Man Pages. (Search wget as example)
    -https://serverfault.com - Question and Answer site. May help you get command suggestions if you know what you’re trying to do. (Search "linux history"      or "user input" as examples)
    -https://ss64.com/bash - Breaks down options and has examples at the bottom usually. (Show "apt-get" as example)
    -https://stackoverflow.com - Good resource when using Google for specific syntax questions. Utilize carefully because an answer you find may not answer      YOUR question. (Search "grep" as example)
    -https://tldp.org/LDP/abs/html/index.html - In depth explanations and good examples. (Show "Special Characters" and "Loops" as examples)
    -http://bit.ly/USACYSscripting - Google Drive which includes helpful examples. (Show AWK)
    -https://www.gnu.org/software/bash/manual/ - For advanced students who want to know how BASH works in the background.
    -https://linuxize.com/post/bash-if-else-statement/ - Good examples of if/else statements.
    -https://google.com - Make Google work FOR you by asking the right questions. (Google "How to take user input with Bash" as example)

 (edited) 

    
   ### Order of Evalution: The order the computer finds a command 
    ```
    1.Redirection <- file need to create file so it happens first
          > output writes to new file
          >> append end of file
          stad in     stad out      stad err
          STDIN       STDOUT         STDERR
          keyboard    monitor        on how code works 
                    |   bof on monitor -------------->
          send STDERR to dev null if dont want to troubleshoot   
          
          
    2.Alias  
    
    alias cat='echo "Nothing to see here"' is example of using alias command unalias to redo it which to find path of command 
        use type tells type of command if alias type -a goes further alias if first the nfunction then binary 
        
        unalias <alias>
        unset <function> <- function
        now the uinset function is a bin 
    
    3.Parameter expansion, comand substitution, arthimetic expansion, and quote removal.
        touch creates file
        touch <file> or touch file file file 
            brace expansion uses {}
            
     **touch file{1..100}**
     **rm file*** <-- globbing**
      rm * removes everything in directory
      
      
    **4.shell function**
    
    5.built -in commands
        built in commmand dont have man pages use help <command>
        
    6.hash tables
        cache 
        
    7.pth variable
        echo $PATH is the  seperated by colon helps speed up computers
        hash command shows cache for command hash table
        sudo rm /bin/<command>
        if run that command it doesnt exist 
        hash -r clears hash table 
        hash = no hash
        
    8.error (eg command not found)
        if this happens command not found 
   
   
    
    
   ### Command chaining operators: <_--- part of number 3 
        ```
        sleep 5 & <-- sleep for five  secrond in the background 
        ; <----
        command;command; runs sequnce if works in session
         ls;cat file STDIO one command STDERR other 
         can use this to get output of multiple command 
         
  &   --Sends process to background (so we can run multiple process parallel) \
  ;   --Run multiple commands in one run, sequentially.\
  \  --To type larger command in multiple lines\
  &&  --Logical AND operator <-- run if first runs properly FIRST HAS TO WORK\
  ||  --Logical OR operator <--- cmd1 || cmd2 || cmd3 cmd2 will only run will cmd1 fails \
  !   --NOT operator\
  |   -- PIPE operator\
  {}  --Command combination operator.\
    [ -f 99.txt ] || { echo " does not exist"; touch 99.txt; }\
  ()  --Precedence operator\



   ### File System and Manipulation:
   
    Absolute   /root is admin / top of file system 
    relative   if cd .. cd //
    pwd shows where your at 
    cd /home cd/home/student $HOME
    cd / root of file system
    cd ~ back to home 
    cd $HOME home directory
    ./ relative file path reference 
    cd byitself takes you home
    cd - toggle between last to locations 
        ```
          - Absolute, Home, and Relative File reference
          
            home dir      ~/ or $HOME
            ab path       /etc/passwd
            relv path     ./ or ..
            
            filesystem cmds
            touch       touch -t [[CC]YY]MMDDhhmm[.ss]
            mkdir       mkdir -p
            rm          rm -rf
            rmdir       rmdir -p
            ls          ls
            cd          cd -
            
            links 
            
            sysmbolic link    A shoprtcut or pointer
            hard link     Persistent, cannot cross file systems
            
            
            .<file> hidden file
            ls -a to look at hidden files
              
          ```
        curl equilivant of cat 
          
          
**curl cht.sh/grep** <--- bettre man page for grep can be used on any command SHOW EXAMPLES

**explianshell.com** explains the command   



 ###  Processes and Memory:
    Process Hierarchy
      kernel
        Init - 01
            BASH
               ps 
          process snapshot
            - ps -elf 
          terminating:
              -kill    kill -9 1234
              -killall  killall firefox 
              
              
              
  ### Cat More || Less
        cat(1) - conatenate files and print on the standard outut" -n line numbers
            head top 10 lines by default 
            tail last 10 lines default
            less parse easier 
            more 
               
        
   ### Finding Files and Dirs:
   
      Find(1) - search for files in a directory hierarchy" does recrusion by default
      -locate     looks for certain file */<file>*
      -whereis    like which but man page
      -which      file path
      -find       
      whatis      summary of what command does
      what do we use find for?
          Does it parse through the content or just files 
          Is it limited to just fikenames or what can it search by?
          
          
                find -iname ".conf" denotes case- insensitive file anything ending .conf
        
            find [LOCATION] [OPTIONS]
                  find /etc -iname "*.conf" 2>/dev/null
                  find /etc -iname "*.conf"  > /dev/null <-- displays errors to screen
                  
                 find -maxdepth <dirs deep> only a certain dic deep
                 file -type   f     only displays files
                 find -mtime 2    modified 2 days ago
                 
  **-mmim**               <-- find out difference of mmim and mtime 
                     
                     
                     
                     
                     
                     
                     
                 
   #### exec option:
    
                 
                 find $HOME/1123/?.txt -type f -exec cp "{}" $HOME/CUT \;
                
                 -exec based on what it founf execute aginst eahc item in my output
                 
                 
                 ls -l PATH/TO/DIRECTORY grep[OPTIONS]"pattern" {} ls {} grep pattern {}
                 
                 
                 
   # DAY 1 challenges:
   
  ## q1.Activity: Using Brace-Expansion, create the following directories within the $HOME directory:

    1123
    1134
    1145
    1156

      mkdir $HOME/{1123,1134,1145,1156}
  ## q2.Use Brace-Expansion to create the following files within the $HOME/1123 directory. You may need to create the $HOME/1123 directory. Make the following files, but utilze Brace Expansion to make all nine files with one touch command.

Files to create:

    1.txt
    2.txt
    3.txt
    4.txt
    5.txt
    6~.txt
    7~.txt
    8~.txt
    9~.txt

  
      touch $HOME/1123/{{1..5},{6~,7~,8~,9~}}.txt
      
      
  ## q3.Using the find command, list all files in $HOME/1123 that end in .txt.
  
  
  
      find $HOME/1123 -type f -name "*.txt"  ## q4.
      
      
  ## q4.List all files in $HOME/1123 that end in .txt. Omit the files containing a tilde (~) character.
  
  
  
      find $HOME/1123 -type f -name "*.txt" | grep -v "~"
      
      
  ## q5.Copy all files in the $HOME/1123 directory, that end in ".txt", and omit files containing a tilde "~" character, to directory $HOME/CUT.
  
  
      cp --copy-content $HOME/1123/{1..9}.txt $HOME/CUT
      
      
  ## q6.Using ONLY the find command, find all empty files/directories in directory /var and print out ONLY the filename (not absolute path), and the inode number, separated by newlines.
  
  Example Output

123 file1
456 file2
789 file3

  
  
      find /var/ -empty -type f,d -printf '%i %f\n'
      
  ## q7.Using ONLY the find command, find all files on the system with inode 4026532575 and print only the filename to the screen, not the absolute path to the file, separating each filename with a newline. Ensure unneeded output is not visible.
  
      find . -type f printf '%f\n' -inum 4026532575 2>/dev/null
      
  ## q8. 
                 
  # DAY 2:
  
    ###
                 
