# DSA
my leetcode submissions

Trapping rain water
my solution:
```Java
class Solution {
    public int trap(int[] height) {
        int totalwater=0;
        for(int i=1;i<height.length;i++){
            int water=expand(height,i,i);
            totalwater+=water;
        }
        return totalwater;
    }
    public static int expand(int arr[],int left,int right){
        int leftmax=-1;
        int rightmax=-1;
        int curr=arr[left];
        while(left>0){
            if(arr[left-1]>leftmax){
                leftmax=arr[left-1];
            }
            left--;
        }
         while(right<arr.length-1){
            if(arr[right+1]>rightmax){
                rightmax=arr[right+1];
            }
            right++;
        }
        if(leftmax-curr>0&&rightmax-curr>0){
        if(leftmax<rightmax)
        return leftmax-curr;
        else
        return rightmax-curr;
        }
        else{
            return 0;
        }
    }
}
```

