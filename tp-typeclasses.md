# Scala - TP2

## Part I - Basic typeclasses

### Show

We'll define a typeclass Show to returns a String

```scala
trait Show[A] {
  def show(a: A): String
}
```

First, implement the typeclass for `Person`.

```scala 3
given Show[Person] = ??? //todo: implement this

case class Person(firstName: String, lastName: String)

val elton: Person = Person("Elton", "John")
summon[Show[Person]].show(elton) //returns "Elton John"
```

Second create extension method to call `.show` on any type A that implements Show.

```scala
val elton: Person = Person("Elton", "John")
elton.show //returns "Elton John"
```

### Eq, Ord

Now that you're more familiar with this pattern, create a typeclass `Eq` with a method `.equal` that returns true if two values are equal.

Create a typeclass named `Ord` with a method `.compare` that return an `Ordering`
```scala 3
enum Ordering {
  case LESS, EQUAL, GREATER
}
```

## Part II - Slightly harder typeclasses

### Mappable 

Let's first remind you about Higher Kinded Types (HKT) : `F[_]` is like a function on types. 
Meaning it cannot be used directly for a value : 
```scala 3
type F[_]

val a: F = ???
```
Doesn't work. You have to define the type in `_`
For example :

```scala 3
type F[_]

val a: F[Int] = ???
```

Let's then study a well known function : `.map`

As seen in this class there is many types that implements this method : `Option`, `Either`, `Try`, `Seq`, `Set` and many more in libraries.

Your job is to :
1. Find a generalized representation of `map`
2. Create a trait that define the typeclass `Mappable` that contains this generalized version and call the function `myMap`
3. Implement `Mappable` for `Option`, `Either` and `List`
4. Use this new `Mappable` typeclass in a function that transforms strings and works for every type that implements `Mappable`

### Chainable

Same steps as for `.map` but for two functions : `.flatMap` and a function `.pure` of signature : 
```scala 3
def pure[A](a: A): F[A]
```

*Fun fact, you just implemented two very famous typeclasses : `Mappable` is called `Functor` and `Chainable` is called `Monad`*