# unsorted-continuous-subarray

class Solution {
public:
    int findUnsortedSubarray(vector<int>& arr) 
    {
        if(arr.size()==1)
        {
            return 0;
        }
        vector <int> newArr=arr;
        sort(newArr.begin(),newArr.end());
        int n=arr.size();
        int i=0,j=n-1;
        while(i<j)
        {
            if(arr[i]==newArr[i])
            {
                i++;
            }
            if(arr[j]==newArr[j])
            {
                j--;
            }
            if(arr[i]!=newArr[i] && arr[j]!=newArr[j])
            {
                break;
            }
        }
        if(i==j)
        {
            return 0;
        }
        else
        {
            return j-i+1;
        }
    }
};
