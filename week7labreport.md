## Week 7 Lab Report

**Sujana Sreenivasan**

### CSE Labs Done Quick


#### Task 1. Delete existing forks of the repository

![delete](./Screen%20Shot%202023-02-23%20at%206.42.01%20PM.png)

I used the keys `<ctrl-R> r <enter>` to remove the lab7 repository from my local computer, and also deleted the repository from my Github account through my browser. This gave me the command `rm -rf ~/lab7` by autocompleting the most recent command I used which started with the letter "r".


#### Task 2. Fork the repository

![fork](./Screen%20Shot%202023-02-23%20at%206.52.27%20PM.png)

I forked the repository directly from Github in my web browser by pressing the "Fork" button in the top right corner. This added the repository to my personal Github account so I can now access its files and directories.

#### Task 3. Start the timer

![timer](Screen%20Shot%202023-02-23%20at%206.55.23%20PM.png)

I started a stopwatch from Google to keep track of how long each of the tasks would take me to do.

#### Task 4. Log into `ieng6`

![ieng6](Screen%20Shot%202023-02-23%20at%206.59.04%20PM.png)

Now we're actually getting into the lab tasks! I logged into my CSE 15l account on `ieng6` by pressing the keys `<up><up><up><up><up><up><enter>`, which gave me the `ssh <myaccount>@ieng6.ucsd.edu` command. This command was 6 up in my search history, so I used the up arrow to access and enter it. I had previously set up an `ssh` key for my `ieng6` account so I did not have to enter my password upon logging in.

#### Task 5. Clone the repository fork from your Github account

![clonefail](./Screen%20Shot%202023-02-23%20at%207.14.59%20PM.png)

I actually ran into an error here because it seems I did not delete the lab7 directory properly on my device - the error message can be seen when I try to use `git clone` initially. I just reran the command `rm -rf lab7` which successfully removed the directory and its files.

![clone](Screen%20Shot%202023-02-23%20at%207.09.12%20PM.png)

I manually entered the command to clone this repository just because I wanted to make sure I had the right SSH key for the repository. The command I used was `git clone <SSH link>` and I got the SSH link directly from Github.

#### Task 6. Run the tests

![tests](./Screen%20Shot%202023-02-23%20at%207.34.07%20PM.png)

This task required us to run the JUnit tests and demonstrate that they fail. After switching into the lab7 directory, I pressed the keys `<up><up><up><up><up><up><up><up><enter>` to get to the `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command to compile the files in the lab7 directory. This is because the command was 8 up in my search history. I repeated the same to access the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` command since it was also 8 up in my history.

#### Task 7. Fix the failing test

![command](./Screen%20Shot%202023-02-23%20at%207.22.03%20PM.png)

I ran the command `nano ListExamples.java` manually so that I could open the file ListExamples.java in the nano text editor and fix the bug that was causing the test to fail.

![nano](Screen%20Shot%202023-02-23%20at%207.22.41%20PM.png)

This is a screenshot of the nano text editor. As can be seen from my cursor position, I found the error in the code to be that the last `while` loop was not updating the value of `index2`, instead incrementing the value of `index1` and causing the loop to run infinitely, something that is reflected in the error message of the JUnit tests. I changed the line of code to reflect the correct index variable, and pressed the keys `<ctrl-O><enter><ctrl-X>` to save my changes and exit out of nano.

#### Task 8. Run the tests again

![tests2](Screen%20Shot%202023-02-23%20at%207.39.03%20PM.png)

Here I compiled and ran the tests again, and now they succeed! This means my code fix was successful. I used the keys `<up><up><up><enter>` to access the 
`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command to compile the files, since this was 3 up in my command history. I repeated the same to access the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` command since it was also 3 up in my history.

#### Task 9. Commit and push the resulting change to your Github account

![commit](Screen%20Shot%202023-02-23%20at%207.47.26%20PM.png)

To commit and push the changes to my Github, I used the commands `git add ListExamples.java`, `git commit -m "Updated"`, and `git push origin main`. I accessed all of these commands by using `<ctrl-R> git <enter>` to search through my command history and find/autocomplete the correct command. This concludes the lab tasks, done quick!

