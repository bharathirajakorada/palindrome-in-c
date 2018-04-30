# palindrome-in-c
checking a phrase which contains mixed alphabets and special characters if it is a palindrome or not.

#include <stdio.h>
#include <string.h>

char lower(char c)
{
    return (c >= 'A' && c <= 'Z') ? (c + 32) : c;
}

// A function to check if a string str is palindrome
void isPalindrome(char str[])
{
    // Start from leftmost and rightmost corners of str
    int l = 0;
    int h = strlen(str) - 1; // last index

    // Handling with special characters
    char str1[h + 1];
    int j = 0, k = 0;
    while(j <= h)
    {
    // check the if condition below
      if(str[j] >= 'A' && str[j] <= 'Z' || str[j] >= 'a' && str[j] <= 'z')
      {
        str1[k]=str[j];
        k++;
      }
      j++;
    }

    int newh = k - 1; //strlen(str2);  h = k - 1

    // Keep comparing characters while they are same
    while (newh > l)
    {
        if (lower(str1[l++]) != lower(str1[newh--]))
        {
            printf("%s is Not Palindrome \n", str);

            return;
        }
    }
    printf("%s is palindrome\n", str);

}

// Driver program to test above function
int main()
{

    // it should handle  mixed case alphabets
    char text[] = "AbutTuba";
    isPalindrome(text);

    // DO NOT MODIFY BELOW TEST CASES
    isPalindrome("A but tuba.");
    isPalindrome("A car, a man, a maraca.");
    isPalindrome("A Toyota! Race fast, safe car! A Toyota!");
    isPalindrome("");


    return 0;
}
