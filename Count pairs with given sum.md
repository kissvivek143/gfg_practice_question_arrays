## Count pairs with given sum

Given an array of N integers, and an integer K, find the number of pairs of elements in the array whose sum is equal to K.


Example 1:

Input:
N = 4, K = 6
arr[] = {1, 5, 7, 1}
Output: 2
Explanation: 
arr[0] + arr[1] = 1 + 5 = 6 
and arr[1] + arr[3] = 5 + 1 = 6.


Example 2:

Input:
N = 4, K = 2
arr[] = {1, 1, 1, 1}
Output: 6
Explanation: 
Each 1 will produce sum 2 with any 1.


```java

//User function Template for Java

class Solution {
    int getPairsCount(int[] arr, int n, int k) {
        // code here
        HashMap<Integer, Integer> m = new HashMap<>();
        int count = 0;
        
        for(int i=0; i<n; i++){
            if(m.containsKey(k - arr[i])){
                count += m.get(k - arr[i]);
            }
            if(m.containsKey(arr[i])){
                m.put(arr[i], m.get(arr[i]) + 1);
            }
            else{
                m.put(arr[i], 1);
            }
        }
        
        return count;
    }
}



## Time complexity - O(n)
## space complexity - O(n)
