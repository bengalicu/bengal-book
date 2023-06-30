---
description: Other constructs
---

### Native code

To make it possible to interact with the operating system and/or the underlying runtime Bengal comes with a class that makes it possible for you to use. The capabilities of that class are limited to what the underlying operating system and/or runtime support so this class is the only non-portable part of Bengal.

### Java integration

The Java integration is delivered through the`Java` class. To interact with Java you would see something like the code snippet below:

```
  String myString = "My String";
  Java java = new Java();
  java.callStaticMethod("java.lang.System.out.println", myString)
```

The code above calls the `callStaticMethod` method which asks to call the`java.lang.System.out.println` static Java method and it passes `myString`. Note that the implementation of the Bengal runtime converts it from the Bengal class to the corresponding Java class. The following table illustrates what conversion is done.

| Bengal Class | Java Class       |
|--------------|------------------|
| String       | java.lang.String |

### Posix integration

The Posix integration is delvered through the `Posix` class. To interact with
a Posix compatible OS you would see something like the code snippet below:

```
  String myString = "My String";
  Posix posix = new Posix();
  posix.call("mylib.so", "myfunction", myString);
```

The code above calls the `call` method which asks to use the `mylib.so` library to call the `myfunction` function and it passes `myString`. Note that the implementation of the Bengal runtime converts it from the Bengal class to the corresponding Linux equivalent. The following table illustrates what conversion is done.

| Bengal Class | Linux equivalent |
|--------------|------------------|
| String       | char*            |

## Default classes

As the primitive types in Bengal are also classes you will have at minimum the
following classes available in any Bengal runtime.

1. Boolean
2. String
3. Integer
4. Character
5. Float
6. Nil
