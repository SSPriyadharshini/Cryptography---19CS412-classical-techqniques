# Cryptography---19CS412-classical-techqniques
# Caeser Cipher
Caeser Cipher using with different key values

# AIM:

To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.


## DESIGN STEPS:

### Step 1:

Design of Caeser Cipher algorithnm 

### Step 2:

Implementation using C or pyhton code

### Step 3:

1.	In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
2.	For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
3.	The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the   
    scheme, A = 0, B = 1, Z = 25.
4.	Encryption of a letter x by a shift n can be described mathematically as,
                       En(x) = (x + n) mod26
5.	Decryption is performed similarly,
                       Dn (x)=(x - n) mod26


## PROGRAM:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

char ALPHABET[] = "abcdefghijklmnopqrstuvwxyz";

void encrypt(char* text, int shift) {
    for (int i = 0; text[i] != '\0'; i++) {
        if (isalpha(text[i])) {
            int index = tolower(text[i]) - 'a';
            text[i] = ALPHABET[(index + shift) % 26];
        }
    }
}

void decrypt(char* text, int shift) {
    encrypt(text, -shift);
}

int main() {
    char choice[10];
    char text[100];
    int shift;
    printf("Do you want to encrypt or decrypt? ");
    scanf("%s", choice);
    printf("Enter the text: ");
    scanf("%s", text);
    printf("Enter the shift: ");
    scanf("%d", &shift);

    if (strcmp(choice, "encrypt") == 0) {
        encrypt(text, shift);
        printf("Encrypted text: %s\n", text);
    } else if (strcmp(choice, "decrypt") == 0) {
        decrypt(text, shift);
        printf("Decrypted text: %s\n", text);
    } else {
        printf("Invalid choice.\n");
    }

    return 0;
}
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/2703ba82-39ed-4b34-8a1b-16e243ea3d38)

## RESULT:
The program is executed successfully

