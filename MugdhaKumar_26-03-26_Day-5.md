class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n = nums.size();
        int insertPos = 0;
        for(int current = 0; current<n; current++){
            if (nums[current]!=0){
                if (current!=insertPos){
                    swap(nums[current], nums[insertPos]);
                }
                insertPos++;
            }
        }
    }
};

// EXPLANATION
// > current is used for scanning
// >insertPos tracks the position for insertion of non- zero integers
// >Line 8 : if(current!=insertPos) is a small optimisation we do to avoid swapping same positions
