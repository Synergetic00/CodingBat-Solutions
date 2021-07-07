## stringTimes

Given a string and a non-negative int n, return a larger string that is n copies of the original string.

stringTimes("Hi", 2) → "HiHi"
stringTimes("Hi", 3) → "HiHiHi"
stringTimes("Hi", 1) → "Hi"

```java
public String stringTimes(String str, int n) {
    if (n <= 0) return "";
    else return str + (stringTimes(str, n-1));
}
```

## frontTimes

Given a string and a non-negative int n, we'll say that the front of the string is the first 3 chars, or whatever is there if the string is less than length 3. Return n copies of the front;

frontTimes("Chocolate", 2) → "ChoCho"
frontTimes("Chocolate", 3) → "ChoChoCho"
frontTimes("Abc", 3) → "AbcAbcAbc"

```java
public String frontTimes(String str, int n) {
    int length = (str.length() < 3) ? str.length() : 3;
    String result = "";
    for (int i = 0; i < n; i++) {
        result += str.substring(0,length);
    }
    return result;
}
```

## countXX

Count the number of "xx" in the given string. We'll say that overlapping is allowed, so "xxx" contains 2 "xx".

countXX("abcxx") → 1
countXX("xxx") → 2
countXX("xxxx") → 3

```java
int countXX(String str) {
    int count = 0;
    for (int i = 0; i < str.length()-1; i++) {
        if (str.substring(i, i+2).equals("xx")) count++;
    }
    return count;
}
```

## doubleX

Given a string, return true if the first instance of "x" in the string is immediately followed by another "x".

doubleX("axxbb") → true
doubleX("axaxax") → false
doubleX("xxxxx") → true

```java
boolean doubleX(String str) {
    if (str.length() < 2) return false;
    else if (str.charAt(0) == 'x') return str.charAt(1) == 'x';
    else return doubleX(str.substring(1));
}
```

## stringBits

Given a string, return a new string made of every other char starting with the first, so "Hello" yields "Hlo".

stringBits("Hello") → "Hlo"
stringBits("Hi") → "H"
stringBits("Heeololeo") → "Hello"

```java
public String stringBits(String str) {
    String result = "";
    for (int i = 0; i < str.length(); i += 2) {
        result += str.charAt(i);
    }
    return result;
}
```

## stringSplosion

Given a non-empty string like "Code" return a string like "CCoCodCode".

stringSplosion("Code") → "CCoCodCode"
stringSplosion("abc") → "aababc"
stringSplosion("ab") → "aab"

```java
public String stringSplosion(String str) {
    String output = "";
    for (int i = 0; i <= str.length(); i++) {
        output += str.substring(0, i);
    }
    return output;
}
```

## last2

