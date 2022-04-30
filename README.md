# Codeforcescpp-374A
#include<bits/stdc++.h>
using namespace std;

int limit = 1000000000;

int moves(int n,int m,int i,int j,int a,int b){
  if(i==n && j==m) return 0;
  int x_diff,y_diff;
  x_diff = abs(i-n);
  y_diff = abs(j-m);
  if(x_diff%a==0 && y_diff%b==0 && (x_diff/a)%2==(y_diff/b)%2){
    return max(x_diff/a,y_diff/b);
  }
  return limit;
}

int main(){
  int n,m,i,j,a,b,mini=limit;
  cin >> n >> m >> i >> j >> a >> b;
  mini = min(moves(1,1,i,j,a,b),mini);
  mini = min(moves(1,m,i,j,a,b),mini);
  mini = min(moves(n,1,i,j,a,b),mini);
  mini = min(moves(n,m,i,j,a,b),mini);

  if((mini==limit || (i+a>n && i-a<1) || (j+b>m && j-b<1)) && mini!=0){
    cout << "Poor Inna and pony!";
  }
  else{
    cout << mini;
  }
  return 0;
}
