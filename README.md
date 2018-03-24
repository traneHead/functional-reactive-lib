[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.rapidpm/rapidpm-functional-reactive/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.rapidpm/rapidpm-functional-reactive)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/a0b7d530374d400fa9a79d270cf95c1a)](https://www.codacy.com/app/sven-ruppert/functional-reactive-lib?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=functional-reactive/functional-reactive-lib&amp;utm_campaign=Badge_Grade)
[![](http://drone.rapidpm.org:8000/api/badges/RapidPM/functional-reactive-lib/status.svg?branch=develop)](http://drone.rapidpm.org:8000/api/badges/RapidPM/functional-reactive-lib/status.svg?branch=develop)


# Release Notes

This Lib is working with
 * Java 08 (open/oracle/ibm/zulu)
 * Java 09 (open/oracle/ibm/zulu)
 * Java 10 (open/oracle/)
 * Java 11 (open/)

## 0.5.3-SNAPSHOT

## 0.5.2
* extend Result<T> with a fluent API
    * void ifFailed -> Result<T> ifFailed
    * void ifPresent -> Result<T> ifPresent
    * void ifAbsent -> Result<T> ifAbsent
    
## 0.5.1
* renamed Tripel (german) to Triple (en)
* pitest is working with junit5 now

## 0.5.0
* Result added ```void ifFailed(Consumer<String> failed);```
* switched to jUnit5
* updated parent pom to 3.5.7

## 0.1.0
* Result added ```<U> Result<U> asFailure()```
* Result added ```<U> Result<U> flatMap(Function<T, Result<U>> mapper)```
* ExceptionFunctions.message() extended exception message with Exception Classname
* added CompletableFutureQueue

## 0.0.6
* ExceptionFunctions added ```Function<Exception, String> message()```
* ExceptionFunctions added ```Function<Exception, Stream<StackTraceElement>> toStackTraceStream()```
* added Sext and Sept data-classes

## 0.0.5
* added model.serial pkg with Data classes only for ```extends Serializable``` types
* Transformations
    + curry / unCurry - BiFunction / TriFunction
* StreamFunctions added ```<T> Function<Predicate<T>, Function<Stream<T>, Stream<T>>> streamFilter()```
* Result.ofNullable
* Result renamed ```bind(Consumer<T> success, Consumer<String> failure)``` 
        to 
        ```ifPresentOrElse(Consumer<T> success, Consumer<String> failure)```
* Result added JDK9 signature ```ifPresentOrElse(Consumer<? super T> action, Runnable emptyAction)```
* Result added JDK9 signature ```Stream<T> stream()```
* Result added ```Result<T> or(Supplier<? extends Result<? extends T>> supplier)```
* Result added ```void ifAbsent(Runnable action)```
* Result added ```<U> Result<U> map(Function<? super T, ? extends U> mapper)```


## 0.0.4
* added Result.thenCombine
* added Result.thenCombineAsync
* added CheckedBiFunction

## 0.0.3
* added CheckedPredicate

## 0.0.2
* basic Datastructures like Pair, Triple, Quad
* added fromOptional and toOptional to the class Result
* added CheckedFunction , CheckedConsumer and CheckedSupplier
* extracted TriFunction from Memoizer to pkg functions
* added QuadFunction
* added StringFunctions
* added Transformations 
* added StringFunctions
* ported Strman-java to functional style