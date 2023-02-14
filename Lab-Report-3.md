# Lab Report 3
### Luke Henry
***

The `grep` command can be used to search for lines containing a pattern, such as a string like "Italy", in a file. 

Using the command `grep --help` in Windows, or `man grep` on other operating systems, I found the following options that modify the function of the `grep` command:

- `-c` - for **count**
- `-i` - for **ignore case**
- `-r` - for **recursive**
- `-o` - for **only matching**

*** 
 
The command `grep -c`, for **count**, returns only the number of lines in a file containing a given patter. 

For example, to get only the number of lines containing the string `"Italy"` in the file `./written_2/travel_guides/berlitz1/WhereToItaly.txt`, you could run the command `grep -c "Italy" ./written_2/travel_guides/berlitz1/WhereToItaly.txt`. This command returns only the number `78`, so there are 78 lines containing the string `"Italy"`.

To get the number of lines containing `"Napoleon"` in `./written_2/travel_guides/berlitz1/HistoryFrance.txt`, you can run the command `grep -c "Napoleon" ./written_2/travel_guides/berlitz1/HistoryFrance.txt`. This command returns the number 9, so there are 9 lines containing the string `"Napoleon"`.

***

The command `grep -i`, for **ignore case**, returns the lines in a file containing a given pattern, regardless of case.

For example, if you wanted to find the lines containing the strings `"the"`, `"The"`, `"THE"`, or any other capitalization of the word "the", in the file `./written_2/travel_guides/berlitz2/Cuba-History.txt`, then using `grep "the"` will not work because it will not count lines containing `"The"` but not `"the"`. Using the command `grep -i "the" ./written_2/travel_guides/berlitz2/Cuba-History.txt' will return all of the lines with any capitalization of the word.

To find the number of lines containing the word "as" in `./written_2/non-fiction/OUP/Fletcher/ch1.txt`, you could use the command `grep -c -i "as" ./written_2/non-fiction/OUP/Fletcher/ch1.txt`. `-c` returns only the number of lines, and `-i` searches regardless of capitalization, for the strings:
- `"AS"`
- `As"`
- `"aS"`
- and `"as"`.

The command returns the number 59, so there are 59 lines with the word "as" in any case. 

***

The command `grep -r`, for **recursive**, returns the lines containing a given pattern in every file inside a given directory. The command searches through all files in a directory for the pattern. 

For example, to get all lines in `./written_2` containing the string `"Cuba"`, you could use the command `grep -r "Cuba" ./written_2`. This returns a list of lines for each file in `./written_2` and in all of its directories containing the string `"Cuba"`. 

If you want to find the number of lines in each file in `./written_2/travel_guides` containing the word `"vacation", not case sensitive, you can use the command `grep -c -i -r "vacation" ./written_2/travel_guides`. This command returns a list containing every file in `./written_2/travel_guides` and in its directories with a count of how many lines contain the non-case sensitive word "vacation".

***

The commmand `grep -o`, for **only matching**, returns only the parts of a file that contain the given pattern. It can be used to search for specific words or phrases so that even if they occur multiple times on the same line, they are still counted for each time they appear. 

For example, the command `grep -o "Nepal" ./written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt` returns a list containg the word "Nepal" several times. This is because the command is returning only the parts of the file that match the string `"Nepal"`. To count how many times the string `"Nepal"` is in the file `./written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt`, you can use the command `grep -c -o "Nepal" ./written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt`. his command returns the number 24. So the string `"Nepal"` occurs 24 times in the file. This is different than the command without the `-o` because that would only show the number of lines containing the string, which is different if the string occurs multiple times in the same line. 

You could count how many times each file in `./written_2` contains the word "government", not case sensisitive in case it is at the start of a sentence, by using the command `grep -c -r -o -i "government" ./written_2`. This returns a list of all files in any directories of `./written_2` with a count of how many times the files contains the word "government", as a string in any case.
