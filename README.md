# DS-Assignments

1) Parenthesis checking:

def is_valid_arrangement(arr):
  open_parenthesis = 0
  open_square_bracket = 0
  greater_than_sign = 0
  less_than_sign = 0

  for symbol in arr:
    if symbol == '(':
      open_parenthesis += 1
    elif symbol == '[':
      open_square_bracket += 1
    elif symbol == '>':
      greater_than_sign += 1
    elif symbol == '<':
      less_than_sign += 1

  if open_parenthesis != close_parenthesis or open_square_bracket != close_square_bracket or greater_than_sign != less_than_sign:
    return False
  else:
    return True


arr = ['(', '[', '<', '>', ')', ']', '(', ')', '<', '>']

print(is_valid_arrangement(arr))

rotate a 1D array:

#include <stdio.h>

void rotate_array(int arr[], int n, int k) {
  int i, j;

  // Initialize two pointers, start and end.
  int start = 0;
  int end = n - k - 1;

  // While start is less than end, swap the elements at start and end.
  while (start < end) {
    int temp = arr[start];
    arr[start] = arr[end];
    arr[end] = temp;

    start++;
    end--;
  }
}

int main() {
  int arr[] = {1, 2, 3, 4, 5, 6, 7};
  int n = sizeof(arr) / sizeof(arr[0]);
  int k = 2;

  // Print the original array.
  printf("Original array: ");
  for (int i = 0; i < n; i++) {
    printf("%d ", arr[i]);
  }
  printf("\n");

  // Rotate the array by k positions.
  rotate_array(arr, n, k);

  // Print the rotated array.
  printf("Rotated array: ");
  for (int i = 0; i < n; i++) {
    printf("%d ", arr[i]);
  }
  printf("\n");

  return 0;
}
