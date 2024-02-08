## Check if two arrays are equal or not


Given two arrays A and B of equal size N, the task is to find if given arrays are equal or not. Two arrays are said to be equal if both of them contain same set of elements, arrangements (or permutation) of elements may be different though.




Note : If there are repetitions, then counts of repeated elements must also be same for two array to be equal.





Example 1:

Input:
N = 5

A[] = {1,2,5,4,0}

B[] = {2,4,5,0,1}

Output: 1
Explanation: Both the array can be 
rearranged to {0,1,2,4,5}



Example 2:

Input:
N = 3

A[] = {1,2,5}

B[] = {2,4,15}

Output: 0
Explanation: A[] and B[] have only 
one common value.


Expected Time Complexity : O(N)

Expected Auxilliary Space : O(N)


```java

//User function Template for Java

class Solution{
    //Function to check if two arrays are equal or not.
    public static boolean check(long A[],long B[],int N)
    {
        //Your code here
        Arrays.sort(A);
        Arrays.sort(B);
        
        for(int i=0; i<N; i++){
            if(A[i] != B[i]){
                return false;
            }
        }
        
        return true;
    }
}
