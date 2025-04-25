EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include <stdio.h>

#define MAX 100  // Maximum number of people

// Structure to store person details
struct Person {
    char name[50];
    int age;
};

int main() {
    struct Person people[MAX];
    int n, i;

    printf("Enter the number of persons: ");
    scanf("%d", &n);

    // Input details
    for (i = 0; i < n; i++) {
        printf("\nEnter details for person %d\n", i + 1);
        printf("Name: ");
        scanf("%s", people[i].name);
        printf("Age: ");
        scanf("%d", &people[i].age);
    }

    // Check eligibility
    printf("\nVaccine Eligibility Status:\n");
    for (i = 0; i < n; i++) {
        if (people[i].age > 6) {
            printf("%s (Age %d): Eligible for Vaccine\n", people[i].name, people[i].age);
        } else {
            printf("%s (Age %d): Not Eligible for Vaccine\n", people[i].name, people[i].age);
        }
    }

    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/f383b65a-505d-4191-90c6-b2f0f0fe5b19)



Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:

```
#include <stdio.h>

// Define a structure
struct Student {
    char name[50];
    int marks1, marks2, marks3;
    float average;
};

// Function to take input and return a structure
struct Student getStudentDetails() {
    struct Student s;

    printf("Enter student name: ");
    scanf("%s", s.name);
    printf("Enter marks for 3 subjects: ");
    scanf("%d %d %d", &s.marks1, &s.marks2, &s.marks3);

    return s; // return structure
}

// Function to calculate average - structure is passed as argument
void calculateAverage(struct Student *s) {
    s->average = (s->marks1 + s->marks2 + s->marks3) / 3.0;
}

// Function to display student details
void displayStudent(struct Student s) {
    printf("\n--- Student Details ---\n");
    printf("Name: %s\n", s.name);
    printf("Marks: %d, %d, %d\n", s.marks1, s.marks2, s.marks3);
    printf("Average: %.2f\n", s.average);
}

int main() {
    struct Student student;

    student = getStudentDetails();   // receiving a structure
    calculateAverage(&student);      // passing structure to function
    displayStudent(student);

    return 0;
}
```


Output:


![image](https://github.com/user-attachments/assets/5d402449-7956-444c-befe-a7a11e031286)





Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

```
#include <stdio.h>

int main() {
    char fileName[100];
    FILE *file;
    char ch;

    // Read file name from user
    printf("Enter the file name to open: ");
    scanf("%s", fileName);

    // Open the file in read mode
    file = fopen(fileName, "r");

    if (file == NULL) {
        printf("Error: Could not open the file %s\n", fileName);
        return 1;
    }

    // Read and display contents
    printf("\n--- File Contents ---\n");
    while ((ch = fgetc(file)) != EOF) {
        putchar(ch);
    }

    fclose(file);
    return 0;
}
```




Output:


![image](https://github.com/user-attachments/assets/400f1957-a2d2-4a0c-89ea-13933dd45d9b)



Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {
    char fileName[100], ch;
    FILE *file;
    char text[1000];

    // Get the file name from user
    printf("Enter the file name: ");
    scanf("%s", fileName);

    // Open file in read mode to display existing content
    file = fopen(fileName, "r");
    if (file == NULL) {
        printf("File not found. Creating a new file.\n");
    } else {
        printf("\n--- Existing File Content ---\n");
        while ((ch = fgetc(file)) != EOF) {
            putchar(ch);
        }
        fclose(file);
    }

    // Open file in append mode to insert new content
    file = fopen(fileName, "a");
    if (file == NULL) {
        printf("Error opening file for writing.\n");
        return 1;
    }

    printf("\nEnter the text to insert (end input with ~ on a new line):\n");

    getchar(); // to clear the newline after scanf
    while (fgets(text, sizeof(text), stdin)) {
        if (text[0] == '~') // sentinel to end input
            break;
        fputs(text, file);
    }

    fclose(file);
    printf("Text successfully added to the file.\n");

    return 0;
}
```




Output:


![image](https://github.com/user-attachments/assets/67d6eb72-c22a-4fee-98a9-a18d71dd3037)




Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Subject {
    char name[50];
    float marks;
};

int main() {
    int n, i;
    struct Subject *subjects;

    printf("Enter the number of subjects: ");
    scanf("%d", &n);

    // Dynamically allocate memory
    subjects = (struct Subject *)malloc(n * sizeof(struct Subject));

    // Check for memory allocation failure
    if (subjects == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Input subject details
    for (i = 0; i < n; i++) {
        printf("\nEnter name of subject %d: ", i + 1);
        scanf("%s", subjects[i].name);
        printf("Enter marks for %s: ", subjects[i].name);
        scanf("%f", &subjects[i].marks);
    }

    // Display subject details
    printf("\n--- Subject Information ---\n");
    for (i = 0; i < n; i++) {
        printf("Subject %d: %s - %.2f marks\n", i + 1, subjects[i].name, subjects[i].marks);
    }

    // Free allocated memory
    free(subjects);
    printf("\nMemory successfully freed.\n");

    return 0;
}
```




Output:


![image](https://github.com/user-attachments/assets/c02f89ae-5f1f-4da0-a7cd-61b5d9e90c39)






Result:
Thus, the program is verified successfully
