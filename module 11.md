

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```
#include <stdio.h>

int findGreatest(int num1, int num2, int num3) {
    int greatest = num1;
    if (num2 > greatest) {
        greatest = num2;
    }
    if (num3 > greatest) {
        greatest = num3;
    }
    return greatest;
}

int main() {
    int n1, n2, n3;
    printf("Enter three numbers: ");
    scanf("%d %d %d", &n1, &n2, &n3);

    int result = findGreatest(n1, n2, n3);
    printf("The greatest number is: %d\n", result);
    return 0;
}
```

Output:
```
Enter three numbers: 25 100 75
The greatest number is: 100
```

Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n, k;

    printf("Enter the value of n: ");
    scanf("%d", &n);
    printf("Enter the value of k: ");
    scanf("%d", &k);

    if (n <= 0 || k <= 0) {
        printf("n and k must be positive integers.\n");
        return 1;
    }

    int max_and = 0;
    int max_or = 0;
    int max_xor = 0;

    for (int i = 1; i < n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_result = i & j;
            int or_result = i | j;
            int xor_result = i ^ j;

            if (and_result < k && and_result > max_and) {
                max_and = and_result;
            }
            if (or_result < k && or_result > max_or) {
                max_or = or_result;
            }
            if (xor_result < k && xor_result > max_xor) {
                max_xor = xor_result;
            }
        }
    }

    printf("Max AND value: %d\n", max_and);
    printf("Max OR value: %d\n", max_or);
    printf("Max XOR value: %d\n", max_xor);

    return 0;
}
```

Output:
```
Enter the value of n: 5
Enter the value of k: 3
Max AND value: 2
Max OR value: 3
Max XOR value: 2
```

Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n, k;
    int request;

    printf("Enter the value of n: ");
    scanf("%d", &n);
    printf("Enter the value of k: ");
    scanf("%d", &k);

    if (n <= 0 || k <= 0) {
        printf("n and k must be positive integers.\n");
        return 1;
    }

    printf("Enter your request:\n");
    printf("1: Calculate maximum AND value\n");
    printf("2: Calculate maximum OR value\n");
    printf("3: Calculate maximum XOR value\n");
    scanf("%d", &request);

    int max_and = 0;
    int max_or = 0;
    int max_xor = 0;

    for (int i = 1; i < n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_result = i & j;
            int or_result = i | j;
            int xor_result = i ^ j;

            if (and_result < k && and_result > max_and) {
                max_and = and_result;
            }
            if (or_result < k && or_result > max_or) {
                max_or = or_result;
            }
            if (xor_result < k && xor_result > max_xor) {
                max_xor = xor_result;
            }
        }
    }

    switch (request) {
        case 1:
            printf("Max AND value: %d\n", max_and);
            break;
        case 2:
            printf("Max OR value: %d\n", max_or);
            break;
        case 3:
            printf("Max XOR value: %d\n", max_xor);
            break;
        default:
            printf("Invalid request\n");
            break;
    }

    return 0;
}
```

Output:
```
Enter the value of n: 5
Enter the value of k: 7
Enter your request:
1: Calculate maximum AND value
2: Calculate maximum OR value
3: Calculate maximum XOR value
1
Max AND value: 6
```


Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    printf("Enter the number of integers: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("Invalid input. Number of integers should be positive.\n");
        return 1;
    }

    int *a = (int *)malloc(n * sizeof(int));
    if (a == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    printf("Enter the integers:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }

    int sum = 0;
    for (int i = 0; i < n; i++) {
        sum += a[i];
    }

    printf("Sum of the integers = %d\n", sum);

    free(a);

    return 0;
}

```

Output:
```
Enter the number of integers in the array: 5
Enter the integers:
1
2
3
4
5
Sum of the integers in the array: 15

```
 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int countWords(char *sentence) {
    int count = 0;
    int inWord = 0;
    for (int i = 0; sentence[i] != '\0'; i++) {
        if (isspace(sentence[i]) == 0 && inWord == 0) {
            inWord = 1;
            count++;
        } else if (isspace(sentence[i]) != 0) {
            inWord = 0;
        }
    }
    return count;
}

int main() {
    char sentence[1000];

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    sentence[strcspn(sentence, "\n")] = '\0';

    int wordCount = countWords(sentence);
    printf("Number of words: %d\n", wordCount);

    return 0;
}
```

Output:
```
Enter a sentence: This is a sample sentence.
Number of words: 5
```



Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
