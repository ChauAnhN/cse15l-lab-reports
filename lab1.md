# **Lab 1 Report**

# **Command** ```cd```
1. ```cd``` with *no* arguments
> <img width="240" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/a10d4bab-c3d0-443b-bd85-7d21201985b5">

**Working Directory:** ```/home```

This specific command gave no outputs because there wasn't a specific argument listed for ```cd```. In other words, there wasn't any path provided for ```cd``` to switch to, which provides the empty output in the screenshot above. This is an expected output.

2. ```cd``` with a path to a *directory* as an argument
> <img width="344" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/b5f56b5d-95e3-4f6f-8476-54b6898fe6e0">

**Working Directory:** ```/home```

By providing a specific path (in this case being ```lecture1```) for the command ```cd``` we changed the current working directory from ```/home``` to ```/home/lecture1```. This is why we received the expected output, ```[user@sahara ~/lecture1]$```.

3. ```cd``` with a path to a *file* as an argument
> <img width="419" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/b429262e-7e12-4797-8b9c-fc56bee40a84">

**Working Directory:** ```/home/lecture1```

As shown above, if we were to try to use ```cd``` on a file, we receive an error message stating ```Not a directory```. This is expected because the file ```es-mx.txt``` does not contain any files within it, meaning it is not a directory.

# **Command** ```ls```
1. ```ls``` with *no* arguments
> <img width="275" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/ba182193-be27-4138-b9be-26690e629f01">

**Working Directory:** ```/home```

Since we haven't added any specific arguments to the command ```ls``` we unsurprisingly received one output: ```lecture1```, which is our root folder. Since the command ```ls``` simply lists the files in the given path, this output is expected.

2. ```ls``` with a path to a *directory* as an argument
> <img width="389" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/d2afa214-f86f-43b3-aa43-9d215f305b63">

**Working Directory:** ```/home```

Since we specified that the command ```ls``` lists the folders within ```lecture1```, we received the expected output above. 

3. ```ls``` with a path to a *file* as an argument
> <img width="422" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/ee949efc-160b-400d-b1ae-85cad637cee6">

**Working Directory:** ```/home```

The output above is an error. Because we didn't change the directory of the root folder, ```ls``` was not able to access the contents of the files ```ar-eg```, ```Hello.java```, and ```README```. If we were to change the directory using the command ```cd```, we should be able to receive the content of the file, as shown in the image below.
> <img width="388" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/37175bc2-2a39-4e1e-ae0f-10bfb5c1d4d5">

# **Command** ```cat```
1. ```cat``` with *no* arguments




