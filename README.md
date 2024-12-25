# Library Management in c


    #include <stdio.h>
    #include <stdlib.h>
    #include <string.h>

    struct library {
        char bookname[20];
        char author[20];
        int pages;
        float price;
    };

    int main() {
        struct library lib[100];
        char bkname[20], arname[20];
        int i, input, count;
        i = input = count = 0;

        while (input != 5) {
            printf("\n\n********######"
                   "WELCOME TO E-LIBRARY "
                   "#####********\n");
            printf("\n\n1. Add book information\n"
                   "2. Display book information\n"
                   "3. List all books of a given author\n"
                   "4. List the count of books in the library\n"
                   "5. Exit\n");
            printf("\nEnter your choice: ");
            scanf("%d", &input);

            switch (input) {
                case 1:
                    printf("Enter book name: ");
                    scanf("%s", lib[count].bookname);

                    printf("Enter author name: ");
                    scanf("%s", lib[count].author);

                    printf("Enter pages: ");
                    scanf("%d", &lib[count].pages);
    
                    printf("Enter price: ");
                    scanf("%f", &lib[count].price);
                    count++;
                    break;
    
                case 2:
                    printf("You have entered the following information:\n");
                    for (i = 0; i < count; i++) {
                        printf("\nBook Name: %s\n", lib[i].bookname);
                        printf("Author Name: %s\n", lib[i].author);
                        printf("Pages: %d\n", lib[i].pages);
                        printf("Price: %f\n", lib[i].price);
                    }
                    break;
    
                case 3:
                    printf("Enter author name to search: ");
                    scanf("%s", arname);
                    for (i = 0; i < count; i++) {
                        if (strcmp(arname, lib[i].author) == 0) {
                            printf("\nBook Name: %s\n", lib[i].bookname);
                            printf("Author Name: %s\n", lib[i].author);
                            printf("Pages: %d\n", lib[i].pages);
                            printf("Price: %f\n", lib[i].price);
                        }
                    }
                    break;
    
                case 4:
                    printf("\nNumber of books in the library: %d\n", count);
                    break;
    
                case 5:
                    printf("Exiting the program. Goodbye!\n");
                    exit(0);
    
                default:
                    printf("\nInvalid choice! Please try again.\n");
            }
        }
        return 0;
    }

