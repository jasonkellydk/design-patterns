# Singleton (creational)

In software engineering, the singleton pattern is a software design pattern that restricts the instantiation of a class to one. This is useful when exactly one object is needed to coordinate actions across the system. The term comes from the mathematical concept of a singleton

## Intent
Restricting the instantiation of a class to a single instance, that can be retrieved easily

## Motivation
* Sometimes we want just a single instance of a class to exist in the system
* For example, we want just one logging class or just one database connection.
* We need to have that one instance easily accessible
* And we want to ensure that additional instances of the class can not be created

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

## Known uses

Singleton is often used to instantiate and maintain database connections because we are never interested in keeping multiple connections alive.

Singleton can also be used for a logging class because logging usually needs to be used over and over again

### Typical examples
* Factory
* Application context object
* Thread pool
* Registry setting
* Driver

## Related patterns

