Android unsafe wrapper (Experimental)
=====================================

Documented android unsafe wrapper for using internal `sun.misc.Unsafe` api.
Android has no `sun.misc.Unsafe` class in standard sdk library.
This library solves this problem by using compiled direct access to system class library (without using reflection).

**Use only for experimental proposes and between pre-compiled dependency from jcenter because `sun.misc.Unsafe` doesn't included in sdk library and you just cannot create Unsafe class from source code!**

For more explanation see this articles list:

1. https://dzone.com/articles/understanding-sunmiscunsafe
2. http://mishadoff.com/blog/java-magic-part-4-sun-dot-misc-dot-unsafe

Adding:
-------
For using in your own projects just add jcenter repository superset:

```groovy
repositories {
    maven {
       url  "https://dl.bintray.com/letuananh035/maven"
    }
}
```
And after it you should just add as compile dependency:

```groovy
implementation 'com.letuananh035:unsafe:0.0.7'
```

Usage:
------

You should use `UnsafeAndroid` library class for `Unsafe` class access:

```java
final UnsafeAndroid unsafe = new UnsafeAndroid();
final Bitmap bitmap = unsafe.allocateInstance(Bitmap.class);
```

## License
```
Copyright 2016 Alexander Efremenkov

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```
