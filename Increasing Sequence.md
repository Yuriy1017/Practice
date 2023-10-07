# Practice
#include<stdio.h>
int main()
{
	int i, n,m,b;
	int a[100];
	scanf("%d", &m); 
	for (int j = 0; j < m; j++)
	{
		scanf("%d", &n);
		for (i = 0; i < n; i++)scanf("%d", &a[i]);
		b = 1; i = 0;
		while (i < n)
		{
			if (a[i] != b)
			{
				i++; b++;
			}
			else b++;
		}
	
	printf("%d\n",b-1);
	}
	return 0;
}
