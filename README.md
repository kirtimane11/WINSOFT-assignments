# WINSOFT-assignments

import java.util.Arrays;
public class MergeArrays {
    public static void mergeArrays(int[] X, int[] Y) {
        int m = X.length;
        int n = Y.length;
        
        int index = m - 1;
        int i = m - n - 1;
        int j = n - 1;

        while (i >= 0 && j >= 0) {
            if (X[i] > Y[j]) {
                X[index--] = X[i--];
            } else {
                X[index--] = Y[j--];
            }
        }  
        while (j >= 0) {
            X[index--] = Y[j--];
        }
    }
       public static void main(String[] args) {
        int[] X = { 0, 2, 0, 3, 0, 5, 6, 0, 0 };
        int[] Y = { 1, 8, 9, 10, 15 };

        mergeArrays(X, Y);
        System.out.println("Merged array: " + Arrays.toString(X));
    }
}
