# C Code to Determine Prime Number

This program is written in C to check whether a given number is a prime number. A prime number is a number greater than 1 that is divisible only by 1 and itself. This program uses a loop to test divisors and determine the primality of the input number.

---

## **Code with Inline Documentation**

```c
#include <stdio.h> // Standard Input/Output library for printf and scanf

int main()
{
    int n = 0, prime = 1; // `n` stores the user's input; `prime` is a flag to indicate primality

    // Prompt the user for input
    printf("Insert your number: ");
    scanf("%d", &n); // Reads an integer and stores it in `n`

    // Handle numbers less than or equal to 1 (not prime)
    if (n <= 1)
    {
        printf("%d is not a prime number.\n", n); // Print result
        return 0; // Exit the program
    }

    // Loop to check divisors from 2 to n/2
    for (int i = 2; i <= (n / 2); i++)
    {
        // Check if `n` is divisible by `i`
        if (n % i == 0)
        {
            prime = 0; // If divisible, set prime flag to 0 (not prime)
            break;     // Break out of the loop
        }
    }

    // Output the result based on the prime flag
    if (prime == 1)
    {
        printf("%d is a prime number.\n", n); // Prime case
    }
    else
    {
        printf("%d is not a prime number.\n", n); // Not prime case
    }

    return 0; // Program ends successfully
}
```

#Step-by-Step Documentation
1. Input Handling
The user is prompted to input an integer using printf("Insert your number: ");.
The input is captured using scanf("%d", &n);.

Key Note: The &n is crucial for correctly storing the input value in the variable n.

2. Edge Case Check
Any number less than or equal to 1 (e.g., -5, 0, 1) is not a prime number.
If this condition is met, the program outputs the result immediately and exits using return 0;.

3. Primality Check
The program uses a for loop starting from 2 to n/2.
If n is divisible by any number in this range, it cannot be prime.
The prime flag is set to 0, and the loop breaks to save computation time.

4. Output
If the prime flag remains 1 after the loop, the number is prime.
Otherwise, it is not a prime number.
The output is displayed using printf.


