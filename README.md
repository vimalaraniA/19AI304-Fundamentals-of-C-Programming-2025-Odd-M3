# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
### Vimala Rani A
### 212223040240
# IAPR-3- Module 3 - FoC
## 5. Implementation of one-dimensional array and multidimensional array.
## 6. Implementation of string manipulation.
# Ex.No:11
  Formulate a C program to convert a given decimal number into its binary equivalent and display it.

# Aim:
To formulate a C program to convert a decimal number into its binary equivalent and display it.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare variables: num (input number), rem (remainder), binary[] (array to store binary digits), and loop counters i and k.
### Step 4: 
  Read the decimal number from the user.
### Step 5: 
  Initialize i = 0.
### Step 6: 
  Repeat while num > 0:
  Divide num by 2 and store the remainder in binary[i].
  Increment i.
  Update num = num / 2.
### Step 7: 
  Display the binary digits in reverse order (from i-1 down to 0).
### Step 8: 
   Stop
# Program:

#include<stdio.h>

int main(){
    int num, rem, i = 0, k;
    int binary[32];
    
    scanf("%d", &num);
    int n = num; 
    
    while(num > 0){
        rem = num % 2;
        binary[i] = rem;
        i++;
        num = num / 2;
    }
    
    for(k = i - 1; k >= 0; k--)
        printf("%d", binary[k]);
    
    printf("\n");
    return 0;
}


# Output:
<img width="555" height="291" alt="image" src="https://github.com/user-attachments/assets/75aa79da-119a-4113-90af-30a722ce0611" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:12
  Develop a C program to read a matrix and find its saddle point. A saddle point is an element that is the minimum in its row and also the maximum in its column. If such an element exists, display its position and value.

# Aim:
  To develop a C program that inputs a matrix, checks each row for its minimum element, verifies whether that element is also the maximum in its corresponding column, and displays the saddle point and its position if it exists.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
 Declare variables i, j, k, m, min, max and a position array pos[2][2].
### Step 4: 
 Read the order of the square matrix m.
### Step 5: 
 Declare an m × m matrix and read its elements.
### Step 6: 
 Display the matrix.
### Step 7: 
   For each row i from 0 to m−1:
- *Step 7.1:* Set min as the first element of the row.  
- *Step 7.2:* Scan the row to find its minimum element and store its position in pos[0].  
- *Step 7.3:* Let j be the column of this minimum element.  
- *Step 7.4:* Set max as the first element of column j.  
- *Step 7.5:* Scan column j to find its maximum element and store its position in pos[1].  
### Step 8: 
  Check if the row minimum equals the column maximum:
- If min == max *and their positions match, then the element is a **saddle point*.
- Print the saddle point value and its position.
### Step 9: 
  Stop
# Program:

#include<stdio.h>

int main(){
    int i, j, k, m, min, max;
    int pos[2][2];

    scanf("%d", &m);
    int mat[m][m];

    for(i = 0; i < m; i++)
        for(j = 0; j < m; j++)
            scanf("%d", &mat[i][j]);

    printf("Matrix:\n");
    for(i = 0; i < m; i++){
        for(j = 0; j < m; j++)
            printf("%d ", mat[i][j]);
        printf("\n");
    }

    int found = 0;

    for(i = 0; i < m; i++){
        min = mat[i][0];
        pos[0][0] = i;
        pos[0][1] = 0;

        for(j = 1; j < m; j++){
            if(mat[i][j] < min){
                min = mat[i][j];
                pos[0][1] = j;
            }
        }

        j = pos[0][1];
        max = mat[0][j];
        pos[1][0] = 0;
        pos[1][1] = j;

        for(k = 1; k < m; k++){
            if(mat[k][j] > max){
                max = mat[k][j];
                pos[1][0] = k;
            }
        }

        if(min == max && pos[0][0] == pos[1][0]){
            printf("Saddle point: %d at position (%d,%d)\n", min, i, j);
            found = 1;
            break;
        }
    }

    if(!found)
        printf("No saddle point found\n");

    return 0;
}


# Output:
<img width="496" height="421" alt="image" src="https://github.com/user-attachments/assets/ea82c049-06aa-4a16-91cd-229c144f0dfb" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:13
  Formulate a C program to reverse a string entered by the user and display the reversed string.

# Aim:
  To formulate a C program that reads a string from the user, reverses it, and prints the reversed string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare two character arrays: s to store the input string and d to store the reversed string.
