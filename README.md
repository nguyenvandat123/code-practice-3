# code-practice-3
![image](https://user-images.githubusercontent.com/127211886/232990990-cd1c8d2d-52cf-4e3e-be58-d895fc3462ee.png)
```sh
#include <iostream>
#include <cstdlib>
using namespace std;
void print_marks(int i,int a[9][7]);
int sum_marks(int i,int b[9][7]);
void sort_sum_marks(int c[9][7]);
int main()
{
	int arrays_marks[9][7];
	for (int j=0;j<6;j++)
	{
		arrays_marks[0][j]=j;
	}
	cout<<"  "<<"\t"<<"\t";
	for (int j=1;j<6;j++)
	{
		cout<<"T"<<arrays_marks[0][j]<<"\t"<<"\t";
	}
	cout<<"sum_marks";
	for (int i=1;i<9;i++)
	{
		for (int j=1;j<6;j++)
		{
			arrays_marks[i][j]=rand()%10+1;
		}
	}
	for(int i=1;i<9;i++)
	{
		arrays_marks[i][6]=sum_marks(i,arrays_marks);
	}
	for (int i=1;i<9;i++)
	{
		print_marks(i,arrays_marks);
		cout<<arrays_marks[i][6];
	}
	cout<<endl;
	sort_sum_marks(arrays_marks);
	return 0;
}
void print_marks(int i, int a[9][7])
{
	cout<<endl;
	cout<<"student"<<i<<"\t";
	for(int j=1;j<6;j++)
	{
		cout<< a[i][j]<<"\t"<<"\t";
	}	
}
int sum_marks(int i,int b[9][7])
{
	int sum=0;
	for(int j=1;j<6;j++)
	{
		sum=sum+b[i][j];
	}
	return sum;
}
void sort_sum_marks(int c[9][7])
{
	int z=1;
	int max=c[z][6];
	for (int i=1;i<9;i++)
	{
		if (c[i][6]>max)
		{
		max=c[i][6];
		z=i;
		} 
	}
	print_marks(z,c);
	cout<<sum_marks(z,c);
}
```
