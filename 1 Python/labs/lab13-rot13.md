# Lab 13: ROT Cipher

Write a program that prompts the user for a string, and encodes it with ROT13. For each character, find the corresponding character, add it to an output string. Notice that there are 26 letters in the English language, so encryption is the same as decryption.


| Index   | 0| 1| 2| 3| 4| 5| 6| 7| 8| 9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|24|25|
|---------|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|
| English | a| b| c| d| e| f| g| h| i| j| k| l| m| n| o| p| q| r| s| t| u| v| w| x| y| z|
| ROT+13  | n| o| p| q| r| s| t| u| v| w| x| y| z| a| b| c| d| e| f| g| h| i| j| k| l| m|


## Version 2

Allow the user to input the amount of rotation used in the encryption / decryption.

## Hints

* Characters in a computer are encoded as numbers, the main encoding scheme is called ASCII (American Standard Code for Information Interchange)
  * ASCII table can be found here: https://www.asciitable.com/
* Python provides functions for converting a character to its ASCII value (`ord`), as well as converting an integer to a character (`chr`)
  * example: `ord('a') -> 97`
  * example: `chr(97) -> 'a'`
* modulus operator (`%`) might come in handy for wrapping numbers around
* `str.isalpha()` can be used to tell if a character is an alphabet character or not
  * this can be useful for skipping over punctuation, whitespace characters, etc.
