#include <stdio.h>
#include <stdlib.h>

int main()
{
   int choice;
   int credit, price;
   int change;
   int number_of_notes;
   int number_of_coins;
   int continue_shopping = 1; // Flag to control the loop

   while (continue_shopping) {
      printf("\n====================================\n");
      printf("      COLD DRINK VENDING MACHINE\n");
      printf("====================================\n");
      printf("1. Coke - UGX.1500\n2. Pepsi - UGX.1000\n3. Sprite - UGX.1500\n4. Fanta - UGX.1500\n5. Mirinda - UGX.1000\n6. Exit\n\n");
      printf("Enter your choice: ");
      scanf("%d", &choice);

      if (choice == 1)
      {
         price = 1500;
         printf("You selected Coke. Insert UGX%d: ", price);
      }
      else if (choice == 2)
      {
         price = 1000;
         printf("You selected Pepsi. Insert UGX%d: ", price);
      }
      else if (choice == 3)
      {
         price = 1500;
         printf("You selected Sprite. Insert UGX%d: ", price);
      }
      else if (choice == 4)
      {
         price = 1500;
         printf("You selected Fanta. Insert UGX%d: ", price);
      }
      else if (choice == 5)
      {
         price = 1000;
         printf("You selected Mirinda. Insert UGX%d: ", price);
      }
      else if (choice == 6)
      {
         printf("Thank you! Have a nice day.\n");
         break; // Exit the loop
      }
      else
      {
         printf("Invalid selection! Please try again.\n");
         continue; // Go back to start of loop
      }

      scanf("%d", &credit);

      if (credit >= price)
      {
         printf("Dispensing your drink... Enjoy!\n");
         if (credit > price)
         {
            change = credit - price;
            printf("Returning change: UGX%d\n", change);

            // Calculate and display denominations
            if (change >= 50000){
                number_of_notes = change / 50000;
                change = change - (number_of_notes * 50000);
                printf("50000 notes: %d\n", number_of_notes);
            }

            if (change >= 20000){
                number_of_notes = change / 20000;
                change = change - (number_of_notes * 20000);
                printf("20000 notes: %d\n", number_of_notes);
            }

            if (change >= 10000) {
                number_of_notes = change / 10000;
                change = change - (number_of_notes * 10000);
                printf("10000 notes: %d\n", number_of_notes);
            }

            if (change >= 5000){
                number_of_notes = change / 5000;
                change = change - (number_of_notes * 5000);
                printf("5000 notes: %d\n", number_of_notes);
            }

            if (change >= 2000){
                number_of_notes = change / 2000;
                change = change - (number_of_notes * 2000);
                printf("2000 notes: %d\n", number_of_notes);
            }

            if (change >= 1000){
                number_of_notes = change / 1000;
                change = change - (number_of_notes * 1000);
                printf("1000 notes: %d\n", number_of_notes);
            }

            if (change >= 500){
                number_of_coins = change / 500;
                change = change - (number_of_coins * 500);
                printf("500 coins: %d\n", number_of_coins);
            }

            if (change >= 200){
                number_of_coins = change / 200;
                change = change - (number_of_coins * 200);
                printf("200 coins: %d\n", number_of_coins);
            }

            if (change >= 100){
                number_of_coins = change / 100;
                change = change - (number_of_coins * 100);
                printf("100 coins: %d\n", number_of_coins);
            }

            if (change >= 50){
                number_of_coins = change / 50;
                change = change - (number_of_coins * 50);
                printf("50 coins: %d\n", number_of_coins);
            }
         }
      }
      else
      {
         printf("Insufficient funds. Please top up: UGX%d\n", price - credit);
         // Don't return 0 here, just continue to next iteration
         continue;
      }

      // Ask if user wants to continue shopping
      printf("\nWould you like to make another purchase? (1 for Yes, 0 for No): ");
      scanf("%d", &continue_shopping);
   }

   printf("\nThank you for using our vending machine! Come again soon!\n");
   return 0;
}
