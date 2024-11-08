## SOURCE CODE

#include <stdio.h>

void add(int *a, int *b, int *result) {
    *result = *a + *b;
}

void subtract(int *a, int *b, int *result) {                           
    *result = *a - *b;
}

void multiply(int *a, int *b, int *result) {
    *result = *a * *b;
}

void divide(int *a, int *b, int *quotient, int *remainder) {
    if (*b != 0) {
        *quotient = *a / *b;
        *remainder = *a % *b;
    } else {
        printf("Error: Division by zero!\n");
    }
}

int main() {
    int num1, num2, result, quotient, remainder;
    char operation;
    char choice;

    do {
        printf("\n<<<<<<<<<<<<<<<<< CALCULATOR >>>>>>>>>>>>>>>>>>>>\n");
        
        printf("Enter first number:\t");
        scanf("%d", &num1);
        
        printf("Enter second number:\t");
        scanf("%d", &num2);
        
        printf("Enter operation (+, -, *, /):\t");
        scanf(" %c", &operation);
        
        switch (operation) {
            case '+':
                add(&num1, &num2, &result);
                printf("Result: %d + %d = %d\n", num1, num2, result);
                break;
            case '-':
                subtract(&num1, &num2, &result);
                printf("Result: %d - %d = %d\n", num1, num2, result);
                break;
            case '*':
                multiply(&num1, &num2, &result);
                printf("Result: %d * %d = %d\n", num1, num2, result);
                break;
            case '/':
                divide(&num1, &num2, &quotient, &remainder);
                if (num2 != 0) {
                    printf("Division result:\n");
                    printf("Quotient: %d\n", quotient);
                    printf("Remainder: %d\n", remainder);
                }
                break;
            default:
                printf("ERROR: Invalid operation\n");
                break;
        }
        
        printf("\nWould you like to perform another calculation? (y/n): ");
        scanf(" %c", &choice);
        
    } while (choice == 'y' || choice == 'Y');

    printf("Thank you for using the calculator!\n");
    
    return 0;
} 
