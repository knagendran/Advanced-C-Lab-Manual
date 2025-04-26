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

struct Person {
    char name[50];
    int age;
};

int main() {
    int n, i;
    
    printf("Enter number of people: ");
    scanf("%d", &n);
    
    struct Person people[n]; 
    
    
    for (i = 0; i < n; i++) {
        printf("\nEnter name of person %d: ", i + 1);
        scanf(" %[^\n]", people[i].name); 
        printf("Enter age of %s: ", people[i].name);
        scanf("%d", &people[i].age);
    }
    
    
    printf("\nVaccine Eligibility:\n");
    for (i = 0; i < n; i++) {
        printf("%s (Age: %d) is ", people[i].name, people[i].age);
        if (people[i].age >= 18) {
            printf("Eligible for the vaccine.\n");
        } else {
            printf("Not eligible for the vaccine.\n");
        }
    }
    
    return 0;
}
```


Output:

![Screenshot 2025-04-26 205345](https://github.com/user-attachments/assets/bb89e730-b0b0-4e1b-8234-934bd168afa3)



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


struct Student {
    char name[50];
    int marks1, marks2, marks3;
    int total;
    float percentage;
};


struct Student calculateResult(struct Student s) {
    s.total = s.marks1 + s.marks2 + s.marks3;
    s.percentage = (s.total / 3.0); // 3 subjects
    return s;
}


int main() {
    struct Student student1;
    
    printf("Enter student's name: ");
    scanf(" %[^\n]", student1.name);
    
    printf("Enter marks for 3 subjects:\n");
    printf("Subject 1: ");
    scanf("%d", &student1.marks1);
    printf("Subject 2: ");
    scanf("%d", &student1.marks2);
    printf("Subject 3: ");
    scanf("%d", &student1.marks3);
    
    
    student1 = calculateResult(student1);
    
    
    printf("\n--- Student Result ---\n");
    printf("Name       : %s\n", student1.name);
    printf("Total Marks: %d\n", student1.total);
    printf("Percentage : %.2f%%\n", student1.percentage);
    
    return 0;
}

```




Output:


![Screenshot 2025-04-26 205345](https://github.com/user-attachments/assets/204eeded-8034-454c-ae28-e0a7a5f926a2)




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
    FILE *file;
    char filename[100];
    scanf("%s", filename);
    file = fopen(filename, "w");
    
    if (file == NULL) {
        printf("Error creating file!\n");
        return 1;
    }
    
    printf("%s File Created Successfully\n", filename);
    printf("%s File Opened\n", filename);
    fclose(file);
    printf("%s File Closed\n", filename);
    
    return 0;
}

```




Output:


![Screenshot 2025-04-26 210516](https://github.com/user-attachments/assets/38ad90c5-d63e-4efa-a72c-d974dff28de3)











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

int main() {
    FILE *file;
    char filename[100];
    int n;
    char text[100];
    scanf("%s", filename);
    file = fopen(filename, "w");
    
    if (file == NULL) {
        printf("Error creating file!\n");
        return 1;
    }
    
    printf("%s Opened\n", filename);
    scanf("%d", &n);
    
    getchar();
    for (int i = 0; i < n; i++) {
        fgets(text, sizeof(text), stdin);
        fprintf(file, "%s", text);
    }
    
    printf("Data added Successfully\n");
    fclose(file);
    
    return 0;
}

```

Output:

![Screenshot 2025-04-26 210727](https://github.com/user-attachments/assets/e7f43acc-d9fe-45be-b0e0-43a8c759a902)





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
#include<stdio.h>
int main()
{
    struct student{
        int regno;
        int s1,s2,s3;
    };
    struct stp{
        float total;
        float percent;
        struct student st;
    };
    struct stp s[5];
    for(int i=0;i<5;i++){
        scanf("%d",&s[i].st.regno);
        scanf("%d",&s[i].st.s1);
        scanf("%d",&s[i].st.s2);
        scanf("%d",&s[i].st.s3);
        s[i].total=s[i].st.s1+s[i].st.s2+s[i].st.s3;
        s[i].percent=s[i].total/3;
    }printf("Student Details are\n");
    for(int i=0;i<5;i++){
        printf("%d       %d       %d       %d       %.2f       %.2f\n",s[i].st.regno,s[i].st.s1,s[i].st.s2,s[i].st.s3,s[i].total,s[i].percent);
    }
}
```




Output:


![Screenshot 2025-04-26 211611](https://github.com/user-attachments/assets/573da820-614f-463f-b095-00a10049002d)







Result:
Thus, the program is verified successfully
