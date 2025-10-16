#include <stdio.h>

int main() {
    int choice;
    float balance = 1000.00;
    float amount;

    do {
        printf("\n-POWERBANK-\n");
        printf("[1] Balance Inquiry\n");
        printf("[2] Deposit\n");
        printf("[3] Withdraw\n");
        printf("[4] Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1: 
                printf("Your current balance: P%.2f\n", balance);
                 break;
            case 2: 
                printf("Enter amount to deposit: P");
                scanf("%f", &amount);
                if (amount >0) {
                    balance += amount;
                    printf("Deposit Successful. New Balance: P%.2f\n", balance);
                } else {
                    printf("Invalid deposit amount.\n");
                }
                break;
            case 3:
                printf("Enter amount to withdraw: P");
                scanf("%f", &amount);
                if (amount <= 0) {
                    printf("Invalid withdrawal amount.\n");
                } else if (balance - amount < 100.00) {
                    printf("Withdrawal denied! You must maintain at lease P100.00 in your account.\n");
                } else {
                    balance -= amount;
                    printf("Withdrawal successful. New balance: P%.2f\n", balance);
                }
                break;
            case 4:
                printf("Thank you for using POWERBANK!\n");
                break;
            default:
                printf("Invalid choice. Please select valid option.\n");
    }
}   while (choice != 4);
     return 0;
}
