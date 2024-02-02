# Java Lambda:

A lambda expression is just a block of code that helps in making your code more concise, These expressions are instances of classes that implement functional interfaces, look a lot like methods and in some quarters are called “anonymous methods”. However, it is an instance with everything but the method stripped away, a lot can be inferred (by the compiler) from the interface definition (which remember, has only one abstract method). The lambda expression is the instance that implements the interface that has been boiled down to the bare essentials.

### Final & Effectively final
- a variable or parameter whose value never changes after it is initialized, is considered for the compiler as effectively final
- a variable or parameter declared with the final keyword is final

When we use a local variable or parameter on a Lambda this variable is considered for the compiler as final or effectively final so the content can't change after it is initialized. This doesn't include class attributes!

## Method References
These methods can, in certain situations, help in making your lambda expressions even more concise. If all your lambda expression does is call one method, then that is an opportunity to use a method reference. If a lambda parameter is simply passed to another method, then the redundancy of specifying the variable twice can be removed.

Types of Method references:
- Bound : instance known at compile-time
- Unbound : instance provided at runtime
- static
- constructor

The context is key! the functional interface type being created is hugely important in determining context, the compiler turns your method references into lambdas in the background

### Basic example: 
List<String> names = Arrays.asList( introduce your list... );
names.forEach(name -> System.out.println(name)); // lambda
names.forEach(System.out::println); // Method reference


### Basic functional interface

```
interface ILambda { void m(); }

ILambda lambda = new ILambda() {
    @Override public void m() { System.out.println("Pre Java 8 Lambda"); }
}; 

ILambda lambda = () -> System.out.println("Java 8 Lambda");
```

### Lambda functional method

```
public static < T > boolean check
        ( T arg, Predicate < T > lambda ){ return lambda.test( arg ); }

check(4, ( n ) -> n % 2 == 0 );
```

### Lamda libraries

- java.util.function.Predicate & BiPredicate : match / validation / filter lambdas
```
Predicate < Integer > predicate = ( tilte ) -> name.statsWith(title) ; 
BiPredicate < String, Integer > biPredicate = ( str, len ) -> boolean ;
```

- java.util.function.Supplier : supply values without any input
```
Supplier < StringBuilder > supplier = ( ) -> new StringBuilder() ;
```

- java.util.function.Consumer & BiConsumer : Use the parameter but are not interested in the return value
```
Consumer < String > consumer = ( arg ) -> void ;
BiConsumer < String, String > biConsumer = ( K, V ) -> void ;
```

- java.util.function.Function & BiFunction : Transform the input into an output (types can be different)
```
Function < String, Integer > function = ( arg ) -> Integer ; 
BiFunction < String, String, Integer > biFunction = ( arg1, arg2 ) -> Integer ;
```

- java.util.function.UnaryOperator & BinaryOperator
```
UnaryOperator< String > unaryOperation = ( name ) -> "My name is " + name ;
BinaryIperator< String > binaryOperation = ( s1, s2 ) -> s1.concat(s2);
```

### Custom lambda

```
interface IEvaluate < T > { boolean isNegative( T arg ); }
IEvaluate< Integer > predicate = ( i ) -> boolean ;
```

