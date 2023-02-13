## Week 5 Lab Report
**Sujana Sreenivasan**

This report will cover four different command line operations with the command `grep`. Each command will be demonstrated through two examples, and the online source where I found each operation will be linked at the top of its section.

### Command Line Operations With `grep`

1. `--color` | [Source](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)

Example 1:

```
grep --color "vista" ./written_2/travel_guides/berlitz1/*.txt
```

Output:

![image1](./Screen%20Shot%202023-02-12%20at%204.43.45%20PM.png)

The `--color` command operates like a standard `grep` command, however highlights the specific text that we are searching for in a different color in the command line output. This is very useful for when you are searching through a large number of files because it makes the particular text easier to see within the file. In the first example, there are a lot of files that contain the word "vista", so it's convenient to have it colored in red so as to distinguish between the files.

Example 2:

```
grep --color "Lucayans" ./written_2/travel_guides/berlitz1/*.txt
```

Output:
![image2](./Screen%20Shot%202023-02-12%20at%204.44.23%20PM.png)

I think this second example really illustrates the effectiveness of the `--color` command, because it makes our search result "Lucayans" stand out in red inside larger paragraphs. This makes it much easier to search through files for specific text.


2. `grep -v` | [Source](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)

Example 1:

```
grep -v "o" ./written_2/travel_guides/berlitz1/HandRHawaii.txt 
       
        Hyatt Regency Waikiki $$$–$$$$ 2424 Kalakaua Avenue,
        Kahala Mandarin Oriental Hawaii $$$$ 5000 Kahala Avenue,
        Maui
        Ohana Maui Islander $$ 660 Wainee Street, Lahaina, HI
        Kauai
        Lanai
```

This is an example of the `-v` option for `grep`, which provides an inverse output to the standard `grep` command. So, rather than return all the lines that contain the specific text, this command returns all the lines that do not contain that text, which is useful when you want to avoid a certain piece of text in your files. This command presents a unique way of searching through files by serving the opposite purpose as the typical `grep` command. For this example, I wanted to find which lines do not contain the lowercase letter "o" in the file HandRHawaii.txt, and this is the output I got. Notice that this still includes any appearances of uppercase "O" - `grep` is by default a case-sensitive command.

Example 2:

```
grep -v "a" ./written_2/travel_guides/berlitz1/HandRHawaii.txt
      
        410 rooms.
        rooms.
        402 rooms.
        <www.outrigger.com>. This 17-story tower, perched on one of the
        66 rooms.
        pools. 806 rooms.
        rooms.
        (808) 879-8763; <www.westin.com>. The most southwesterly of
        immense koi pools. 310 rooms.
        rooms.
        grounds. 1,240 rooms.
        350 rooms.
        with dozens of turtles. 545 rooms.
        60 rooms.
```

This second example does the same thing as the first, but instead of returning the lines that don't contain "o", it returns the files that don't contain the lowercase letter "a". The above output is what I got when running this command.


3. `-c` | [Source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

Example 1:

```
grep -c "travel" ./written_2/travel_guides/berlitz1/WhereToMadeira.txt
2
```

The `-c` option for `grep` returns the number of lines that contain the text fragment rather than the lines themselves. This is very convenient if you are just looking for files or specific parts of files that contain the specified text, and provides a cleaner result than the typical text output of a standard `grep` command. In the first example, I used `grep -c` to see how many lines contained the word "travel" in the file WhereToMadeira.txt, which gave me an easy-to-read answer of 2 lines.

Example 2:

```
grep -c "travel" ./written_2/non-fiction/OUP/Abernathy/*.txt
./written_2/non-fiction/OUP/Abernathy/ch1.txt:0
./written_2/non-fiction/OUP/Abernathy/ch14.txt:0
./written_2/non-fiction/OUP/Abernathy/ch15.txt:0
./written_2/non-fiction/OUP/Abernathy/ch2.txt:3
./written_2/non-fiction/OUP/Abernathy/ch3.txt:0
./written_2/non-fiction/OUP/Abernathy/ch6.txt:0
./written_2/non-fiction/OUP/Abernathy/ch7.txt:0
./written_2/non-fiction/OUP/Abernathy/ch8.txt:0
./written_2/non-fiction/OUP/Abernathy/ch9.txt:0
```

In this second example, I run the command on all the .txt files in the Abernathy directory. This format gives me a unique output in that I am able to see the number of lines in which "travel" appears for each file in the directory. This command thus provides an effective way to search for a specific piece of text in a directory, by giving a nice output of the number of lines containing the text in each file.


4. `-i` | [Source](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

Example 1:

```
grep -i "where" ./written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
        Where to go
        wherever you go, the essence of a Los Angeles vacation is experiencing
        real attraction is the exterior courtyard, where autographs,
        Blvd. ), where hi-tech interactive exhibits reveal the history of the
        satin bras and panties is their renowned “Lingerie Museum,” where you
        trade as the B-tank, where Moses parted the waters in The Ten
        Fairfax), where young tourists, local hipsters, and fashionable freaks
        museum also features a fishbowl laboratory where visitors can see
        Hip gives way to chic at Doheny Drive, where the Strip ends
        as Rodeo Drive (pronounced Ro-DAY-oh), where top designers showcase
        renowned, however, as the setting where Julia Roberts’ and Richard
        elsewhere. Of particular note are the interactive video stations
        and gardens (701 Stone Canyon Road), where celebs often linger.
        Avenue, where celebrities living in the coastal enclaves come to shop
        at the vast man-made harbor of Marina del Rey, where harbor cruises and
        are several beach access points where you can still admire the rolling
        marsh, where you can see shorebirds such as the great blue heron and
        to this fantasy mall, where whimsical shops and fun, informal
        Pasadena is famous for the Rose Bowl stadium where, at
        three-dimensional cartoon world where children can explore Mickey
        (7711 Beach Boulevard, Buena Park), where film stars from the 1920s to
        Dinner and Tournament (7662 Beach Boulevard), where diners eat with
        frame. Don’t miss the chapel in the cathedral tower, where you’ll find
        slower, and dress is more casual. It’s the kind of place where the big
        decision of the day will be where you go for sunset cocktails. Life is
        in use in California, and the only remaining chapel where Father
```

Our final command here is the `-i` tag for `grep`. This option enables us to search case-insensitively for a particular piece of text in a file. This can be very useful when looking for all appearances of a particular word or phrase because the output returns all lines that contain this text, regardless of whether the text appears in lowercase, uppercase, or a combination of the two. In the first example, I wanted to find all appearances of the word "where" in the file WhereToLosAngeles.txt. By using the `-i` command, I am able to get an output of all lines that contain this word, and as can be seen from the output, this includes both uppercase and lowercase appearances.

Example 2:

```
grep -i -v "o" ./written_2/travel_guides/berlitz1/HandRHawaii.txt  
      
        Hyatt Regency Waikiki $$$–$$$$ 2424 Kalakaua Avenue,
        Maui
        Kauai
        Lanai
```

For this second example of using `-i`, I wanted to revisit a previous example in which we used a different command. Remember how `grep` searches case-sensitively by default, and as a result, we got an output that included appearances of capital "O" when we used `grep -v` on the file HandRHawaii.txt. In this example, we see how using the `-i` tag returns lines that do not contain the letter "o" in any form. This example also shows that `grep` commands can be layered with each other to obtain a specific functionality, which can make searching through files and directories very efficient.

### The End