Given a string, return the count of the number of times that a substring length 2 appears in the string and also as the last 2 chars of the string, so "hixxxhi" yields 1 (we won't count the end substring).

last2("hixxhi") → 1
last2("xaxxaxaxx") → 1
last2("axxxaaxx") → 2

```java
public int last2(String str) {
    if (str.length() < 2) return 0;
    String end = str.substring(str.length()-2);
    int count = 0;
    for (int i = 0; i < str.length()-2; i++) {
        if (str.substring(i,i+2).equals(end)) count++;
    }
    return count;
}
```

## arrayCount9

Given an array of ints, return the number of 9's in the array.

arrayCount9([1, 2, 9]) → 1
arrayCount9([1, 9, 9]) → 2
arrayCount9([1, 9, 9, 3, 9]) → 3

```java
public int arrayCount9(int[] nums) {
    int count = 0;
    for (int i = 0; i < nums.length; i++) {
        if (nums[i] == 9) count++;
    }
    return count;
}
```

## arrayFront9

Given an array of ints, return true if one of the first 4 elements in the array is a 9. The array length may be less than 4.

arrayFront9([1, 2, 9, 3, 4]) → true
arrayFront9([1, 2, 3, 4, 9]) → false
arrayFront9([1, 2, 3, 4, 5]) → false

```java
public boolean arrayFront9(int[] nums) {
    int length = (nums.length < 4) ? nums.length : 4;
    int count = 0;
    for (int i = 0; i < length; i++) {
        if (nums[i] == 9) return true;
    }
    return false;
}
```

## array123

Given an array of ints, return true if the sequence of numbers 1, 2, 3 appears in the array somewhere.

array123([1, 1, 2, 3, 1]) → true
array123([1, 1, 2, 4, 1]) → false
array123([1, 1, 2, 1, 2, 3]) → true

```java
public boolean array123(int[] nums) {
    for (int i = 0; i < nums.length-2; i++) {
        if (nums[i] == 1 && nums[i+1] == 2 && nums[i+2] == 3) return true;
    }
    return false;
}
```

## stringMatch

Given 2 strings, a and b, return the number of the positions where they contain the same length 2 substring. So "xxcaazz" and "xxbaaz" yields 3, since the "xx", "aa", and "az" substrings appear in the same place in both strings.

* stringMatch("xxcaazz", "xxbaaz") → 3
* stringMatch("abc", "abc") → 2
* stringMatch("abc", "axc") → 0

```java
public int stringMatch(String a, String b) {
    int length = Math.min(a.length(), b.length());
    int count = 0;
    for (int i = 0; i < length-1; i++) {
        if (a.substring(i, i+2).equals(b.substring(i, i+2))) count++;
    }
    return count;
}
```

## stringX

Given a string, return a version where all the "x" have been removed. Except an "x" at the very start or end should not be removed.

* stringX("xxHxix") → "xHix"
* stringX("abxxxcd") → "abcd"
* stringX("xabxxxcdx") → "xabcdx"

```java
public String stringX(String str) {
    if (str.length() <= 2) return str;
    String output = "";
    for (int i = 1; i < str.length()-1; i++) {
        if (str.charAt(i) != 'x') {
            output += str.charAt(i);
        }
    }
    return str.charAt(0) + output + str.charAt(str.length()-1);
}
```

## altPairs

Given a string, return a string made of the chars at indexes 0,1, 4,5, 8,9 ... so "kittens" yields "kien".

* altPairs("kitten") → "kien"
* altPairs("Chocolate") → "Chole"
* altPairs("CodingHorror") → "Congrr"

```java
public String altPairs(String str) {
    String output = "";
    for (int i = 0; i < str.length(); i += 4) {
        int length = Math.min(2, str.length()-i);
        output += str.substring(i, i+length);
    }
    return output;
}
```

## stringYak

Suppose the string "yak" is unlucky. Given a string, return a version where all the "yak" are removed, but the "a" can be any char. The "yak" strings will not overlap.

* stringYak("yakpak") → "pak"
* stringYak("pakyak") → "pak"
* stringYak("yak123ya") → "123ya"

```java
public String stringYak(String str) {
    String output = "";
    for (int i = 0; i < str.length(); i++) {
        if (i+2 < str.length() && str.charAt(i) == 'y' && str.charAt(i+2) == 'k') i += 2;
        else output += str.charAt(i);
    }
    return output;
}
```

## array667

Given an array of ints, return the number of times that two 6's are next to each other in the array. Also count instances where the second "6" is actually a 7.

* array667([6, 6, 2]) → 1
* array667([6, 6, 2, 6]) → 1
* array667([6, 7, 2, 6]) → 1

```java
public int array667(int[] nums) {
    int count = 0;
    for (int i = 0; i < nums.length-1; i++) {
        if (nums[i] == 6) {
            if (nums[i+1] == 6 || nums[i+1] == 7) count++;
        }
    }
    return count;
}
```

## noTriples

Given an array of ints, we'll say that a triple is a value appearing 3 times in a row in the array. Return true if the array does not contain any triples.

* noTriples([1, 1, 2, 2, 1]) → true
* noTriples([1, 1, 2, 2, 2, 1]) → false
* noTriples([1, 1, 1, 2, 2, 2, 1]) → false

```java
public boolean noTriples(int[] nums) {
    for (int i = 0; i < nums.length-2; i++) {
        if (nums[i] == nums[i+1] && nums[i] == nums[i+2]) return false;
    }
    return true;
}
```

## has271

Given an array of ints, return true if it contains a 2, 7, 1 pattern: a value, followed by the value plus 5, followed by the value minus 1. Additionally the 271 counts even if the "1" differs by 2 or less from the correct value.

* has271([1, 2, 7, 1]) → true
* has271([1, 2, 8, 1]) → false
* has271([2, 7, 1]) → true

```java
public boolean has271(int[] nums) {
    for (int i = 0; i < nums.length-2; i++) {
        if (nums[i]+5 == nums[i+1]) {
            if (Math.abs((nums[i]-1) - nums[i+2]) <= 2) return true;
        }
    }
    return false;
}
```