# acm_practice
/*质因数分解

问题描述
求出区间[a,b]中所有整数的质因数分解。
输入格式
输入两个整数a，b。
输出格式
每行输出一个数的分解，形如k=a1*a2*a3...(a1<=a2<=a3...，k 也是从小到大的)(具体
可看样例)
样例输入
3 10
样例输出
3=3
4=2*2
5=5
6=2*3
7=7
8=2*2*2
9=3*3
10=2*5
提示
先筛出所有素数，然后再分解。
数据规模和约定
2<=a<=b<=10000
出现次数最多的整数*/
#include <iostream>
#include<algorithm>
#include<string>
#include<vector>
using namespace std;
/* run this program using the console pauser or add your own getch, system("pause") or input loop */
bool isPrime(int num){
    int tmp =num- 1;
    for(int i= 2;i <=tmp; i++)
      if(num %i== 0)
         return 0 ;
    return 1 ;
}
int fun(int num){
    if(num%2==0){
        if(num==2){
            cout<<"2"<<endl;
            return 0;
        }
        num/=2;
        cout<<"2*";
        fun(num);
    }
    else if(num%3==0){
        if(num==3){
            cout<<"3"<<endl;
            return 0;
        }
        num/=3;
        cout<<"3*";
        fun(num);
    }
    else{
        cout<<num<<endl;
        return 0;
    }

}
int main(){
    int i,a,c,b,begin,end;
    cin>>begin>>end;
    for( i = begin; i <= end; i++){
        if(isPrime(i) == 1)
            cout<<i<<"="<<i<<endl;
        else{
            cout<<i<<"=";
            fun(i);
        }
    }
	return 0;
}