### Step 4: 
  Read the string from the user using scanf("%[^\n]s", s);
### Step 5: 
  Find the length of the string s by traversing it until the null character '\0' is encountered.
### Step 6: 
  Initialize a counter j for the reversed string.
### Step 7: 
  Copy characters from the end of s to the beginning of d using a loop until all characters are copied in reverse order.
### Step 8: 
  Terminate the reversed string d with the null character '\0'.
### Step 9: 
  Print the reversed string.
### Step 10: 
  Stop
# Program:

#include<stdio.h>

int main(){
    char s[100], d[100];
    int i, j = 0, len = 0;

    scanf("%[^\n]s", s);

    while(s[len] != '\0')
        len++;

    for(i = len - 1; i >= 0; i--){
        d[j] = s[i];
        j++;
    }
    d[j] = '\0';

    printf("%s\n", d);
    return 0;
}


# Output:
<img width="608" height="319" alt="image" src="https://github.com/user-attachments/assets/950662cd-c2ef-4a9a-ab68-e041af4da70b" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:14
  Formulate a C program to count the frequency of each character in a given string and display the count of every character.

# Aim:
  To formulate a C program that accepts a string from the user and calculates the frequency of each character in the string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array s[100] to store the input string, an integer array visited[256] initialized to 0, and variables i, n, and count.
### Step 4: 
  Read the string from the user using scanf("%[^\n]", s);
### Step 5: 
  Calculate the length of the string using strlen(s) and store it in n.
### Step 6: 
 For each character s[i] in the string (from i = 0 to n - 1):
 - If visited[(unsigned char)s[i]] == 0 (character not yet counted):  
  - Initialize count = 0.  
  - Loop through the string again and increment count for every occurrence of s[i].  
  - Print s[i] and its count.  
  - Set visited[(unsigned char)s[i]] = 1 to mark it as counted.
### Step 7: 
  Repeat Step 6 for all characters.
### Step 8:
  Stop
# Program:

#include<stdio.h>
#include<string.h>

int main(){
    char s[100];
    int visited[256] = {0};
    int i, j, n, count;

    scanf("%[^\n]", s);
    n = strlen(s);

    for(i = 0; i < n; i++){
        if(visited[(unsigned char)s[i]] == 0){
            count = 0;
            for(j = 0; j < n; j++){
                if(s[i] == s[j])
                    count++;
            }
            printf("%c: %d\n", s[i], count);
            visited[(unsigned char)s[i]] = 1;
        }
    }

    return 0;
}


# Output:
<img width="459" height="481" alt="image" src="https://github.com/user-attachments/assets/84718156-4bbd-434b-b60e-63811a13ef24" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:15
  Formulate a C program to remove duplicate words from a given string and display the string with only unique words.

# Aim:
  To formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array str to store the input string and a 2D array words to store individual words.
### Step 4: 
  Read the input string using scanf("%[^\n]s", str);
### Step 5: 
 Split the string into words:
 - Traverse the string character by character.  
 - When a space is encountered, terminate the current word with '\0' and move to the next row in words.  
 - Otherwise, copy the character into the current word.
### Step 6: 
  Compare each word with all other words to detect duplicates:
  - If a duplicate is found, mark it by setting the first character to '\0'.
### Step 7: 
  Print all words that are not marked as duplicates.
### Step 8: 
  Stop
# Program:

#include<stdio.h>
#include<string.h>

int main(){
    char str[200], words[50][50];
    int i = 0, j = 0, k = 0, wordCount = 0;

    scanf("%[^\n]s", str);

    while(str[i] != '\0'){
        if(str[i] == ' '){
            words[wordCount][j] = '\0';
            wordCount++;
            j = 0;
        } else {
            words[wordCount][j] = str[i];
            j++;
        }
        i++;
    }
    words[wordCount][j] = '\0';
    wordCount++;

    for(i = 0; i < wordCount; i++){
        if(words[i][0] == '\0') continue;
        for(j = i + 1; j < wordCount; j++){
            if(strcmp(words[i], words[j]) == 0){
                words[j][0] = '\0';
            }
        }
    }

    for(i = 0; i < wordCount; i++){
        if(words[i][0] != '\0')
            printf("%s ", words[i]);
    }
    printf("\n");

    return 0;
}


# Output:

<img width="666" height="369" alt="image" src="https://github.com/user-attachments/assets/ab308e44-e74a-42c6-b503-eb68a9225ace" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.
