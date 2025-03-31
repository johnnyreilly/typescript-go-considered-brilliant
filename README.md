# TypeScript-Go considered brilliant

TypeScript is being ported to Go. It's quite likely that you know this by now, as there have been excellent communications from the TypeScript team in a variety of forums.

It's been an object lesson in how to communicate well; straightforward, clear and open.

There's no shortage of content out there detailing what is known about the port. This piece is not that. Rather, it's the reflections of two people in the TypeScript community. What our thoughts, feelings and reflections on the port are.

It's going to be a somewhat unstructured wander through our reactions and hopes. Bucle up for opinions and feelings.

## Who are John Reilly and Ashley Claymore?

John Reilly is a software engineer and an early adopter of TypeScript. He worked on Definitely Typed, the home of high quality type definitions which allow the integration of TypeScript and JavaScript. He wrote the history of Definitely Typed and featured in the TypeScript documentary. He also worked (and works) on ts-loader, the webpack loader for TypeScript. He works at Investec, a South African bank and is based in London. The greatest city on earth (in his opinion).

Ashley is ....

## Performance 

It's useful to think about what the Go port meaningfully changes. 

Josh Goldberg has [provided a useful framing on different aspects of TypeScript](https://www.learningtypescript.com/articles/what-is-typescript). It's four things:
1. Language
2. Type Checker
3. Compiler
4. Language services

The language and type checker are unaffected by the port. Syntax is unchanged. You'll still be writing `type`s and `interfaces`s as you were before. No difference.

The same applies to the type checker. Code that failed to type check before, will still fail to type check with TypeScript-Go:

```ts
const i: number = "not actually a number";
```

This is where the differences begin. The compiler and the language services do change. They become an order of magnitude faster.

Put your hands up if you don't care about performance. That's right, no hands went up. We all care about performance. If you ever have the misfortune to work with technology that lags, which breaks you out of flow as you are working, you notice it. It's almost the only thing you can notice.

The TypeScript team has always cared about performance, particularly in the area of development tooling. Anders Hejlsberg in particular has mentioned in interviews, the needs for language servers to provide fast feedback as people work. Something measured in milliseconds and not seconds.

What are the implications of these changes to the TypeScript ecosystem? Put simply: a faster VS Code and faster builds.

Where John works, at Investec, there are many engineers who use VS Code, and spend part of their engineering life writing TypeScript and JavaScript. All those engineers will benefit from a snappier development experience. When they open up a project in VS Code, the time taken for the language service to wake up will drop dramatically. As they refactor their code, the experience will be faster. The "time to red squiggly line" metric will decrease. And that's a good thing.

As a consequence, engineers should be incrementally more effective, given that there are less pauses in their workflow.

The same incremental gain applies to builds. As our engineers build applications, they run TypeScript builds on their machines and in a Continuous Integration context.  These will all be faster than they were before. We'll continually bank a performance improvement which is a benefit. 

This, of course, is not Investec or Bloomberg specific. Rather this is a general improvement that everyone will benefit from.

## The TypeScript team stop writing TypeScript

Many languages have [bootstrapping compilers](https://en.wikipedia.org/wiki/Bootstrapping_(compilers)). The compiler is written in the program language that is the compiler for. TypeScript has been an example of this since it was first open sourced. That is about to change; the compiler will stop being written in TypeScript and will start being written in Golang. This is possibly the first example of a language moving away from having a bootstrapping compiler.

Of all the aspects about the Golang port, this one was the one that caused John most anxiety. The TypeScript team will be moving away from writing TypeScript in their day to day lives. This means there is reduced [dogfooding](https://en.wikipedia.org/wiki/Eating_your_own_dog_food) - which means a reduction in direct feedback to the makers of TypeScript.

Given how broad the TypeScript community is, this is perhaps not the concern that it might be. The team are very connected with the community and even if they are writing TypeScript less, people who are writing more will be sure to be vocal. It's maybe worth remembering that for most of the time TypeScript has been around, the team has often written TypeScript in a style that is not representative of the broader community.  We're thinking here of modules.  Until Jake Bailey's mammoth work to [migrate the TypeScript codebase to use modules](https://devblogs.microsoft.com/typescript/typescripts-migration-to-modules/), the codebase used namespaces.  This didn't stop TypeScript working with ES Modules at all.  So it seems reasonable we need not fear.

Another angle on this, is wondering if the TypeScript team might become less involved with TC39 (the committee that develops the JavaScript language specification).  ASHLEY SAY THINGS!

 as they will have less of a stake in the direct usage of JavaScript, at least as consumers if not producers

## Go a good choice?

The internet is mad it's not Rust. But that section of the internet is mad that everything isn't Rust.

Not rust. Pragmatic choice though 
Swc was enough for me
Maybe bun is going to give us the perf but nope
First language to start bootstrapping and then stop
What about ts-loader? APIs not sure - maybe it's the end? Hotel California webpack 

