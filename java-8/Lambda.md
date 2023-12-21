# Java Lambda:

### Implementación de Lambda desde una interfaz funcional básica

interface ILambda { void m(); }

void preJavaEight(){
    ILambda lambda = new ILambda() {
        @Override public void m() { System.out.println("Pre Java 8 Lambda"); } }; }
        
void javaEight
        ( ){ ILambda lambda = () -> System.out.println("Java 8 Lambda"); }

### Implementación de L desde un método funcional

public static < T > boolean check
        ( T arg, Predicate < T > lambda ){ return lambda.test( arg ); }
        
void methodLambda
        ( ) { check(4, ( n ) -> n % 2 == 0 ); }

### Implementación de Lambda custom desde una interfáz

interface IEvaluate < T > { boolean isNegative( T arg ); }

void customLambda
        ( ) { IEvaluate< Integer > predicate = ( i ) -> i < 0 ; }

### Implementación de Lambda custom desde una interfáz desde java.util.funcion.Predicate

void predicateLambda
        ( ) { Predicate < Integer > predicate = ( i ) -> i < 0 ; }

