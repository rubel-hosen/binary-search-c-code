#include<stdio.h>
int main()
{
    int n,i,choice,j;
    printf("How money number?\t");
    scanf("%d",&n);
    int arr[n];
    printf("\nEnter your number:\n");
    for(i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
    }
    printf("\nEnter your choice number:\t");
    scanf("%d",&choice);

    int found = binary_search(arr,n,choice);
    printf("\nYour index location is: %d",found);
    return 0;
}

int binary_search(int arr[],int n,int choice)
{
    int mid;
    int left=0;
    int right=n-1;

    while(left<=right)
    {
        mid=(left+right)/2;
        if(arr[mid]==choice)
        {
            return mid;
        }
        if(arr[mid]<choice)
        {
            left=mid+1;
        }
        else{
            right=mid-1;
        }
    }

    return -1;

}
