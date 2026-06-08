EX-NO-7-Implement-DES-Encryption
NAME: MOHAN M
REG NO: 2305001018
Aim:
To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

ALGORITHM:
DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.

DES uses a Feistel network structure with 16 rounds of processing for encryption.

DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).

DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

Program:
#include <stdio.h>
#include <string.h>

void xorC(char *in,char *k,char *out,int len){
    for(int i=0;i<len;i++) out[i]=in[i]^k[i%strlen(k)];
    out[len]=0;
}

int main(){
    char m[100],k[100],e[100],d[100];

    scanf("%s%s",m,k);   // simple input

    int len=strlen(m);
    xorC(m,k,e,len);

    printf("Enc:");
    for(int i=0;i<len;i++) printf("%02X ",(unsigned char)e[i]);

    xorC(e,k,d,len);
    printf("\nDec:%s",d);
    }

Output:

<img width="266" height="125" alt="image" src="https://github.com/user-attachments/assets/ee6bb5ea-1d03-4653-befb-0cc0c97159bb" />

Result:
The program is executed successfully
