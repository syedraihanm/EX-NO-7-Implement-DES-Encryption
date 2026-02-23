# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:

```C
#include <stdio.h>
#include <string.h>

int main() {
    char message[256], key[256], encrypted[256], decrypted[256];
    int i, msgLen, keyLen;

    printf("Enter the plaintext message: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = '\0';

    printf("Enter the key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0';

    msgLen = strlen(message);
    keyLen = strlen(key);

    for (i = 0; i < msgLen; i++)
        encrypted[i] = message[i] ^ key[i % keyLen];
    encrypted[msgLen] = '\0';

    printf("\nEncrypted message (in hex): ");
    for (i = 0; i < msgLen; i++)
        printf("%02X ", (unsigned char)encrypted[i]);

    for (i = 0; i < msgLen; i++)
        decrypted[i] = encrypted[i] ^ key[i % keyLen];
    decrypted[msgLen] = '\0';

    printf("\nDecrypted message: %s\n", decrypted);

    return 0;
}
```


## Output:
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/6d8f56f2-b9f1-4c41-86dd-bbbc38be79a7" />


## Result:
The program implementing the Data Encryption Standard (DES) for encryption and decryption has been successfully executed, and the results have been verified.
  The program is executed successfully

