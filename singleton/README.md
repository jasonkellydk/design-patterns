# Singleton (creational)

In software engineering, the singleton pattern is a software design pattern that restricts the instantiation of a class to one. This is useful when exactly one object is needed to coordinate actions across the system. The term comes from the mathematical concept of a singleton

## Intent
Restricting the instantiation of a class to a single instance, that can be retrieved easily

* Ensure that only one instance of a class is created
* Provide a global point of access to that object

## Motivation
* Sometimes we want just a single instance of a class to exist in the system
* For example, we want just one logging class or just one database connection.
* We need to have that one instance easily accessible
* And we want to ensure that additional instances of the class can not be created

## Useful when

Singleton is often used to instantiate and maintain database connections because we are never interested in keeping multiple connections alive.
Singleton can also be used for a logging class because logging usually needs to be used over and over again

* overuse of resources
* incorrect behavior and/or inconsistent results
* need for one global point of access

### Typical examples
* Factory
* Application context object
* Thread pool
* Registry setting
* Driver

## UML Diagram

![Singleton UML](../assets/uml/singleton.svg)

## Implementation

<!-- tabs:start -->

#### ** Kotlin **

```kotlin
    // The object keyword will create a singleton
    object Singleton {}
```

#### ** Java **

```java
    class Singleton
    {
        // static variable instance of type Singleton
        private static Singleton instance = null;

        // private constructor restricted to this class itself
        private Singleton()
        {
            // Silence is golden
        }

        // static method to create instance of Singleton class
        public static Singleton getInstance()
        {
            if (instance == null)
                instance = new User();

            return instance;
        }
    }

    // Thread safe implementation
   class Singleton {

       private static Singleton instance;

       private Singleton(){}

       public static synchronized Singleton getInstance(){
           if(instance == null){
               instance = new Singleton();
           }
           return instance;
       }
   }
```

#### ** C# **

```csharp
    public class Singleton
    {
        // Eager loading (also makes it thread safe)
        private static readonly Singleton instance = new Singleton();

        // private constructor restricted to this class itself
        private Singleton()
        {
            // Silence is golden
        }

        // static method to get instance of Singleton class
        public static Singleton getInstance()
        {
            return instance;
        }
    }
```

#### ** JavaScript **

```js
    class Singleton {}

    // This will always export the same reference of the object
    export new Singleton();
```

<!-- tabs:end -->

## Consequences

Singleton is often considered an anti-pattern because it will often be used in use cases where it should not be applied

### Warnings
* The reflection API can be used to break a singleton
* Prevent cloning and serialization to ensure a class is a singleton

## Known uses

Examples of the singleton pattern in the JDK
* ```java.lang.Runtime```  is a singleton which is returned with ```java.lang.Runtime.getRuntime()```
* ```java.awt.Toolkit``` is a singleton which is returned with ```Toolkit.getDefaultToolkit()```
* ```java.io.Console()``` is a singleton which is returned from another class with ```java.lang.System.console()```

## Other

This category have relevant information about the pattern

### Singleton vs static classes

Singletons and static classes can be used without explicitly
creating object, both provide only one instance, and both
provide easy accessibility

**Use static class in place of a singleton when**
* the singleton does not maintain any state, or
* to bundle a bunch of utility methods

**A singleton class can be**
* lazy loaded while static classes are always eagerly loaded
* serialized (but should not!) whereas static classes may not
* extended and polymorphism applied, and its methods overriden

**A static object is created at class load time**
* no opportunity to supply any data before it instantiates
* no control over who accesses the object as anybody can access a publicly available static instance

**Examples of the singleton pattern in the JDK**
* ```java.lang.Runtime```  is a singleton which is returned with ```java.lang.Runtime.getRuntime()```
* ```java.awt.Toolkit``` is a singleton which is returned with ```Toolkit.getDefaultToolkit()```
* ```java.io.Console()``` is a singleton which is returned from another class with ```java.lang.System.console()```

**Examples of static classes in the JDK**
* ```java.lang.Math```
* ```java.lang.System```

