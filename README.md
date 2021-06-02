## Reproduction of Zinc bug with `scalac -release`

```
> sbt clean compile && sbt compile 'last compileIncremental'
[info] Updated file /Users/jz/code/zinc-bug-release-flag/project/build.properties: set sbt.version to 1.5.2
[info] welcome to sbt 1.5.2 (AdoptOpenJDK Java 11.0.11)
[info] loading project definition from /Users/jz/code/zinc-bug-release-flag/project
[info] loading settings for project zinc-bug-release-flag from build.sbt ...
[info] set current project to zinc-bug-release-flag (in build file:/Users/jz/code/zinc-bug-release-flag/)
[info] Executing in batch mode. For better performance use sbt's shell
[success] Total time: 0 s, completed 2 Jun. 2021, 11:08:31 am
[info] compiling 1 Scala source to /Users/jz/code/zinc-bug-release-flag/target/scala-2.12/classes ...
[success] Total time: 3 s, completed 2 Jun. 2021, 11:08:34 am
[info] welcome to sbt 1.5.2 (AdoptOpenJDK Java 11.0.11)
[info] loading project definition from /Users/jz/code/zinc-bug-release-flag/project
[info] loading settings for project zinc-bug-release-flag from build.sbt ...
[info] set current project to zinc-bug-release-flag (in build file:/Users/jz/code/zinc-bug-release-flag/)
[info] Executing in batch mode. For better performance use sbt's shell
[info] compiling 1 Scala source to /Users/jz/code/zinc-bug-release-flag/target/scala-2.12/classes ...
[success] Total time: 3 s, completed 2 Jun. 2021, 11:08:41 am
[debug] [zinc] IncrementalCompile -----------
[debug] IncrementalCompile.incrementalCompile
[debug] previous = Stamps for: 1 products, 1 sources, 5 libraries
[debug] current source = Set(${BASE}/src/main/scala/test.scala)
[debug] Invalidating '/876/java/io/PrintStream.sig' because could not find class java.io.PrintStream on the classpath.
[debug] Invalidating '/8/java/lang/String.sig' because could not find class java.lang.String on the classpath.
[debug] Invalidating '/8/java/lang/System.sig' because could not find class java.lang.System on the classpath.
[debug] Invalidating '/876/java/lang/Object.sig' because could not find class java.lang.Object on the classpath.
[debug] > initialChanges = InitialChanges(Changes(added = Set(), removed = Set(), changed = Set(), unmodified = ...),Set(),Set(/876/java/io/PrintStream.sig, /876/java/lang/Object.sig, /8/java/lang/String.sig, /8/java/lang/System.sig),API Changes: Set())
[debug]
[debug] Initial source changes:
[debug] 	removed: Set()
[debug] 	added: Set()
[debug] 	modified: Set()
[debug] Invalidated products: Set()
[debug] External API changes: API Changes: Set()
[debug] Modified binary dependencies: Set(/876/java/io/PrintStream.sig, /876/java/lang/Object.sig, /8/java/lang/String.sig, /8/java/lang/System.sig)
[debug] Initial directly invalidated classes: Set()
[debug] Sources indirectly invalidated by:
[debug] 	product: Set()
[debug] 	binary dep: Set(${BASE}/src/main/scala/test.scala)
[debug] 	external source: Set()
[debug] all 1 sources are invalidated
[debug] Initial set of included nodes:
[debug] Recompiling all sources: number of invalidated sources > 50.0% of all sources
[debug] compilation cycle 1
[info] compiling 1 Scala source to /Users/jz/code/zinc-bug-release-flag/target/scala-2.12/classes ...
[debug] Getting org.scala-sbt:compiler-bridge_2.12:1.5.3:compile for Scala 2.12.14
[debug] [zinc] Running cached compiler 64ceb4ce for Scala compiler version 2.12.14
[debug] [zinc] The Scala compiler is invoked with:
[debug] 	-release
[debug] 	8
[debug] 	-bootclasspath
[debug] 	/Users/jz/Library/Caches/Coursier/v1/https/repo1.maven.org/maven2/org/scala-lang/scala-library/2.12.14/scala-library-2.12.14.jar
[debug] 	-classpath
[debug] 	/Users/jz/code/zinc-bug-release-flag/target/scala-2.12/classes
[debug] Scala compilation took 2.092767315 s
[debug] done compiling
```