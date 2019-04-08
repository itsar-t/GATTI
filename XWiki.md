# Case study

## Part 2

[XWiki][xwiki] is a software tool which purpose is to allow for users/developers to build mainly small applications as they put it "in a quick and organic manner" which otherwise wasn't likely to be build due to costs and complexity.

On their homepage can be found their [testing strategy][test] during the development of the software.

One thing they mention as a rule is that every time code gets commited the code must have associated automated tests.

 They also have tests in their CI which automatically executes and checks the mutation score which they mention is used to check the quality of their tests.
 The software they use to check this mutation score is [PITest][pitest].

They do not use the default mutation engine, I assume it is is because it takes to long, rather they use the [PIT-Decartes][decartes] mutation engine that is used for extreme mutation testing. They mention that it gives good indicators on what needs to be fixed.

Since they not using the default mutation engine (Gregor) they lose the functionalty of introducing tiny mutations in the code which are used for fine-grain testing the test suite.  

### Other testing performed

- Frequent unit and functional tests (CI also does this after every commit)
- Dock based testing is being increasingly used by the developers
- Manual tests at the releases that isn't covered by automated tests
- Performance tests
- Responsiveness tests
- Accessibility tests at each commit
- HTML5 validity tests at each commit

## Part 3

**1)  </br>What reason did you have for developing PITest?</br> Why did you choose to develop a tool for mutation testing? </br>Which situations is it good for and less good for?**

*I wrote it mainly because I was bored at work. Implementing a mutation testing tool was much more interesting than what I was being paid to do, so I had some fun putting it together and play with some ideas for how to write Java differently. I also wrote it because I thought it would help with some problems I was having at work with poorly written tests, but that was secondary to it being fun.
It's good for any situation where you are writing Java and have some code that is not so badly written that it is not possible to write proper unit tests. I use it on pretty much everything I do to stop me making mistakes. It lets me be lazy and incompetent and get away with it.
Unfortunately if you inherit code that is really badly designed with singletons, mutable static state or other poor choices that prevent properly isolated and repeatable unit tests from being written then mutation testing isn't a practical option.*

**2) How mature do you find PITest to be? Is it suitable for use by companies developing real-world software at scale?</br> Why / why not?**

*PIT is now very mature, it's getting on for 10 years old. It is used by companies all over the world.
</br>The way in which it is used is however probably very different from how many of the academics who studied/study mutation testing assumed it would be used. They often imagine a very waterfall style of development with mutation testing as some sort of final QA step. They also assume it is a technique that would only be used in safety critical systems due to the cost of implementing it in this waterfall manner. I have spoken to academics who refuse to believe that mutation testing is happening in the real world as they look to their contacts in these sorts of industries and don't see evidence of these big expensive top down driven exercises that they have imagined.
The way mutation testing is actually being used is mainly by individual developers, running the tool as they write the code and tests.*


**3) How do you plan to evolve and develop PITest going forward? </br> What are the main improvements needed to take it to the next level?**

*Unfortunately I have no particular plans to evolve pitest. Although it is widely used, in both industry and research, it doesn't bring me any income, so I find that I have less and less time to work on it due to other commitments. There are fundamental changes that would improve it, but those changes require larger chunks of time than I have.
</br>So it's evolution is currently limited to merging pull requests and making small improvements that can be fitted into the odd unplanned spare evening. *


[xwiki]: https://www.xwiki.org/xwiki/bin/view/Main/
[test]: https://dev.xwiki.org/xwiki/bin/view/Community/Testing/
[pitest]: http://pitest.org/
[decartes]: https://github.com/STAMP-project/pitest-descartes
