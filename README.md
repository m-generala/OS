OS
==
#include<stdio.h>
#include<stdlib.h>
#include<pthread.h>
#define SIZE 10

int sorter (const void * a, const void * b)
{
   return ( *(int*)a - *(int*)b );
}
void* QSORT(void* arg){
	qsort(arg, SIZE, sizeof(int), sorter);
}

int main(){
int arr[SIZE];
int i,j;
for (i = SIZE-1 ; i>=0 ; i--)
	{
		arr[j]= i;
		j++;
	};
	pthread_t thread;
	pthread_create(&thread,NULL,QSORT,arr);

	
	printf("\nsus\n");
	for (i=0;i<SIZE;i++){
	
	printf("%d\n",arr[i]);
	}
	return 0;
}

