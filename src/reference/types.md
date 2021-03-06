# Types and Namespaces

Emojicode is a strongly type language and therefore has very strict rules
concerning types.

Types are defined by classes, protocols, enums and primitives. Seperate chapters
are devoted to classes, protocols and enums.

## Primitives

Primitives are a special kind of type as they are part of the language and are
nowhere defined in the s package. They are built into the language and therefore
also directly known by the compiler. As with class types you can call methods on
primitives, you, however, cannot inherit from primitives or extend them. Methods
of primitive types are known as *primitive methods*.

You have already gotten to the primitive types. They are:

- 🚂
- 🚀
- 👌
- 🔣
- ✨

## Namespaces

Each type when defined is loaded into a namespace. By definition the type
doesn’t bascially belong to this namespace but is *reachable* through this
namespace. A type may actually even be reachable through multiple namespaces.

>!H The facts above play a very important role when importing other packages.

Everywhere a type name is expected you can either just use the name of the type
without explicitely specifying a namespace and the type will be assumed to be
reachable thorugh the default namespace 🔴, or you can explicitely specify a
namespace with the namespace accessor:

```
🔶 namespace name
```

This identifies type *name* of namespace *namespace*. Both must be exactly one
identifier.

This is an example of explicitly referring to the 🔡 class in 🔴:

```
🔶🔴🔡
```

You can use this syntax everywhere you would specify a type name, thus also when
declaring a type. The example below declares the class 🎁 and makes it available
in namespace 🎅:

```
🐇 🔶🎅🎁 🍇

🍉
```

Remember that the class’s name is nevertheless just 🎁 but was made reachable
in the 🎅 namespace.

## ⚪ Something

Something is a special type as it is compatible to *all* other types. Because of
this you cannot call methods or perform any actions on ⚪.

It is an abstract type and therefore only known at compile-time. You cannot cast
to ⚪ at run-time.

## 🔵 Someobject

Someobject is compatible to *all* instances of classes, but not to primitive
values.

It is an abstract type and therefore only known at compile-time. You
cannot cast to 🔵 at run-time.

## 🔲 Casting

*Casting* is a way to determine whether a value is of a given type and to treat
the value as this type of value.

Type casting is implemented with the 🔲 statment:

```
🔲 something type
```

*something* must be the value to cast and *type* must be a valid type.

If *something* can be casted to *type* *something* is returned as *type*.
If *something* cannot be casted to *type* Nothingness is returned.

Here for instance, a value from a parsed JSON string is downcasted:

```
🍦 object 🗞 🔤"catwalk"🔤 👴 object is of type ⚪️
🍦 string 🍺 🔲 object 🔡

😀 string 👴 Prints catwalk
```

Type casting may not be confused with type conversion. You can’t cast 🚂 to
🚀. In such a case you would have to use appropriate methods.
