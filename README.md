# Counting Characters in C


Characters--the building blocks of strings--are stored in computers in a code called ASCII. Each symbol in the latin alphabet is assigned an integer value between 1-127 so that each character can be stored in one byte of memory. See the [ASCII table](http://www.asciitable.com) for the specific assignments of characters to integers.


Strings in C and assembly language are implemented as arrays that can have a variable length. The length of the string is not explicitly encoded anywhere--there is no `String.length` property or method that can easily tell us the length of a string. Instead, strings have a special NULL terminator to mark the end of the string. The NULL terminator is a single byte that has the special value 0, which does not code for any printable characters in ASCII. For example, the string "NEIL" is shown below coded as a NULL-terminated ASCII string.


|    Character    | ASCII |
|-----------------|-------|
|        N        | 0x4E  |
|        E        | 0x45  |
|        I        | 0x49  |
|        L        | 0x4C  |
| NULL TERMINATOR | 0x00  |

The string "NEIL" is 5 bytes long (including the NULL terminator at the end), so it will not fit into a 32-bit (4-byte) integer. We can only tell how long the string is by counting the number of bytes starting at the beginning up to (and including) the NULL terminator.

If there is no `String.length` in C, how are we supposed to find out how many characters are in a string? The C library provides a function called `strlen` that we can call to count the number of characters in the string.

    #include <string.h>
    
    void main() {
      char s[] = "the quick brown fox jumped over the lazy dog";
      int s_length = strlen(s);
    }

## Part 1: Counting Occurrences of a Character

Write a program that loops through a string and counts all occurrences of a character. You can start by counting the occurrences of the character `a`. Make your program more versatile by making it possible to count the occurrences of any character.

## Part 2(a): Converting One Character to Another -- Retabbing

[Studies have shown](https://stackoverflow.blog/2017/06/15/developers-use-spaces-make-money-use-tabs/) that developers who use spaces to indent instead of tabs make 10% more money. Write a program that loops through a string and swaps all occurrences of the tab character (`\t`) for a space character.

## Part 2(b): Retabbing v2

Modify your program from part 2(a) to **copy** characters from one string into a second string. When you encounter a tab character, don't copy it. Instead, insert four spaces in the second string.

## Part 3: Checksumming

Write a program to add up the ASCII values of all characters in a string and print out the sum. For example, in the string `NEIL` above, the ASCII values are `0x4E`, `0x45`, `0x49`, `0x4C`. Their sum is `0x4E + 0x45 + 0x49 + 0x4C = 0x128`.


