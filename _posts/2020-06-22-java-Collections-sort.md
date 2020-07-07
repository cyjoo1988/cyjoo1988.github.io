---
title: Sorting Java Collections
date: 2020-06-22 11:30
categories: Java Collections
---

## Collections' Native Sorting Method  
The `java.util.Collections` class provides a native method to sort its elements in an ascending order by the #natural ordering#.  
Elements can be ordered by any of the raw data types ( e.g. int, String, ...).  
The #natural ordering#s of some of these data types are as follows:  

String  Alphabetical



``` JAVA
List<String> list = new ArrayList<String>();
list.add("Bacon");
list.add("Eggs");
list.add("Coffee");

Collections.sort(list);

list.forEach(item -> System.out.println(item));
```

`Output:`  
Bacon  
Coffee  
Eggs

If the collection is comprised of customised objects, that object must implement the ##Comparable Interface##.  

```Java
public class SampleDto implements Comparable<SampleDto> {
  private int order;
  private String date;
}

public class sampleTest {
  public static void main(String[] args
}
```


## Implementing Customised Sorting Method  
