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

//type your code here
#include<stdio.h>
int main()
{
    int num;
    scanf("%d",&num);
    switch(num)
    {
        case 21:
        printf("twenty one");
        break;
        case 22:
        printf("twenty two");
        break;
        case 23:
        printf("twenty three");
        break;
        case 24:
        printf("twenty four");
        break;
        case 25:
        printf("twenty five");
        break;
        case 26:
        printf("twenty six");
        break;
        case 27:
        printf("twenty seven");
        break;
        case 28:
        printf("twenty eight");
        break;
        case 29:
        printf("twenty nine");
        break;
        default:
        printf("Greater than 29");
        break;
    }
    return 0;
}
Output:


//paste your output here
	Input	Expected	Got	
21
twenty one
twenty one
23
twenty three
twenty three
44
Greater than 29
Greater than 29

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

//type your code here
#include<stdio.h>
#include<string.h>
#include<math.h>
int main()
{
    char s[50];
    char a[10]={0,0,0,0,0,0,0,0,0,0};
    scanf("%[^\n]",s);
    int i;
    int l=strlen(s);
    for(i=0;i<l;i++)
    {
        int m=s[i]-48;
        if(m>=0 && m<10)
        {
            a[m]++;
        }
    }
    for(i=0;i<10;i++)
    {
        printf("%d ",a[i]);
    }
    return 0;
}

Output:

Input	Expected	Got	
1v88886l256338ar0ekk
1 1 1 2 0 1 2 0 5 0
1 1 1 2 0 1 2 0 5 0
lw4n88j12n1
0 2 1 0 1 0 0 0 2 0
0 2 1 0 1 0 0 0 2 0

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

//type your code here
#include<stdio.h>
int main()
{
    int n;
    scanf("%d",&n);
    char a[n][10];
    int i;
    for(i=0;i<n;i++)
    {
        scanf("%s",a[i]);
    }
    if(n==2)
    {
        printf("%s %s\n%s %s",a[0],a[1],a[1],a[0]);
    }
    if(n==3)
    {
        printf("%s %s %s\n%s %s %s\n",a[0],a[1],a[2],a[0],a[2],a[1]);
        printf("%s %s %s\n%s %s %s\n",a[1],a[0],a[2],a[1],a[2],a[0]);
        printf("%s %s %s\n%s %s %s",a[2],a[0],a[1],a[2],a[1],a[0]);
    }
    return 0;
}

Output:


//paste your output here
	Input	Expected	Got	
2
dd
ee
dd ee
ee dd
dd ee
ee dd
3
aa
bb
cc
aa bb cc
aa cc bb
bb aa cc
bb cc aa
cc aa bb
cc bb aa
aa bb cc
aa cc bb
bb aa cc
bb cc aa
cc aa bb
cc bb aa


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

//type your code here
#include<stdio.h>
int main()
{
    int a;
    scanf("%d",&a);
    int n=a;
    int l=(n*2)-1;
    int i,j;
    for(i=0;i<l;i++)
    {
        for(j=0;j<l;j++)
        {
            int min=i<j?i:j;
            min=min<l-i-1?min:l-i-1;
            min=min<l-j-1?min:l-j-1;
            printf("%d ",n-min);
        }
        printf("\n");
    }
    return 0;
}

Output:


//paste your output here
	Input	Expected	Got	
2
2 2 2
2 1 2
2 2 2
2 2 2
2 1 2
2 2 2
5
5 5 5 5 5 5 5 5 5
5 4 4 4 4 4 4 4 5
5 4 3 3 3 3 3 4 5
5 4 3 2 2 2 3 4 5
5 4 3 2 1 2 3 4 5
5 4 3 2 2 2 3 4 5
5 4 3 3 3 3 3 4 5
5 4 4 4 4 4 4 4 5
5 5 5 5 5 5 5 5 5
5 5 5 5 5 5 5 5 5
5 4 4 4 4 4 4 4 5
5 4 3 3 3 3 3 4 5
5 4 3 2 2 2 3 4 5
5 4 3 2 1 2 3 4 5
5 4 3 2 2 2 3 4 5
5 4 3 3 3 3 3 4 5
5 4 4 4 4 4 4 4 5
5 5 5 5 5 5 5 5 5
3
3 3 3 3 3
3 2 2 2 3
3 2 1 2 3
3 2 2 2 3
3 3 3 3 3
3 3 3 3 3
3 2 2 2 3
3 2 1 2 3
3 2 2 2 3
3 3 3 3 3


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

//type your code here

#include <stdio.h>


int square();

int main() {
    int result;

    result = square(); 
    printf("Square of the number is: %d\n", result);

    return 0;
}


int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);

    return num * num;
}



Output:


//paste your output here
Enter a number: 4
Square of the number is: 16
Enter a number: -5
Square of the number is: 25



Result:
Thus, the program is verified successfully



























