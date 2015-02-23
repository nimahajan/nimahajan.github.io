One of the most important feature of scala is callback functions. Just like javascript, one can pass on a callback function that would be called after something happens in the called function.

Lets take an example code with a simple callback function in it.

```
object Timer {
  def main(args: Array[String]) {
    oncePerSecond(5,timeFlies)
  }

  def oncePerSecond(paramCount:Int ,callback:(Int) => Int) {
    var count = paramCount;
    while (count>0) {
      count = callback(count);
      Thread sleep 1000;
    }
  }

  def timeFlies(printCount : Int) : Int = {
    println( "Time flies like an arrow...");
    return printCount-1;
  }
}
```

In above example, timeFlies is a callback function.
###Things to notice here 
1. Notice how callback functions are declared in the arguments of oncePerSecond function. Its requires a callback that takes an Int as parameter and returns an Int.
2. Scala probably likes to make code look beautiful and clean. Thread sleep 1000 is equivalent to Thread.sleep(1000). 
