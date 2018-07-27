#include<iostream>
#include<cstring>
using namespace std;
const int MAXN = 1e5+5;
char str[MAXN];
int len;
int Next[MAXN];
int res[MAXN];
void getNext()
{
	Next[0] = -1;
	int i = 0, j = -1;
	while(i <= len)
	{
		if(j == -1 || str[i] == str[j])
		{
			Next[++i] = ++j;
		}
		else
		{
			j = Next[j];
		}
	}
}
int main()
{
	for(;;){
	
	scanf("%s",str);
	len = (int)strlen(str);
	getNext();
//	for(int i = 1; i <= len; i++)
//		printf("%d ",Next[i]);
//	printf("\n");
memset(res,0,sizeof(res));
	for(int i = len; i >= 1; i--)
	{
		res[i]++;
		res[Next[i]] += res[i];
		printf("res[%d]=%d Next[%d]=%d res[%d]=%d\n",i,res[i],i,Next[i],Next[i],res[Next[i]]);
	}
	for(int i = 1; i<=len; i++) {
		printf("%d ",res[i]);
}
	printf("\n");
}
//	long long ans = 0;
//	for(long long i = 1; i <= len; i++)
//	{
//		ans = max(i * res[i], ans);
//	}
//	printf("%lld\n",ans);
	return 0;
}
https://github.com/Ostrichcrab/KMP/blob/master/2%5DZ%25YTCWW%40F2731F%7B%60FGE%60O.png
