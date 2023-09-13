# 100-Days-Of-Code-Challenge
The "100 Days of Code" challenge is a commitment to dedicate 100 consecutive days to coding and programming activities.
#Day1:Topic Backtracking
class Backtracking {
    public static void printPermutation(String str, String perm, int idx){
        if(str.length() == 0){
            System.out.println(perm);
            return;
        }
        for(int i=0;i<str.length();i++){
            char currChar = str.charAt(i);
            String newStr = str.substring(0, i) + str.substring(i+1);
            printPermutation(newStr, perm + currChar, idx+1);
            }
        }
    public static void main(String[] args) {
        String str = "ABC";
        printPermutation(str, "",0);
    }
}
Output: All the possible combinations:
ABC
ACB
BAC
BCA
CAB
CBA


#Day 2 Backtracking Level-2:
Word break problem:
// A recursive program to print all possible
// partitions of a given string into dictionary
// words
import java.io.*;
import java.util.*;

class GFG {

// Prints all possible word breaks of given string
static void wordBreak(int n, List<String> dict, String s)
{
	String ans="";
	wordBreakUtil(n, s, dict, ans);
}

static void wordBreakUtil(int n, String s, List<String> dict, String ans)
{
	for(int i = 1; i <= n; i++)
	{

	// Extract substring from 0 to i in prefix
	String prefix=s.substring(0, i);

	// If dictionary contains this prefix, then
	// we check for remaining string. Otherwise
	// we ignore this prefix (there is no else for
	// this if) and try next
	if(dict.contains(prefix))
	{
		// If no more elements are there, print it
		if(i == n)
		{

		// Add this element to previous prefix
		ans += prefix;
		System.out.println(ans);
		return;
		}
		wordBreakUtil(n - i, s.substring(i,n), dict, ans+prefix+" ");
	}
	}
}

// main function
public static void main(String args[])
{
	String str1 = "iloveicecreamandmango"; // for first test case
	String str2 ="ilovesamsungmobile";	 // for second test case
	int n1 = str1.length();				 // length of first string
	int n2 = str2.length();				 // length of second string

	// List of strings in dictionary
	List <String> dict= Arrays.asList("mobile","samsung","sam","sung",
									"man","mango", "icecream","and",
									"go","i","love","ice","cream");		
	System.out.println("First Test:");

	// call to the method
	wordBreak(n1,dict,str1);
	System.out.println("\nSecond Test:");

	// call to the method
	wordBreak(n2,dict,str2);
}
}
Output:
First Test:i love ice cream and man goi love ice cream and mangoi love icecream and man goi love icecream and mangoSecond Test:i love sam sung mobilei love samsung mobile





#Day 2: Topic-Recursion:
Here we will print the no. from 5 to 1 using recursion which also includes a base condition:
public class Recursion{
    public static void printnos(int n){
        if(n == 0){     //Base Condition
            return;
        }
        for(int i = 5; i > 0; i--){
            System.out.println(+i);
        }
    }
    public static void main(String args[]){
            int n=5;
            printnos(n-1);
        }
#Output:
5
4
3
2
1


