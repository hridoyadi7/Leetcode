# Leetcode

830. Positions of Large Groups
    vector<vector<int>> largeGroupPositions(string s) {
        vector<vector<int>>v;
        int i=0,j=0,count=0;
        int n=s.length();
        while(i<n && j<n)
        {
            if(s[i]==s[j])
            {
                j++;
                count++;
                if(j==n && count>=3)
                {
                    vector<int>v1;
                    v1.push_back(i);
                    v1.push_back(j-1);
                    v.push_back(v1);
                }
            }
            else
            {
                if(count>=3)
                {
                    vector<int>v1;
                    v1.push_back(i);
                    v1.push_back(j-1);
                    v.push_back(v1);
                }
                i=j;
                count=0;
            }
        }
        return v;
    }
	)
