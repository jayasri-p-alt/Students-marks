# Students-marks
Making studen marks and ti calculator the marks, percentage, total marks etc.. 
#include <stdio.h>

// Define structure for student
struct Student {
    int rollNo;
    char name[50];
    float marks[5];   // marks for 5 subjects
    float total;
    float average;
};

int main() {
    int i, j, n;
    
    printf("Enter number of students: ");
    scanf("%d", &n);

    struct Student s[n];  // array of students

    // Input student details
    for (i = 0; i < n; i++) {
        printf("\nEnter details of student %d\n", i + 1);
        printf("Roll Number: ");
        scanf("%d", &s[i].rollNo);

        printf("Name: ");
        scanf("%s", s[i].name);

        s[i].total = 0;
        for (j = 0; j < 5; j++) {
            printf("Enter marks of subject %d: ", j + 1);
            scanf("%f", &s[i].marks[j]);
            s[i].total += s[i].marks[j];
        }
        s[i].average = s[i].total / 5.0;
    }

    // Display student results
    printf("\n\n--- Student Result Calculator ---\n");
    printf("RollNo\tName\tTotal\tAverage\n");
    for (i = 0; i < n; i++) {
        printf("%d\t%s\t%.2f\t%.2f\n",
               s[i].rollNo, s[i].name, s[i].total, s[i].average);
    }

    return 0;
}
