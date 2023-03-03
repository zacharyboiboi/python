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
          
          
**curl cht.sh/grep** <--- better man page for grep can be used on any command SHOW EXAMPLES

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
    
                 
                 
                
                 -exec based on what it founf execute aginst eahc item in my output
                 
                 
                 ls -l PATH/TO/DIRECTORY grep[OPTIONS]"pattern" {} ls {} grep pattern {}
                 
                 
                 
   # DAY 1 challenges:
   
  ## q1.Activity: Using Brace-Expansion, create the following directories within the $HOME directory:

    1123
    1134
    1145
    1156

      **mkdir $HOME/{1123,1134,1145,1156}** <--- create 4 directories using brace expansion within home directory
   or   mkdir $HOME/11{23,34,45,56}   
         Brace expansion is a mechanism by which arbitrary strings may be generated, for commands that will take multiple arguements. For the below examples, the first example is equivalent to the second command. 
         
         brace expansion uses {}
      
      
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
                        or
      touch $HOME/1123/{1..5}.txt $HOME/1123/{6..9}~.txt <------ can uses multiple arguements with spaces note the ~.txt as a good way to get it done.
      
      we leanred can use brace expnasion to crate files a nd directories 
      
      
  ## q3.Using the find command, list all files in $HOME/1123 that end in .txt.
  
  
  
      find $HOME/1123 -type f -name "*.txt"   <------ encrouages to uses double quotes to prevent uninteded results 
      find /PATH/LOCATION/ [BOOLEAN] [OPTIONS]
      find $HOME/1123 -iname "*.txt" <-- case insensitive 
      find $HOME/1123/*.txt <-- shortesst form
      
  ## q4.List all files in $HOME/1123 that end in .txt. Omit the files containing a tilde (~) character.
  
  
  
      find $HOME/1123 -type f -name "*.txt" | grep -v "~" <--- Omit means not show so all txt fils without ~  
      find $HOME/1123 -iname "*.txt" | egrep -v "~"      <---- egrep grep -v meansnot usually ends with filename butsince | can uses jus t~
      find $HOME/1123 -iname "*.txt" ! -iname "*~*"       <---- the booleans operator left of the options only effects option inforn of it 
      find $HOME/1123 -iname "*[^~].txt"                  <----- regex way not tiddla
      find $HOME/1123 -type f \(-iname "*.txt" ! -iname "*~*" \) <-- more regex
      find $HOME/1123 -type f -iname '[0-9].txt'          <--- more regex 
      find $HOME/1123/*.txt ! -iname "*~*"
      | passes the output of one command and passes it into the net command 
      
      
  ## q5.Copy all files in the $HOME/1123 directory, that end in ".txt", and omit files containing a tilde "~" character, to directory $HOME/CUT.
  
  
      cp --copy-content $HOME/1123/{1..9}.txt $HOME/CUT        **or**         find $HOME/1123/?.txt -type f -exec cp "{}" $HOME/CUT \;
          
          use middle mouse button on terminal to copy and paste 
          find LOCATION OPTIONS -exec COMMAND {}
          **find $HOME/1123 -iname "*[^~].txt" -exec cp {} $HOME.CUT \;**
              cp $HOME/1123/*[^~].txt $HOME/CUT
          
          grep pattern filename  <------- thought process
          -exec grep pattern {} \; <----exec is kinda like pipe grabs output of first command and executes it it second command the src file for cp to CUT
          cp scr_file dst_file
          -exec cp {} $HOME/CUT \;
          haf to create $HOME/CUT
      
      
  ## q6.Using ONLY the find command, find all empty files/directories in directory /var and print out ONLY the filename (not absolute path), and the inode number, separated by newlines.
  
  Example Output

123 file1 \
456 file2 \
789 file3 \
  
      **find /var/ -empty -type f,d -printf '%i %f\n'**    <---return all empty files in /var using prescribed formate(inode filename\n) no absolute path"
      
      
     Process:
     
      difference between zero size file and empty file 
      find /var 
      find /var 2>/dev/null
      find /var 2>/dev/null | head 
      find /var 
      man find | egrep "empty" or man find | egrep "^\s+\-(type|name|exec)\s" 
      egrep = grep -E 
      egrep -B1  "root|student" /etc/passwd
      curl cht.sh/find | egrep "printf"
      find /var -empty -printf '%f\n' 2>/dev/null | head
      man find | egrep "indoe"
      find /var -empty -printf 'Inode: %i  File: %f\n' 2>/dev/null | head
      
      
      
  ## q7.Using ONLY the find command, find all files on the system with inode 4026532575 and print only the filename to the screen, not the absolute path to the file, separating each filename with a newline. Ensure unneeded output is not visible.
  
      find . -type f printf '%f\n' -inum 4026532575 2>/dev/null
      
      find / -inum 999 -printf '%f\n' 2>/dev/null | head 
      
      this chanllege find all files across system for spefic inode prit filename with newline used man find | egrep inode number 
      use hitsory to see step by step proecess of execution
      
      
      
  ## q8. Using only the ls -l and cut Commands, write a BASH script that shows all filenames with extensions ie: 1.txt, etc., but no directories, in $HOME/CUT. Write those to a text file called names in $HOME/CUT directory. Omit the names filename from your output.
  
  
  
 ls -l $HOME/CUT | cut  -d. -f1- -s | cut -d: -f2| cut -d' ' -f2 > $HOME/CUT/names
    
    cut on open space last item .txt extensions or only extensions 
    -s suppress anyhting hwat dosnt match demands 
    -d is delimter can be anything 
    -f is fields can be range to infinity 
    
    
    
    
  # DAY 2: 
 ## Overview
    Condiontionals
    Command Substitution
    Commands
 
 ## Conditionals 
  Logical operators used in bash condiotional expressions 
    -e file exist
    -ffile exist and is a regular file
    -d file exist and is a directory
    == strings, is equal to strings
    -eq numbers, is equal to
    != strings, is NOT equal to
    
  The if condiotional expression helps automate the decision-making process during a program
  
  if [[condition]]; then
     command 
  elif [[ condition ]]; then
     command
  else 
     command
  fi 
  
  
  when to use (== vs.-eq) &(!= vs -ne)"
      if its letters use symbols ie == or !=
      if its numbers use letters ie -eq -ne
    
    
    
    
 ## Command Substitution
 
 
 echo todays is $(date)
 PROC =$(ps-elf)
 
 
 
 
 
 
 ## Commands
 **alias**
 ```
    alias
        -view all alias
    alaias vim ='nano'
        -creates alias vim for nano
    unalias vim
        -unalias vim so it no longer resolves as nano
    alias egrep='egrep -- color=auto'
        -best use of aliases to include common options of cmds
    \egrep  
        negate the alias to run egrep without 
        --color=auto option
     Rules/limits 
        -Aliases are NOT persistent by default.
        -Alias names CANNOT use / $ '' = or any of the shell metacharacters or quoting characters
    
   ``` 
    
    
    
    
 **sort**
 ```
 sort(1) - sort lines of text files 
    sort
       - sort content according to position on ASCII table
    sort -n
       -sorts content numerically
     sort -u
        -sort content uniquely
     sort -mn
         -sort content numerically reversed
     sort -t'+'
        -specify field seperator '+'
  ```  
 **uniq**
   ```
   uniq(1)-report or omit repeated lines
      
      uniq
         -select content uniquely, MUST ALREADY BE SORTED 
      uniq -c
         -select content uniquely with a count reading 
      uniq -u
          -Display only the unique lines (lines wihtout duplicates)
      uniq -d
          -Display only the duplicate lines (opposite of -u)
    
   ```
    
 **awk**
  ```
     awk(1) - pattern scanning and process language
          
          Syntax:
              awk [options] 'selection_criteria {action }' input-file > output-file 
                    awk -f: '{print $1}'
                          -displays 1st field delimited by a ":"
                    awk '{print $2}'
                          -displays 2nd field; delimited automatically by wite space.
                     awk -f: '($3 == 0) {print $1}' /etc/passwd
                          - collon on filed sepertor if third field equals zero print field 1 aka username 
   ```
  **sed**
  
  ```
      sed(1) - stream editor for filtering and transforming text"
          
            sed 's/abc/123/'
                -Replace FIRST  occurrence of abc in every line with 123
            sed 's/abc/123/g'
                -Replace EVERY occurrence of abc in every line with 123
            sed '/sus/d'
                -Delete the sus lines. Output everything else.
            sed -i '<expression>' file.txt
                 -"sed inplace" to make changes permament in file.txt
        
        IS NOT PERMAMENT UNLESS OUTUT TO A FILE 
        
        used for substituion can used anything / + usuall if substituion has slashes sed s/<pattern>/<change>/g' substitutes gloablly pattern wiht change           slash seperators can be different.
        
        egrep "student" /etc/passwd | sed 's/student/Longo/g;s@1001@1775@g' <-- multiple arguments 
        Longo:x:1775:1775::/home/Longo:/bin/bash
        
        can be used for deletion sed'/PATTERN/d'
        
        egrep "student|root" /etc/passwd 
        root:x:0:0:root:/root:/bin/bash
        student:x:1001:1001::/home/student:/bin/bash
        
        student@lin-ops:~$ egrep "student|root" /etc/passwd | sed '/root/d'
        student:x:1001:1001::/home/student:/bin/bash

        
        
  ```    
  
  
  #### demo time:
  ```
      alias:
          alias no spaces name=wantyour want
          aliases unless saved in bash rc are not permement
          alias is a shell built in   
          
     sort uniq: 
        cat abcs | sort | uniq -c | sort -r
        cat abcs | sort | uniq -c888
        file sort -k2n <--- sorts the second column numerically 
        sort -t',' -k2nr file | cut -d, -f2
  ```      
 ```     
      awk:
      
        egrep "root" /etc/passwd | awk -F: '{print $3,$1,$4}'
    0 root 0
    
    
    
         awk -F: '{print $1,$3,$4}' /etc/passwd | column -t 
          awk -F: '!/root/{print $1}' /etc/passwd
          date | awk '{print$2,$3,$6 of the year of the lorad}'
          date | awk '{print $NF}' <---- last one there is a way to count backwards 
          egrep "/bin/false|/bin/bash" /etc/passwd | awk -F: '{OFS=":"}($7="/bin/Bash"){print $1}'
          echo "Pyhton is better then bash" | awk '{print $NF,$2,$3,$4,$1}' <-- swicth las tand first to change output 
          echo "Pyhton is better then bash" | awk '{$1="BASH";$5="Python";print}' <------------ tranforming the string using awk with new variables semicolons can add MULTIPLES FIELDS WHNE TRANFORMING 
          
          
    declaing variables <variable>=<value> can then be used in awk by importing them
    
         SUBJECT=Leaders
         VERB=inspire
         OBJECT=people
          echo "cracker are fun" | awk -v ss==$SUBJECT -v vv=$VERB -v oo=$OBJECT '{$1=ss;$2=vv;$3=oo;print}'
          =Leaders inspire people
    ```    
    
    
    
    
   ```      
       
      sed:
             - sed 's/FINPATTERN/REPLACEPATTERN/g' 
             
             
        egrep 'student|root' /etc/passwd | sed 's/student/instructor/g'
    root:x:0:0:root:/root:/bin/bash
    instructor:x:1001:1001::/home/instructor:/bin/bash
        
        egrep "student|root" /etc/passwd | sed 's/ \/bin\/bash / \/bin\/btter /g'
        egrep "student|root" /etc/passwd | sed 's_/bin/bash_/bin/sus_g'
                                             sed expression
                                             
          egrep "student|root" /etc/passwd | sed 's+/bin/bash+/bin/sus+g;s*student*hackermna*g;s#1001#1331#g'                                   
                                             
             egrep "student|root" /etc/passwd | sed '/root/d' <---- deletion 
          student:x:1001:1001::/home/student:/bin/bash   
    ```   
          
  ### Activities 6-10
  
  
 ##### q6.Write a basic bash script that greps ONLY the IP addresses in the text file provided (named StoryHiddenIPs in the current directory); sort them             uniquely by number of times they appear. HIGH TO LOW 
      
      egrep -o "(\b25[0-5]|\b2[0-4][0-9]|\b[01]?[0-9][0-9]?)(\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)){3}" StoryHiddenIPs | sort | uniq -c | sort -r
      
      egrep -o only return match not whole line given IP sort them count them and reverse order 
          still confused on how to sort and use uniq 
       Regex.
           egrep "([0-9]{1,3}\.){3}[0-9]{1,3}" <file>
          
          
 ##### q7.Using ONLY the awk command, write a BASH one-liner script that extracts ONLY the names of all the system and user accounts that are not UIDs 0-3.Only display those that use /bin/bash as their default shell.The input file is named $HOME/passwd and is located in the current directory. Output the results to a file called $HOME/SED/names.txt
      
      awk -F: '($NF=="/bin/bash" && $3>3) {print $1}' $HOME/passwd > $HOME/SED/names.txt
        
        awk natrually serpates by a vraibel amount of space 
        
 ##### q8.Find all dmesg kernel messages that contain CPU or BIOS (uppercase) in the string, but not usable or reserved (case-insensitive)Print only the msg itself, omitting the bracketed numerical expressions ie: [1.132775]
  
  dmesg | egrep 'BIOS|CPU' | egrep -vi 'usable|reserved' | cut -d']' -f2-
          -i means case insensitive
          -v means get rid of lines what match 
      
      
 ##### q9. Write a Bash script using "Command Substitution" to replace all passwords, using openssl, from the file $HOME/PASS/shadow.txt with the MD5 encrypted password: Password1234, with salt: bad4u Output of this command should go to the screen/standard output. You are not limited to a particular command, however you must use openssl. Type man openssl passwd for more information.
 
 OPEN=$(openssl passwd -1 -salt bad4u Password1234)

awk -F: -v "vv=$OPEN" '{OFS=":"}{$2=vv; print$0}' $HOME/PASS/shadow.txt  <---- perfect example of variable substitution REPLACES Passwords
      second part of etc shadow 
      sudo cat /etc/shadow 

 command substitution 
      openssl <file> <hash> <salt <password> <---- syntax
      OFS retains colon seperator 
      using set can use spaces replace with colon
 
 
 ##### q10.Using ONLY sed, write all lines from $HOME/passwd into $HOME/PASS/passwd.txt that do not end with either /bin/sh or /bin/false.

sed '/\/bin\/false/d' '/\/bin\/sh/d' $HOME/passwd > $HOME/PASS/passwd.txt <--- can also use semi colons to pass multiple arguements 
           /d deletes and sends to file half to backslash bin/fasle and /bin/sh 

# Day 3:


## BASH Parameters (Variables):


      Parameter vs Variable:

      -In a bash context, a parameter is an entity that stores values.
      -Furthermore, a parameter can be a 
            name (varaible)
            number (positionbal parameter)
            special character (special parameter)
      -Therefore a variable is a parater denoted by a name 
            like man bash
            
 ##### BASH PARAMETERS (VARIABLES)
        
        Variables are parameters set with a name (identiier) on the left of an equal sign and a value (or nothing) on the right side.
        Variables are user defined.
        
     ** NOTE: There CANNOT be any spaces any spaces on either side of teh equal sign **
     
     **Special Parameters:**
          $#  = This parameter repersents the number of arguements passed to the shell script
          $0  = This parameter repersents the scrpt nmae
          $i  = this parameter repersents the ith argument passed to the shell script like s1,s2
          s*  = This parameter gives all arguements passed to the shell script seperated by space.
          $!  = This parameter gives PID of the last background running process
     *    $?  = parameter repersents how command was run 0 good it work 1 error it didnt work
     *    $$  = parameter repersents process id of current shell 
     *    $-  = parameter repersents current flag repersented in shell bash bourne etc 
          $@  = This parameter holds all arugemts apssed to the script and reat them as an array It is similar to the $* parameter
          
## Functions:
      Functions:
          -Allow breaking of code into more manageable blocks
          -series of command executed as if a single command
          -Can contain varaibles, loops, accept parameters, and return a value 
          -declare functions first, thne call it 
          -there are few different formats/styles for laying out a function
          -DEMO: function.sh
                 #!/bin/bash
  ```
  2 #function decalration thingy section
  3 function focus() {
  4  echo '"Your focus dtermines your reality." -Qui-Gon Jin'
  5 
  6 
  7 
  8 
  9 }
 10 
 11 hello() {
 12     echo '"hello" -Obi Wan Kenobi'
 13 
 14 }
 15 #invoke that function yo
 16 #focus
 17 
 18 
 19 function odd() {
 20     echo '"Never tell me the odds." -Han Solo'
 21 
 22 
 23 }
 24 hello
 25 odd
 26 
```
## Variable Substituion:
      -Ultimately, its just replacing a variable with its value.
      
 ```  1 #!/bin/bash
  2 
  3 sub1() {
  4     #simple variable substituion
  5     name="John"
  6     echo $name
  7 }
  8 
  9 sub2() {
 10     #variable subsitution within double quotes
 11     name="John"
 12     echo "My name isnt $name"
 13 }
 14 sub3() {
 15     #variable subsittution with single quotes
 16     name="zach"
 17     echo 'Your name is $name'
 18 }
 19 sub4() {
 20     #using curly braces t oseperate variable surroudning text
 21     name="john"
 22     echo "My name is $namenny5"
 23     echo "My name is ${name}nny5"
 24 }
 25 #invoke functions 
 26 #sub1
 27 #sub2
 28 #sub3
 29 #sub4
 30 
 31 sub5() {
 32     #use curly braces to substitute the value of a variable insdie parameter expansio    n
 33     name="John"
 34     echo ${name:0:2}
 35 }
 36 

 ```


### Activities 11-15:


##### q11.  Using find, find all files under the $HOME directory with a .bin extension ONLY.Once the file(s) and their path(s) have been found, remove the file Ensure there is no trailing / at the end of the directory path when outputting to standard output.You may need to sort the output depending on the command(s) you use. Have each path displayed only once.

      find $HOME -type f  -iname "*.bin" -printf '%h\n' 2>/dev/null | sort | uniq

##### q12.

##### q13.

##### q14.

##### q15.


#!/bin/bash
  2 #create a vraivble FILE assigning the value of arg1 (postional parameter 1)
  3 FILE=$1
  4 cat $FILE

echo "rah marine corps" > file1
  284  echo "rah Navy bois" > file2
  285  cat file1
  286  cat file1 file2
  287  vim scripty.sh && chmod +x scripty.sh
  288  ./scripty.sh  file1
  289  ./scripty.sh  file2
  
  
  
  $0 	The name of the script
$1 	The first argument to the script
$2 	The second argument to the script
$n 	The n-th argument to the script
$# 	The number of arguments to the script
$@ 	A list of all arguments to the script
$* 	A list of all arguments to the script
${#N} 	The length of the value of positional parameter N (Korn shell only)
  
  

