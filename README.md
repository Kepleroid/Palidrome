# Palidrome
int main(){
    char string [100];
    printf("Enter a string: ");
    scanf("%[^\n]", string);
    int isPalindrome = 1;  // assign 0 to this if the string is a NOT palindrome
    // write code to test if string is a palindrome
    // will take 2 indices, i and j, initialize i at the first character and
    // j at last character
    int i = 0, j = strlen(string) - 1;
    // iterate as long as i is less than j and still palindrome property is holding so far.
    while(i < j && isPalindrome){
        // skip all the spaces or punctuation marks from left
        while(string[i] == ' ' || string[i] == '?' || string[i] == '.'|| string[i] == ',' || string[i] == '!'){
            i++;
        }
        // also skip all spaces and punctuation marks from right
        while(string[j] == ' ' || string[j] == '?' || string[j] == '.'|| string[j] == ',' || string[j] == '!'){
            j--;
        }
        // Now get the ith character in upper case
        char left = (char)(string[i] >= 'a' && string[i] <= 'z'? string[i]-32 : string[i]);
        // get the jth character also in upper case, (making case insensitive, taking both to same cases)
        char right = (char)(string[j] >= 'a' && string[j] <= 'z'? string[j]-32 : string[j]);
        if (right != left){
            isPalindrome = 0;
        }
        // move i from left to right
        i++;
        // move j from right to left
        j--;
    }
    // at the end you need to test
    if (isPalindrome){
        printf("Yes, it is Palindrome!\n");
    }
    else{
        printf("No, not a Palindrome\n");
    }
    return 0;
}
