---
layout: post
title: Hello Scala !
---

##About
Its about time (because its never too late) to start learning scala seriously. So I started reading blogs, books etc. I started remembering some non-usual syntax. But best way is probably to start coding small. So I am going to start with some simple algorithms written in scala to learn basics.


###1.Sum of first N numbers recursively
```
package com.nimahajan.sample

object SumUtility {
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
1. "object" - Makes class singleton. No static in scala.
2. "main" function is also not static.
3. recursive function needs to specify return type. 
4. For all function parameters, data type is after the variable name.


###2.String Pattern Matching
```
object StringPatternMatchUtility {
 
 def main(args: Array[String]) {
      val inputString = "mahajan"; 
      val pattern = "haj";
      println("The Pattern Matches At Position :" + matchPattern(inputString, pattern));
 }
  
 def matchPattern(input: String, pattern: String): Int = {
    val loop = new Breaks;

    for (i<- 0 to input.length-1) {
      var foundMatch = true;
      loop.breakable {
        for (j<-0 to pattern.length-1) {
          if (i+j >= input.length || input.charAt(i+j) != pattern.charAt(j)) {
            foundMatch = false;
            loop.break();
          }
        }
      }
      if(foundMatch){
        return i;
      }
    }
    return -1;
  }
}
```
####Things to notice here -
1. val is like final in Java. A very good explanation is available at the [stackoverflow] (http://stackoverflow.com/questions/1791408/what-is-the-difference-between-a-var-and-val-definition-in-scala)
2. break -  Scala does have 'break'. However there are various other ways to break out of loop. More at [stackoverflow]
(http://stackoverflow.com/questions/2742719/how-do-i-break-out-of-a-loop-in-scala)
3. For loop syntax is another thing to look for -
  * If you want to do usual increment by 1, you can do  - for(j <- 0 to count).
  * If you want to increment by say 2, you can do - for (j <- 0 until max by 2).
4. There is no ++ OR -- operator in scala.

