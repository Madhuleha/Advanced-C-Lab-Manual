

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
#include <stdio.h>
int max_of_four(int a, int b, int c, int d) {
    if (a >= b && a >= c && a >= d)
        return a;
    else if (b >= a && b >= c && b >= d)
        return b;
    else if (c >= a && c >= b && c >= d)
        return c;
    else
        return d;
}
int main() {
    int n1, n2, n3, n4, greater;
    printf("Enter four integers:\n");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    greater = max_of_four(n1, n2, n3, n4);
    printf("The greatest number is: %d\n", greater);
    return 0;
}


Output:
Enter four integers:
23 14 78 12
The greatest number is: 78


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

#include<stdio.h>
int main(){
int a,b;
scanf("%d%d",&a,&b);
int and=0,or=0,xor=0;
for(int i=1;i<=a;i++){
for(int j=i+1;j<=a;j++){
if((i&j)>and && (i&j)<b)
{
and=i&j;
}
if((i|j)> or && (i|j)<b)
{
or=i|j;
}
if((i^j)> xor && (i^j)<b)
{
xor=i^j;
}
}
}
printf("AND :%d\n",and);
printf("OR  :%d\n",or);
printf("XOR :%d\n",xor);
}



Output:
 5 4
 
AND :2
OR  :3
XOR :3


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
#include<stdio.h>
#include<stdlib.h>
int* total_books;
int** total_pages;
int main(){
    int total_shelves;
    scanf("%d",&total_shelves);
    
    total_books=calloc(total_shelves,sizeof(int));
    int total_queries;
    scanf("%d",&total_queries); 
     total_pages=malloc(total_shelves*sizeof(int*));
     for(int i=0;i<total_shelves;i++){
         total_pages[i]=calloc(1100,sizeof(int));
     }
     while(total_queries--)
     {
         int type_query;
         scanf("%d",&type_query);
         if(type_query==1)
         {
             int shelf,pages;
             scanf("%d %d ",&shelf,&pages);
             total_books[shelf]++;
             int *book=total_pages[shelf];
             while(*book!=0)
             book++;
             *book=pages;
         }
         else if(type_query==2){
             int x,y;
             scanf("%d %d",&x,&y);
             printf("%d\n",*(*(total_pages+x)+y));
         }
         else
         {
             int x;
             scanf("%d",&x);
             printf("%d\n",*(total_books+x)); 
             
         }
     }
     if(total_books)
     {
         free(total_books);
     }
       for(int i=0;i<total_shelves;i++) 
       {
           if(*(total_pages+i))
           {
               free(*(total_pages+i));
           }
       }
       if(total_pages)
       {
           free(total_pages);
         
       }
       return 0;
     
    
}


Output:
78
2


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
#include <stdio.h>
int main() {
    int n; 
    printf("Enter the number of integers: ");
    scanf("%d", &n); 
    int a[n]; 
    int sum = 0; 
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) { 
        scanf("%d", &a[i]); 
        sum += a[i];        
    }
    printf("Sum of the integers is: %d\n", sum);
    return 0;
}


Output:
Enter the number of integers: 3
Enter 3 integers:
10 20 30
Sum of the integers is: 60


 


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
#include <stdio.h>
int main() { // Step 1: Input the sentence
    int i = 0, words = 0;
    int inWord = 0; 
    printf("Enter a sentence:\n");
    fgets(sentence, sizeof(sentence), stdin); 
    while (sentence[i] != '\0') {
        if (sentence[i] != ' ' && sentence[i] != '\n' && sentence[i] != '\t') {
            if (inWord == 0) {
                words++; // Start of a new word
                inWord = 1;
            }
        } else {
            inWord = 0; 
        }
        i++;
    }
    printf("Total number of words: %d\n", words);
    return 0;
}


Output:
Enter a sentence:
Hello world! This is C programming.
Total number of words: 6




Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
