# Singleton

In software engineering, the singleton pattern is a software design pattern that restricts the instantiation of a class to one. This is useful when exactly one object is needed to coordinate actions across the system. The term comes from the mathematical concept of a singleton

### Category


### UML Diagram

![Singleton UML](/assets/uml/singleton.svg)

### Examples

<!-- tabs:start -->

#### ** Kotlin **

```kotlin
    object User {
        private var test = ""
    }
```

#### ** Java **

```java
    class User
    {
        // static variable single_instance of type Singleton
        private static User instance = null;
        private String test = "";

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
```

#### ** C# **

```csharp
    public class User
    {
        private String test = "";
        private static readonly User instance = new User();

        // private constructor restricted to this class itself
        private User()
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
    class User {
        test = "";
    }

    export new User();
```

<!-- tabs:end -->
