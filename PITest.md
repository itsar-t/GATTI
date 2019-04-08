# [PITest][pitest]
[PITest][pitest] is a mutation testing system for java and jvm (java virtual machine) which main purpose is to asses the quality and hence generate confidence of a written test suite.  

**Testing Approach:** Mutation testing
</br>**Testing Level:** Unit test
</br>**Target application domain:** The test suite of a java application.
****

## Features
- Users are able to plug-in their own functionallity into the software.
- The prioritizing order in which test should be executed can be defined by users but are by default cheapest (least amount of time) first.  
- Other mutation engines than [PITest's][pitest] default one (Gregor) can be integrated in the software.
- Extreme mutation testing can be used through decartes ([PIT-Decartes][decartes]) a mutation engine designed for [PITest][pitest]
- Able to gather data from previous mutation testing cycles to eleminate redundant testing in future ones.

## Pros
- Fast (compared to previous mutation testing) due to:
  - parallelization
  - good test selection (using collected line-coverage data)
  - no compilation (bytecode changed to create mutations)
  - rememberes data from previous testing (if turned on)
- Generates easy to read, color-coded reports where line-coverage is combined with mutation-coverage.
  - Makes it easy to find the exact location (class, linenumber) of the code where something may not work as intended or not been correctly tested.
- Works with almost all mocking frameworks.

## Cons
- Mutation testing is an expensive operation
  - Even if [PITest][pitest] has increased the performance of mutation testing a whole lot it can still require a bit of time to perform.
- Can be time-consuming
  - Sometimes it can be hard finding the reason behind a failed test since it can occur for several resons. It could as easily be due to a missing test case as it can occur because of an equivalent mutant. Requires a human to analyse and figure out the reason.
- Only works with java / jvm.


## Required information / models
Java-code written in such a way that proper unit tests can be written for it. Unit tests made with either **JUnit** or **TestNG**.   

## Target platform and dependencies

Source-code for [PITest][pitest] can be dowloaded or cloned in to on [GitHub][git]. There exist several softwares with the plugin to use [PITest][pitest].

**Plugins:**
- [Gradle][gradle]
- [Maven][maven]
- [Eclipse][eclipse]
- [IntelliJ][intellij]

**Dependencies:**
- **Java 5** or above
- **JUnit 4.6** or above
- **TestNG 6.1.1** (may work with earlier versions)
- **JUnit** or **TestNG** to be on the classpath.
- **JVM** that supports **XStream’s enhanced mode**.

## Updates


- **Latest update:** 1.4.7 was released on 29 Apr 2019
- **First release date:** 0.33 was released on 25 Mar 2014 on [GitHub][gitrel]
  - According to the releases section on [PITest][pitest] this wasn't the first release but rather the first release after [PITest][pitest] migrated to GitHub. Earlier realeses can be seen [here][release].

## Licensing / Cost
[PITest][pitest] is a free open-source software with [Apache License, Version 2.0][license]

## Tutorials and documentation
The best way to get started would be to go through the [quickstart guide][quick] on the tools webpage.

**Videos:**
- [Mutation Testing][brief] - a video where *Henry Cole* (developer of [PITest][pitest]) talks about the concept of mutation testing and briefly introduces his testing tool (28 min).
- [Mutation Testing + Live Demo][long] - a video  a video where *Henry Cole* (developer of [PITest][pitest]) talks about the concept of mutation testing (same presentation as above) and also performs a live demo of his tool (103 min).

## Usage examples
According to *Henry Cole* (developer of [PITest][pitest]) his tool has been used all over the world. Here is a few examples I've heard him mention:
- **The Ladders** - New York
- **SKY** - Livingston
- Insurance Companies
- Investment banks
- Biotech Companies
- Norway's e-voting system

After some digging I also found that [PITest][pitest] is being used by [XWiki][xwiki].

## Alternative tools
- [MutPy][pyt] - Mutation testing tool for python.
- [Mull][mull] - Mutation testing tool with a strong focus on C and C++ languages.
- [Stryker][stryker] - Mutation testing tool with support fot JavaScript & TypeScript, C# and Scala

[pitest]: http://pitest.org/
[license]: https://www.apache.org/licenses/GPL-compatibility.html
[decartes]: https://github.com/STAMP-project/pitest-descartes
[git]: https://github.com/hcoles/pitest
[gradle]: https://gradle-pitest-plugin.solidsoft.info/
[maven]: https://github.com/STAMP-project/pitmp-maven-plugin
[eclipse]: https://github.com/philglover/pitclipse
[intellij]: https://plugins.jetbrains.com/plugin/7119-pit-mutation-testing-idea-plugin
[release]: http://pitest.org/downloads/
[gitrel]: https://github.com/hcoles/pitest/releases?after=pitest-parent-1.0.0
[quick]: http://pitest.org/quickstart/
[brief]: https://vimeo.com/145201725
[long]: https://www.youtube.com/watch?v=nf2xpqcZouY
[xwiki]: https://dev.xwiki.org/xwiki/bin/view/Community/Testing/
[pyt]: https://github.com/mutpy/mutpy
[mull]: https://github.com/mull-project/mull
[stryker]: https://stryker-mutator.io/
