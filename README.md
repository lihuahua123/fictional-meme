#include <iostream>

using namespace std;
void swap(int& a ,int& b )
{
    int temp=a;
    a=b;
    b=temp;

}
bool issort(int s[],int size)
{
    for(int i=1;i<size;i++)
    {
        if(s[i-1]>s[i])
        {
          return false;
        }
    }
    return true;
}

int main()
{
    int i=1;
    int num;
    cin>>num;
    int s[1000];
    while(num--)
    {
        int all;
        cin>>all;
        int count=0;
        for(int i=0;i<all;i++)
        {
            cin>>s[i];
        }
        while(!issort(s,all))
        {for(int i=all-1;i>0;i--)
        {
            if(s[i-1]>s[i])
            {
                swap(s[i-1],s[i]);
                count++;
            }
        }}

        cout<<"Scenario #"<<i<<":"<<endl;
        cout<<count<<endl;
        cout<<endl;
         for(int i=0;i<all;i++)
        {
            cout<<s[i]<<" ";
        }
        cout<<endl;
        i++;
    }
    return 0;
}

