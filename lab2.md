# **Lab 2 Report**

## **Part 1**
1. ChatServer Code File
> <img width="960" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/7aa4f498-244f-4d45-8164-2fa0d7bbaa01">
> <img width="960" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/8407fa97-e6b5-4148-aa36-bfc0f35e310d">
> <img width="960" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/1f2c6b6f-58ea-46c4-9fea-838590a2f7de">

2. Output: Message 1
> <img width="604" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/12e4a4db-37e5-423b-bc49-a86aaf7e2b01">

The method `String handleRequest(URI url)` is called when we add `/add-message?s=Hello&user=jpolitz` to the port URL. As shown in the code screenshots, the URL is first split by the `&` symbol and stored into the String array `parameters`. Afterwards, each `parameter` index is split by the `=` sign and then stored into the String array `userName`. The value `Hello` at `userName[0]` and the value `jpolitz` at `userName[1]` are then stored into the appropriate instance variables, `message` and `user`, which changes the instance variables' values from `null` to `Hello` and `jpolitz`. Lastly, the relevant instance variable `memory` is changed from empty string to store the string formatted `user` and `message`. Then, it is returned to the web server.

2. Output: Message 2
> <img width="599" alt="image" src="https://github.com/ChauAnhN/cse15l-lab-reports/assets/130714987/3426da9b-5f2d-4475-83eb-05fffd575cd0">

Similar to the previous screenshot, the method `String handleRequest(URI url)` is called when we add `/add-message?s=How are you&user=yash` to the port URL. The same arguments `.split()` and `.equals()` are applied, and the URL following `/add-messages` is split by the `&` sign and then by the `=` sign. The instance variable `user`'s value then changed from `jpolitz` from the last iteration to `yash` when we set the variable to now equal to the value at `userName[0]`. Similarly, the instance variable `message` is changed from `Hello` to `How are you` when we set the variable to now equal the value at `userName[1]`. Then, the value of the instance variable `memory` is changed when we add the new String formatted `user` and `message` to the variable.

## **Part 2**
1. 

