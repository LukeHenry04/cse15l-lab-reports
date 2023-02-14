# Week 2 Lab Report
### Luke Henry
***

The `grep` command can be used to search for lines containing a pattern, such as a string like "Italy", in a file. 

Using the command `grep --help` in Windows, or `man grep` on other operating systems, I found the following options that modify the function of the `grep` command:

- `-c` - for **count**
- `-i` - for **ignore case**
- `-r` - for **recursive**
- `-o` - for **only matching**

*** 
 
The command `grep -c`, for count, returns only the number of lines in a file containing a given patter. 

For example, to get only the number of lines containing the string "Italy" in the file `./written_2/travel_guides/berlitz1/WhereToItaly.txt`, you could run the command `grep -c ./written_2/travel_guides/berlitz1/WhereToItaly.txt`. This command returns only the number `78`, so there are 78 lines containing the string "Italy".

To get the number of lines containing "Napoleon" in `./written_2/travel_guides/berlitz1/HistoryFrance.txt`, you can run the command ` grep -c "Napoleon" ./berlitz1/HistoryFrance.txt`. This command returns the number 9, so there are 9 lines containing the string "Napoleon".

***

The command `grep -i`, for ignore case, returns the lines in a file containing a given pattern, regardless of case.

For example, if you wanted to find the lines containing "the", "The", "THE", or any other capitalization of the word "the", in the file `./written_2/travel_guides/berlitz2/Cuba-History.txt`, then using `grep "the"` will not work because it will not count lines containing "The" but not "the". Using the command `grep -i "the" ./written_2/travel_guides/berlitz2/Cuba-History.txt' will return all of the lines. 

If y
