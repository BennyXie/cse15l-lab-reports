# Ways to Use "grep"
### All cited from https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/
The following is the content of /written_2.txt:
```
Benny is the best.
I could not resist his charisma.
Scientists are working on those theories to explain,
explain this always ongoing charisma.
BENNY, let's go!
```
1. grep -w  
    Sometimes, we just want to search the word "is" but not "resist", which contains the word "is".
    To do this, we use "-w".
    ```
    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)
    $ grep is written_2.txt 
    Benny is the best.
    I could not resist his charisma.
    Scientists are working on those theories to explain,
    explain this unlimited charisma.

    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)
    $ grep -w is written_2.txt
    Benny is the best.
    ```
    In this example, without "-w", there are so many lines containing "is"! With "-w", 
    our life is much easier, and there is only one output.
    ```
    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)
    $ grep the written_2.txt 
    Benny is the best.
    Scientists are working on those theories to explain,

    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)
    $ grep -w the written_2.txt 
    Benny is the best.
    ```
    In this example, grep included "theories" because it contains "the",
    but in the second example, "theories" is not included.
2. grep -i  
    Adding "-i" allows us to ignore case.
    ```
    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)
    $ grep benny written_2.txt

    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)
    $ grep -i benny written_2.txt 
    Benny is the best.
    GO BENNY!
    ```
    When we search "benny", there is no match, sadly, because the case does not match.
    After we add "-i", it ignores case, and thus we gets all the "Benny"s.
    ```
    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)
    $ grep GO written_2.txt 

    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)
    $ grep -i GO written_2.txt 
    explain this always ongoing charisma.
    BENNY, let's go!
    ```
    We got nothing from search "GO", but when we add "-i", all the go's appeared.  
3. grep -E  
    What if we want to search two words at the same time?
    ```
    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)
    $ grep -E "Benny|go" written_2.txt 
    Benny is the best.
    explain this always ongoing charisma.
    BENNY, let's go!
    ```
    We got every line that contains either "Benny" or "go".
    ```
    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)
    $ grep -E "resist|not" written_2.txt
    I could not resist his charisma.
    ```
    Although "resist" and "not" all appeared in this line, it only apppears once. So be aware!
4. grep -c  
    What if we want to know in how many lines did a word appear in this file?
    ```
    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)   
    $ grep -c the written_2.txt 
    2
    ```
    There are two "the" on line 1 and 3 (in theories).
    ```
    Tian@PizzaHut MINGW64 ~/GitHub_Workspace/cse15l-lab-reports (main)   
    $ grep -c "is" written_2.txt
    4
    ```
    Take heed of this! "-E" does not count the total times of appearance, but only the lines, 
    so here, only 4 lines contain "is", while there are actually 5 "is".
