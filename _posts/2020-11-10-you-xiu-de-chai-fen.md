---
title:  "优秀的拆分"
date:   2020-11-10
excerpt: CSP题解。
project: true
tag: [CSP-2020-J]
comments: true
---
```c++
#include <bits/stdc++.h>
using namespace std;
int a[1000],cnt;
int main(){
	freopen("power.in","r",stdin);
	freopen("power.out","w",stdout);//常规读写
	int n;
	cin>>n;
	if(n%2!=0){cout<<-1<<endl;return 0;}//如果是奇数，排除
	int res=1;//用来不断乘二
	while(n!=0){
		a[++cnt]=n%2*res;
		n/=2;
		res*=2;
	}//循环，并存储每次的数据
	for(int i=cnt;i>=2;i--){
		if(a[i]!=0){
			cout<<a[i]<<' ';//输出啦
		}
	}
	return 0;
}
```

其实就是分类讨论而已。