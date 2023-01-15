# zio-snippets README

A collection of snippets to improve productivity when writing ZIO code in Scala.

For now, only tested for Scala 2.

## Features

The extension provides a number of snippets, 
some of which are short and should be used within the file, 
some are longer and intended to populate an entire file.

In the following list of snippets, `???` represents placeholders 
that can be filled one by one, using the tab key.  
(Notice: If two placeholders are expected to contain the same text,
e.g. class and companion object,
then they will be populated at once.)

### Short Snippets

#### For Comprehensions

Simple vanilla Scala for comprehension:

```scala
for {
  _ <- ???
} yield ()
```


For comprehension with the first element being `ZIO.unit`:

```scala
for {
  _ <- ZIO.unit
  ???
} yield ()
```


For comprehension with the first element being `ZIO.succeed(???)`, 
that will yield the result of the succeed:

```scala
for {
  ??? <- ZIO.succeed(???)
} yield ???
```


#### ZIO Test

ZIO Test suite:

```scala
suite("???")(
  ???
)
```


ZIO Test test

```scala
test("???"){
  ???
  
  assertTrue(true)
}
```


ZIO Test effectful test with for comprehension

```scala
test("???"){
  for {
    _ <- ??? 
  } yield assertTrue(true)
}
```



### File Template Snippets

The file template snippets are intended to populate a new or empty file. 
They are not package aware, so the package will have to be added manually. 
(There is a reminder comment included for that.)


#### Service Pattern

A simple snippet to add a new service according to the 
[ZIO service parttern]([https://](https://zio.dev/reference/service-pattern/introduction)).  
Note: Normally the trait might live in a separate file, 
there are multiple ways to create the layer
and you might want to implement accessors on the companion object.
This is simply a starting point to build up your service.

```scala
// Ensure package

import zio._

trait ??? {
  ???
}

final case class ???() extends ??? {
  //
}

object ??? {
  val layer = ZLayer.fromFunction(???.apply _)
}
```


#### ZIO App

A simple, runnable ZIO app.

```scala
// Ensure package

import zio._

object ??? extends ZIOAppDefault {
  
  def run = app
  
  val app =
    for {
      _ <- ZIO.unit
      ???
  } yield ()
}
```


#### ZIO Test App/Spec

A simple, executable ZIO Test spec file.

```scala
// Ensure package

import zio._
import zio.test._

object ??? extends ZIOSpecDefault {
  
  def spec = 
    suite("???")(
      ???
    )
}
```


## Known Issues

None


## Roadmap

The extension is currently in a testing stage.
Depending on my personal usage experience 
(and potential user feedback),
more snippets will likely be added in the future.

It would be cool to eventually make this snippet collection part of a bigger VSCode ZIO extension,
which might have more advanced features.


## Feedback and Contributions

This is free, open source software. 
All contributions are welcome. 
If you are interested in contributing, please get in touch via 
[GitHub issues](https://github.com/BalduinLandolt/zio-snippets/issues).

Any feedback, improvement suggestions or additional snippets you would like to see,
are most welcome. 
Please open an [issue on GitHub](https://github.com/BalduinLandolt/zio-snippets/issues) for this too.

## Release Notes

For the full release notes, please see the [changelog](CHANGELOG.md).

### [0.0.1] - 2023-01-15

Initial test release: A first couple of snippets.
