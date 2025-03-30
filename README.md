# TypeScript-go considered brilliant

TypeScript is being ported to Go. It's quite likely that you know this by now, as there have been excellent communications from the TypeScript team in a variety of forums.

It's been an object lesson in how to communicate well; straightforward, clear and open.

There's no shortage of content out there detailing what is known about the port. This piece is not that. Rather, it's the reflections of two people in the TypeScript community. What our thoughts, feelings and reflections on the port are.

It's going to be a somewhat unstructured wander through our reactions and hopes. Fingers crossed that's interesting for you!

## Who are John Reilly and Ashley Claymore?

John Reilly is a software engineer who was an early adopter of TypeScript. He worked on Definitely Typed, the home of high quality type definitions which allow the integration of TypeScript and JavaScript. He wrote the history of Definitely Typed and featured in the TypeScript documentary. He also worked (and works) on ts-loader, the webpack loader for TypeScript. He works at Investec, a South African bank and is based in London. The greatest city on earth (in his opinion).

Ashley is ....

## Performance 

It's useful to think about what the Go port meaningfully changes. 

Josh Goldberg has provided a useful framing on what TypeScript actually is. LINK It's four things:
1. Language
2. Type Checker
3. Compiler
4. Language services

The language and type checker are unaffected by the port. Syntax is unchanged. Code that failed to type check before, will still fail to type check.

But the compiler and the language services do change. They become an order of magnitude faster.

Put your hands up if you don't care about performance. That's right, no hands went up. We all care about performance.

If you ever have the misfortune to work with technology that lags, which breaks you out of flow as you are working, you notice it. It's almost the only thing you can notice.

The TypeScript team has always cared about performance, particularly in the area of development tooling.

Anders Hejlsberg in particular has mentioned in interviews, the needs for language servers to provide fast feedback. Something measured in milliseconds and not seconds.

https://learning-typescript-git-what-is-7c9279-josh-goldbergs-projects.vercel.app/articles/what-is-typescript

What are the implications of these changes to the TypeScript ecosystem? Put bluntly: a faster VS Code and faster builds.

Where I work, in Investec, we have many engineers who use VS Code and spend part of their engineering life writing TypeScript and JavaScript. All those engineers will benefit from a snappier development experience. When they open up a project in VS Code, the time taken for the language service to wake up will drop dramatically. As they refactor their code, the experience will be faster. The "time to red squiggly line" will drop.  

Engineers should be incrementally more effective, given that there are less pauses in their workflow.

The same incremental gain applies to builds. As our engineers build applications, they run TypeScript builds on their machines and in a Continuous Integration context.  These will all be faster than they were before. We'll continually bank a performance improvement which is a benefit. 

This, of course, is not Investec or Bloomberg specific. Rather this is a general improvement that everyone will benefit from.


TypeScript team won't be writing TS themselves - could this distance them from the community?
Probably not - community is too established to let this happen 
Also they've written atypical TS for most of that time due to lack of modules until 5.0
Wonder if it might reduce the TypeScript teams involvement with TC39 as they will have less of a stake in the direct usage of JavaScript, at least as consumers if not producers
Not rust. Pragmatic choice though 
Swc was enough for me
Maybe bun is going to give us the perf but nope
First language to start bootstrapping and then stop
What about ts-loader? APIs not sure - maybe it's the end? Hotel California webpack 

