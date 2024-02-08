## Peak element

Given an array of integers arr[] of size n, find any one of its peak elements. An element is considered to be peak if it's value is greater than or equal to the values of its adjacent elements (if they exist). The array is guaranteed to be in ascending order before the peak element and in descending order after it.




Note: The output will be 1 if the index returned by your function is correct; otherwise, it will be 0.




Example 1:

Input: 
n = 3
arr[] = {1, 2, 3}
Possible Answer: 2
Generated Output: 1
Explanation: The index returned is 2, which corresponds to the value 3. Since 3 is indeed a peak element in this array, the generated output is 1, indicating that the returned index is correct.





Example 2:

Input:
n = 3
arr[] = {3, 4, 2}
Possible Answer: 1
Output: 1
Explanation: The index returned is 1, which corresponds to the value 4. Since 4 is indeed a peak element in this array, the generated output is 1, indicating that the returned index is correct.



Expected Time Complexity: O(log n).
Expected Auxiliary Space: O(1)



```java
class Solution
{
	// Function to find the peak element
	// arr[]: input array
	// n: size of array a[]
	public int peakElement(int[] arr,int n)
    {
       //add code here.
       
       int l = 0;
       int r = n-1;
       int mid = 0;
       
       while(l <= r){
           mid = (l+r) >> 1;
           if( (mid == 0 || arr[mid-1] <= arr[mid]) && 
                (mid == n-1 || arr[mid+1] <= arr[mid]) ){
               break;
           }
           if(mid > 0 && arr[mid-1] > arr[mid]){
               r = mid-1;
           }
           else{
               l = mid+1;
           }
       }
       
       return mid;
    }
}
