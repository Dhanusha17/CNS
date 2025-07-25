## EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER
## NAME: DHANUSHA K
## REG NO: 212223040034
## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


## PROGRAM :-
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main() {
    char plain[100], cipher[100];
    int key, i, length;

    printf("\nEnter the plain text: ");
    scanf("%99s", plain);

    printf("\nEnter the key value: ");
    scanf("%d", &key);

    length = strlen(plain);
    printf("\n\n\tPLAIN TEXT: %s", plain);
    printf("\n\n\tENCRYPTED TEXT: ");

    for (i = 0; i < length; i++) {
        cipher[i] = plain[i] + key;
        if (isupper(plain[i]) && cipher[i] > 'Z') {
            cipher[i] -= 26;
        }
        if (islower(plain[i]) && cipher[i] > 'z') {
            cipher[i] -= 26;
        }

        printf("%c", cipher[i]);
    }

    cipher[length] = '\0'; 
    printf("\n\n\tAFTER DECRYPTION: ");
    for (i = 0; i < length; i++) {
        plain[i] = cipher[i] - key;

        if (isupper(cipher[i]) && plain[i] < 'A') {
            plain[i] += 26;
        }
        if (islower(cipher[i]) && plain[i] < 'a') {
            plain[i] += 26;
        }
        printf("%c", plain[i]);
    }
    plain[length] = '\0'; 

    printf("\n");

    return 0; 
}


```
## OUTPUT :-
![Screenshot 2025-03-21 140258](https://github.com/user-attachments/assets/fc5d9789-b4cc-4721-a98f-b9a9e6ccf6d9)

## RESULT:
The program is executed successfully.
