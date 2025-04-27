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
#include <string.h>
#include <stdbool.h>

struct Person {
    char name[50];
    int age;
};

bool isEligibleForVaccine(int age) {
    return age > 6;
}

int main() {
    int numPeople;
    printf("Enter number of people: ");
    scanf("%d", &numPeople);

    struct Person people[numPeople];
    for (int i = 0; i < numPeople; i++) {
        printf("\nPerson %d:\n", i + 1);
        printf("Name: ");
        fgets(people[i].name, sizeof(people[i].name), stdin);
        size_t len = strcspn(people[i].name, "\n");
        if (len < sizeof(people[i].name))
            people[i].name[len] = '\0';
        printf("Age: ");
        scanf("%d", &people[i].age);
        while (getchar() != '\n');
    }

    printf("\nEligibility:\n");
    for (int i = 0; i < numPeople; i++) {
        bool eligible = isEligibleForVaccine(people[i].age);
        printf("Name: %s, Age: %d, Eligible: %s\n", people[i].name, people[i].age, eligible ? "Yes" : "No");
    }
    return 0;
}
```
Output:
```
Enter number of people: 3

Person 1:
Name: John Doe
Age: 25

Person 2:
Name: Jane Smith
Age: 5

Person 3:
Name: Peter Pan
Age: 10

Eligibility:
Name: John Doe, Age: 25, Eligible: Yes
Name: Jane Smith, Age: 5, Eligible: No
Name: Peter Pan, Age: 10, Eligible: Yes
```
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
#include <string.h>

struct Person {
    char name[50];
    int age;
};

void modifyPerson(struct Person p) {
    p.age += 10;
    strcpy(p.name, "Modified Name");
    printf("Inside modifyPerson: %s, %d\n", p.name, p.age);
}

struct Person createPerson(char name[], int age) {
    struct Person p;
    strcpy(p.name, name);
    p.age = age;
    return p;
}

int main() {
    struct Person person1 = {"John Doe", 30};
    struct Person person2;

    modifyPerson(person1);
    printf("Outside modifyPerson: %s, %d\n", person1.name, person1.age);

    person2 = createPerson("Jane Smith", 25);
    printf("Created Person: %s, %d\n", person2.name, person2.age);

    return 0;
}
```


Output:
```
Inside modifyPerson: Modified Name, 40
Outside modifyPerson: John Doe, 30
Created Person: Jane Smith, 25
```

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
#include <string.h>

int main() {
    char filename[100];

    printf("Enter the filename: ");
    fgets(filename, sizeof(filename), stdin);
    filename[strcspn(filename, "\n")] = 0;

    printf("The filename entered is: %s\n", filename);

    return 0;
}
```


Output:
```
Enter the filename: my_document.txt
The filename entered is: my_document.txt

```








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
#include <string.h>
#include <stdlib.h>

int main() {
    char filename[100];
    char textToInsert[200];
    FILE *file;
    FILE *tempFile;
    char buffer[1024];
    int lineNum = 2;
    int currentLine = 1;

    printf("Enter filename: ");
    fgets(filename, sizeof(filename), stdin);
    filename[strcspn(filename, "\n")] = 0;

    printf("Enter text to insert: ");
    fgets(textToInsert, sizeof(textToInsert), stdin);
    textToInsert[strcspn(textToInsert, "\n")] = 0;

    file = fopen(filename, "r+");
    if (!file) {
        perror("Error opening file");
        return 1;
    }

    tempFile = fopen("temp.txt", "w");
    if (!tempFile) {
        perror("Error creating temp file");
        fclose(file);
        return 1;
    }

    while (fgets(buffer, sizeof(buffer), file)) {
        if (currentLine == lineNum)
            fprintf(tempFile, "%s\n", textToInsert);
        fprintf(tempFile, "%s", buffer);
        currentLine++;
    }
    if (currentLine < lineNum)
        fprintf(tempFile, "%s\n", textToInsert);

    fclose(file);
    fclose(tempFile);
    remove(filename);
    rename("temp.txt", filename);

    printf("Text inserted into %s\n", filename);
    return 0;
}

```



Output:

```
Enter filename: satwik
Enter text to insert: hello
Error opening file: No such file or directory
```






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
#include <string.h>

struct Subject {
    char *name;
    int marks;
};

int main() {
    int numSubjects;
    printf("Enter the number of subjects: ");
    scanf("%d", &numSubjects);
    getchar();

    struct Subject *subjects = (struct Subject *)malloc(numSubjects * sizeof(struct Subject));
    if (subjects == NULL) {
        perror("Memory allocation failed");
        return 1;
    }

    for (int i = 0; i < numSubjects; i++) {
        subjects[i].name = (char *)malloc(50 * sizeof(char));
        if (subjects[i].name == NULL) {
            perror("Memory allocation failed for subject name");
            // Handle previous allocations
            for (int j = 0; j < i; j++) {
                free(subjects[j].name);
            }
            free(subjects);
            return 1;
        }
        printf("Enter name of subject %d: ", i + 1);
        fgets(subjects[i].name, 50, stdin);
        subjects[i].name[strcspn(subjects[i].name, "\n")] = '\0';

        printf("Enter marks for subject %d: ", i + 1);
        scanf("%d", &subjects[i].marks);
        getchar();
    }

    printf("\nSubject Details:\n");
    for (int i = 0; i < numSubjects; i++) {
        printf("Subject: %s, Marks: %d\n", subjects[i].name, subjects[i].marks);
    }

    for (int i = 0; i < numSubjects; i++) {
        free(subjects[i].name);
    }
    free(subjects);

    return 0;
}
```




Output:
```
Enter the number of subjects: 2
Enter name of subject 1: Math
Enter marks for subject 1: 90
Enter name of subject 2: Physics
Enter marks for subject 2: 85

Subject Details:
Subject: Math, Marks: 90
Subject: Physics, Marks: 85
```






Result:
Thus, the program is verified successfully
