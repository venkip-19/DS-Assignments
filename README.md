rotate array:

#include <stdio.h>

void rotate_array(int arr[], int n, int k) {
  int i, j;

 
  int start = 0;
  int end = n - k - 1;

  
  while (start < end) {
    int temp = arr[start];
    arr[start] = arr[end];
    arr[end] = temp;

    start++;
    end--;
  }
}

int main() {
  int arr[] = {1, 2, 3, 4, 5, 8, 9};
  int n = sizeof(arr) / sizeof(arr[0]);
  int k = 2;

  
  printf("Original array: ");
  for (int i = 0; i < n; i++) {
    printf("%d ", arr[i]);
  }
  printf("\n");

  rotate_array(arr, n, k);

  printf("Rotated array is : ");
  for (int i = 0; i < n; i++) {
    printf("%d ", arr[i]);
  }
  printf("\n");

  return 0;
}

parenthesis editing:

#include <stdio.h>

int is_valid_arrangement(char *arr, int n) {
  int open_parenthesis = 0, open_square_bracket = 0, greater_than_sign = 0, less_than_sign = 0;
  for (int i = 0; i < n; i++) {
    if (arr[i] == '(') {
      open_parenthesis++;
    } else if (arr[i] == ')') {
      open_parenthesis--;
    } else if (arr[i] == '[') {
      open_square_bracket++;
    } else if (arr[i] == ']') {
      open_square_bracket--;
    } else if (arr[i] == '<') {
      less_than_sign++;
    } else if (arr[i] == '>') {
      less_than_sign--;
    }

    if (open_parenthesis < 0 || open_square_bracket < 0 || less_than_sign > greater_than_sign) {
      return 0;
    }
  }
  return 1;
}

int main() {
  char arr[] = {'(', '[', '<', '>', ')', ']', '(', ')', '<', '>'];
  int n = sizeof(arr) / sizeof(arr[0]);
  printf("Is the parenthesis arrangement valid? %d\n", is_valid_arrangement(arr, n));
  return 0;
}

