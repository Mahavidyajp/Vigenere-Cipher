# Vigenere Cipher
Vigenere Cipher using with different key values

## AIM:
To develop a simple C program to implement Vigenere Cipher.

## DESIGN STEPS:
Step 1:
Design of Vigenere Cipher algorithnm

Step 2:
Implementation using C or pyhton code

Step 3:
Testing algorithm with different key values. ALGORITHM DESCRIPTION: The Vigenere cipher is a method of encrypting alphabetic text by using a series of different Caesar ciphers based on the letters of a keyword. It is a simple form of polyalphabetic substitution.To encrypt, a table of alphabets can be used, termed a Vigenere square, or Vigenere table. It consists of the alphabet written out 26 times in different rows, each alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses a different alphabet from one of the rows used. The alphabet at each point depends on a repeating keyword.

## PROGRAM:

```
#include <stdio.h>
#include <ctype.h>
#include <string.h>
#include <stdlib.h>

void encipher();
void decipher();

int main() {
    int choice;
    while (1) {
        printf("\n1. Encrypt Text");
        printf("\n2. Decrypt Text");
        printf("\n3. Exit");
        printf("\n\nEnter Your Choice: ");
        scanf("%d", &choice);
        getchar(); // to consume the newline character left by scanf
        
        if (choice == 3)
            exit(0);
        else if (choice == 1)
            encipher();
        else if (choice == 2)
            decipher();
        else
            printf("Please Enter a Valid Option.\n");
    }
    return 0;
}

void encipher() {
    unsigned int i;
    char input[50];
    int key;

    printf("\n\nEnter Plain Text: ");
    fgets(input, sizeof(input), stdin);
    input[strcspn(input, "\n")] = 0; // Remove the newline character
    
    printf("\nEnter Key Value: ");
    scanf("%d", &key);
    
    printf("\nResultant Cipher Text: ");
    for (i = 0; i < strlen(input); i++) {
        if (isalpha(input[i])) {
            char offset = isupper(input[i]) ? 'A' : 'a';
            printf("%c", offset + ((input[i] - offset + key) % 26));
        } else {
            printf("%c", input[i]);
        }
    }
    printf("\n");
}

void decipher() {
    unsigned int i;
    char input[50];
    int key;

    printf("\n\nEnter Cipher Text: ");
    fgets(input, sizeof(input), stdin);
    input[strcspn(input, "\n")] = 0; // Remove the newline character
    
    printf("\nEnter Key Value: ");
    scanf("%d", &key);
    
    printf("\nResultant Plain Text: ");
    for (i = 0; i < strlen(input); i++) {
        if (isalpha(input[i])) {
            char offset = isupper(input[i]) ? 'A' : 'a';
            printf("%c", offset + ((input[i] - offset - key + 26) % 26));
        } else {
            printf("%c", input[i]);
        }
    }
    printf("\n");
}
```
## OUTPUT:

![Screenshot 2024-09-04 155525](https://github.com/user-attachments/assets/d888e0ea-64b9-49db-95a9-b719860cd28e)


## RESULT:
The program is executed successfully
