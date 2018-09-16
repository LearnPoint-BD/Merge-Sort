//# Merge-Sort
#include <stdio.h>

int Merge(int L[],int R[],int A[],int nL,int nR)

{

    int i=0,j=0,k=0;

    while(i<nL&&j<nR){

        if(L[i]<R[j]){

        A[k++]=L[i++];

        }

        else{

        A[k++]=R[j++];

        }

    }

    while(i<nL){

        A[k++]=L[i++];


    }

    while(j<nR){

        A[k++]=R[j++];

    }


}

void MergeSort(int A[],int n)

{

    int i,mid;

    if(n<2){

        return;

    }

    else{

        mid=n/2;

        int Left[mid],Right[n-mid];

        for(i=0;i<mid;i++){

            Left[i]=A[i];

        }

        for(i=mid;i<n;i++){

            Right[i-mid]=A[i];

        }

        MergeSort(Left,mid);

        MergeSort(Right,n-mid);

        Merge(Left,Right,A,mid,n-mid);

    }




}

int main(void)
{

	int i,n;
	printf("Enter the size of the array\n");

	scanf("%d",&n);
	int A[n];

	printf("Enter the array elements:");

	for(i=0;i<n;i++){

	    scanf("%d",&A[i]);

	}


MergeSort(A,n);


for(i=0;i<n;i++){

	    printf("%d ",A[i]);

	}

	return 0;

}


