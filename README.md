# days_in_a_month
#include <stdio.h>

int main() {
    int month, year;

    // Get user input for month and year
    printf("Enter month (1-12): ");
    scanf("%d", &month);
    printf("Enter year: ");
    scanf("%d", &year);

    // Check for valid month input
    if (month < 1 || month > 12) {
        printf("Invalid month input.\n");
        return 1; // Exit program with error code
    }

    // Determine the number of days in the given month
    int daysInMonth;
    switch (month) {
        case 4: case 6: case 9: case 11:
            daysInMonth = 30;
            break;
        case 2:
            if ((year % 4 == 0 && year % 100 != 0) || year % 400 == 0) {
                daysInMonth = 29; // Leap year
            } else {
                daysInMonth = 28; // Non-leap year
            }
            break;
        default:
            daysInMonth = 31;
    }

    // Output the result
    printf("There are %d days in month %d of year %d.\n", daysInMonth, month, year);

    return 0;
}
