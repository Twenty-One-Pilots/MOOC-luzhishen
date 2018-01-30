# MOOC-luzhishen
MOOC上的鲁智深吃馒头问题
今天在MOOC
https://www.icourse163.org/learn/HIT-69005?tid=1002224001#/learn/content?type=detail&id=1002961243&cid=1003430611
上看到这个问题，模仿高赞回答编写了程序，如下
注意一点就是N是101而不是100，不然由于数组a[]是从a[0]开始的，
就会产生数组中数据溢出，出现a[100]的情况。
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
