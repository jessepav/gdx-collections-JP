# gdx-collections-JP

A variant of [`gdx-collections`](https://github.com/mini2Dx/gdx-collections) with a simpler build
system, and a Java 7 target. Also, this project does not rename packages, but leaves all classes
in their original `com.badlogic.gdx.*` structure.

From `gdx-collections`:

> [LibGDX](https://libgdx.com/) [collection classes](https://github.com/libgdx/libgdx/wiki/Collections)
> extracted into a standalone library (i.e. no OpenGL, LWJGL, etc. required)
> 
> This is useful for those who need high performance collections on the JVM but aren't building an
> application with LibGDX.

## Building

`ant dist` will generate 

```
gdx-collections-JP.jar
gdx-collections-JP-javadoc.jar
gdx-collections-JP-sources.jar
```

in the `dist` directory.

Run `ant -p` for other targets.

## Updating Collections Classes

`src-includes.lst` contains the relative paths of all the files that we're using from `LibGDX`.
If any additional files are needed, add them to that file.

Then run `ant -Dgdx.version=<version> copysrc` (where `<version>` is a released LibGDX version
number, such as `1.9.13`), which will fetch the `gdx-<version>-sources.jar` file from Maven Central
and copy all the referenced files out of the .jar and into our `src` folder.


<!-- :maxLineLen=100: -->