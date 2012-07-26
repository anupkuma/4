4
=

Write a method to decide if two strings are anagrams or not.



Here we have created two HashMaps<Character,Integer>. In hashmaps, we will be storing each character and occurrence of each character. Now using For loop, we will scan through all the characters of string. Then for each character in a string, we will check the occurrence of that character. If occurrence is Null, then we will increment corresponding integer value to 1 and if character is already present then increment the frequency by 1. Doing same thing for another string in second HashMap. Then comparing if both the HashMaps are same. If they are same than both the strings are anagrams.

import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;

public class CheckingAnagrams {
  public static void main(String[] args) {
		
		Scanner in = new Scanner(System.in);
		System.out.println("Enter a first string");
		String str1 = in.nextLine();
		System.out.println("You entered " + str1);
		System.out.println("Enter a second string");
		String Str2= in.nextLine();
		
		
		 Map<Character, Integer> mapA = new HashMap<Character, Integer>();
		 
		     Map<Character, Integer> mapB = new HashMap<Character, Integer>();
		 
		     for (int i = 0; i < str1.length(); ++i) {
		 
		         int count;
		 
		         count = mapA.get(str1.charAt(i)) == null ? 1 : mapA.get(str1.charAt(i)) + 1;
		 
		         mapA.put(str1.charAt(i), count);
		 
		         count = mapB.get(Str2.charAt(i)) == null ? 1
		 
		                 : mapB.get(Str2.charAt(i)) + 1;
		 
		         mapB.put(Str2.charAt(i), count);
		 
		     }
		 
		     if(str1.equalsIgnoreCase(Str2)){
		    	 System.out.println("Words are anagrams to each other"); 
		    	 System.exit(1);
		     }
		     if(mapA.equals(mapB)){
		    	 System.out.println("Words are anagrams to each other");
		     }
		     else {
		    	 System.out.println("Words aren't anagrams to each other");
		     }

		
	}
}
