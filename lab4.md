# Lab 4 Report 

**4. Log into ieng6**
> <img width="728" alt="311888912-45dc6628-71f9-4351-93a0-89dee6261329" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/7bbe8b79-c2b3-4ebd-84bd-b634985355a9">

> **Keys Used:** `ssh <SPACE> chn032@ieng6.ucsd.edu <ENTER>`, `yes <ENTER>`

The input is highlighted in orange and the output is shown in the rest of the photo. For this step, I first used `ssh` to log into ieng6 with my UCSD email. Then, when the terminal prompted me to confirm if I really wanted to log in, I typed in the command `yes`, which allowed me to get into the desired account. 

**5. Clone your fork of the repository from your Github account (using the SSH URL)**
> <img width="437" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/924ab328-80c1-45ae-a56d-6ce38a2f642f">

> **Keys Used:** `git <SPACE> clone <SPACE> git@github.com:ChauAnhN/labreport4.git <ENTER>`

This step didn't require as many steps as the first one did. Here, I simply used the command `git clone`, followed by the ssh URL, to make a copy of the forked repo into my VS Code. 

**6. Run the tests, demonstrating that they fail**
> <img width="492" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/a4758d0d-0307-4b90-bb04-08d66006b29f">

> **Keys Used:** `cd <SPACE> lab7 <ENTER>`, `bash <SPACE> test.sh`

Here, I first `cd` the `lab7` directory so I can access the `.java` files in the folder. Then I compiled and ran the tests using the command `bash` and the file `test.sh`, which contains the `javac` and `java` commands.

**7. Edit the code file to fix the failing test**
> <img width="310" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/a22b8bbe-de8a-4a42-99e5-5363a172598d">

> **Keys Used:** `vim List<TAB> Examples.java`, `<K> <K> <K> <K> <K> <K> <L> <L> <L> <L> <L> <L> <L> <L> <L> <L> <L> <I> <DELETE> 2 <ESC> :wq <ENTER>`

Here, I used the command `vim` to open the file `ListExamples.java` and edit it. Once the file is opened, I utilized the `<K>` key to navigate upward to the line containing the error. Once I was on the correct line, I used the key `<L>` to move the cursor to the right of the number causing the error (which was `1` in this case). Afterwards, I used the key `<I>` to enter vim insert mode, `<DELETE>` to delete the 1, replaced it by typing the number `2`, `<ESC>` to escape vim insert mode, and `:wq` to save my edit and exit vim.

**8. Run the tests, demonstrating that they now succeed**
> <img width="241" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/6e210dc6-0919-4467-9823-6bfc9eb4b0af">

> **Keys Used:** `bash <SPACE> test.sh`
  
Here, I decided to use the command `bash` to run the tester file since it's faster than the `javac` `lib` command I used earlier. It's an effective command since it executes the earlier `javac` `lib` command, which is stored in a separate file called `test.sh`.

**9. Commit and push the resulting change to your Github account (you can pick any commit message!)**
> <img width="320" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/3c3e35bb-7267-48a7-9d14-dcf52d6f8901">

> <img width="292" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/fc6e6343-7db6-4aad-b0f7-2d4936a43046">

> **Keys Used:** `git <SPACE> add <SPACE> .`, `git <SPACE> commit <SPACE> -m <SPACE> <SHIFT> "Edits made <SHIFT> "`, `git push`

Here, I first used the command `git add` to add all the changes made to the desktop file and prepare them to be committed to Github. After typing in that command, I used the command `git commit -m` to create a new commit for Github. Lastly, I used the command `git push` to add the commits to Github.

