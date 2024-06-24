```c
// hmz
#include <stdio.h>
struct Student {
    char name[200];
    char section;
    int id ;
    int marks[3];
    float averageMark;
};
float averageMark(int marks[], int amountOfMarks){
    // Sum of all marks
    int sum=0,i;
    float average;
    for(i=0; i< amountOfMarks; i++){
        sum+= marks[i];
    }
    average = sum/amountOfMarks;
    return average;
}
struct Student getHighest(struct Student students[] , int numberOfStudents){
    // Temporary highest student, thought to be the first
    struct Student highest = students[0];
    int i;
    for(i=0; i<numberOfStudents; i++){
        // Get the highest student based on the highest average mark
        if(students[i].averageMark > highest.averageMark) highest = students[i];
    }
    return highest;
};
void inputStudents(struct Student students[], int numberOfStudents){
    int i;
    for(i=0; i < numberOfStudents; i++){
        printf("\n\nEnter the information for student #%d\n", i+1);
        printf("Enter student's name\n");
        // When scanning a string, getchar needs to be used around it should there be more scanfs
        getchar();
        scanf("%[^\n]s", &students[i].name);
        printf("Enter student's section\n");
        getchar();
        scanf("%c", &students[i].section);
        printf("Enter student's id\n");
        scanf("%d", &students[i].id);
        printf("Enter student's Marks for 3 subjects\n");
        // Input all three marks at once
        scanf("%d%d%d",&students[i].marks[0], &students[i].marks[1], &students[i].marks[2]);
        // Get the average mark of three
        students[i].averageMark = averageMark(students[i].marks, 3);

    }
    return;
};
void printStudentData (struct Student stud){
    printf("Student Name: %s\n", stud.name);
    printf("Student Section: %c\n", stud.section);
    printf("Student ID: %d\n", stud.id);
    printf("Student Average Mark: %f\n", stud.averageMark);
}
int main(){
    int numberOfStudents;
    printf("Enter the amount of students\n");
    scanf("%d", &numberOfStudents);
    // The array that will hold all the students
    struct Student students[numberOfStudents];
    // Populate the array with values
    inputStudents(students, numberOfStudents);
    // The student with the highest marks
    struct Student highest = getHighest(students, numberOfStudents);
    printf("\n\nThe highest is:\n")
    // Print the information for highest ranking student
    printStudentData(highest);
    return 0;
}
```
# Questions
**Question 1**
> Define the `Student` structure

**Question 2**
> Explain the `averageMark` function

**Question 3**
> Explain the `inputStudents` function

**Question 4**
> Explain the `main` function

**Question 5**
> What are being printed in the `printStudentData` function

**Question 6**
> How many students are in the `students` array

**Question 7**
> Provide an example of the input and output for this program

