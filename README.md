# acm_practice
/*
捉鬼大师

世界上有鬼吗？如果有，那就一定有捉鬼大师，但是捉鬼大师的能力有限，他们只能
消灭位于他们东南面的鬼，也就是说，如果把捉鬼大师的位置视为原点，那么他们只
能消灭第四象限的鬼怪（位于X 轴的正半轴，Y 的负半轴）。
现在给出一些鬼的坐标和一些捉鬼大师的坐标，请问有多少鬼不能消灭？
1.输入：
第一行：给出两个数字g,b 对应于鬼的个数和捉鬼大师的个数。接下来的g 行，每行两
个整数，是每个鬼的坐标（之间用空格隔开），在接下来的b 行，每行两个整数，是每
个捉鬼大师的坐标（之间用空格个隔开），不会有重复的鬼和捉鬼大师出现。
2.输出：
无法被消灭的鬼的坐标x,y 之间用一个空格隔开，注意这些坐标输出顺序必须按照y 值
的降序排列，当y 相等时，则按照x 的降序排列
范例
输入：
5 2
4 2
2 2
1 1
1 -2
2 -3
3 2
0 -1
输出：
1 1
2 2
4 2
*/
#include <iostream>
#include<algorithm>
#include<string>
#include<vector>
using namespace std;
/* run this program using the console pauser or add your own getch, system("pause") or input loop */

int main(){
	int bx[100],by[100];
	int ax[100],ay[100];
	int tmpx[100],tmpy[100];
	int n,a,b,i,j,k = 0,tmp1,tmp2;
	cin >> b >> a;
	for(i = 0;i < b; i++){
        cin >> bx[i] >>by[i];
	}
	for(i = 0; i < a; i++){
        cin >> ax[i] >> ay[i];
	}
	for(i = 0; i < a; i++){
        for(j = 0; j < b; j++){
            if(ay[i]<by[j]&&ay[i]<by[j]){
                tmpx[k] = bx[j];
                tmpy[k] = by[j];
                k++;
            }
        }
	}
	cout<<endl;
	for(i = 0; i <k; i++){
        for(j = i+1; j < k; j++){
            if(tmpy[i]>tmpy[j]){
                swap(tmpy[i],tmpy[j]);
                swap(tmpx[i],tmpx[j]);
            }
            else if(tmpy[i]==tmpy[j]&&tmpx[i]>tmpx[j]){
                swap(tmpx[i],tmpx[j]);
                swap(tmpy[i],tmpy[j]);
            }
        }
	}
	for(i = 0; i < k; i++){
            cout << tmpx[i]<<" "<<tmpy[i]<<endl;

	}
	return 0;
}
