#include<stdio.h>
int main()
{
	int i,j;
	printf(" ");
	for(j=1;j<=9;j++)
	printf("%4d",j);
	printf("\n");
	printf(" ");
	for(j=1;j<=9;j++)
	printf("   -");
    printf("\n");          //打印表头
	for(i=1;i<=9;i++)
	{
		printf("%d",i);
		for(j=1;j<=i;j++)
			printf("%4d",i*j);//打印乘法表
			printf("\n");
		}	
	return 0;
 }
