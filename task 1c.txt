import java.util.Arrays;

public class ProductExceptSelf {
    public static int[] productExceptSelf(int[] nums) {
        int n = nums.length;
        int[] left = new int[n];
        int[] right = new int[n];
        int[] answer = new int[n];
        
        left[0] = 1;
        for (int i = 1; i < n; i++) {
            left[i] = nums[i - 1] * left[i - 1];
        }
        
        right[n - 1] = 1;
        for (int i = n - 2; i >= 0; i--) {
            right[i] = nums[i + 1] * right[i + 1];
        }
        
        for (int i = 0; i < n; i++) {
            answer[i] = left[i] * right[i];
        }
        
        return answer;
    }

    public static void main(String[] args) {
        int[] ar = {1, 2, 3, 4, 5};
        int[] result = productExceptSelf(ar);
        System.out.println("Input Array: " + Arrays.toString(ar));
        System.out.println("Product Except Self: " + Arrays.toString(result));
    }
}
