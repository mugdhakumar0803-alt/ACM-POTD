class Solution {
public:
    int climbStairs(int n) {
        if (n <= 2) return n;
        int prev = 1, curr = 2;
        for (int i = 3; i <= n; i++) {
            int temp = prev + curr;
            prev = curr;
            curr = temp;
        }
        return curr;
    }
};
