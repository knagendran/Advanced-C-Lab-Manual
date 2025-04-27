EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
```
#include <stdio.h>

int main() {
    int number;
    printf("Enter a number (0-9): ");
    scanf("%d", &number);

    if (number >= 0 && number <= 9) {
        const char *words[] = {
            "zero", "one", "two", "three", "four",
            "five", "six", "seven", "eight", "nine"
        };
        printf("%s\n", words[number]);
    } else {
        printf("Invalid input\n");
    }

    return 0;
}
```



Output:
```
Enter a number (0-9): 3
three

```




Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
```
#include <stdio.h>

int main() {
    int numbers[100];
    int n;

    printf("Enter the number of integers: ");
    scanf("%d", &n);

    printf("Enter the integers (0-9 allowed): ");
    for (int i = 0; i < n; i++) {
        scanf("%d", &numbers[i]);
    }

    int frequency[10] = {0};
    for (int i = 0; i < n; i++) {
        if (numbers[i] >= 0 && numbers[i] <= 9) {
            frequency[numbers[i]]++;
        }
    }

    printf("Frequencies: ");
    for (int i = 0; i < 10; i++) {
        printf("%d ", frequency[i]);
    }
    printf("\n");

    return 0;
}
```




Output:

```
Enter the number of integers: 10
Enter the integers (0-9 allowed): 1 2 3 4 5 6 7 8 9 0
Frequencies: 1 1 1 1 1 1 1 1 1 1
```





Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

void swap(char *a, char *b) {
    char t = *a;
    *a = *b;
    *b = t;
}

void reverse(char *str, int start, int end) {
    while (start < end)
        swap(&str[start++], &str[end--]);
}

int nextPermutation(char *str) {
    int len = strlen(str), i = len - 2, j = len - 1;
    while (i >= 0 && str[i] >= str[i + 1])
        i--;
    if (i < 0)
        return 0;
    while (str[j] <= str[i])
        j--;
    swap(&str[i], &str[j]);
    reverse(str, i + 1, len - 1);
    return 1;
}

int main() {
    char str[100];
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';
    qsort(str, strlen(str), sizeof(char), (int (*)(const void *, const void *))strcmp);
    printf("Permutations:\n");
    printf("%s\n", str);
    while (nextPermutation(str))
        printf("%s\n", str);
    return 0;
}
```




Output:

```
Enter a string: abc
Permutations:
abc
acb
bac
bca
cab
cba

```





Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
```
#include <stdio.h>

int main() {
    int n, i, j, num = 1;

    printf("Enter the value of n: ");
    scanf("%d", &n);

    for (i = 1; i <= n; i++) {
        for (j = 1; j <= i; j++) {
            printf("%d ", num++);
        }
        printf("\n");
    }

    return 0;
}

```


Output:

```
Enter the value of n: 4
1 
2 3 
4 5 6 
7 8 9 10

```



Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:
```
#include <stdio.h>

int getSquare() {
    int number;
    printf("Enter a number: ");
    scanf("%d", &number);
    return number * number;
}

int main() {
    int square = getSquare();
    printf("The square is: %d\n", square);
    return 0;
}

```



Output:
```
Enter a number: 5
The square is: 25

```




Result:
Thus, the program is verified successfully



























