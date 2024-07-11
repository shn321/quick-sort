# quick-sort
#include<stdio.h>
#include<conio.h>
int main()
{
    int i,n,num[25];
    void quicksort(int[], int, int);
    printf("\n HOW MANY ELEMENTS ARE YOU GOING TO ENTER?:");
    scanf("%d",&n);
    printf("\n ENTER %d ELEMENTS:",n);
    for(i=0;i<n;i++)
    scanf("%d",&num[i]);
     printf("\n BEFORE SORTING ELEMENTS ARE:");
    for(i=0;i<n;i++)
        printf("%d",num[i]);
    quicksort(num,0,n-1);
    printf("\n AFTER SORTING ELEMENTS ARE:");
    for(i=0;i<n;i++)
        printf("%d",num[i]);
        return 0;
}
        void quicksort(int num[25], int first, int last)
        {
            int i,j,pivot,temp;
            if (first<last)
            {
                pivot=first; 
                i=first; 
                j=last;
                while(i<j)
                {
                    while(num[i]<=num[pivot]&& i<last)
                        i++;
                    while(num[j]>num[pivot])
                        j--;
                    if(i<j)
                    {
                        temp=num[i];
                        num[i]=num[j];
                        num[j]=temp;
                }
            }
            temp=num[pivot];
            num[pivot]=num[j]; num[j]=temp;
            quicksort(num,first,j-1);
            quicksort(num,j+1,last);
}
}
