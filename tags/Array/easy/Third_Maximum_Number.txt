//Description:
//Given a non-empty array of integers, return the third maximum number in this array. 
//If it does not exist, return the maximum number. The time complexity must be in O(n).
//-------------------------------------------
//Solution:
public class Solution{
	//Meythod 1
	//思路：遍历数组，同时记录三个最大的数。利用整形的包装类可以为null值来确定是否找到了第三大的数。
	//如果第三大的数为空，则返回第一大的数。否则意味着已经找到了第三大的数。
	public int thirdMax(int[] nums){
		Integer max1 = null;
        Integer max2 = null;
        Integer max3 = null;
        for (Integer n : nums) {
            if (n.equals(max1) || n.equals(max2) || n.equals(max3)) continue;
            if (max1 == null || n > max1) {
                max3 = max2;
                max2 = max1;
                max1 = n;
            } else if (max2 == null || n > max2) {
                max3 = max2;
                max2 = n;
            } else if (max3 == null || n > max3) {
                max3 = n;
            }
        }
        return max3 == null ? max1 : max3;
	}
} 