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
