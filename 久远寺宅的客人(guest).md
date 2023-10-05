# Practice
#include<stdio.h>
int cmp(const void* a, const void* b)
{
	return *(int*)b - *(int*)a;
}
int main()
{
	int i, n,m,k,c=0;
	int a[1000],b[1000];
	scanf("%d%d%d", &n,&m,&k);
	for(i=0;i<n;i++)scanf("%d", &a[i]);
	for(i=0;i<m;i++)scanf("%d", &b[i]);
	qsort(a,n,sizeof(int),cmp);
	qsort(b, m,sizeof(int),cmp);
	for (i = 0; i < m; i++)
	{
		int kk = k;
		if (b[i] > a[i])
		{
			for(int j=i;j>=0;j--)
			{
				if (a[j] + kk >= b[i])
				{
					a[j] += kk;
					c += kk / k;
					break;
				}
				if (j == 0) { kk += k; j = i+1; }
			}
			qsort(a, n, sizeof(int), cmp);
			i = -1;
		}

	}
	printf("%d\n",c);
	return 0;
}
