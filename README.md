# MPS Libraries for Java 8

MPS uses Java 11 since version 2019.2 and all the JARs are compiled with Java 11 as the target, including libraries that
can be used by the generated code, such as collections and closures runtimes.

This makes it impossible to run the generated code under Java 8 VM anymore.

The solution is to build these libraries to be Java 8-compatible and this is what this project does.

# Checking out

```shell script
git clone git@github.com:mbeddr/mps-libs-java8.git --recurse-submodules --shallow-submodules
```

Or if you already cloned it without submodules:
```shell script
git submodule update --init --depth 1
```

The shallow/depth parameters tell Git to skip cloning the decades of MPS history and only get the one required commit.

# Building

Build using Maven (`mvn package` or `mvn install` or `mvn deploy` depending on your needs).

# For Maintainers: Updating to a New Version of MPS

`VVVV` below is the new MPS version.

1. Update Maven version:
   ```shell script
   mvn versions:set -DnewVersion=VVVV
   ```

2. Update the MPS submodule to the new version:
   ```shell script
   cd MPS
   git fetch --depth 1 origin tag VVVV
   git checkout VVVV
   ```
