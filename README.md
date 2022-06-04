# Packages

## Learning Goals

- Create and use packages 

## Packages in Java

Every time we have created a class so far, we have not specified a "package" for
it. In Java, packages are used to organize classes into "namespaces". Think of a
"namespace" as a bucket. Everything inside that bucket, all the classes inside
the package, must have a name that is unique inside the bucket.

Let's say company A, The Acme Corp, wants to implement student grading
functionality, and I, The Dunder Mifflin company, also want to implement student
grading functionality. And we both have the brilliant idea to create a
`StudentGradeTranslator` to help translate numerical grades into letter grades.

If Java only had a single namespace for all the classes that all the programmers
in the world ever wanted to create, then a lot of names would collide for people
who wanted to implement similar functionality, like our 2 companies in the
example above.

By convention, package names usually start with the reverse of a company's
domain name. E.g. `com.acme` and `com.dundermifflin` for the 2 fictional
companies in our example. From there, most companies package their classes based
on the systems and sub-systems they represent. So my `StudentGradeTranslator`
class may end up in a package named `com.dundlermifflin.grading` while the
Acme's class may end up in a package named `com.acme.education`.

Here are the main things you should know about packages in Java:

1. A package definition is not required for a class in Java - without one, the
   class belongs to the default namespace. Note: this is not recommended for any
   classes you will share with other developers/companies, as it is likely to
   create confusion and potential name collisions.
2. When a class belongs to a certain package, the package definition must be the
   first instruction in the class' source code and follow this format: "package
   <package-name>;". For my sample package, the package statement would be:
   `package com.dundlermifflin.grading;`
3. The rest of the class definition remains the same
4. Anyone who would want to use my class would have to import it using the
   "fully qualified class name", which starts with the package name and is
   following by a "." and the name of the class. For my example, I could import
   my `StudentGradeTranslator` class which resides in my
   `com.dundlermufflin.grading` package with the following `import` statement:
   `import com.dundlermufflin.grading.StudentGradeTranslator`
5. All classes within the same package can see and use each other without
   needing an `import` statement
6. Packages are a natural boundary for classes and access rules for classes,
   their fields and methods, are influenced by their position in a package -
   more on this in the section about "access modifiers".
