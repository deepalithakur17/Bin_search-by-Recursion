# Bin_search-by-Recursion
//binary search of number by recursions
#include<bits/stdc++.h>
using namespace std;

bool solve(int *arr,int size,int key)
{
    int mid=(size)/2;
    cout<<mid<<endl;
    if(key==arr[mid])
    {
        cout<<"element found at index "<<mid<<endl;
        return 0;
        
    }
    else if(mid==0||mid>=sizeof(arr)/4)
    {
        cout<<"element not found"<<endl;
        return 0;
    }
    else
    {
        if(key>arr[mid])
        {
            size=size+mid;
            solve(arr,size,key);
        }
        else
        {
            size=size-mid;
            solve(arr,size,key);
        }
    }
    
    
}

int main()
{
    int n;
    cout<<"enter the number of elements: ";
    cin>>n;
    int arr[n];
    for(int i=0;i<n;i++)
    {
        cout<<"enter arr["<<i<<"]=";
        cin>>arr[i];
    }
    int key;
    cout<<"enter an element to search :";
    cin>>key;
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        if(arr[j]>arr[j+1])
        {
            int temp=arr[j];
            arr[j]=arr[j+1];
            arr[j+1]=temp;
        }
    }
    for(int i=0;i<n;i++)
    {
        cout<<arr[i]<<" ";
    }
    cout<<endl;
    solve(arr,n-1,key);
    
    
}
