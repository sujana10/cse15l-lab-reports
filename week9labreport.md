### Week 9 Lab Report
**Sujana Sreenivasan**

For this lab report, I'm going to be exploring four different command line operations with the command `find`. Each command will be demonstrated through two examples, and the online source where I found each operation will be linked at the top of its section.

### Command Line Operations With `find`

1. `find ./ -name` | [Source](https://geekflare.com/linux-find-commands/)

Example 1:

```
find written_2/travel_guides/berlitz1 -name "Hand*"
```
Output:

```
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIsrael.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRMadrid.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRHawaii.txt
```
The `-name` option for `find` allows us to search for files and directories using a specific part of the file name, which is really helpful when you want to conduct a specific search without manually looking through the directory, perhaps. In this example, I want to find all the files that begin with "Hand" in the directory berlitz1, and using this command along with "Hand*" to represent the files provides the desired output.

Example 2:

```
find written_2/travel_guides/berlitz1 -name "*Israel*"
```
Output:

```
written_2/travel_guides/berlitz1/HistoryIsrael.txt
written_2/travel_guides/berlitz1/IntroIsrael.txt
written_2/travel_guides/berlitz1/WhatToIsrael.txt
written_2/travel_guides/berlitz1/WhereToIsrael.txt
written_2/travel_guides/berlitz1/HandRIsrael.txt
```
Here is another example of using the `-name` add-on. In this case, I wanted to find all files containing the word "Israel" in their title in the berlitz1 directory, and so I used the * symbol both preceding and following the key word when entering my command. This gave me the output I wanted, and shows just how useful the `-name` command can be. It allows for a really specific search within a directory to find files with a specific phrase in their title, and can help narrow down one's search greatly.

2. `find ./ -type` | [Source](https://geekflare.com/linux-find-commands/)

Example 1:

```
find written_2/travel_guides -type f -name "*z*" 

    written_2/travel_guides/berlitz1/IntroIbiza.txt
    written_2/travel_guides/berlitz1/WhatToIbiza.txt
    written_2/travel_guides/berlitz1/HandRIbiza.txt
    written_2/travel_guides/berlitz1/WhereToIbiza.txt
    written_2/travel_guides/berlitz1/HistoryIbiza.txt
    
```
The `-type` extension for `find` allows the user to specify if they want an output of just files or just directories. This is extremely useful for when you are searching for a specific file or directory that meets a certain condition, and you want to make your output more specific as well. In this example, I wanted to find all of the files in travel_guides that contained the letter "z", and got a clean output of just .txt files. Notice that this does not include any appearances of uppercase "Z" - `find` is by default a case-sensitive command.


Example 2:

```
find written_2/travel_guides -type d -name "*z*"

    written_2/travel_guides/berlitz1
    written_2/travel_guides/berlitz2
```
In this second example, I ran the same command, but instead used `-type d` so that I would instead get all of the directories within travel_guides containing the letter "z". This illustrates the convenience of this extension as it really narrows down one's `find` output based on user preference, which will make for a more effective perusal through a directory.

3. `find ./ -iname` | [Source](https://geekflare.com/linux-find-commands/)

Example 1:

```
find written_2/travel_guides -type f -iname "*ca*"

    written_2/travel_guides/berlitz1/HistoryJamaica.txt
    written_2/travel_guides/berlitz1/HandRJamaica.txt
    written_2/travel_guides/berlitz1/HistoryMallorca.txt
    written_2/travel_guides/berlitz1/HandRMallorca.txt
    written_2/travel_guides/berlitz1/WhereToMallorca.txt
    written_2/travel_guides/berlitz1/WhatToMallorca.txt
    written_2/travel_guides/berlitz1/IntroJamaica.txt
    written_2/travel_guides/berlitz1/WhatToJamaica.txt
    written_2/travel_guides/berlitz1/IntroMallorca.txt
    written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt
    written_2/travel_guides/berlitz2/California-WhereToGo.txt
    written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
    written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
    written_2/travel_guides/berlitz2/California-History.txt
    written_2/travel_guides/berlitz2/Cancun-History.txt
    written_2/travel_guides/berlitz2/CostaBlanca-History.txt
    written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt
    written_2/travel_guides/berlitz2/Canada-History.txt
    written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
    written_2/travel_guides/berlitz2/CanaryIslands-History.txt
    written_2/travel_guides/berlitz2/CanaryIslands-WhatToDo.txt
    written_2/travel_guides/berlitz2/California-WhatToDo.txt
    written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt
```
Our next command here is the `-iname` tag for `find`. This option enables us to search case-insensitively for some text in a file or directory title. This can be very useful when looking for all appearances of a particular word or phrase because the output returns all items that contain this text in its title, regardless of whether the text appears in lowercase, uppercase, or a combination of the two. In the first example, I wanted to find all appearances of the letters "ca" in the directory travel_guides. By using the `-iname` command with `find`, I am able to get an output of all file titles that contain this word, and as can be seen from the output, this includes both uppercase and lowercase appearances. Also, since I used `type -f` in my command, we get an output of only files, not directories.

Example 2:

```
find written_2 -type d -iname "*c*" 

    written_2/non-fiction
    written_2/non-fiction/OUP/Rybczynski
    written_2/non-fiction/OUP/Fletcher
    written_2/non-fiction/OUP/Castro
```
In this second example, I wanted to try something a little different. I ran the command `-iname *c*` using `-type d` to find all the directories in written_2 that contain the letter "c". As can be seen from the output, we got a result of directories that contain lowercase or uppercase "c". These examples also show that `find` commands can be strung together to obtain quite a specific functionality, which can make searching through directories very efficient for the user.

4. `find <cmd1> -o <cmd2>` | [Source](https://linuxhandbook.com/find-command-examples/)

Example 1:

```
find written_2 -name "*E*" -o -name "*P*"

    written_2/non-fiction/OUP
    written_2/non-fiction/OUP/Castro/chP.txt
    written_2/travel_guides/berlitz1/HistoryEgypt.txt
    written_2/travel_guides/berlitz1/IntroEdinburgh.txt
    written_2/travel_guides/berlitz1/WhereToEgypt.txt
    written_2/travel_guides/berlitz1/WhereToEdinburgh.txt
    written_2/travel_guides/berlitz1/WhatToEdinburgh.txt
    written_2/travel_guides/berlitz1/HistoryEdinburgh.txt
    written_2/travel_guides/berlitz1/IntroEgypt.txt
    written_2/travel_guides/berlitz1/WhatToEgypt.txt
    written_2/travel_guides/berlitz2/Portugal-History.txt
    written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
    written_2/travel_guides/berlitz2/Poland-WhatToDo.txt
    written_2/travel_guides/berlitz2/Paris-WhereToGo.txt
    written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
    written_2/travel_guides/berlitz2/PuertoRico-History.txt
    written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
    written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
    written_2/travel_guides/berlitz2/Poland-History.txt
    written_2/travel_guides/berlitz2/Paris-WhatToDo.txt
```
The final command we're discussing here is the `-o` option for `find`. It basically works as a logical OR operator and allows the user to include multiple conditions in their search when using `find`. In this example, I wanted to find all item titles that contained a capital "E" OR a capital "P" in the written_2 directory, and was able to get that in the output. This is helpful when you are conducting a less specific search for a file or directory and maybe want to check for different conditions. The `-o` tag greatly expands one's ability to conduct a search through a directory.

Example 2:

```
find written_2 -name "*ii*" -o -type d 

    written_2
    written_2/non-fiction
    written_2/non-fiction/OUP
    written_2/non-fiction/OUP/Berk
    written_2/non-fiction/OUP/Abernathy
    written_2/non-fiction/OUP/Rybczynski
    written_2/non-fiction/OUP/Kauffman
    written_2/non-fiction/OUP/Fletcher
    written_2/non-fiction/OUP/Castro
    written_2/travel_guides
    written_2/travel_guides/berlitz1
    written_2/travel_guides/berlitz1/WhatToHawaii.txt
    written_2/travel_guides/berlitz1/HistoryHawaii.txt
    written_2/travel_guides/berlitz1/WhereToHawaii.txt
    written_2/travel_guides/berlitz1/HandRHawaii.txt
    written_2/travel_guides/berlitz2
```
This `-o` option can also be used with two unrelated commands. In this second example, I wanted to get an output of all files and directories that contained the string "ii", as well as all directories within written_2. Though these two commands are pretty different from each other in terms of their outputs and functionality, our `-o` command allows us to string them together to conduct a really unique search. The different tags for the `find` command thus permit the user to find pretty useful combinations of files and directories when conducting a search, ultimately providing a truly unique functionality that can support many different forms of searches.
