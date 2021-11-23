EA1 - Extra Activity File Handling (for those who have not present last practical)

#include <stdio.h>
#include <stdlib.h>

void main()
{
    FILE *fptr;
    int idnumber, idnumber2;
    char studname [1000], studname2 [1000];
    float grade1, grade2, grade3;
    float grade4, grade5, grade6;
    float average, total;



    fptr = fopen("Student Data 1.txt", "w");

    if (fptr == NULL)
    {
    printf("File does not exists! \n");
    return;
    }

    printf (" [DATA FILE] \n\n");
    printf(" STUDENT #1 \n");
    printf(" Enter the name : ");
    scanf("%s", studname);
    fprintf(fptr, "Name : %s\n", studname);


    printf("\n Enter the ID number : ");
    scanf("%d", &idnumber);
    fprintf(fptr, "ID Number : %d\n", idnumber);


    printf("\n Math Grade : ");
    scanf("%f", &grade1);
    fprintf(fptr, "Math Grade : %.2f\n",grade1);


    printf("\n Science Grade : ");
    scanf("%f", &grade2);
    fprintf(fptr, "Sciencce Grade : %.2f\n",grade2);

    printf("\n English Grade : ");
    scanf("%f", &grade3);
    fprintf(fptr, "English Grade : %.2f\n",grade3);


    total = grade1+grade2+grade3;
    printf("\n Total Grade : %.2f\n", total );
    fprintf(fptr, "Total Grade : %.2f\n", total);

    average = (grade1+grade2+grade3)/3;
    printf(" Grade Average : %.2f\n\n\n", average);
    fprintf(fptr, "Grade Average : %.2f\n", average);


    fclose(fptr);


    fptr = fopen("Student Data 2.txt", "w+");

    if (fptr == NULL)
    {
    printf("File does not exists! \n");
    return;
    }



    printf(" STUDENT #2");
    printf("\n Enter the name : ");
    scanf("%s", studname2);
    fprintf(fptr, "Name : %s\n", studname2);


    printf("\n Enter the ID number : ");
    scanf("%d", &idnumber2);
    fprintf(fptr, "ID Number : %d\n", idnumber2);


    printf("\n Math Grade : ");
    scanf("%f", &grade4);
    fprintf(fptr, "Math Grade : %.2f\n", grade4);


    printf("\n Science Grade : ");
    scanf("%f", &grade5);
    fprintf(fptr, "Science Grade : %.2f\n", grade5);

    printf("\n English Grade : ");
    scanf("%f", &grade6);
    fprintf(fptr, "English Grade : %.2f\n", grade6);


    total = grade4+grade5+grade6;
    printf("\n Total Grade : %.2f\n", total );
    fprintf(fptr, "Total Grade : %.2f\n", total);

    average = (grade4+grade5+grade6)/3;
    printf(" Grade Average : %.2f\n\n\n", average);
    fprintf(fptr, "Grade Average : %.2f\n", average);


    fclose(fptr);



    return 0;
}
M3FT - Strings Final Task
#include <stdio.h>
#include <string.h>
int string_length(char s[]) {
   int i = 0;

   while(s[i]!='\0')
      i++;

   return i;
}
void string_reverse(char st[]) {
   int i,j,len;
   char ch;

   j = len = string_length(st) - 1;
   i = 0;

   while(i < j) {
      ch = st[j];
      st[j] = st[i];
      st[i] = ch;
      i++;
      j--;
   }
}

int main (void) {
   char strn[100];
   printf("Enter sentence: ");
   fgets(strn,sizeof(strn),stdin);



   char reverse[100] = "", temp[50];
   int i, j, n;

   n = strlen(strn)-1;

   for(i = n-1; i >= 0; --i) {

      for(j = 0; i >= 0 && strn[i] != ' '; --i,++j)
         temp[j] = strn[i];

      temp[j] = '\0';

      string_reverse(temp);

      strcat(reverse,temp);
      strcat(reverse," ");
   }

   printf("Original - %s\0", strn);
   printf("Reversed - %s\n",reverse);

   return 0;
