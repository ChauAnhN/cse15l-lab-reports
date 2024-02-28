# Lab 1 Report 

**4. Log into ieng6**
> <img width="459" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/cb58b62b-d017-472f-a30c-18b01fb7ff03">

> **Keys Used:** `ssh <SPACE> chn032@ieng6.ucsd.edu <ENTER>`, `yes <ENTER>`

For this step, I first used `ssh` to log into ieng6 with my UCSD email. Then, when the terminal prompted me to confirm if I really wanted to log in, I typed in the command `yes`, which allowed me to get into the desired account. 

**5. Clone your fork of the repository from your Github account (using the SSH URL)**
> <img width="414" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/3a4457cd-d741-43dd-bdb7-cc899855f10f">

> **Keys Used:** `git <SPACE> clone <SPACE> https://github.com/ChauAnhN/lab7 <ENTER>`

This step didn't require as many steps as the first one did. Here, I simply used the command `git clone` to make a copy of the forked repo into my VS Code. 

**6. Run the tests, demonstrating that they fail**
> <img width="675" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/4fcf008d-a907-4884-9305-a8fc09d2ae97">

> **Keys Used:** `cd <SPACE> lab7/ <ENTER>`, `<CTRL> <P> javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`, `<CTRL> <P> java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore <SPACE> ListExamplesTests.java`

Here, I first `cd` the `lab7` directory so I can access the `.java` files in the folder. Then I copy and pasted the `javac` `lib` command to compile the tester file. Finally, I ran the test using `java` `-cp`, which commands the tester file to run its test cases.

**7. Edit the code file to fix the failing test**
> <img width="310" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/a22b8bbe-de8a-4a42-99e5-5363a172598d">

> **Keys Used:** `vim List<TAB> Examples.java`, `<K> <K> <K> <K> <K> <K> <L> <L> <L> <L> <L> <L> <L> <L> <L> <L> <L> <I> <DELETE> 2 <ESC> :wq <ENTER>`

Here, I used the command `vim` to open the file `ListExamples.java` and edit it. Once the file is opened, I utilized the `<K>` key to navigate upward to the line containing the error. Once I was on the correct line, I used the key `<L>` to move the cursor to the right of the number causing the error (which was `1` in this case). Afterwards, I used the key `<I>` to enter vim insert mode, `<DELETE>` to delete the 1, replaced it by typing the number `2`, `<ESC>` to escape vim insert mode, and `:wq` to save my edit and exit vim.

**8. Run the tests, demonstrating that they now succeed**
> <img width="241" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/6e210dc6-0919-4467-9823-6bfc9eb4b0af">

> **Keys Used:** `bash <SPACE> test.sh`
  


