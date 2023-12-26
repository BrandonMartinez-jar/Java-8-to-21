# Java Lambda:

### Implementación de Lambda desde una interfaz funcional básica

```
interface ILambda { void m(); }

ILambda lambda = new ILambda() {
    @Override public void m() { System.out.println("Pre Java 8 Lambda"); }
}; 
        
ILambda lambda = () -> System.out.println("Java 8 Lambda");
```

### Implementación de Lambda desde un método funcional
```
public static < T > boolean check
        ( T arg, Predicate < T > lambda ){ return lambda.test( arg ); }
        
check(4, ( n ) -> n % 2 == 0 );
```

### Implementación de Lambda custom desde una interfáz

```
interface IEvaluate < T > { boolean isNegative( T arg ); }

IEvaluate< Integer > predicate = ( i ) -> boolean ;
```

### Implementación de Lambda custom desde una interfáz desde:

- java.util.function.Predicate
```
Predicate < Integer > predicate = ( i ) -> boolean ;
```

- java.util.function.BiPredicate
```
BiPredicate < String, Integer > biPredicate = ( str, len ) -> boolean ;
```

- java.util.function.Supplier
```
Supplier < StringBuilder > supplier = ( ) -> new StringBuilder() ;
```

- java.util.function.Consumer
```
Consumer < String > consumer = ( arg ) -> void ;
```

- java.util.function.BiConsumer
```
BiConsumer < String, String > biConsumer = ( K, V ) -> void ;
```

- java.util.function.Function
```
Function < String, Integer > function = ( arg ) -> Integer ; 
```

- java.util.function.BiFunction
```
BiFunction < String, String, Integer > biFunction = ( arg1, arg2 ) -> Integer ;
```
