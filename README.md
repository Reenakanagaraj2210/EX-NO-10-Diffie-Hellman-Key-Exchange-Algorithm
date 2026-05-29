# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:

```
#include <stdio.h>
#include <math.h>

// Function to calculate (base^exp) % mod
long long power(long long base, long long exp, long long mod)
{
    long long result = 1;

    while (exp > 0)
    {
        result = (result * base) % mod;
        exp--;
    }

    return result;
}

int main()
{
    long long p, g;
    long long a, b;
    long long A, B;
    long long keyA, keyB;

    // Public values
    printf("Enter prime number (p): ");
    scanf("%lld", &p);

    printf("Enter primitive root (g): ");
    scanf("%lld", &g);

    // Private keys
    printf("Enter private key for User A: ");
    scanf("%lld", &a);

    printf("Enter private key for User B: ");
    scanf("%lld", &b);

    // Public keys
    A = power(g, a, p);
    B = power(g, b, p);

    printf("\nPublic Key of A = %lld", A);
    printf("\nPublic Key of B = %lld", B);

    // Shared secret keys
    keyA = power(B, a, p);
    keyB = power(A, b, p);

    printf("\n\nSecret Key computed by A = %lld", keyA);
    printf("\nSecret Key computed by B = %lld", keyB);

    return 0;
}

```

## Output:

<img width="940" height="582" alt="image" src="https://github.com/user-attachments/assets/297c6bc1-3846-486b-a2bf-3aa1ec6dee7d" />


## Result:
  The Diffie-Hellman-Key-Exchange-Algorithm is executed successfully

