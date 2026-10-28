# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```
#include <stdio.h>
#include <string.h>

void caesarEncrypt(char *text, int key)
{
    key = ((key % 26) + 26) % 26;

    for (int i = 0; text[i] != '\0'; i++)
    {
        char c = text[i];

        if (c >= 'A' && c <= 'Z')
        {
            text[i] = (char)((c - 'A' + key) % 26 + 'A');
        }
        else if (c >= 'a' && c <= 'z')
        {
            text[i] = (char)((c - 'a' + key) % 26 + 'a');
        }
    }
}

void caesarDecrypt(char *text, int key)
{
    caesarEncrypt(text, -key);
}

int main(void)
{
    char message[100];
    int key;

    printf("Enter the message to encrypt: ");

    if (fgets(message, sizeof(message), stdin) == NULL)
    {
        printf("Error reading message.\n");
        return 1;
    }

    message[strcspn(message, "\n")] = '\0';

    printf("Enter the Caesar Cipher key: ");

    if (scanf("%d", &key) != 1)
    {
        printf("Invalid key.\n");
        return 1;
    }

    caesarEncrypt(message, key);
    printf("Encrypted Message: %s\n", message);

    caesarDecrypt(message, key);
    printf("Decrypted Message: %s\n", message);

    return 0;
}
```

## OUTPUT:
<img width="274" height="77" alt="image" src="https://github.com/user-attachments/assets/998e7fcf-a103-4408-be0b-1e6dbc0e5d95" />

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
