---
layout: post
title:  方格取数
date:   2020-11-11
excerpt: CSP题解。
tag:
- CSP-2020-J
comments: true
---
```c++
#include <bits/stdc++.h>
using namespace std;
const int MAXN=1001;
long long dp[MAXN][MAXN];
long long a[MAXN][MAXN] ;
int main(){
	int n,m;
	cin>>n>>m;
	for(int i=1;i<=n;i++){
		for(int j=1;j<=m;j++){
			cin>>a[i][j];
		}
	}
	for(int j=1;j<=m;j++){
		for(int i=1;i<=n;i++){
			dp[i][j]=dp[i][j-1]+a[i][j];
		}
		long long res=dp[1][j-1] + a[1][j];
		for(int i=2;i<=n;i++){
			dp[i][j]=max(dp[i][j],res+a[i][j]);
			res=max(dp[i][j-1],res)+a[i][j];
		}
		res=dp[n][j-1]+a[n][j];
		for (int i=n-1;i>=1;i--){
			dp[i][j]=max(dp[i][j],res+a[i][j]);
			res=max(dp[i][j-1],res)+a[i][j] ;
		}
	}
	cout<<dp[n][m]<<endl;
	return 0;
}
```

这题不加注释，懂的都懂，不懂的也不多解释。。。