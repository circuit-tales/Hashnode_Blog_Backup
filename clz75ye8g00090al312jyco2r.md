---
title: "Understanding return 1, return -1, and exit (1) in C Programming"
seoTitle: "Understanding return 1, return -1, and exit(1) in C Programming"
seoDescription: "Learn the differences between return 1, return -1, and exit(1) in C programming, and how to use them for effective error handling in your code."
datePublished: Sun Jul 28 2024 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clz75ye8g00090al312jyco2r
slug: understanding-return-1-return-1-and-exit-1-in-c-programming
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1722267502491/38813a5b-80b3-448e-8f6f-4e6cf3a9b034.webp
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1722267911375/2b150015-e34c-487e-a0b8-9ec07535a640.png
tags: c-programming, code, programming-blogs, programming, error-handling, programming-ciovqvfcb008mb253jrczo9ye, programming-languages, learntocode, codenewbies, programming-tips, cprogramminglanguage, programming-basics, computer-science-programming-beginners-guide-learn-to-code-technology-coding-basics-computer-science-for-beginners-programming-fundamentals-software-development-coding-tutorial-algorithm-basics-data-structures-programming-languages-tech-education-coding-101-computer-science-introduction-technology-for-beginners-computer-science-concepts-programming-for-newbiescomputer-science-explained-computer-science-basics-flowchart-pseudocode-programming-for-beginners, errorhandling, returnstatement

---

### 1\. `return 1`;

* **Usage**: This is usually used to return from the `main` function in a C program.
    
* **Meaning**: Returning `1` from `main` typically indicates an error or abnormal termination of the program.
    

## Example

```c
#include <stdio.h>

int main() {
    // Some condition that causes an error
    if (error_condition) {
        return 1; // Indicates an error
    }

    printf("Program completed successfully.\n");
    return 0; // Indicates success
}
```

**Explanation**: In the above example, if `error_condition` is true, the program will return `1` to indicate an error. If not, it will print a message and return `0` to indicate success.

### 2\. `return -1`

* **Usage**: Returning `-1` from the `main` function or other functions is a non-standard way to indicate an error. It's often used in function definitions to return a value to the caller indicating something went wrong.
    
* **Meaning**: It signals an error or an exceptional condition.
    
    ## Example
    
    ```c
    #include <stdio.h>
    
    int check_value(int value) {
        if (value < 0) {
            return -1; // Indicates an error
        }
        return 0; // Indicates success
    }
    
    int main() {
        int result = check_value(-5);
    
        if (result == -1) {
            printf("Error: Value is negative.\n");
            return -1; // Indicates an error in main
        }
    
        printf("All values are valid.\n");
        return 0; // Indicates success
    }
    ```
    
    **Explanation**: In this example, the function `check_value` returns `-1` if the input value is negative. The `main` function also returns `-1` to indicate an error if `check_value` returns `-1`.
    
    ### 3\. `exit (1)`
    
    * **Usage**: The `exit` function terminates the program immediately and can be called from anywhere in the code. It passes an exit status to the operating system.
        
    * **Meaning**: `exit(1)` indicates an error or abnormal termination, while `exit(0)` indicates successful completion
        
        ## Example
        
        ```c
        #include <stdio.h>
        #include <stdlib.h>
        
        int main() {
            // Some condition that causes an error
            if (error_condition) {
                printf("Encountered an error. Exiting...\n");
                exit(1); // Indicates an error and terminates the program
            }
        
            printf("Program completed successfully.\n");
            exit(0); // Indicates success and terminates the program
        }
        ```
        
        **Explanation**: In this example, if `error_condition` is true, the program prints an error message and calls `exit(1)` to terminate the program with an error status. If not, it prints a success message and calls `exit(0)` to terminate the program successfully.
        

### Summary

* `return 1`: Used in the `main` function to indicate an error. The value `1` is passed to the operating system.
    
* `return -1`: Often used in functions to indicate an error. It's a non-standard way to return an error value to the caller.
    
* `exit(1)`: Immediately terminates the program and passes an exit status to the operating system. `exit(1)` indicates an error, while `exit(0)` indicates success.
    

By understanding these different ways to handle errors and terminate a program, you can write more robust and predictable C code.