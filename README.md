Task:
Implement a method to perform basic string compression using the counts of repeated
characters. For example, the string aabcccccaaa would become a2blc5a3. If the "compressed"
string would not become smaller than the original string, your method should return the original
string. You can assume the string has only uppercase and lowercase letters (a - z).

Example 1:
Input: "aabcccccaaa"
Output: "a2b1c5a3"

Example 2:
Input: "abbccd"
Output: "abbccd"
Explanation:
The compressed string is "a1b2c2d1", which is longer than the original string.





import java.util.*; 
import java.io.*;

class Main {

  public static String compressString(String S) {
    String finalString = "";
    char[] charArray = S.toCharArray();
    int i = 1;
    int num = 1;

    while(i <= charArray.length){
      if(i == charArray.length){
        finalString += charArray[i-1] + Integer.toString(num);
      }else{
        if(charArray[i-1] == charArray[i]){
          num++;
        }else{
         finalString += charArray[i-1] + Integer.toString(num);
         num = 1;
        }
      }
      i++;
    }
    if(S.length() < finalString.length()){
      finalString = S;
    }
    return finalString;
  }

  public static void main (String[] args) {  
    // keep this function call here     
    Scanner s = new Scanner(System.in);
    System.out.println(compressString(s.nextLine())); 
  }
}
