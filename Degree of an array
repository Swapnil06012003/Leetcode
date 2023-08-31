class Solution {
public:
    int findShortestSubArray(vector<int>& nums){
       
       int n = nums.size();
       map<int, int>freq;         //[number , freq]      
       int maxFreq = INT_MIN;

       for(int i=0 ; i<n ; i++)
       {
           freq[nums[i]]++;
           maxFreq = max(maxFreq, freq[nums[i]]);
       }

       set<int>st;   //contains elements with maximum freq

       for(auto it : freq)
       {
           if(it.second == maxFreq)
           {
               st.insert(it.first);
           }
       }

       map<int, int>startInd, endInd;    //[element , starting index]

       for(int i=0 ; i<n ; i++)
       {
           startInd[nums[i]] = -1;
           endInd[nums[i]] = -1;

       }

       for(int i=0 ; i<n; i++)
       {
           if(startInd[nums[i]] == -1)
           {
               //it's the first time the element has occured
               startInd[nums[i]] = i;
           }
       }

       for(int i=n-1 ; i>=0 ; i--)
       {
           if(endInd[nums[i]] == -1)
           {
               //last index
               endInd[nums[i]] = i;
           }
       }

       int len = INT_MAX;

       for(int i=0 ; i<n ; i++)
       {
           if(st.find(nums[i]) != st.end())     //only maxFreq element 
           {

              len = min(len , endInd[nums[i]] - startInd[nums[i]] + 1);
           }
       }

       return len;
        
    }
};
