# Hash_agile-Round1

## LONGEST PALINDROME SUBSTRING
## PROBLEM STATEMENT:
Creating and implementing a software that determines the longest palindromic substring within a given string is the aim of this problem. An ordered set of characters that reads the same both forward and backward is known as a palindromic substring. Without using any of the built-in string manipulation functions, the computer should be able to detect this substring.

Input: A single character string str, with a length ranging from 1 to 1000 characters, is accepted
by the program.

Output: The longest palindromic substring in the input string will be produced by the software.
Any substring with a maximum length can be returned if there are several of them

## Program code
```
#include<stdio.h>


int getStringlen(char str[]) {
    int length = 0;
    while (str[length] != '\0') {
        length++;
    }
    return length;
}


int isPalin(char str[], int start, int end) {
    while (start < end) {
        if (str[start] != str[end])
            return 0; 
        start++;
        end--;
    }
    return 1; 
}

void longPalinSub(char str[]) {
    int num = getStringlen(str);
    int l_start = 0; 
    int l_length = 1; 
    int i,j;
    for(i=0; i<num;i++) 
    {
        for(j=i;j<num;j++) 
        {
            if(isPalin(str,i,j)) 
            {
                int curr_len = j - i + 1;
                if (curr_len > l_length) {
                    l_start = i;
                    l_length = curr_len;
                }
            }
        }
    }

    printf("Longest Palindrome substring:");
    for (int i=l_start;i <l_start+l_length;i++) {
        printf("%c", str[i]); 
    }
    printf("\n");
}

int main() {
    
    char input1[] = "babad";
    printf("Input: %s\n", input1);
    longPalinSub(input1);


    char input2[] = "cbbd";
    printf("Input: %s\n", input2);
    longPalinSub(input2);


    char input3[] = "noonmadamracecar";
    printf("Input: %s\n", input3);
    longPalinSub(input3);

    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/71b046e6-c56d-4058-9a1d-83e583000327)
