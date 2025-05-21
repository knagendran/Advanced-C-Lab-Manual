EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim: To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:

Declare structure eligible with age (integer) and n (character array)
Declare variable e of type eligible
Input age and name using scanf, store in e
If e.age <= 6
Print "Vaccine Eligibility: No" Else
Print "Vaccine Eligibility: Yes"
Print details (e.age, e.n)
Return 0
Program:

#include <stdio.h>
struct Person {
    char name[50];
    int age;
};
int main() {
    int n;
    printf("Enter the number of persons: ");
    scanf("%d", &n);
    struct Person persons[n];
    for (int i = 0; i < n; i++) {
        printf("\nEnter name of person %d: ", i + 1);
        scanf("%s", persons[i].name);
        printf("Enter age of person %d: ", i + 1);
        scanf("%d", &persons[i].age);
    }
    printf("\nVaccine Eligibility Report:\n");
    for (int i = 0; i < n; i++) {
        printf("Name: %s, Age: %d - ", persons[i].name, persons[i].age);
        if (persons[i].age > 6)
            printf("Vaccine Eligibility: Yes\n");
        else
            printf("Vaccine Eligibility: No\n");
    }
    return 0;
}
Output:
![Screenshot 2025-05-21 131840](https://github.com/user-attachments/assets/6349bcf2-a555-4709-8d80-4e1ef8adf61d)
Result: Thus, the program is verified successfully.

EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION Aim: To write a C program for passing structure as function and returning a structure from a function

Algorithm:

Define structure numbers with members a and b.
Declare variable n of type numbers.
Prompt the user to enter values for a and b.
Input values for a and b into n using scanf.
Call the add function with n as an argument.
Print the result returned by the add function.
Return 0
Program:

#include <stdio.h>
#include <string.h>
struct Person {
    char name[50];
    int age;
};
void displayPerson(struct Person p) {
    printf("\n--- Displaying Person Info ---\n");
    printf("Name: %s\n", p.name);
    printf("Age: %d\n", p.age);
}
struct Person createPerson() {
    struct Person newPerson;
    printf("Enter name: ");
    scanf("%s", newPerson.name);
    printf("Enter age: ");
    scanf("%d", &newPerson.age);
    return newPerson;
}
int main() {
    struct Person p1 = createPerson();
    displayPerson(p1);
    return 0;
}

Output:
![Screenshot 2025-05-21 131947](https://github.com/user-attachments/assets/343f5169-45fe-42b2-9fa4-89770c117a85)

Result: Thus, the program is verified successfully

EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim: To write a C program to read a file name from user

Algorithm:

Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare a character array name to store the file name.
Prompt the user to enter a file name. Use scanf to input the file name into the name array.
Print a message indicating that the file with the specified name has been created successfully.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use fclose to close the file.
Print a message indicating that the file has been closed.
End the main function.
Return 0 to indicate successful program execution.
Program:

#include <stdio.h>
int main() {
    char filename[100];
    FILE *file;
    printf("Enter the file name to open: ");
    scanf("%s", filename);
    file = fopen(filename, "r");
    if (file == NULL)
    {
        printf("Error: Cannot open file '%s'\n", filename);
    }
    else
    {
        printf("File '%s' opened successfully.\n", filename);
        fclose(file);
    }

    return 0;
}

Output:
![Screenshot 2025-05-21 132128](https://github.com/user-attachments/assets/bfe71e4a-c2aa-4b01-b3c6-9daa33c38e5e)

Result: Thus, the program is verified successfully

EXP NO:4 PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE Aim: To write a C program to read, a file and insert text in that file Algorithm:

Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare character arrays name and text. Declare an integer variable num.
Prompt the user to enter a file name and the number of strings. Use scanf to input the file name into the name array and the number of strings into the num variable.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use a loop to input strings from the user and write them to the file using fputs.
Use fclose to close the file.
Print a message indicating that data has been added successfully.
End the main function.
Return 0 to indicate successful program execution.
Program:

#include <stdio.h>
#include <stdlib.h>
int main() {
    char filename[100];
    char text[500];
    FILE *file;
    printf("Enter the file name: ");
    scanf("%s", filename);
    file = fopen(filename, "a");
    if (file == NULL) {
        printf("Error: Could not open file %s\n", filename);
        return 1;
    }
    printf("Enter text to insert into the file:\n");
    getchar();
    fgets(text, sizeof(text), stdin);
    fputs(text, file);
    fclose(file);
    printf("Text inserted into file successfully.\n");
    file = fopen(filename, "r");
    if (file == NULL) {
        printf("Error: Could not open file to read contents.\n");
        return 1;
    }
    printf("\n--- File Content After Insertion ---\n");
    char ch;
    while ((ch = fgetc(file)) != EOF) {
        putchar(ch);
    }
    fclose(file);
    return 0;
}

Output:
![Screenshot 2025-05-21 132214](https://github.com/user-attachments/assets/06bea771-5d5d-4b4d-9626-653f95cec2cb)

Result: Thus, the program is verified successfully

Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim: The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm: 1.Input the number of subjects.

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

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#define NAME_LENGTH 100
struct Subject {
    char name[NAME_LENGTH];
    float marks;
};
int main() {
    int n;
    struct Subject *subjects;
    printf("Enter number of subjects: ");
    scanf("%d", &n);
    subjects = (struct Subject *)malloc(n * sizeof(struct Subject));
    if (subjects == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }
    for (int i = 0; i < n; i++) {
        printf("\nEnter name of subject %d: ", i + 1);
        scanf(" %[^\n]", subjects[i].name);  // Read string with spaces
        printf("Enter marks for subject %d: ", i + 1);
        scanf("%f", &subjects[i].marks);
    }
    printf("\n--- Subject Information ---\n");
    for (int i = 0; i < n; i++) {
        printf("Subject %d: %s | Marks: %.2f\n", i + 1, subjects[i].name, subjects[i].marks);
    }
    free(subjects);
    return 0;
}
Output:
![Screenshot 2025-05-21 132327](https://github.com/user-attachments/assets/1a13e245-792b-4ec6-9199-f75d3b35ae19)

Result: Thus, the program is verified successfully
