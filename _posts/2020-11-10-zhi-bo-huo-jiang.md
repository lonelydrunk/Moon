---
title:  "直播获奖"
date:   2020-11-12
excerpt: CSP题解。
project: true
tag: [CSP-2020-J]
comments: true
---
```c++
#include<iostream>
#include<cstdio>
using namespace std;
int main(){
	freopen("live.in","r",stdin);
	freopen("live.out","w",stdout);//常规读写
	int i,n,w,tong[10005]={0};//桶排序准备
	cin>>n>>w;
	for(i=1;i<=n;i++){
		int x;//申请临时变量
		cin>>x;
        tong[x]++;//桶排序，对应加1
		int p=max(1,i*w/100);//每次获奖的人数
		for(int i=600;i>=0;i--){
			p-=tong[i];//每次减一下
			if(p<=0){//如果比规定人数多，输出
				cout<<i<<' ';
				break;
			}
		}
	}
	return 0;//结束啦
}
```

这题很水，由于分数有限制，<=600分，桶排序就行。

（用sort的我很悲伤）