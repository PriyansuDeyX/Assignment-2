# Assignment-2

int largest(int arr[], int n) {
    int max = arr[0]; // assume first element is largest
    for (int i = 1; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    return max;
}


 2 .  class Solution:
       def getSecondLargest(self, arr, n):
        first = second = -1
        
        for i in range(n):
            if arr[i] > first:
                second = first
                first = arr[i]
            elif arr[i] > second and arr[i] != first:
                second = arr[i]
        
        return second

3.  class Solution {
  public:
    void pushZerosToEnd(vector<int>& arr) {
        int n = arr.size();
        int count = 0;  // Index to place the next non-zero element

        // Traverse the array
        for (int i = 0; i < n; i++) {
            if (arr[i] != 0) {
                // Place current non-zero at the next available position
                arr[count++] = arr[i];
            }
        }

        // Fill the remaining positions with zeros
        while (count < n) {
            arr[count++] = 0;
        }
    }
}

4. class Solution {
  public:
    vector<int> frequencyCount(vector<int>& arr) {
        int n = arr.size();
        vector<int> freq(n, 0); // initialize a result vector of size n with 0s

        for (int i = 0; i < n; i++) {
            // arr[i] should be in range 1 to n
            if (arr[i] >= 1 && arr[i] <= n) {
                freq[arr[i] - 1]++;  // use (value - 1) for 0-based index
            }
        }

        return freq;
    }
};


5.

def reverseArray(arr):
    return arr[::-1]
   
n = int(input())
arr = list(map(int, input().split()))

res = reverseArray(arr)

print(*res)

6.
    #include <stdio.h>
    void spiralOrder(int n, int m, int mat[n][m], int result[], int *size) {
    int top = 0, bottom = n - 1, left = 0, right = m - 1;
    *size = 0;
    
    while (top <= bottom && left <= right) {
        // Traverse top row
        for (int i = left; i <= right; i++)
            result[(*size)++] = mat[top][i];
        top++;
        
        //Traverse right column
        for (int i = top; i <= bottom; i++)
            result[(*size)++] = mat[i][right];
        right--;
        
        // Traverse bottom row
        if (top <= bottom) {
            for (int i = right; i >= left; i--)
                result[(*size)++] = mat[bottom][i];
            bottom--;
        }
        
        // Traverse left column
        if (left <= right) {
            for (int i = bottom; i >= top; i--)
                result[(*size)++] = mat[i][left];
            left++;
        }
  }

}



 9. 90 DEGREE ROTATE
#include <stdio.h>
void printMatrix(int n, int mat[n][n]) {
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            printf("%d ", mat[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int mat[3][3] = {
        {0, 1, 2},
        {3, 4, 5},
        {6, 7, 8}
    };

    rotate90AntiClockwise(3, mat);
    printMatrix(3, mat);
    return 0;
}

10.
void transpose(int n, int mat[n][n]) {
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            int temp = mat[i][j];
            mat[i][j] = mat[j][i];
            mat[j][i] = temp;
        }
    }
}




