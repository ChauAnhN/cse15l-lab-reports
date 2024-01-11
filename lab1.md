# **Lab 1 Report**

# **Command** ```cd```
1. ```cd``` with *no* arguments
> <img width="240" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/a10d4bab-c3d0-443b-bd85-7d21201985b5">

**Working Directory:** ```/home```

This specific command gave no outputs because there wasn't a specific argument listed for ```cd```. In other words, there wasn't any path provided for ```cd``` to switch to, which provides the empty output in the screenshot above. This is an expected output.

2. ```cd``` with a path to a *directory* as an argument.
> <img width="344" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/b5f56b5d-95e3-4f6f-8476-54b6898fe6e0">

**Working Directory:** ```/home```

By providing a specific path (in this case being ```lecture1```) for the command ```cd``` we changed the current working directory from ```/home``` to ```/home/lecture1```. This is why we received the expected output, ```[user@sahara ~/lecture1]$```.

3. ```file``` with a path to a *directory* as an argument.
> <img width="419" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/b429262e-7e12-4797-8b9c-fc56bee40a84">

**Working Directory:** ```/home/lecture1```

As shown above, if we were to try to use ```cd``` on a file, we receive an error message stating ```Not a directory```. This is expected because the file ```es-mx.txt``` does not contain any files within it, meaning it is not a directory.





