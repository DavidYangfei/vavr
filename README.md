[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.vavr/vavr/badge.png)](https://maven-badges.herokuapp.com/maven-central/io.vavr/vavr)
[![Build Status](https://travis-ci.org/vavr-io/vavr.png)](https://travis-ci.org/vavr-io/vavr)
[![codecov](https://codecov.io/gh/vavr-io/vavr/branch/master/graph/badge.svg)](https://codecov.io/gh/vavr-io/vavr)
[![Gitter Chat](https://badges.gitter.im/Join%20Chat.png)](https://gitter.im/vavr-io/vavr)

# [Vavr](http://vavr.io/)

Vavr is an object-functional language extension to Java 11, which aims to increase code quality and readability.
It provides persistent collections, functional abstractions for error handling, concurrent programming, pattern matching and much more.

To stay up to date please follow the [blog](http://blog.vavr.io).

## Overview

Vavr is greatly inspired by Scala and closely aligns to its naming scheme.

### Control

| scala.util.Try\[T+]<br><small>v2.13</small> | io.vavr.control.Try\<T><br><small>v1</small> | java.util.Optional\<T><br><small>v11</small> |
| --- | --- | --- |
| **Tests** | | |
| isFailure() | isFailure() | isEmpty() |
| isSuccess() | isSuccess() | isPresent() |
| **Handlers** | | |
| _pattern matching_ | onFailure(Consumer) | |
| _pattern matching_ | onSuccess(Consumer) | ifPresent(Consumer) |
| _pattern matching_ | | ifPresentOrElse(Consumer, Runnable) |
| **Unwrapping** | | |
| fold((Throwable) => U, (T) ⇒ U) | fold(Function, Function) | |
| get() | get() | get() |
| _pattern matching_ | getCause() | _n/a_ |
| getOrElse(=> T) | getOrElse(T) | orElse(T) |
| getOrElse(=> T) | getOrElseGet(Supplier) | orElseGet(Supplier) |
| getOrElse(=> T) | | orElseThrow() |
| getOrElse(=> T) | getOrElseThrow(Function) | orElseThrow(Supplier) |
| **Recovery** | | |
| orElse(=> Try) | orElse(Callable) | or(Supplier) |
| recover(PartialFunction) | recover(Class, CheckedFunction) | _n/a_ |
| recoverWith(PartialFunction) | recoverWith(Class, CheckedFunction) | _n/a_ |
| **Transformation** | | |
| collect(PartialFunction) | | |
| failed() | failed() | _n/a_ |
| filter((T) => Boolean) | filter(CheckedPredicate) | filter(Predicate) |
| flatMap((T) => Try) | flatMap(CheckedFunction) | flatMap(Function) |
| flatten() | | |
| map((T) => U) | map(CheckedFunction) | map(Function) |
| | mapFailure(CheckedFunction) | n/a |
| transform((T) => Try, (Throwable) => Try) | transform(CheckedFunction, CheckedFunction) | _n/a_ |
| **Iteration** | | |
| foreach((T) ⇒ U) | forEach​(Consumer) | |
| productIterator() | iterator() | |
| _n/a_ | spliterator() | |
| _n/a_ | stream() | stream() |
| **Conversion** | | |
| toEither() | toEither(Function) | _n/a_ |
| toOption() | toOption() | _n/a_ |
| _n/a_ | toOptional() | _n/a_ |
