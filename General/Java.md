#string #stringbuffer #stringbuilder
### String, StringBuffer, StringBuilder

```java
class Main {
	public static void main(String args[]) {
		// String
		String str = "Sriharish Sriparimalarengan Jayanthi Ravikumar";
        String str2 = "sriharish";
        String str3 = "                 ";
        String array[] = str.split("\\s+");
        System.out.println("Length of the String is: " + str.length());
        System.out.println("Character: " + str.charAt(0));
        System.out.println("Substring: " + str.substring(3));
        System.out.println("Substring index: " + str.substring(3, 7));
        System.out.println("Index of: " + str.indexOf("s", 1));
        System.out.println("Upper case: " + str.toUpperCase());
        System.out.println("Lower case: " + str.toLowerCase());
        System.out.println("Equals: " + str.equals(str2));
        System.out.println("Equals Ignore Case: " + str.equalsIgnoreCase(str2));
        System.out.println("startsWith: " + str.startsWith("Ravikumar"));
        System.out.println("endsWith: " + str.endsWith("Ravikumar"));
        System.out.println("Contains: " + str.contains("sri"));
        System.out.println("Replace: " + str.replace("i", "ii"));
        System.out.println("Split: " + str.replace("i", "ii"));
        // for(String part : array) {
        //     System.out.println(part);
        // }
        System.out.println("Trim: " + str3.trim());
        System.out.println("isEmpty: " + str3.trim().isEmpty());
        System.out.println("Concat: " + str.concat(str2));
        
        byte h = 0;
        short a = 3;
        int b = 342;
        long c = 1L;
        float d = 3.45f;
        double e = 4.3345;
        char f = 'a';
        boolean g = false;
        System.out.println(String.valueOf(h) + " " +  
        ((Object)String.valueOf(h)).getClass().getSimpleName());
        System.out.println(String.valueOf(a) + " " +  ((Object)String.valueOf(a)).getClass().getSimpleName());
        System.out.println(String.valueOf(b) + " " +  ((Object)String.valueOf(b)).getClass().getSimpleName());
        System.out.println(String.valueOf(c) + " " +  ((Object)String.valueOf(c)).getClass().getSimpleName());
        System.out.println(String.valueOf(d) + " " +  ((Object)String.valueOf(d)).getClass().getSimpleName());
        System.out.println(String.valueOf(e) + " " +  ((Object)String.valueOf(e)).getClass().getSimpleName());
        System.out.println(String.valueOf(f) + " " +  ((Object)String.valueOf(f)).getClass().getSimpleName());
        System.out.println(String.valueOf(g) + " " +  ((Object)String.valueOf(g)).getClass().getSimpleName());
        String str = new String("Harish");
        String str2 = str.intern();
        str = new String("harish");
        System.out.println(str2);

		// Here sb and sbf methods are similiar
        StringBuilder sb = new StringBuilder();
        StringBuffer sbf = new StringBuffer();
        sb.append("Sriharih");
        sb.insert(7, 's');
        sb.delete(9, 18);
        sb.deleteCharAt(9);
        sb.replace(0, 9, "hsiraH");
        sb.reverse();
        sb.setCharAt(0, 'h');
        sb.trimToSize();
        System.out.println(sb.capacity());
    }
}
```


```java
// Online Java Compiler
// Use this editor to write, compile and run your Java code online
import java.util.*;

class HelloWorld {
    
    public static int substringOccurences(String str, String subStr) {
        int index = str.indexOf(subStr);
        int count = 0;
        while(index != -1) {
            count++;
            index = str.indexOf(subStr, index+1);
        }
        return count;
    }
    
    public static String reverseString(String str) {
        StringBuilder sb = new StringBuilder(str);
        return sb.reverse().toString();
    }
    
    public static String removeDuplicates(String str) {
        Set<Character> set = new HashSet<>();
        StringBuilder result = new StringBuilder();
        for (char ch : str.toCharArray()) {
            if(!set.contains(ch)) {
                result.append(ch);
                set.add(ch);
            }
        }
        return result.toString();
    }
    
    public static String reverseWords(String str) {
        if (!str.contains(" ")) return str;
        StringBuilder result = new StringBuilder();
        String array[] = str.split("\\s+");
        for (int i = array.length - 1; i >= 0; i--) {
            result.append(array[i]);
            if(i != 0) result.append(" ");
        }
        return result.toString();
    }
    
    public static boolean anagramChecker(String strOne, String strTwo) {
        if(strOne.length() != strTwo.length()) return false;
        char charArrayOne[] = strOne.toCharArray();
        char charArrayTwo[] = strTwo.toCharArray();
        Arrays.sort(charArrayOne);
        Arrays.sort(charArrayTwo);
        return Arrays.equals(charArrayOne, charArrayTwo);
    }
    
    public static String longestCommonPrefix(String strArray[]) {
        if(strArray == null || strArray.length == 0) return "";
        String prefix = strArray[0];
        for (int i = 1; i < strArray.length; i++) {
            String current = strArray[i];
            int j = 0;
            while (j < prefix.length() && j < current.length() && prefix.charAt(j) == current.charAt(j)) {
                j++;
            }
            prefix = prefix.substring(0, j);
        }
        return prefix;
    }
    
    public static void main(String[] args) {
        // System.out.println(substringOccurences("abababab", "aba"));
        // System.out.println(reverseString("harish"));
        // String str = "hello";
        // System.out.println(removeDuplicates(str));
        // System.out.println(reverseWords("harish hs"));
        // String anagramResult = (anagramChecker("listen", "silent")) ? "Anagram" : "Not a angram";
        System.out.println(longestCommonPrefix(new String[]{"aHello", "Hell", "He"}));
    }
}
```