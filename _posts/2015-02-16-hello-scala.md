---
layout: post
title: Hello Scala !
---

##About
Its about time (because its never too late) to start learning scala seriously. So I started reading blogs, books etc. I started remembering some non-usual syntax. But best way is probably to start coding small. Some simple algorithms written in scala to learn basics.

###Sum of first N numbers recursively
```
package com.nimahajan.sample

Object SumUtility {
  def main(args: Array[String]) {
      println("Sum of first N number is " + sumOfFirstN(10));
  }

  def sumOfFirstN(i : Int) : Int = {
	  if(i==1){
	   return 1;
	  }
	  return i + sumOfFirstN(i-1);
  }
}
```

####Things to notice here -
1. "Object" - Makes class singleton. No static in scala.
2. "main" function is also not static.
3. recursive function needs to specify return type. 
4. For all function parameters, data type is after the variable name.



