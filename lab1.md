# **Lab 1 Report**

# **Command** ```cd```
1. ```cd``` with *no* arguments
> <img width="240" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/a10d4bab-c3d0-443b-bd85-7d21201985b5">

**Working Directory:** ```/home```

This result is not an error. The purpose of ```cd``` is to switch the current working directory to the listed path, so the command shouldn't give any outputs in general.

2. ```cd``` with a path to a *directory* as an argument
> <img width="344" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/b5f56b5d-95e3-4f6f-8476-54b6898fe6e0">

**Working Directory:** ```/home```

The result shown in the above image is not an error. Since the purpose of ```cd``` is to change the current working directory to the one listed, then the command would *not* produce an output. However, in the image, it is evident that the command performed its function because the current working directory changed from ```/home``` to ```/home/lecture1```, as demonstrated by the directory prompt now being ```[user@sahara ~/lecture1]$```.

3. ```cd``` with a path to a *file* as an argument
> <img width="419" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/b429262e-7e12-4797-8b9c-fc56bee40a84">

**Working Directory:** ```/home/lecture1```

The result above is an error. If we were to try to use ```cd``` on a file, we receive a message stating ```Not a directory```. This is expected because the file ```es-mx.txt``` does not contain any files within it, meaning it is not a directory.

# **Command** ```ls```
1. ```ls``` with *no* arguments
> <img width="275" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/ba182193-be27-4138-b9be-26690e629f01">

**Working Directory:** ```/home```

The output above is not an error. Since we haven't added any specific arguments to the command ```ls``` we unsurprisingly received one output: ```lecture1```, which is our root folder. Since the command ```ls``` simply lists the files in the given path, this output is expected.

2. ```ls``` with a path to a *directory* as an argument
> <img width="389" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/d2afa214-f86f-43b3-aa43-9d215f305b63">

**Working Directory:** ```/home```

The message above is not an error. Since we specified that the command ```ls``` lists the folders within ```lecture1```, we received the expected output above. 

3. ```ls``` with a path to a *file* as an argument
> <img width="388" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/37175bc2-2a39-4e1e-ae0f-10bfb5c1d4d5">

**Working Directory:** ```/home```

The output above is not an error. Since we changed the directory of the folder from ```[user@sahara ~/lecture1]$``` to ```[user@sahara ~/lecture1/messages]$```, ```ls``` was able to access and list the contents of the file.

# **Command** ```cat```
1. ```cat``` with *no* arguments
> <img width="245" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/b98b38ef-afec-4a55-b084-e8d6e02cd525">

**Working Directory:** ```/home```

The output above is an error. This is because ```cat``` is meant to print out the specific file (or files) listed, and since ```cat``` was written without arguments terminal, it ends up copying everything typed into the terminal. To rectify this, we can press ```[Control] + [C]```.

2. ```cat``` with a path to a *directory* as an argument
> <img width="277" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/638377ce-a63b-405a-a158-b3ca52d1959e">


**Working Directory:** ```/home/lecture1```

The output shown above is an error. This is because ```cat``` is meant to print out the contents of a *file*, and since the argument listed is a directory, the terminal error message is printed.

3. ```cat``` with a path to a *file* as an argument
> <img width="641" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/26f9b965-41d1-45b4-89a1-82dd4e3c4098">

**Working Directory:** ```/home/lecture1```

The resulting output is not an error since the command ```cat``` is utilized to print out the two following files: ```Hello.java``` and ```README```. 


