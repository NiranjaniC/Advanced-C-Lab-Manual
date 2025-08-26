EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "forty one"
-	Case 6: Print "forty two"
-	Case 13: Print "forty three"
-	...
-	Case 13: Print "forty nine"
-	Default: Print "Greater than 49"
4.	Exit the program.
 
Program:
```
#include <stdio.h>

int main() {
    int n;
    scanf("%d", &n);

    if (n >= 41 && n <= 49) {
        switch(n) {
            case 41: printf("forty one\n"); break;
            case 42: printf("forty two\n"); break;
            case 43: printf("forty three\n"); break;
            case 44: printf("forty four\n"); break;
            case 45: printf("forty five\n"); break;
            case 46: printf("forty six\n"); break;
            case 47: printf("forty seven\n"); break;
            case 48: printf("forty eight\n"); break;
            case 49: printf("forty nine\n"); break;
        }
    } else if (n > 49) {
        printf("Greater than 49\n");
    }

    return 0;
}
```
Output:

<img width="752" height="203" alt="image" src="https://github.com/user-attachments/assets/9cd4d73e-21ee-4b99-b722-7494ca2c15be" />

Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 9 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 9.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 9
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
```
#include <stdio.h>
#include <string.h>

int main() {
    char str[1000];
    int freq[10] = {0};  // array to store digit frequencies (0-9)

    scanf("%s", str);  // read input string

    for (int i = 0; str[i] != '\0'; i++) {
        if (str[i] >= '0' && str[i] <= '9') {
            freq[str[i] - '0']++;  // convert char to digit and count
        }
    }

    // Print the frequencies
    for (int i = 0; i < 10; i++) {
        printf("%d ", freq[i]);
    }
    printf("\n");

    return 0;
}
```
Output:

<img width="753" height="171" alt="image" src="https://github.com/user-attachments/assets/8cfe2f8a-170e-4290-b23a-c939e6573606" />

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

#define MAX 100

// Swap two strings
void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}

// Compare function for qsort
int cmpstr(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

// Generate next lexicographical permutation
int next_permutation(char *arr[], int n) {
    int i = n - 2;
    while (i >= 0 && strcmp(arr[i], arr[i + 1]) >= 0)
        i--;

    if (i < 0) return 0;

    int j = n - 1;
    while (strcmp(arr[j], arr[i]) <= 0)
        j--;

    swap(&arr[i], &arr[j]);

    // Reverse suffix
    int left = i + 1, right = n - 1;
    while (left < right) {
        swap(&arr[left], &arr[right]);
        left++;
        right--;
    }

    return 1;
}

// Print the permutation
void print_permutation(char *arr[], int n) {
    for (int i = 0; i < n; i++) {
        printf("%s", arr[i]);
        if (i != n - 1) printf(" ");
    }
    printf("\n");
}

int main() {
    int n;
    scanf("%d", &n);
    
    char *arr[MAX];
    for (int i = 0; i < n; i++) {
        arr[i] = malloc(100);  // allocate space for each string
        scanf("%s", arr[i]);
    }

    // Sort initially to start with the smallest lex permutation
    qsort(arr, n, sizeof(char *), cmpstr);

    print_permutation(arr, n);

    while (next_permutation(arr, n)) {
        print_permutation(arr, n);
    }

    // Free memory
    for (int i = 0; i < n; i++) {
        free(arr[i]);
    }

    return 0;
}
```

Output:

<img width="760" height="299" alt="image" src="https://github.com/user-attachments/assets/48ca4919-5173-4655-b89e-b7ff9b64c9d9" />

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
#include <stdlib.h>

int main() {
    int n;
    scanf("%d", &n);

    int size = 2 * n - 1;

    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++) {
            int min = i < j ? i : j;
            min = min < size - i ? min : size - i - 1;
            min = min < size - j - 1 ? min : size - j - 1;
            printf("%d", n - min);
            if (j != size - 1) printf(" ");
        }
        printf("\n");
    }

    return 0;
}
```

Output:

<img width="762" height="455" alt="image" src="https://github.com/user-attachments/assets/e3f6627e-7ad2-45a5-bddd-8ec12df8b450" />

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
int square();

int main() {
    int result;
    result = square();
    printf("The square of the given number is: %d\n", result);

    return 0;
}

int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);

    return num * num;  
}
```
Output:

<img width="967" height="470" alt="image" src="https://github.com/user-attachments/assets/5d312c5c-e30a-4b39-80bf-1ea266e27689" />

Result:
Thus, the program is verified successfully



























