# MOOC-luzhishen
MOOC上的鲁智深吃馒头问题
#include <stdio.h>
#define N 101
void Find(int a[], int n);
void Print(int a[], int n);
int main()
{
	int a[N];
	Find(a , N);
	Print(a, N);
	return 0;
}
void Find(int a[], int n)
{
	int i, count = 0, sum = 0;
	for (i = 0; i < n; i++)
		a[i] = i;
	do
	{
		for (i = 1; i < n; i++)
		{
			if (a[i] == 0)continue;
			count++;
			if (count % 5 == 0)
			{
				a[i] = 0;
				sum++;
			}
		}
	} while (sum != 99);
}
void Print(int a[], int n)
{
	int i;
	for (i =1; i < n; i++)
	{
		if (a[i] != 0)
		{
			printf("Lu Zhishen's number is %d\n", i);
		}
	}
}
