# Bill
\\Bill of a restauarant
#include <stdio.h>

int main() {
    
    char menu[][20] = {"Burger", "Pizza", "Sandwich", "French Fries", "Coke"};
    float prices[] = {250, 350, 200, 150, 100};

    int numItems;
    int i;
    char item[20];
    float total = 0.0;

    printf("Welcome to the Restaurant!\n");
    printf("Menu:\n");
    for (i = 0; i < 5; i++) {
        printf("%d. %s - Rs%.2f\n", i + 1, menu[i], prices[i]);
    }

    printf("\nEnter the number of items you want to order: ");
    scanf("%d", &numItems);

   
    for (i = 0; i < numItems; i++) {
        printf("\nEnter item name: ");
        scanf("%s", item);

        
        int found = 0;
        for (int j = 0; j < 5; j++) {
            if (strcmp(item, menu[j]) == 0) {
                total += prices[j];
                found = 1;
                break;
            }
        }

        if (!found) {
            printf("Item not found in the menu!\n");
            i--;  
        }
    }

  
    printf("\nBill Details\n");
    printf("Total Items: %d\n", numItems);
    printf("Total Bill: Rs%.2f\n", total);

    return 0;
}

