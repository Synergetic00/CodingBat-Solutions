## helloName

```java
public String helloName(String name) {
  return "Hello "+name+"!";
}
```

## makeAbba

```java
```

## makeTags

```java
```

## makeOutWord

```java
public String makeOutWord(String out, String word) {
  String first = out.substring(0,2);
  String last = out.substring(2,4);
  
  return first + word + last;
}
```

## extraEnd

```java
```

## firstTwo

```java
```

## firstHalf

```java
public String firstHalf(String str) {
  return str.substring(0,(str.length())/2);
}
```

## withoutEnd

```java
```

## comboString

```java
```

## nonStart

```java
public String nonStart(String a, String b) {
  return (a.substring(1,a.length()))+(b.substring(1,b.length()));
}
```

## left2

```java
```

## right2

```java
```

## theEnd

```java
public String theEnd(String str, boolean front) {
  if (front) {
    return str.substring(0,1);
  }
  else
  {
    return str.substring(str.length()-1,str.length());
  }
}
```

## withouEnd2

```java
```

## middleTwo

```java
```

## endsLy

```java
public boolean endsLy(String str) {
  if (str.length()<2) return false;
  return str.substring(str.length()-2,str.length()).equals("ly");
}
```

## nTwice

```java
```

## twoChar

```java
```

## middleThree

```java
public String middleThree(String str) {
  int num = str.length();
  int space = (num-3)/2;
  return str.substring(space,num-space);
}
```

## hasBad

```java
```

## atFirst

```java
```

## lastChars


Given 2 strings, a and b, return a new string made of the first char of a and the last char of b, so "yo" and "java" yields "ya". If either string is length 0, use '@' for its missing char.


lastChars("last", "chars") → "ls"
lastChars("yo", "java") → "ya"
lastChars("hi", "") → "h@"

```java
public String lastChars(String a, String b) {
  String s;
  String f;
  if (a != "")
  {
    s = a.substring(0,1);
  }
  else s = "@";
  if (b != "")
  {
    f = b.substring(b.length()-1,b.length());
  }
  else f = "@";
  return s+f;
}
```

## conCat

```java
```

## lastTwo

```java
```

## seeColor

```java
```

## frontAgain

```java
```

## minCat

```java
```

## extraFront

```java
```

## without2

```java
```

## deFront

```java
```

## startWord

```java
```

## withoutX

```java
```

## withoutX2

```java
```