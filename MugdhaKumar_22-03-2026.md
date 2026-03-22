class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        if(nums.empty()) return 0;
        int n = nums.size();
        int i = 0; //our slow pointer
        for(int j = 1; j<n; j++){
            if(nums[i] != nums[j]){
                i++;
                nums[i]=nums[j];//To overwrite the element repeated
            }
        }
        return i+1;
    }
};
