IT Thoughts
===========

<h3>ABOUT</h3>

This is a collection of articles illustrating the principles highlighted within the IT Framework (https://github.com/ibmendoza/it-framework).



<h3>COPYRIGHT</h3>

All rights and copyright are reserved by respective authors of the articles herein.

Compiled by Isagani Mendoza (http://itjumpstart.wordpress.com)

<h3>SHARE</h3>

You can freely share this PDF as long as it is not used for any commercial purposes.

<h1>Requirements Gathering</h1>

<h2>Specification by Example</h2>

By Gojko Adzic ([source](http://specificationbyexample.com/key_ideas.html))

<h3>Key Ideas</h3>

Specification by Example is a set of process patterns that facilitate change in software products to ensure that the right product is delivered efficiently. When I say the right product, I mean software that delivers the required business effect or fulfills a business goal set by the customers or business users and it is flexible enough to be able to receive future improvements with a relatively flat cost of change.

These processes are patterns because they occur in several different contexts and produce similar results. Most of the teams implemented these process ideas by trial and error, looking for better ways to do things and implement software more efficiently.
Deriving Scope From Goals

Many teams expect a customer, a product owner or a business user to come up with the scope of work before the implementation starts. Everything before that is often not considered as a problem in the domain of a software development team. Software delivery teams expect business users to specify exactly what they want, and then the teams will go and implement that. This is supposedly how the customers will be happy. In fact, this is where the issues with building the right product start. Implementation scope represents a solution to a business problem or a way to reach a business goal. By relying on customers to give us a list of user stories, use cases, or anything like that, we, in effect, ask them to design a solution. Business users are not software designers. If they define scope, the project does not benefit from the knowledge of the people in the delivery team. This often results in software that does what the customer asked for but does not deliver what they really wanted or is functionally incomplete.

Instead of requirements that are already a solution for an unknown problem, really successful teams derive scope from goals. They start with a business goal that the customer wants to achieve. They collaboratively define the scope that achieves that business goal, starting from the desired business effect. They allow the team to come up with a good solution together with the business users. The business users focus on communicating the intent of the desired feature--the value that they expect to get out of it. This helps everyone understand what is needed. The team can then suggest a solution that is cheaper, faster, easier to deliver or maintain than what the business users would come up with on their own. For more information, see Impact Mapping.

<h3>Specifying Collaboratively</h3>

If developers and testers are not engaged in designing the specifications, those specifications have to be separately communicated to the team. In practice, this leaves a lot of opportunities for misunderstanding and details being lost in translation. As a consequence, business users have to validate the software after delivery, and teams have to go back to change it if it fails validation. This is all unnecessary rework.

Instead of relying on any single person to get the specifications right in isolation, successful delivery teams engage in specifying the solution collaboratively with the business users. People coming from different backgrounds use different heuristics to solve problems and have different ideas. Technical experts know how the underlying infrastructure can be used better, or how emerging technologies can be applied. Testers know how the system is likely to break or where to look for potential issues, and these issues should be prevented from occurring in the first place. All this information needs to be captured as the specification of work.

Specifying Collaboratively enables us to harness the knowledge and experience of the whole team. It also creates a collective ownership of specifications, making everyone much more engaged in the delivery process.
Illustrating using examples

Natural language is ambiguous and context dependent, so any requirements described in natural language are rarely complete. They simply don't provide a full and unambiguous context for development or testing. Developers and testers have to interpret such requirements to produce software and test scripts, and different people might interpret tricky concepts differently. This is especially problematic when something seems obvious but we need domain expertise or knowledge of a particular jargon to understand it fully. Small differences in understanding will produce a large cumulative effect, often causing rework straight after delivery. This causes unnecessary delays. Instead of waiting for specifications to be made concrete for the first time in programming language code, successful teams make them concrete by illustrating using examples. They identify and record key examples, typical representative examples for all important classes of functions required to fulfill a specification. Developers and testers often suggest additional examples that illustrate edge cases or particularly problematic areas of the system. This flushes out functional gaps and inconsistencies and ensures that everyone involved has a shared understanding of what needs to be delivered, avoiding rework caused by misinterpretation and translation.

If the system works correctly for all the key examples, we know that it meets the specification we collaboratively agreed on. In fact, key examples effectively define what the software needs to do. They are both the target for development and an objective evaluation criterion to check whether the development is done. If the key examples are easy to understand and communicate, we can replace the requirements with the key examples.
Refining the specification

An open discussion during the collaboration on specifications builds a shared understanding of the domain, but the resulting examples often have a lot more detail than is really needed to illustrate a particular feature. Business users think about the system from the user interface perspective so they will offer examples of how something should work at the level of clicking on links and filling in fields. Using such verbose descriptions overconstrains the system and already specifies how something should be done rather than just what is to be done. Surplus details make the examples harder to communicate and understand. Key examples need to get cleaned up to be useful. By refining the specification from key examples, removing all the extraneous details, successful teams get a very concrete and precise context for development and testing. They define the target with enough detail to implement and verify it but without any additional information. They define what the software is supposed to do, not how it does it.

Refined examples can be used as an acceptance criterion for delivery. Development is not done until the system works correctly for all these examples. With some additional information to make key examples easier to understand, they make up a specification with examples, which is at the same time a specification of work, an acceptance test, and a future functional regression test.

<h3>Automating validation without changing specifications</h3>


Once we agree on specifications with examples and refine them, we can use them as a target for implementation and to validate the product. The system will be validated many times with these tests during development, to ensure that it meets the target. Running these checks manually would introduce unnecessary delays and the feedback from that would be very slow.

Quick feedback is an essential part of developing software in short iterations or in flow mode, so we need to make the process of validating the system cheap and efficient. An obvious solution to this is automation. However, this automation is conceptually different from the usual developer or tester automation. If we automate the validation of the key examples using traditional programming (unit) automation tools or traditional functional test automation tools, we risk introducing problems if things get lost in translation between the business specification and technical automation. Technically automated specifications will become inaccessible to business users. When the requirements change (and it is when, not if) or when developers or testers need further clarification, we won't be able to just use the specification that we previously automated. We could keep the key examples also in a more readable form, such as Word documents or web pages but, as soon as there is more than one version of truth, we'll have synchronization issues. That is why big paper documentation is never completely correct.

To get the most out of key examples, successful teams automate the validation without changing the information. They keep everything in the specification literally the same when automating, without any risk of mistranslation issues. As they automate validation without changing specifications, the key examples stay almost in the form they were in on a whiteboard--human-readable and accessible to all team members.

An automated specification with examples, still in a human-readable form and easily accessible to all team members, becomes an executable specification. We can use it as a target for development and easily check if the system does what we agreed. We can use that same document to get clarification from business users. If we need to change the specification, we have to do it in one place only.


<h3>Validating frequently</h3>

In order to efficiently support a software system, we have to know what it does and why. In many cases, the only way to do this is to drill down into programming code or find someone who can do that for you, if you aren't a hieroglyphics expert. Code is often the only thing we can really trust. Most written documentation is out of date even before the project is delivered. Programmers become oracles of knowledge and bottlenecks of information. Executable specifications can easily be validated against the system to check if it still does what it was supposed to do. If this validation is frequent, then we could have as much confidence in the executable specifications as we have in the code.

By checking all their executable specifications frequently, the teams quickly discover any differences between the system and the specifications. Because their executable specifications are easy to understand, the teams can discuss the changes with their business users and decide how to address the problems. They constantly keep their systems and executable specifications in sync.


<h3>Evolving a documentation system</h3>

The most successful teams are not satisfied with just a set of frequently validated executable specifications. They ensure that the specifications are well organized, easy to find and access, and consistent. As their project evolves, the team's understanding of the domain changes. Market opportunities cause changes to the business domain models. The teams that get the most out of Specification by Example update the specifications to reflect those changes, evolving a living documentation system. A living documentation replaces all the artifacts that teams need for delivering the right product but in a way that fits nicely with short iterative or flow processes.

Living documentation is a reliable and authoritative source of information on system functionality, which anyone can easily access. It is as reliable as the code, but much easier to read and understand. Support staff can use it to find out what the system does and why. Developers can use it as a target for development. Testers can use it for testing. Business analysts can use it as a starting point when analyzing the impact of a requested change of functionality. And it gives us regression testing for free.

Living documentation is the end-product of Specification by Example. To create a living documentation system, many teams have ended up designing a domain specific language for specifications and tests. They structured their specifications around that language to keep them consistent and easy to understand and to minimize long-term maintenance costs. When retrofitting executable specifications into already existing products, teams often had to make the system and the architecture more testable, which required senior people to plan and implement serious design changes.

<h1>Much ado about UNIX Philosophy</h1> 

<h2>Where the UNIX philosophy breaks down</h2>

by John D. Cook ([source](http://www.johndcook.com/blog/2010/06/30/where-the-unix-philosophy-breaks-down))

Unix philosophy says a program should do only one thing and do it well. Solve problems by sewing together a sequence of small, specialized programs. Doug McIlroy summarized the Unix philosophy as follows.

> This is the Unix philosophy: Write programs that do one thing and do it well. Write programs to work together. Write programs to handle text streams, because that is a universal interface.

This design philosophy is closely related to “orthogonality.” Programs should have independent features just as perpendicular (orthogonal) lines run in independent directions.

In practice, programs gain overlapping features over time.  A set of programs may start out orthogonal but lose their uniqueness as they evolve. I used to think that the departure from orthogonality was due to a loss of vision or a loss of discipline, but now I have a more charitable explanation.

The hard part isn’t writing little programs that do one thing well. The hard part is combining little programs to solve bigger problems. In McIlroy’s summary, the hard part is his second sentence: Write programs to work together.

Piping the output of a simple shell command to another shell command is easy. But as tasks become more complex, more and more work goes into preparing the output of one program to be the input of the next program. Users want to be able to do more in each program to avoid having to switch to another program to get their work done.

For example, think of the Microsoft Office suite. There’s a great deal of redundancy between the programs. At a high level, Word is for word processing, Excel is the spreadsheet, Access is the database etc. But Excel has database features, Word has spreadsheet features, etc. You could argue that this is a terrible mess and that the suite of programs should be more orthogonal. But someone who spends most of her day in Excel doesn’t want to switch over to Access to do a query or open Word to format text. Office users are grateful for the redundancy.

Software applications do things they’re not good at for the same reason companies do things they’re not good at: to avoid transaction costs. Companies often pay employees more than they would have to pay contractors for the same work. Why? Because the total cost includes more than the money paid to contractors. It also includes the cost of evaluating vendors, writing contracts, etc. Having employees reduces transaction costs.

When you have to switch software applications, that’s a transaction cost. It may be less effort to stay inside one application and use it for something it does poorly than to switch to another tool. It may be less effort to learn how to do something awkwardly in a familiar application than to learn how to do it well in an unfamiliar application.

Companies expand or contract until they reach an equilibrium between bureaucracy costs and transaction costs. Technology can cause the equilibrium point to change over time. Decades ago it was efficient for organizations to become very large. Now transaction costs have lowered and organizations outsource more work.

Software applications may follow the pattern of corporations. The desire to get more work done in a single application leads to bloated applications, just as the desire to avoid transaction costs leads to bloated bureaucracies. But bloated bureaucracies face competition from lean start-ups and eventually shed some of their bloat or die. Bloated software may face similar competition from leaner applications. There are some signs that consumers are starting to appreciate software and devices that do less and do it well.

<h2>The Fallacy of Tiny Modules</h2>

by Eran Hammer ([source](http://hueniverse.com/2014/05/30/the-fallacy-of-tiny-modules/))

There is this myth, that if you break software into many tiny, super focused pieces, life is better. Bullshit.

Remember when object oriented languages were the shit? Breaking a complex system into small discrete pieces, exposing an abstracted interface, and reusing code by keeping everything highly specialized? Wasn’t it fun!

Call it what you like. Microservices, tiny modules, components, whatever. The bottom line is simple – at some point, someone has to put it all together and then, all the complexity is going to surface and the shit will hit the fan. Microservices are a nice idea and can be a valid architecture decision in some cases, but let’s not pretend that the people running the overall system are going to like it. Trading a large code based routing table for a large load balancer configuration isn’t better (actually, it is usually way worse).

Those promoting the idea of a utopia with a million tiny node modules living happily on npm keep using UNIX as their winning argument. The problem is that it is a false comparison. Small focused components making up the UNIX shell environment are only viable because UNIX is part of a curated distribution. Someone did the nasty hard work of picking a baseline functionality for you. More than that, that collection has been defined into a standard so that whatever UNIX flavor you are on, you can feel right at home.

Imagine if UNIX came with nothing but the kernel. No distributions. You install an empty kernel and then use some package manager to pick your copy, move, and list commands. Not much fun anymore, is it?. But wait, now go pick your flavor of grep, sed, and awk. Now make sure they all work well together and use the same flavor of regular expressions. Now make sure you keep everything up to date for security and stability.

This is what frameworks provide. In practice, a framework is a curated collection of functionality provided as a distribution. By picking a framework, you are picking a “single purpose node distribution” suitable for your application needs. The framework should allow you to swap the components with others but that baseline is the main value proposition. You buy into an ecosystem and in return you get a usable environment out of the box.

Tiny modules are a useful tool and a valuable design because they allow the construction of highly specific environments. But in most application development environments of any meaningful size, someone has to be the curator. Someone has to pick what’s being used and keep the collection both in sync and up to date, just like every UNIX distribution does.

You can argue that this someone is the developer building the application but that’s just not practical for the same reason you let others pick your operating system toolbox, your hardware toolbox, and even within node, your built-in toolbox. And this is just what’s under your web app. Don’t forget the entire front end side on top of it. Drawing the line at “everything on top of node” is an impractical and unproductive choice.

This is why frameworks matter. Go pick one.

(The author is highly biased as the lead developer of one such framework - Hapi.js)

<h2>Many Things</h2>

by James Halliday ([source](http://substack.net/many_things))

**So it is**

As a true believer in the UNIX way of tiny self-contained modules that each do just one thing, I find myself at a fundamental disagreement when talking with IDE-adherents or framework-oriented programmers.

When abstractions are kept to the minimum necessary, it's much easier to see which ones are good ideas and which ones are mistaken ideas. With larger collections of ideas branded into cohesive framework ideologies, it's very easy for unjustified abstractions to sneak in under the cover of the more useful pieces.

So it is with many things.

Do one thing well even if that one thing turns out to be a bad idea. Publish your mistakes to save the next person who gets the same idea about how things could be the trouble of re-implementing the same mistakes.

**Monopoly**

It used to be the languages had a monopoly on abstractions. The standard distribution would bundle some handy libraries to do common things like option parsing, making http requests, and sending email. This made sense at the time. When you installed a distribution of UNIX or Linux you get the BSD or GNU toolchain of handy utilities so the same logic should apply.

But these standard libraries grew rotten. Nobody could give them the love and care they needed because the core team was too busy evolving the language, iterating on the runtime, and improving performance. The core team forgot about poor little distutils.

It's actually far worse than merely forgetting about a neglected expanded core: the versioning on core modules is intrinsically linked to the distribution release cycle as a whole so making any changes becomes a beaurocratic protracted struggle that few potential contributors have the patience for. Warts accumulate. Code calcifies around bugs that make it impossible to make necessary changes without breaking everything.
pulling from the outside

The reason bundles can work for system distributions is that the people working on the distributions are just pulling in from external resources, not pushing the new iterations themselves. The work happens outside from the community at large and is pulled in. This independence makes it much less daunting to fix bugs, improve APIs, and experiment.

Need to make a breaking change? No problem, just bump the major version. Trust that any packages downstream will be sufficiently careful with their dependency semvers.

**Welded shut**

Frameworks side-step the versioning problem that core platforms have by adopting the system distribution model for bundling up handy, common utilities in a convenient way.

However, when you choose a framework, you trade away some temporary convenience for long-term flexibility. This may be an appealing bargain, particularly for short-lived applications as it imposes an immediate sense of structure on an otherwise blank slate that might very indeed get software built before a deadline.

However, it's much harder to change your mind about a choice that you never made yourself. When frameworks make your decisions for you, you very often won't even realize that a decision has been made at all so it's much harder to identify problems when the assumptions grounded in that technology choice no longer apply.

Another problem with short-sighted calculations is that it's very hard to know which applications really are one-offs and which ones will have a surprisingly enduring lifespan. And when a project "ends", it doesn't usually "end". It's just that the current contract is up, so any improvements will need to be made in a separate contract with perhaps a different team at the helm. Extend empathy to next person to work on some code, because that next person could be you!

An argument I often hear in favor of frameworks is that it helps a big team rally around some common tools that everybody is familiar with. This is true, but I often observe the same benefits collaborating with people who use some of my favorite low-level stream modules like through and duplexer or when authors use interfaces from node core like .pipe().

To be fair, there is a distinction here between frameworks that are sheer mudballs of compounded assumptions and frameworks that take the time to carefully factor out themselves into lots of tiny pieces. I think an important standard to judge frameworks is how many of the framework's core abstractions can be used ala-carte without using the framework itself. If your framework melts away into an informal collection of modules that happen to work well together but can be easily repurposed by people who don't use the framework, then you have built something very sublime.

**Cooking up some modules**

If some problems naturally turn out to naturally trend towards monopoly then that is something that we should notice and accept. However, I expect that the number of these natural monopolies which actually exist is far lower than many people assume right now.

Tools like github and free-for-all package managers like npm continue to remove barriers to entry to such a point that the fitness landscape of software is a fundamentally different place than just 10 years ago.

What we need right now is not more frameworks to give a collection of modules a cohesive "brand" with divisive opinions about what "belongs". Instead, we need more recipes, articles, talks, and screencasts about how all these pieces fit together.

We need to be better about how to go from problem A to solution B by way of modules X, Y, and Z.

There should be more public discussion about what modules to use for which problems and when.

There should be more meta-analysis too about different fundamental design axioms at work behind certain clusters of libraries versus other clusters.

Keep publishing modules and learning new facts by experiment of course, but if we are going to obtain this lofty goal set forth by ryan dahl


> I want programming computers to be like coloring with crayons and playing with duplo blocks.

Then we'll need more than code. We'll need documentation and community!

<h2>UNIX Philosophy and Node.js</h2>

by Isaac Schlueter ([source](http://blog.izs.me/post/48281998870/unix-philosophy-and-node-js))

At TxJS the other day, I gave a talk where I mentioned that the Unix Philosophy is a crucial part of the patterns, opinions, and culture of Node.js. As usual, I made my slides available online well in advance of the talk video being available.

For some reason, this brief mention of “Unix Philosophy” set off a few peoples’ ire. Since I had only 25 minutes, and every slide could probably be its own talk entirely, I was rather light on elaboration. Chances are, the video won’t add all that much context. But the goal was to pique conversation, so maybe that’s a success if it invites criticism. After all, uninformed trolling is just an invitation for education, so I thought I’d explain.

Eric S. Raymond collected a few of the best explanations of the Unix Philosophy in his book, The Art Of Unix Programming. He elaborates on 17 specific principles, but my favorite formulation of the Unix Philosophy is the terse explanation from Doug McIlroy as quoted by Salus in A Quarter Century of Unix:

This is the Unix philosophy:

- Write programs that do one thing and do it well.

- Write programs to work together.

- Write programs to handle text streams, because that is a universal interface.

McIlroy’s slightly longer original 4-point formulation is this:


1. Make each program do one thing well. To do a new job, build afresh rather than complicate old programs by adding new features.
2. Expect the output of every program to become the input to another, as yet unknown, program. Don’t clutter output with extraneous information. Avoid stringently columnar or binary input formats. Don’t insist on interactive input.
3. Design and build software, even operating systems, to be tried early, ideally within weeks. Don’t hesitate to throw away the clumsy parts and rebuild them.
4. Use tools in preference to unskilled help to lighten a programming task, even if you have to detour to build the tools and expect to throw some of them out after you’ve finished using them.

Mike Gancarz, who worked on the X Window System, summed up the Unix Philosophy in 9 points:

1. Small is beautiful.
2. Make each program do one thing well.
3. Build a prototype as soon as possible.
4. Choose portability over efficiency.
5. Store data in flat text files.
6. Use software leverage to your advantage.
7. Use shell scripts to increase leverage and portability.
8. Avoid captive user interfaces.
9. Make every program a filter.

That last point really resonates with something that Ryan Dahl has often said, “Every program is a proxy.” The first 3 are basically James Halliday’s rules for living.

All too often, people get hung up on the wrong aspects of the Unix Philosophy, and miss the forest for the trees. The Unix Philosophy is not about a specific implementation, or anything that is necessarily unique to any Unix operating system or program. It’s not about file descriptors, pipes, sockets, or signals. Those sorts of complaints are like saying that someone is not a buddhist unless they speak Pali.

Unix Philosophy is an outlook for software development, not any specific technical development in software. It is an ideal to reach for, and perhaps ironically, it is an ideal that instructs us to occasionally eschew idealism in favor of practicality.

In Node, the basic building block that people share and interact with is not a binary on the command line, but rather a module loaded in by require(). The universal interface is a text stream, but it’s a JavaScript Stream object, rather than a stdio pipe. (The stdio pipes are of course represented by JavaScript streams, because that is our universal interface, so what else would we use?)

So, in terms of Node.js, here’s how I’d express the Unix Philosophy. Alas, I am no McIlroy, and I lack the time or skill to write this any shorter.


- Write modules that do one thing well. Write a new module rather than complicate an old one.

- Write modules that encourage composition rather than extension.

- Write modules that handle data Streams, because that is the universal interface.

- Write modules that are agnostic about the source of their input or the destination of their output.

- Write modules that solve a problem you know, so you can learn about the ones you don’t.

- Write modules that are small. Iterate quickly. Refactor ruthlessly. Rewrite bravely.

- Write modules quickly, to meet your needs, with just a few tests for compliance. Avoid extensive specifications. Add a test for each bug you fix.

- Write modules for publication, even if you only use them privately. You will appreciate documentation in the future.

- Working is better than perfect.

- Focus is better than features.

- Compatibility is better than purity.

- Simplicity is better than anything.

The Unix Philosophy is an ideology of pragmatism. It is about balancing the twin needs of writing good software, and writing any software at all. It’s a practical set of advice for trading a moderate increase in development cost for a much larger reduction in maintenance costs.

In the real world, we are faced with the completely unfair constraint of being human while writing programs and while debugging them, and none of these costs can ever be reduced to zero. This ideology is contextual, and can be applied at all levels of the stack. It is an open acknowledgement that we are actually not smart enough to know how to write the software we need the first time around, because we usually can only fully understand our problems once we have finished solving them.

None of these rules are sacrosanct! In fact, in many cases, they can be at odds, or even completely contradictory. However, if we keep our units of programming small, with simple universal interfaces, we can find leverage the piecemeal structure as a quality ratchet, swapping out clumsy parts as we go along.

Nothing about the Unix Philosophy explicitly relates to a culture of software sharing. However, it should be no mystery that it comes from the software community where we argue at length about the best way to make our programs properly Free. Software that is developed according to these principles is easier to share, reuse, repurpose, and maintain.

<h2>Tenets of the UNIX Philosophy</h2>

by Mike Gancarz ([source](http://www.ru.j-npcs.org/usoft/WWW/LJ/Articles/unixtenets.html))

The main tenets of the Unix Philosophy are as follows:

1. Small is beautiful.
    Small programs are easy to understand.
    Small programs are easy to maintain.
    Small programs consume fewer system resources.
    Small programs are easier to combine with other tools. 

2. Make each program do one thing well.
    "The best program...does but one task in its life and does it well."
    "The program is loaded into memory, accomplishes its function, and then gets out of the way to allow the next single-minded program to begin." 

3. Build a prototype as soon as possible.
    Prototyping is a learning process.
    Early prototyping reduces risk. 

4. Choose portability over efficiency.
    Next ---'s hardware will run faster.
    Don't spend too much time making a program run faster.
    The most efficient way is rarely portable.
    Good programs never die--they are ported to new hardware platforms. 

5. Store numerical data in flat ASCII files.
    ASCII text is a common interchange format.
    ASCII text is easily read and edited.
    ASCII data files simplify the use of Unix text tools.
    Increased portability overcomes the lack of speed (of flat ASCII text files...)
    The lack of speed is overcome by next year's machine. 

6. Use software leverage to your advantage
    Good programmers write good code; great programmers "borrow" good code.
    Avoid the not-invented-here syndrome.
    Allow other people to use your code to leverage their own work.
    Automate everything. 

7. Use shell scripts to increase leverage and portability.
    Shell scripts give you awesome leverage
    Shell scripts leverage your time, too.
    Shell scripts are more portable than C.
    Resist the desire to rewrite shell scripts in C. 

8. Avoid captive user interfaces.
    CUIs assume that the user is human.
    CUI command parsers are often big and ugly to write.
    CUIs tend to adopt a "big is beautiful" approach.
    Programs having CUIs are hard to combine with other programs.
    CUIs do not scale well.
    CUIs do not take advantage of software leverage. 

9. Make every program a filter.
    Every program written since the dawn of computing is a filter.
    Programs do not create data--people do.
    Computers convert data from one form to another.
    Use stdin for data input;
    Use stdout for data output;
    Use stderr for out-of-band information. 

Ten Lesser Tenets

1. Allow the User to tailor the environment.
2. Make operating system kernels small and lightweight.
3. Use lower case and keep it short.
4. Save Trees.
5. Silence is golden.
6. Think parallel.
7. The sum of the parts is greater than the whole.
8. Look for the 90 percent solution.
9. Worse is better. (I won't try to explain this one...)
10. Think hierarchically. 

"Unix owes much of its success to the fact that its developers saw no particular need to retain strong control of its source code."

<h1>The Case Against OOP</h1>

<h2>Execution in the Kingdom of Nouns</h2>

by Steve Yegge ([source](http://steve-yegge.blogspot.com/2006/03/execution-in-kingdom-of-nouns.html))

They've a temper, some of them—particularly verbs: they're the proudest—adjectives you can do anything with, but not verbs—however, I can manage the whole lot of them! Impenetrability! That's what I say!

— Humpty Dumpty

Hello, world! Today we're going to hear the story of Evil King Java and his quest for worldwide verb stamp-outage.1

Caution: This story does not have a happy ending. It is neither a story for the faint of heart nor for the critical of mouth. If you're easily offended, or prone to being a disagreeable knave in blog comments, please stop reading now.

Before we begin the story, let's get some conceptual gunk out of the way.

The Garbage Overfloweth

All Java people love "use cases", so let's begin with a use case: namely, taking out the garbage. As in, "Johnny, take out that garbage! It's overflowing!"

If you're a normal, everyday, garden-variety, English-speaking person, and you're asked to describe the act of taking out the garbage, you probably think about it roughly along these lines:

  *get* the garbage bag from under the sink
  *carry* it out to the garage
  *dump* it in the garbage can
  *walk* back inside
  *wash* your hands
  *plop* back down on the couch
  *resume* playing your video game (or whatever you were doing)

Even if you don't think in English, you still probably still thought of a similar set of actions, except in your favorite language. Regardless of the language you chose, or the exact steps you took, taking out the garbage is a series of actions that terminates in the garbage being outside, and you being back inside, because of the actions you took.

Our thoughts are filled with brave, fierce, passionate actions: we live, we breathe, we walk, we talk, we laugh, we cry, we hope, we fear, we eat, we drink, we stop, we go, we take out the garbage. Above all else, we are free to do and to act. If we were all just rocks sitting in the sun, life might still be OK, but we wouldn't be free. Our freedom comes precisely from our ability to do things.

Of course our thoughts are also filled with nouns. We eat nouns, and buy nouns from the store, and we sit on nouns, and sleep on them. Nouns can fall on your head, creating a big noun on your noun. Nouns are things, and where would we be without things? But they're just things, that's all: the means to an end, or the ends themselves, or precious possessions, or names for the objects we observe around around us. There's a building. Here's a rock. Any child can point out the nouns. It's the changes happening to those nouns that make them interesting.

Change requires action. Action is what gives life its spice. Action even gives spices their spice! After all, they're not spicy until you eat them. Nouns may be everywhere, but life's constant change, and constant interest, is all in the verbs.

And of course in addition to verbs and nouns, we also have our adjectives, our prepositions, our pronouns, our articles, the inevitable conjunctions, the yummy expletives, and all the other lovely parts of speech that let us think and say interesting things. I think we can all agree that the parts of speech each play a role, and all of them are important. It would be a shame to lose any of them.

Wouldn't it be strange if we suddenly decided that we could no longer use verbs?

Let me tell you a story about a place that did exactly that...

**The Kingdom of Nouns**

In the Kingdom of Javaland, where King Java rules with a silicon fist, people aren't allowed to think the way you and I do. In Javaland, you see, nouns are very important, by order of the King himself. Nouns are the most important citizens in the Kingdom. They parade around looking distinguished in their showy finery, which is provided by the Adjectives, who are quite relieved at their lot in life. The Adjectives are nowhere near as high-class as the Nouns, but they consider themselves quite lucky that they weren't born Verbs.

Because the Verb citizens in this Kingdom have it very, very bad.

In Javaland, by King Java's royal decree, Verbs are owned by Nouns. But they're not mere pets; no, Verbs in Javaland perform all the chores and manual labor in the entire kingdom. They are, in effect, the kingdom's slaves, or at very least the serfs and indentured servants. The residents of Javaland are quite content with this situation, and are indeed scarcely aware that things could be any different.

Verbs in Javaland are responsible for all the work, but as they are held in contempt by all, no Verb is ever permitted to wander about freely. If a Verb is to be seen in public at all, it must be escorted at all times by a Noun.

Of course "escort", being a Verb itself, is hardly allowed to run around naked; one must procure a VerbEscorter to facilitate the escorting. But what about "procure" and "facilitate?" As it happens, Facilitators and Procurers are both rather important Nouns whose job is is the chaperonement of the lowly Verbs "facilitate" and "procure", via Facilitation and Procurement, respectively.

The King, consulting with the Sun God on the matter, has at times threatened to banish entirely all Verbs from the Kingdom of Java. If this should ever to come to pass, the inhabitants would surely need at least one Verb to do all the chores, and the King, who possesses a rather cruel sense of humor, has indicated that his choice would be most assuredly be "execute".

The Verb "execute", and its synonymous cousins "run", "start", "go", "justDoIt", "makeItSo", and the like, can perform the work of any other Verb by replacing it with an appropriate Executioner and a call to execute(). Need to wait? Waiter.execute(). Brush your teeth? ToothBrusher(myTeeth).go(). Take out the garbage? TrashDisposalPlanExecutor.doIt(). No Verb is safe; all can be replaced by a Noun on the run.

In the more patriotic corners of Javaland, the Nouns have entirely ousted the Verbs. It may appear to casual inspection that there are still Verbs here and there, tilling the fields and emptying the chamber pots. But if one looks more closely, the secret is soon revealed: Nouns can rename their execute() Verb after themselves without changing its character in the slightest. When you observe the FieldTiller till(), the ChamberPotEmptier empty(), or the RegistrationManager register(), what you're really seeing is one of the evil King's army of executioners, masked in the clothes of its owner Noun.

**Verbs in Neighboring Kingdoms**

In the neighboring programming-language kingdoms, taking out the trash is a straightforward affair, very similar to the way we described it in English up above. As is the case in Java, data objects are nouns, and functions are verbs.2 But unlike in Javaland, citizens of other kingdoms may mix and match nouns and verbs however they please, in whatever way makes sense for conducting their business.

For instance, in the neighboring realms of C-land, JavaScript-land, Perl-land and Ruby-land, someone might model taking out the garbage as a series of actions — that is to say, verbs, or functions. Then if they apply the actions to the appropriate objects, in the appropriate order (get the trash, carry it outside, dump it in the can, etc.), the garbage-disposal task will complete successfully, with no superfluous escorts or chaperones required for any of the steps.

There's rarely any need in these kingdoms to create wrapper nouns to swaddle the verbs. They don't have GarbageDisposalStrategy nouns, nor GarbageDisposalDestinationLocator nouns for finding your way to the garage, nor PostGarbageActionCallback nouns for putting you back on your couch. They just write the verbs to operate on the nouns lying around, and then have a master verb, take_out_garbage(), that springs the subtasks to action in just the right order.

These neighboring kingdoms generally provide mechanisms for creating important nouns, when the need arises. If the diligent inventors in these kingdoms create an entirely new, useful concept that didn't exist before, such as a house, or a cart, or a machine for tilling fields faster than a person can, then they can give the concept a Class, which provides it with a name, a description, some state, and operating instructions.

The difference is that when Verbs are allowed to exist independently, you don't need to invent new Noun concepts to hold them.

Javalanders look upon their neighbors with disdain; this is the way of things in the Kingdoms of Programming.

**If You Dig a Hole Deep Enough...**

On the other side of the world is a sparsely inhabited region in whose kingdoms Verbs are the citizens of eminence. These are the Functional Kingdoms, including Haskellia, Ocamlica, Schemeria, and several others. Their citizens rarely cross paths with the kingdoms near Javaland. Because there are few other kingdoms nearby, the Functional Kingdoms must look with disdain upon each other, and make mutual war when they have nothing better to do.

In the Functional Kingdoms, Nouns and Verbs are generally considered equal-caste citizens. However, the Nouns, being, well, nouns, mostly sit around doing nothing at all. They don't see much point in running or executing anything, because the Verbs are quite active and see to all that for them. There are no strange laws mandating the creation of helper Nouns to escort each Verb, so there are only exactly as many Nouns as there are Things in each kindgom.

As a result of all this, the Verbs have the run of the place, if you'll pardon the expression. As an outsider, you could easily form the impression that Verbs (i.e., the functions) are the most important citizens by far. That, incidentally, is why they're called the Functional Kingdoms and not the Thingy Kingdoms.

In the remotest regions, beyond the Functional Kingdoms, lies a fabled realm called Lambda the Ultimate. In this place it is said that there are no nouns at all, only verbs! There are "things" there, but all things are created from verbs, even the very integers for counting lambs, which are the most popular form of trading currency there, if the rumors speak truth. The number zero is simply lambda(), and 1 is lambda(lambda()), 2 is lambda(lambda(lambda())), and so on. Every single Thing in this legendary region, be it noun, verb or otherwise, is constructed from the primal verb "lambda".3

To be quite honest, most Javalanders are blissfully unaware of the existence of the other side of the world. Can you imagine their culture shock? They would find it so disorienting that they might have to invent some new nouns (such as "Xenophobia") to express their new feelings.

**Are Javalanders Happy?**

You might think daily life in Javaland would be at best a little strange, and at worst grossly inefficient. But you can tell how happy a society is through their nursery rhymes, and Javaland's are whimsically poetic. For instance, Javaland children oft recite the famous cautionary tale:

```java
For the lack of a nail,
    throw new HorseshoeNailNotFoundException("no nails!");

For the lack of a horseshoe,
    EquestrianDoctor.getLocalInstance().getHorseDispatcher().shoot();

For the lack of a horse,
    RidersGuild.getRiderNotificationSubscriberList().getBroadcaster().run(
      new BroadcastMessage(StableFactory.getNullHorseInstance()));

For the lack of a rider,
    MessageDeliverySubsystem.getLogger().logDeliveryFailure(
      MessageFactory.getAbstractMessageInstance(
        new MessageMedium(MessageType.VERBAL),
        new MessageTransport(MessageTransportType.MOUNTED_RIDER),
        new MessageSessionDestination(BattleManager.getRoutingInfo(
                                        BattleLocation.NEAREST))),
      MessageFailureReasonCode.UNKNOWN_RIDER_FAILURE);

For the lack of a message,
    ((BattleNotificationSender)
      BattleResourceMediator.getMediatorInstance().getResource(
        BattleParticipant.PROXY_PARTICIPANT,
        BattleResource.BATTLE_NOTIFICATION_SENDER)).sendNotification(
          ((BattleNotificationBuilder)
            (BattleResourceMediator.getMediatorInstance().getResource(
            BattleOrganizer.getBattleParticipant(Battle.Participant.GOOD_GUYS),
            BattleResource.BATTLE_NOTIFICATION_BUILDER))).buildNotification(
              BattleOrganizer.getBattleState(BattleResult.BATTLE_LOST),
              BattleManager.getChainOfCommand().getCommandChainNotifier()));

For the lack of a battle,
    try {
        synchronized(BattleInformationRouterLock.getLockInstance()) {
          BattleInformationRouterLock.getLockInstance().wait();
        }
    } catch (InterruptedException ix) {
      if (BattleSessionManager.getBattleStatus(
           BattleResource.getLocalizedBattleResource(Locale.getDefault()),
           BattleContext.createContext(
             Kingdom.getMasterBattleCoordinatorInstance(
               new TweedleBeetlePuddlePaddleBattle()).populate(
                 RegionManager.getArmpitProvince(Armpit.LEFTMOST)))) ==
          BattleStatus.LOST) {
        if (LOGGER.isLoggable(Level.TOTALLY_SCREWED)) {
          LOGGER.logScrewage(BattleLogger.createBattleLogMessage(
            BattleStatusFormatter.format(BattleStatus.LOST_WAR,
                                         Locale.getDefault())));
        }
      }
    }

For the lack of a war,
    new ServiceExecutionJoinPoint(
      DistributedQueryAnalyzer.forwardQueryResult(
        NotificationSchemaManager.getAbstractSchemaMapper(
          new PublishSubscribeNotificationSchema()).getSchemaProxy().
            executePublishSubscribeQueryPlan(
              NotificationSchema.ALERT,
              new NotificationSchemaPriority(SchemaPriority.MAX_PRIORITY),
              new PublisherMessage(MessageFactory.getAbstractMessage(
                MessageType.WRITTEN,
                new MessageTransport(MessageTransportType.WOUNDED_SURVIVOR),
                new MessageSessionDestination(
                  DestinationManager.getNullDestinationForQueryPlan()))),
              DistributedWarMachine.getPartyRoleManager().getRegisteredParties(
                PartyRoleManager.PARTY_KING ||
                PartyRoleManager.PARTY_GENERAL ||
                PartyRoleManager.PARTY_AMBASSADOR)).getQueryResult(),
        PriorityMessageDispatcher.getPriorityDispatchInstance())).
      waitForService();

All for the lack of a horseshoe nail.
```

It remains wonderful advice, even to this very day.

Although the telling of the tale in Javaland differs in some ways from Ben Franklin's original, Javalanders feel their rendition has a distinct charm all its own.

The main charm is that the architecture is there for all to see. Architecture is held in exceptionally high esteem by King Java, because architecture consists entirely of nouns. As we know, nouns are things, and things are prized beyond all actions in the Kingdom of Java. Architecture is made of things you can see and touch, things that tower over you imposingly, things that emit a satisfying clunk when you whack them with a stick. King Java dearly loves clunking noises; he draws immense satisfaction from kicking the wheels when he's trying out a new horse-drawn coach. Whatever its flaws may be, the tale above does not want for things.

One of our first instincts as human beings is to find shelter from the elements; the stronger the shelter, the safer we feel. In Javaland, there are many strong things to make the citizens feel safe. They marvel at the massive architectural creations and think "this must be a strong design". This feeling is reinforced when they try to make any changes to the structure; the architectural strength then becomes daunting enough that they feel nobody could bring this structure down.

In addition to the benefits of a strong architecture, everything in Javaland is nicely organized: you'll find every noun in its proper place. And the stories all take a definite shape: object construction is the dominant type of expression, with a manager for each abstraction and a run() method for each manager. With a little experience at this kind of conceptual modeling, Java citizens realize they can express any story in this style. There's a kind of "noun calculus" backing it that permits the expression of any abstraction, any computation you like. All one needs are sufficient nouns, constructors for those nouns, accessor methods for traversing the noun-graph, and the all-important execute() to carry out one's plans.

The residents of the Kingdom of Java aren't merely happy — they're bursting with pride!

**StateManager.getConsiderationSetter("Noun Oriented Thinking", State.HARMFUL).run()** 

Or, as it is said outside the Kingdom of Java, "Noun Oriented Thinking Considered Harmful".

Object Oriented Programming puts the Nouns first and foremost. Why would you go to such lengths to put one part of speech on a pedestal? Why should one kind of concept take precedence over another? It's not as if OOP has suddenly made verbs less important in the way we actually think. It's a strangely skewed perspective. As my friend Jacob Gabrielson once put it, advocating Object-Oriented Programming is like advocating Pants-Oriented Clothing.

Java's static type system, like any other, has its share of problems. But the extreme emphasis on noun-oriented thought processes (and consequently, modeling processes) is more than a bit disturbing. Any type system will require you to re-shape your thoughts somewhat to fit the system, but eliminating standalone verbs seems a step beyond all rationale or reason.

C++ doesn't exhibit the problem, because C++, being a superset of C, allows you to define standalone functions. Moreover, C++ provides a distinct namespace abstraction; Java overloads the idea of a Class to represent namespaces, user-defined types, syntactic delegation mechanisms, some visibility and scoping mechanisms, and more besides.

Don't get me wrong; I'm not claiming C++ is "good". But I do find myself appreciating the flexibility of its type system, at least compared with Java's. C++ suffers from problems causing reasonable-looking sentences to cause listeners to snap and try to kill you (i.e., unexpected segfaults and other pitfalls for the unwary), and it can be extremely difficult to find the exact incantation for expressing a particular thought in C++. But the range of succinctly expressible thoughts far exceeds Java's, because C++ gives you verbs, and who'd want to speak in a language that doesn't?

Classes are really the only modeling tool Java provides you. So whenever a new idea occurs to you, you have to sculpt it or wrap it or smash at it until it becomes a thing, even if it began life as an action, a process, or any other non-"thing" concept.

I've really come around to what Perl folks were telling me 8 or 9 years ago: "Dude, not everything is an object."

It's odd, though, that Java4 appears to be the only mainstream object-oriented language that exhibits radically noun-centric behavior. You'll almost never find an AbstractProxyMediator, a NotificationStrategyFactory, or any of their ilk in Python or Ruby. Why do you find them everywhere in Java? It's a sure bet that the difference is in the verbs. Python, Ruby, JavaScript, Perl, and of course all Functional languages allow you to declare and pass around functions as distinct entities without wrapping them in a class.

It's certainly easier to do this in dynamically typed languages; you just pass a reference to the function, obtained from its name, and it's up to the caller to invoke the function with the proper arguments and use its return value correctly.

But many statically-typed languages have first-class functions as well. This includes verbosely-typed languages like C and C++, and also type-inferring languages like Haskell and ML. The languages just need to provide a syntax for creating, passing and invoking function literals with an appropriate type signature.

There's no reason Java couldn't simply add first-class functions and finally enter the grown-up, non-skewed world that allows people to use verbs as part of their thought processes. In fact there's a JVM language called The Nice programming language that sports a very Java-like syntax, but also includes expressive facilities for using verbs: standalone functions, which Java forces you to wrap with Callbacks or Runnables or other anonymous interface implementation classes to be able to refer to them.

Sun wouldn't even have to break their convention of requiring all functions to be "owned" by classes. Every anonymous function could carry an implicit "this" pointer to the class in which it was defined; problem solved.

I don't know why Sun insists on keeping Java squarely planted in the Kingdom of Nouns. I doubt it's a matter of underestimating their constituency; they added generics, which are a far more complex concept, so they clearly no longer care deeply about keeping the language simple. And that's not a bad thing, necessarily, because Java's established now: it makes more sense to start giving Java programmers tools that let them program the way they think.

I sure hope they fix this, so I can take the trash out and get back to my video game. Or whatever I was doing.

<h2>Why OO Sucks</h2>

by Joe Armstrong ([source](http://harmful.cat-v.org/software/OO_programming/why_oo_sucks))

When I was first introduced to the idea of OOP I was skeptical but didn’t know why - it just felt “wrong”. After its introduction OOP became very popular (I will explain why later) and criticising OOP was rather like “swearing in church”. OOness became something that every respectable language just had to have.

As Erlang became popular we were often asked “Is Erlang OO” - well, of course the true answer was “No of course not” - but we didn’t to say this out loud - so we invented a serious of ingenious ways of answering the question that were designed to give the impression that Erlang was (sort of) OO (If you waved your hands a lot) but not really (If you listened to what we actually said, and read the small print carefully).

At this point I am reminded of the keynote speech of the then boss of IBM in France who addressed the audience at the 7th IEEE Logic programming conference in Paris. IBM prolog had added a lot of OO extensions, when asked why he replied:

“Our customers wanted OO prolog so we made OO prolog”

I remember thinking “how simple, no qualms of conscience, no soul-searching, no asking "Is this the right thing to do” …

**Why OO sucks**

My principle objection to OOP goes back to the basic ideas involved, I will outline some of these ideas and my objections to them.

**Objection 1 - Data structure and functions should not be bound together**

Objects bind functions and data structures together in indivisible units. I think this is a fundamental error since functions and data structures belong in totally different worlds. Why is this?

*Functions do things. They have inputs and outputs. The inputs and outputs are data structures, which get changed by the functions. In most languages functions are built from sequences of imperatives: “Do this and then that …” to understand functions you have to understand the order in which things get done (In lazy FPLs and logical languages this restriction is relaxed).

> Data structures just are. They don’t do anything. They are intrinsically declarative. “Understanding” a data structure is a lot easier than “understanding” a function.

Functions are understood as black boxes that transform inputs to outputs. If I understand the input and the output then I have understood the function. This does not mean to say that I could have written the function.

Functions are usually “understood” by observing that they are the things in a computational system whose job is to transfer data structures of type T1 into data structure of type T2.

> Since functions and data structures are completely different types of animal it is fundamentally incorrect to lock them up in the same cage.

**Objection 2 - Everything has to be an object**

Consider “time”. In an OO language “time” has to be an object. But in a non OO language a “time” is a instance of a data type. For example, in Erlang there are lots of different varieties of time, these can be clearly and unambiguously specified using type declarations, as follows:

```erlang
-deftype day() = 1..31.
-deftype month() = 1..12.
-deftype year() = int().
-deftype hour() = 1..24.
-deftype minute() = 1..60.
-deftype second() = 1..60.
-deftype abstime() = {abstime, year(), month(), day(), hour(), min(), sec()}.
-deftype hms() = {hms, hour(), min(), sec()}.
...
```

Note that these definitions do not belong to any particular object. they are ubiquitous and data structures representing times can be manipulated by any function in the system.

There are no associated methods.

**Objection 3 - In an OOPL data type definitions are spread out all over the place**

In an OOPL data type definitions belong to objects. So I can’t find all the data type definition in one place. In Erlang or C I can define all my data types in a single include file or data dictionary. In an OOPL I can’t - the data type definitions are spread out all over the place.

Let me give an example of this. Suppose I want to define a ubiquitous data structure. ubiquitous data type is a data type that occurs “all over the place” in a system.

As lisp programmers have know for a long time it is better to have a smallish number of ubiquitous data types and a large number of small functions that work on them, than to have a large number of data types and a small number of functions that work on them.

A ubiquitous data structure is something like a linked list, or an array or a hash table or a more advanced object like a time or date or filename.

In an OOPL I have to choose some base object in which I will define the ubiquitous data structure, all other objects that want to use this data structure must inherit this object. Suppose now I want to create some “time” object, where does this belong and in which object…

**Objection 4 - Objects have private state**

State is the root of all evil. In particular functions with side effects should be avoided.

While state in programming languages is undesirable, in the real world state abounds. I am highly interested in the state of my bank account, and when I deposit or withdraw money from my bank I expect the state of my bank account to be correctly updated.

Given that state exists in the real world what facilities should programming language provide for dealing with state?

- OOPLs say “hide the state from the programmer”. The states is hidden and visible only through access functions.
- Conventional programming languages (C, Pascal) say that the visibility of state variables is controlled by the scope rules of the language.
- Pure declarative languages say that there is no state.

The global state of the system is carried into all functions and comes out from all functions. Mechanisms like monads (for FPLs) and DCGs (logic languages) are used to hide state from the programmer so they can program “as if state didn’t matter” but have full access to the state of the system should this be necessary.

The “hide the state from the programmer” option chosen by OOPLs is the worse possible choice. Instead of revealing the state and trying to find ways to minimise the nuisance of state, they hide it away.

**Why OO was popular?**

- Reason 1 - It was thought to be easy to learn.
- Reason 2 - It was thought to make code reuse easier.
- Reason 3 - It was hyped.
- Reason 4 - It created a new software industry.

I see no evidence of 1 and 2. Reasons 3 and 4 seem to be the driving force behind the technology. If a language technology is so bad that it creates a new industry to solve problems of its own making then it must be a good idea for the guys who want to make money.

This is is the real driving force behind OOPs.

<h1>The Case Against RPC</h1>

<h2>The Road we didn't go down</h2>

I've been following an interesting discussion on the Erlang mailing list where Steve Vinoski and friends have been telling us what's wrong with RPC.

The discussion started on 22 May, the general topic of conversation was the announcement that facebook had deployed a chat server written in Erlang.

In one of the posts Steve said:

>"What all those years of CORBA taught me, BTW, is that RPC, for a number of reasons, is generally A Really Bad Idea. Call it a hard-won lesson. The Erlang flavor of RPC is great because the entire Erlang system has distribution fundamentally designed and built into it, but for normal languages, RPC creates more problems than it solves."

-- Steve Vinoski

Future posts asked Steve to elaborate on this.

Steve posted a long and brilliant summary of the problems with RPC to the Erlang mailing list:

>"But if you don't have the time or energy, the fundamental problem is that RPC tries to make a distributed invocation look like a local one. This can't work because the failure modes in distributed systems are quite different from those in local systems, ..."
  
-- Steve Vinoski

Precisely - yes yes yes. As I read this my brain shouted YES YES YES - thank you Steve. Steve wrote more about this in [RPC under fire](http://steve.vinoski.net/pdf/IEEE-RPC_Under_Fire.pdf)

**This the road we didn't go down**

Steve went down this road and saw what was there and saw that it stunk, but he came back alive and could tell us what he had seen.

The fundamental problem with taking a remote operation and wrapping it up so that it looks like a local operation is that the failure modes of local and remote operations are completely different.

If that's not bad enough, the performance aspects are also completely different. A local operation that takes a few microseconds, when performed through an RPC, can suddenly take milliseconds.

If programmers cannot tell the difference between local and remote calls then it will be impossible to write efficient code. Badly placed RPCs in the middle of some mess of software can (and does) destroy performance.

> I have personally witnessed the failure of several large projects precisely because the distinction between local and remote procedure calls was unclear.

Note that this factor becomes even worse in large projects with dozens of programmers involved. If the team is small there is a chance that the participants know which calls are local and which calls are remote.

<h1>The Case Against ORM</h1>

<h2>Object-Relational Mapping is the Vietnam of Computer Science</h2>

by Jeff Atwood ([source](http://blog.codinghorror.com/object-relational-mapping-is-the-vietnam-of-computer-science/))

I had an opportunity to meet Ted Neward at TechEd this year. Ted, among other things, famously coined the phrase "Object-Relational mapping is the Vietnam of our industry" in late 2004.

It's a scary analogy, but an apt one. I've seen developers struggle for years with the huge mismatch between relational database models and traditional object models. And all the solutions they come up with seem to make the problem worse. I agree with Ted completely; there is no good solution to the object/relational mapping problem. There are solutions, sure, but they all involve serious, painful tradeoffs. And the worst part is that you can't usually see the consequences of these tradeoffs until much later in the development cycle.

Ted posted a much anticipated blog entry analyzing the ORM problem in minute detail. It's a long post. But unless you're a battle-scarred veteran of the ORM wars, I highly recommend at least skimming through it so you're aware of the many pitfalls you can run into trying to implement an ORM solution. There are a lot of magic bullets out there, and no shortage of naive developers.

Ted's post is excellent and authoritative, but it's a little wordy; I felt like I was experiencing a little slice of Vietnam while reading it. Let's skip directly to the summary at the end which provides an great list of current (and future) solutions to the ORM problem:

1. **Abandonment**. Developers simply give up on objects entirely, and return to a programming model that doesn't create the object/relational impedance mismatch. While distasteful, in certain scenarios an object-oriented approach creates more overhead than it saves, and the ROI simply isn't there to justify the cost of creating a rich domain model. ([Fowler] talks about this to some depth.) This eliminates the problem quite neatly, because if there are no objects, there is no impedance mismatch.
2. **Wholehearted acceptance**. Developers simply give up on relational storage entirely, and use a storage model that fits the way their languages of choice look at the world. Object-storage systems, such as the db4o project, solve the problem neatly by storing objects directly to disk, eliminating many (but not all) of the aforementioned issues; there is no "second schema", for example, because the only schema used is that of the object definitions themselves. While many DBAs will faint dead away at the thought, in an increasingly service-oriented world, which eschews the idea of direct data access but instead requires all access go through the service gateway thus encapsulating the storage mechanism away from prying eyes, it becomes entirely feasible to imagine developers storing data in a form that's much easier for them to use, rather than DBAs.
3. **Manual mapping**. Developers simply accept that it's not such a hard problem to solve manually after all, and write straight relational-access code to return relations to the language, access the tuples, and populate objects as necessary. In many cases, this code might even be automatically generated by a tool examining database metadata, eliminating some of the principal criticism of this approach (that being, "It's too much code to write and maintain"). 
4. **Acceptance of ORM limitations**. Developers simply accept that there is no way to efficiently and easily close the loop on the O/R mismatch, and use an ORM to solve 80% (or 50% or 95%, or whatever percentage seems appropriate) of the problem and make use of SQL and relational-based access (such as "raw" JDBC or ADO.NET) to carry them past those areas where an ORM would create problems. Doing so carries its own fair share of risks, however, as developers using an ORM must be aware of any caching the ORM solution does within it, because the "raw" relational access will clearly not be able to take advantage of that caching layer. 
5. **Integration of relational concepts into the languages**. Developers simply accept that this is a problem that should be solved by the language, not by a library or framework. For the last decade or more, the emphasis on solutions to the O/R problem have focused on trying to bring objects closer to the database, so that developers can focus exclusively on programming in a single paradigm (that paradigm being, of course, objects). Over the last several years, however, interest in "scripting" languages with far stronger set and list support, like Ruby, has sparked the idea that perhaps another solution is appropriate: bring relational concepts (which, at heart, are set-based) into mainstream programming languages, making it easier to bridge the gap between "sets" and "objects". Work in this space has thus far been limited, constrained mostly to research projects and/or "fringe" languages, but several interesting efforts are gaining visibility within the community, such as functional/object hybrid languages like Scala or F#, as well as direct integration into traditional OO languages, such as the LINQ project from Microsoft for C# and Visual Basic. One such effort that failed, unfortunately, was the SQL/J strategy; even there, the approach was limited, not seeking to incorporate sets into Java, but simply allow for embedded SQL calls to be preprocessed and translated into JDBC code by a translator.
6. **Integration of relational concepts into frameworks**. Developers simply accept that this problem is solvable, but only with a change of perspective. Instead of relying on language or library designers to solve this problem, developers take a different view of "objects" that is more relational in nature, building domain frameworks that are more directly built around relational constructs. For example, instead of creating a Person class that holds its instance data directly in fields inside the object, developers create a Person class that holds its instance data in a RowSet (Java) or DataSet (C#) instance, which can be assembled with other RowSets/DataSets into an easy-to-ship block of data for update against the database, or unpacked from the database into the individual objects. 

Ted quickly posted a [followup entry](http://blogs.tedneward.com/2006/06/27/Thoughts+On+Vietnam+Commentary.aspx) which addressed common criticisms of his original post. If you have an itchy left mouse finger poised over the "comment" link right now, you may want to read that first.

Personally, I think the only workable solution to the ORM problem is to pick one or the other: either abandon relational databases, or abandon objects. If you take the O or the R out of the equation, you no longer have a mapping problem.

It may seem crazy to abandon the traditional Customer object – or to abandon the traditional Customer table – but picking one or the other is a totally sane alternative to the complex quagmire of classes, objects, code generation, SQL, and stored procedures that an ORM "solution" typically leaves us with.

Both approaches are certainly valid. I tend to err on the side of the database-as-model camp, because I think [objects are overrated](http://blog.codinghorror.com/why-objects-suck/).

<h1>The Case Against UML</h1>

<h2>13 reasons for UML’s descent into darkness</h2>

by Daniel Pietraru ([source](http://littletutorials.com/2008/05/15/13-reasons-for-umls-descent-into-darkness/))

UML lost the programmers. There is no doubt about it… in my mind. And when a software design technology loses the programmers it fades away no matter what the academia thinks. This happened because UML was pushed in a direction that most code writers don’t like: it started to look a lot like bureaucratic paper work. If we list what went wrong it starts to look a lot like the mishaps of other committee driven technologies like CORBA for example. In random order I can list:

1. **Design by committee**. This one is very big and usually a recipe for failure in the long term. Just look at CORBA and for a new case at the never ending list of web service standards.
2. **The obsessive focus on monetizing UML**. Trying to sell expensive tools for a technology that is not mature enough and only makes promises to the management (just express your ideas in pictures and the code will be generated by our magic wand) can only work in short term. At some moment somebody realizes the costs are too big for the benefits. Lots of programmers instinctively hated the whole thing. Others were persuaded by management or by curiosity to try it. Most of them never used UML tools for more than a project.
3. **Tries to unify everything even the kitchen sink (UML specs > 800 pages)**. When you try to offer a solution for every problem in a domain, in the end you are not offering anything useful for any problem in that domain. UML tried to solve all the issues with software development. My feeling is it just forgot about the “software development” part. Software is used or it can be used in almost every human activity. Trying to capture everything is an impossible task – even at 800 pages, UML covers only a small part of the complexity of software engineering needs. It is too big but still too generic and abstract.
4. **Departure from what programmers perceived as the initial goal**. As a programmer I liked the standardization UML provided for design related communication. It was great to be able to use a common set of symbols to communicate my ideas to another programmer or designer. I think most programmers still use only the class diagram and maybe occasionally when they write a document the sequence diagram. UML started to go up into the stratosphere with all those business oriented diagrams that even the business people didn’t understand or use.
5. Concept bloat. Trying to bridge UML to reality made it incorporate concepts from all the languages in fashion during the last 10-15 years. Anybody knows how to represent a Java anonymous inner class?
6. **Always catch-up with new languages and concepts**. In continuation of the above… and because the promised prize was full code generation you have to be able to represent specific language constructs. Closures in UML anybody?
7. **UML attempts to become a programming language**. By aiming to be able to generate full code actually UML tries to be a programming language. In my mind there is a big problem with a general purpose graphical programming language. In human history the written form of all languages evolved from graphical to textual. Alphabets proved to be more versatile and more expressive than pictures in capturing ideas. Try to describe any simple process in images. The funny thing is you still have to annotate the images with words. And the full text version with no pictures still gives you more details. Pictures prove to be good at sharing ideas and allowing people to visualize concepts. But in the end words are better at describing the fine details.
8. **The need for expensive tools vs. just a text editor**. The entry level for using UML for more than just informally sharing ideas on a white-board is very high. Tools that are any good are insanely expensive. On top of that they need training as they are not all the time the most intuitive tools. They start to look like a solution screaming for a problem to solve. Consulting companies seem to love these tools since they open opportunities for expensive training courses.
9. **Lack of model clarity**. Pictures are interpretable. I heard this kind of complaints from programmers trying to understand the design of a system from UML diagrams: you need to read the code to understand what the diagrams mean.
10. **Lack of solutions for real software design issues**. While the specifications are huge there are no good solutions for problems common in software systems. Quick examples are:
  - No solution for multi-tasking and communication between tasks
  - No dependency between use cases

11. **Assumes you can know everything before writing the first line of code**. The concept of writing first the user manual and then the generate the code based on it is a noble goal but… probably impossible to achieve. In practice everything is so dynamic, that the maintenance of the UML diagrams so they conform with the reality of the code becomes very fast a chore nobody wants to do.
12. **Treat software development like manufacturing**. Software design is not manufacturing no matter how much management likes to think about it this way. Software creation is a creative activity so a more accurate description would be craft, art or something along this line. UML tries to standardize and formalize the unknown, the imagination and the talent.
13. **UML tools focus on the wrong goal**. Most of the UML tools out there promise code generation. This is most of the time useless since they generate just empty class bodies with no logic. It is also cumbersome and annoying because one has to keep the code and the diagrams in sync. Some even use ugly formatted comments as markers.
Another problem with these tools is the amount of real estate diagram elements take on the screen. I tried many times to look at UML diagrams of complicated systems but looking at only the lower left corner of a class square along with two crossed segments doesn’t help much with understanding. I think the tools should have focused on reverse engineering for documentation purposes. In my opinion no decent reasonable priced tool exists in this area. Even tools that manage to decently reverse engineer the code do a poor job for documentation purposes since they cannot differentiate between what is essential and what is just noise/boilerplate in the code.
As a result most finished projects that use UML have code that doesn’t resemble at all the nice UML diagrams drawn at the beginning of the project.
In general I don’t think code generation is a good idea. Usually what can be generated is repetitive code and most projects would be better off with that common code implemented in a library and called from there.

In the end as a conclusion I think UML had a generous idea to bring software designers speak a common language. But this idea got lost on the way for economical reasons. And when the value is lost the customers leave.

<h1>Writing Good Code</h1>

by Tyler Treat ([source](http://bravenewgeek.com/writing-good-code/))

There’s no shortage of people preaching the importance of good code. Indeed, many make a career of it. The resources available are equally endless, but lately I’ve been wondering how to extract the essence of building high-quality systems into a shorter, more concise narrative. This is actually something I’ve thought about for a while, but I’m just now starting to formulate some ideas into a blog post. The ideas aren’t fully developed, but my hope is to flesh them out further in the future. You can talk about design patterns, abstraction, encapsulation, and cohesion until you’re blue in the face, but what is the essence of good code?

Like any other engineering discipline, quality control is a huge part of building software. This isn’t just ensuring that it “works”—it’s ensuring it works under the complete range of operating conditions, ensuring it’s usable, ensuring it’s maintainable, ensuring it performs well, and ensuring a number of other characteristics. Verifying it “works” is just a small part of a much larger picture. Anybody can write code that works, but there’s more to it than that. Software is more malleable than most other things. Not only does it require longevity, it requires giving in to that malleability. If it doesn’t, you end up with something that’s brittle and broken. Because of this, it’s vital we test for correctness and measure for quality.

**SCRAP for Quality**

Quality is a very subjective thing. How can one possibly measure it? Code complexity and static analysis tooling come to mind, and these are deservedly valued, but it really just scratches the surface. How do we narrow an immensely broad topic like “quality” into a set of tangible, quantifiable goals? This is really the crux of the problem, but we can start by identifying a sort of checklist or guidelines for writing software. This breaks that larger problem into smaller, more digestible pieces. The checklist I’ve come up with is called SCRAP, an acronym defined below. It’s unlikely to be comprehensive, but I think it covers most, if not all, of the key areas.

        	      

SCRAP             |for Quality
------------------|------------------
Scalability       |Plan for growth
Complexity 	      |Plan for humans
Resiliency 	      |Plan for failure
API 	          |Plan for integration
Performance 	  |Plan for execution

Each of these items is itself a blog post, so this is only a brief explanation. There is definitely overlap between some of these facets, and there are also multiple dimensions to some.

**Scalability** is a plan for growth—in code, in organization, in architecture, and in workload. Without it, you reach a point where your system falls over, whether it’s because of a growing userbase, a growing codebase, or any number of other reasons. It’s also worth pointing out that without the ‘S’, all you have is CRAP. This also helps illustrate some of the overlap between these areas of focus as it leads into Complexity, which is a plan for humans. Scalability is about technology scale and demand scale, but it’s also about people scale. As your team grows or as your company grows, how do you manage that growth at the code level?

**Planning** for people doesn’t just mean managing growth, it also means managing complexity. If code is overly complex, it’s difficult to maintain, it’s difficult to extend, and it’s difficult to fix. If systems are overly complex, they’re difficult to deploy, difficult to manage, and difficult to monitor. **Plan for humans, not machines**.

**Resiliency** is a strategy for fault tolerance. It’s a plan for failure. What happens when you crash? What happens when a service you depend on crashes? What happens when the database is unavailable? What happens when the network is unreliable? Systems of all kind need to be designed with the expectation of failure. **If you’re not thinking about failure at the code level, you’re not thinking about it enough**.

One thing you should be noticing is that “people” is a cross-cutting concern. After all, it’s people who design the systems, and it’s people who write the code. While **API** is a plan for integration, it’s people who integrate the pieces. This is about making your API a first-class citizen. It doesn’t matter if it’s an internal API, a library API, or a RESTful API. It doesn’t matter if it’s for first parties or third parties. **As a programmer, your API is your user interface**. It needs to be clean. It needs to be sensible. It needs to be well-documented. If those integration points aren’t properly thought out, the integration will be more difficult than it needs to be.

The last item on the checklist is **Performance**. I originally defined this as a plan for speed, but I realized there’s a lot more to performance than doing things fast. It’s about doing things well, which is why I call Performance a plan for execution. Again, this has some overlap with Resiliency and Scalability, but it’s also about measurement. It’s about benchmarking and profiling. It’s about testing at scale and under failure because testing in a vacuum doesn’t mean much. It’s about optimization.

This brings about the oft-asked question: how do I know when and where to optimize? While premature optimization might be the root of all evil, it’s not a universal law. **Optimize along the critical path and outward from there only as necessary**. The further you get from that critical path, the more wasted effort it’s going to end up being. It depreciates quickly, so don’t lose sight of your optimization ROI. This will enable you to ship quickly and ship quality code. But once you ship, you’re not done measuring! It’s more important than ever that you continue to measure in production. Use performance and usage-pattern data to drive intelligent decisions and intelligent iteration. The payoff is that this doesn’t just apply to code decisions, it applies to all decisions. This is where the real value of measuring comes through. **Decisions that aren’t backed by data aren’t decisions, they’re impulses**. Don’t be impulsive, be empirical.

**Going Forward**

There is work to be done with respect to quantifying the items on this checklist. However, I strongly suspect even just thinking about them, formally or informally, will improve the overall quality of your code by an equally-unmeasurable order of magnitude. If your code doesn’t pass this checklist, it’s tech debt. Sometimes that’s okay, but remember that tech debt has compounding interest. If you don’t pay it off, you will eventually go bankrupt.

It’s not about being a 10x developer. It’s about being a 1x developer who writes 10x code. By that I mean the quality of your code is far more important than its quantity. Quality will outlast and outperform quantity. These guidelines tend to have a ripple effect. Legacy code often breeds legacy-like code. Instilling these rules in your developer culture helps to make engineers cognizant of when they should break the mold, introduce new patterns, or improve existing ones. **Bad code begets bad code, and bad code is the atrophy of good developers**.

<h1>Starbucks Does Not Use Two-Phase Commit</h1>

by [Gregor Hohpe](http://www.enterpriseintegrationpatterns.com/ramblings/18_starbucks.html) (source)

**Hotto Cocoa o Kudasai**

I just returned from a 2 week trip to Japan. One of the more familiar sights was the ridiculous number of Starbucks (スターバックス) coffee shops, especially around Shinjuku and Roppongi. While waiting for my "Hotto Cocoa" I started to think about how Starbucks processes drink orders. Starbucks, like most other businesses is primarily interested in maximizing throughput of orders. More orders equals more revenue. As a result they use asynchronous processing. When you place your order the cashier marks a coffee cup with your order and places it into the queue. The queue is quite literally a queue of coffee cups lined up on top of the espresso machine. This queue decouples cashier and barista and allows the cashier to keep taking orders even if the barista is backed up for a moment. It allows them to deploy multiple baristas in a Competing Consumer scenario if the store gets busy.

**Correlation**

By taking advantage of an asynchronous approach Starbucks also has to deal with the same challenges that asynchrony inherently brings. Take for example, correlation. Drink orders are not necessarily completed in the order they were placed. This can happen for two reasons. First, multiple baristas may be processing orders using different equipment. Blended drinks may take longer than a drip coffee. Second, baristas may make multiple drinks in one batch to optimize processing time. As a result, Starbucks has a correlation problem. Drinks are delivered out of sequence and need to be matched up to the correct customer. Starbucks solves the problem with the same "pattern" we use in messaging architectures -- they use a Correlation Identifier. In the US, most Starbucks use an explicit correlation identifier by writing your name on the cup and calling it out when the drink is complete. In other countries, you have to correlate by the type of drink.

**Exception Handling**

Exception handling in asynchronous messaging scenarios can be difficult. If the real world writes the best stories maybe we can learn something by watching how Starbucks deals with exceptions. What do they do if you can't pay? They will toss the drink if it has already been made or otherwise pull your cup from the "queue". If they deliver you a drink that is incorrect or nonsatisfactory they will remake it. If the machine breaks down and they cannot make your drink they will refund your money. Each of these scenarios describes a different, but common error handling strategy:

- **Write-off** - This error handling strategy is the simplest of all: do nothing. Or discard what you have done. This might seem like a bad plan but in the reality of business this option might be acceptable. If the loss is small it might be more expensive to build an error correction solution than to just let things be. For example, I worked for a number of ISP providers who would chose this approach when there was an error in the billing / provisioning cycle. As a result, a customer might end up with active service but would not get billed. The revenue loss was small enough to allow the business to operate in this way. Periodically, they would run reconciliation reports to detect the "free" accounts and close them.
- **Retry** - When some operations of a larger group (i.e. "transaction") fail, we have essentially two choices: undo the ones that are already done or retry the ones that failed. Retry is a plausible option if there is a realistic chance that the retry will actually succeed. For example, if a business rule is violated it is unlikely a retry will succeed. However, if an external system is not available a retry might well be successful. A special case is a retry with Idempotent Receiver. In this case we can simply retry all operations since the successful receivers will ignore duplicate messages.
- **Compensating Action** - The last option is to undo operations that were already completed to put the system back into a consistent state. Such "compensating actions" work well for example if we deal with monetary systems where we can recredit money that has been debited.

All of these strategies are different than a two-phase commit that relies on separate prepare and execute steps. In the Starbucks example, a two-phase commit would equate to waiting at the cashier with the receipt and the money on the table until the drink is finished. Then, the drink would be added to the mix. Finally the money, receipt and drink would change hands in one swoop. Neither the cashier nor the customer would be able to leave until the "transaction" is completed. Using such a two-phase-commit approach would certainly kill Starbucks' business because the number of customers they can serve within a certain time interval would decrease dramatically. This is a good reminder that a two-phase-commit can make life a lot simpler but it can also hurt the free flow of messages (and therefore the scalability) because it has to maintain stateful transaction resources across the flow of multiple, asynchronous actions.

**Conversations**

The coffee shop interaction is also a good example of a simple, but common Conversation pattern. The interaction between two parties (customer and coffee shop) consists of a short synchronous interaction (ordering and paying) and a longer, asynchronous interaction (making and receiving the drink). This type of conversation is quite common in purchasing scenarios. For example, when placing an order on Amazon the short synchronous interaction assigns an order number and all subsequent steps (charging credit card, packaging, shipping) are done asynchronously. You are notified via e-mail (asynchronous) when the additional steps complete. If anything goes wrong, Amazon usually compensates (refund to credit card) or retries (resend lost goods).

In summary we can see that the real world is often asynchronous. Our daily lives consists of many coordinated, but asynchronous interactions (reading and replying to e-mail, buying coffee etc). This means that an asynchronous messaging architecture can often be a natural way to model these types of interactions. It also means that often we can look at daily life to help design successful messaging solutions. Domo arigato gozaimasu!

<h1>Accountants Don't Use Erasers</h1>

by Pat Helland ([source](http://blogs.msdn.com/b/pathelland/archive/2007/06/14/accountants-don-t-use-erasers.aspx))

Many kinds of computing are "append-only".  By that, I mean that observations about the world are recorded in perpetuity.  Derived results from those observations may be calculated on demand (or kept as a running tally) but you can't rewrite history. 

I spent much of my career working on the transaction plumbing for database systems.  In these systems, all changes are made to a transaction log.  The log describes both the before and after images of all record changes made by each transaction.  The log is appended to at a rapid clip (indeed, some of the fun performance optimizations in achieving the astonishing throughput of SQL Server and other database systems are about optimizing the writes to the tail of the log).  You NEVER modify the log other than by appending to the end of it.  You archive the log for posterity.  In the past, you might delete old log files after many months or years.  Nowadays, legislation makes that more problematic.

Well, if EVERYTHING in the history of the database is represented in the log, what is the actual database itself?  Well, it is a rollup of a view of the changes represented in the log.  The database is a cache of a subset of the log (the subset that represents the latest updates to all the records by the transactions that happened to commit).

So, accountants don't use erasers or they end up in jail.  When an entry is made in the accounting records, it will live forever.  There may be another entry added to ensure that a mistake is corrected but the mistake will not be erased.  The summary of the impact of all of these accounting entries will occasionally be tallied (e.g. your end-of-month balance for your checking account).  Now, the June statement may not reflect some outstanding (and uncashed) checks you've written but those are likely to show up in July's statement.   Quarterly results issued to corporate stockholders will usually include some small correction to earlier quarterly results because of small transactions that legally occurred in the earlier quarter but whose accounting information wasn't rolled up in time for that quarter.  There is uncertainty in the result and that is acknowledge by the mechanism of republishing corrected results.

**The Append-Only View of Distributed Single-Master Computing**

Distributed work is frequently represented as append-only artifacts on the interoperating systems.  When you deposit your neighbor's check in your account, an entry is made into your bank account showing a deposit and some linkage to the check and your neighbor's bank.  If your bank is smart, a hold is placed on the funds.  When the physical check is shipped to the clearing house to be sent to your neighbor's bank, his bank identifies the account and attempts to debit the account.  If the check clears, funds are moved from bank to bank and the hold is released on the funds (admittedly, sometimes these holds are timeout based rather than linked to the clearing of the check).  If the check bounces (it is, after all, from your neighbor), a debit is appended to your account (both for the amount of the check and for the fine associated with having an idiot for a neighbor).  None of this involved deleting or updating ANYTHING except the interim rollup balance of your checking account which could be calculated on demand.  Frequently, a new interim balance is just appended to the bank account.

Lots of today's computing follows this pattern.  Inventory balances are maintained by tracking incoming and outgoing changes to the inventory.   Sometimes, the inventory balance (in a centralized system) is characterized as "At this time on this date, the inventory for product-X is amount-Y".  In this fashion, the information about the balance is true in perpetuity.  It just becomes as artifact of history.  

**Knowledge and Event-Horizons**

In a replicated system (say there are N replicas with an opinion of the balance), it becomes more complex.  Imagine a world in which independent actions are taken by replicas which are making guesses (see "Memories, Guesses, and Apologies") and the knowledge of these guesses is gradually oozing back-and-forth across the replicas.  By all the replicas sharing their knowledge of the changes that they have made over time, you end up with two opinions chasing each other within each replica.

First, there is a point in history prior to which your replica-K has complete knowledge of what ALL the other replicas have done... "Gee, I haven't heard from replica-J since 9AM last Wednesday but prior to that, I know what all N replicas have done."  That means YOU have complete knowledge of what happened to the inventory of Product-X up until 9AM last Wednesday (assuming a tight control of the set of N replicas).  Since then, you have partial knowledge.

Now if I hear from Replica-K about his changes that have occurred since last Wednesday, I can advance my uncertainty window to Wednesday at 10PM which was the last time I heard from Replica-1.  This is an ongoing way to cope with independent decision making and the coping with uncertainty.   It is an extension (for multi-master decision making) on the way in which a running balance is managed in a bank account (which processes "the truth as of a point in time" in a centralized fashion).

Now, you say, I am MAD!  Stark raving MAD!  How can people cope with the chaos and confusion.   Well, as I pointed out when discussing my take on the CAP Conjecture, consistency is what people are frequently willing to sacrifice to ensure unfettered availability in the face of partitions.  

[As an aside, in my misspent youth, I was chief architect and lead programmer for Tandem's NonStop Transaction Monitoring Facility (TMF) which did the database logging and recovery for Tandem's NonStop SQL.  Think of this as the data-protecting and preserving part of the super-duper high-availability system of its day.  On the (really pretty rare) times when a system was stuck and needed help to get going, early in my tenure I worked hard to guarantee transactional consistency.  I wanted to ensure we did NOT bring the database back online unless we correctly processed all the committed and aborted transactions and recreated a pristine and correct system.  As I gained more experience, I noticed a large percentage of the customers (but certainly not all of them) just plain wanted the durn thing up and running... They would figure out the mess later.  As I matured (well... at least aged), I learned to ask at the beginning of the crisis whether the priority was availability or the priority was correctness.  I was surprising the number of times availability was more important. ]

So, two interweaving themes are being presented:

1) You don't really ever delete ANYTHING.  As a matter of fact, you don't update anything either... You just accrete new knowledge and distill new implications based upon your increasing knowledge.

2) People (and applications) will act on their partial knowledge and then, when learning new facts, take new actions.   Sometimes, you realize you shouldn't have taken the action but, gee, it was a great decision based on what you knew at the time.   Since you weren't omniscient, you could have perfect knowledge and could make perfect decisions... Shit happens and you deal with it.

**Idempotence and the Lack of Erasers**

One final observation...  If you never forget anything and never change it, providing idempotent processing takes a completely different twist.  You wrote everything down and, if you hear it again, it's just old news to be dropped on the floor.   That's cool. 

More to be written soon about:

1) Idempotence, and

2) Generating output with elevated abstractions to ensure commutativity

3) Dampening algorithms in redundantly executing multi-master systems...

I've added these to the list of blog entries to write... the list keeps getting longer as I think of things to rant about faster than I am ranting.   Sigh.debate

<h1>How testing could transform higher education</h1>

by Jay Kreps ([source](http://blog.empathybox.com/post/40412765107/how-testing-could-transform-higher-education))

I think the online education movement is amazing. College classes, like youth, are wasted on the young. College students are usually getting their first chance to live away from their parents and figure out who they are, which, understandably, seems more immediate and alive than 19th century English lit. or linear algebra or whatever class material they happen to study. So for a lot of students college is just the last hoop in a series of hoops they have to jump through before they are allowed to start their own life. So I think classes full of people who want to learn that subject is a great idea.

The most interesting phenomenon in this transformation is that education is changing from a non-scalable medium like theater or opera performances to a scalable medium like film or mp3s. This has the usual effect: average quality rises dramatically, price drops, and demand rises. It is all well and good to [debate](http://pennyhacks.com/2011/12/28/stanford-free-classes-a-review-from-a-stanford-student/) whether the Stanford students who took the [Machine Learning class](https://www.coursera.org/course/ml) in person got a better experience than those who took the class online, but very likely all but a handful or those who took the online class wouldn’t have been admitted as Stanford students at all.

I do think this will transform the university. With a non-scalable medium, taking a class from the third best algorithms professor in the world is a great opportunity, but with a scalable medium it isn’t clear why anyone wouldn’t just want the best. So expect huge pressure to improve the quality of teaching (which is completely lacking today). And expect these top professors to be treated much more like rock stars, and make a lot of money from teaching. (This isn’t suprising, the value created by a class of 200k people is just so much higher than from a class of 150, it would be surprising if the professor couldn’t capture at least some of that).

But that isn’t what I want to talk about. I want to talk about testing and how I think testing, done right, could have an equal impact on higher education.

People say that these online classes will never replace colleges, and that may be true in some sense. I think if you break up the value of college into its constituant pieces there are really three parts: 


1. Learning. This gets a lot of the press though, as I said, it may not be the most central aspect for many students.
2. Certification. It is not enough to know something, you need to prove to others that you know it. Companies don’t have the time to devise deep evaluations of everything you were supposed to learn in school so they use silly heuristics like your grades or the reputation of your school. For many people this is why they go to school, to get a degree.
3. "The college experience."

Let’s go through each of these.

Learning, is what all articles about MOOCs and online education cover, and though I have a lot to add, I will save it for another time.

By “the college experience” I mean all the non-educational aspects of college. This is the friends, late night conversations, sex, drugs, alcohol, and all that. This is the first time many kids have to move out on their own, away from family and friends who have known them sense grade school, and kind of start fresh. For many people who start a career directly after college this may be both the first and the last chance they have to reinvent themselves. But college administrators have no particular expertise in providing this, and fortunately the college experience isn’t that hard to replicate. I think you just need dorms—i.e. housing where lots of young people are close together—and you need kids to move away from where they grew up and the rest takes care of itself. The housing could probably be cheap and nice too if it weren’t provided by universities, which, whatever their strengths, are not exactly the most efficient landlords.

So that leaves certification. That is what I really want to talk about.

Unlike this [article](http://www.slate.com/blogs/moneybox/2013/01/07/moocs_and_bucks_is_there_a_real_business_opportunity_here.html), I think online education companies will make lots of money. The reasons are simple. Education takes a lot of time, so people will pay for better quality. If you are going to spend a few hundred hours in a class you want it to be good, and you would pay a few hundred dollars to get something 10% better for your time. And that doesn’t even address the more irrational reasons. People are used to paying a lot for education, and I think there is an irrational part of human nature that tends to assess prices relative to what they are used to.

But I don’t think producing classes is the best business in this space, and it may not even be the most transformative for education. The best business is certification or testing.

I think people can’t see how important this is because certification and testing is so broken now. How is it broken?

First, it has become customary that colleges get to assess their own students, which, since colleges are paid by the students, has led to the inevitable grade inflation.

Second, colleges have no motivation to make grades good–they don’t benefit by making grades comparable or accurate. How does a 3.3 average from Berkeley compare to a 3.5 from Georgia Tech? Nobody knows and I doubt either Berkeley or Georgia Tech would want to answer that question if they could.

Third GPAs, the usual summary measurement of grades, is a terrible statistic. It averages together lots of subjects in a way that likely isn’t meaningful for anything in particular other than measuring how much, on average, the candidate cared about getting good grades. It is easily manipulated by taking easy classes, which is exactly the wrong thing to reward. And it values consistency over all else (since getting an A is pretty easy these days, getting a high GPA is more about never screwing up then being particularly good at anything).

I have done a fair amount of hiring which let’s you look at GPAs and then do an in person assessment. GPAs aren’t worthless but neither are they worth much.

In short colleges do a terrible job at assessment which has made hiring use grades less than they should.

Outside of grades, most tests kind of suck. The normal “standardized” tests are overly general (one 3 hour test may cover your whole high school or college education). They also try to test subjects like English that are hard to test. Boiling your high school education down to an SAT score or your college education down to a GRE score is silly.

Interestingly the concept of “certification” has arisen in the professional context appart from schools. This is your “Microsoft Certified Systems Engineer” and the like. These certifications have a bad reputation purely because they are pass/fail and aimed at fairly low-end jobs. Having an MCSE is kind of like putting on your resume that you passed high school algebra. It’s not a bad thing, but if you have to say so (or you have to ask) that isn’t good. Harder certifications—an MD, for example—has a better reputation. But any pass/fail test will be aimed at preventing very bad quality rather than finding very good quality (having an MD, after all, doesn’t indicate a good doctor).

But imagine a group of people who care deeply about data working seriously on the idea of assessing skills. First your score would have to be closer to a percentile rank not pass/fail, and that rank would have to be against other people taking the test. Percentiles are wonderful because you know exactly what it means (a 99.9 means the candidate was better than 99.9 percent of all test takers) where as an ‘A’ doesn’t come with that. There are plenty of hard problems to get right: you have to randomize the question pool to avoid cheating, but you have to guarantee a fixed performance (can’t have people lucking out and getting all easy questions).

The other problem with existing tests is that they are too general. This makes studying for them stressful. Tests should cover a single specific area (i.e. “Linear Algebra”) not a general field (“math”). One can always create scores for general areas by taking scores in a set of tests for core subjects in that area.

I think this kind of testing would need to be done in person over a period of a day or so per subject. This sounds ridiculously time consuming compared to short tests like the SATs, but I think that is not an unreasonable percentage of time to spend on assessment and it would stand in for the “final” since this would be a much better, more comparable test.

I think it is easy to miss how powerful this is. To see it, you have to think about the hiring process as it works today. Let’s say there are three types of hiring: unskilled, skilled but inexperienced, and skilled and experienced. Unskilled hiring is not complicated (“have you ever been convicted of a felony?”). Hiring skilled, experienced people is generally done based on what they have accomplished; if they are really good they have been working for a while then they will have done some big things and have people who will vouch for them. This is going to be better than any test. In other words, LinkedIn can solve that problem. But hiring skilled, inexperienced people is pretty hard because they haven’t had an opportunity to do anything yet.

Let me illustrate this by describing the process for hiring new college graduates for a programming job. These are people who have specialized skills (programming) but no real work experience to judge. This process is pretty standard for good silicon valley companies and goes something like this. First you eliminate candidates from all but the best schools. You know that the best programmers at the worse schools are better than the worse programmers at the best schools, but this kind of blunt heuristic is all you have. Then you interview these candidates essentially at random (maybe you look at their projects or internships or whatever but it is done so quickly it is basically random). The first round of interview is usually a one hour phone screen. Assessing a persons skill set in one hour over the phone is, of course, totally impossible. So you reject lots of good people for silly reasons like taking a little longer to answer the one question you had time for. Interviewers are generally poorly calibrated against one-another so it matters almost as much whether you get an easy interviewer as how well you answer unless you are a complete failure. This, if successful, will be followed up by a series of in person one hour interviews. Refining this process, standardizing the question set, avoiding cheating, and calibrating the scores of your interview process are a huge amount of work and usually done wrong.

But the real inefficiency is this. Once you have invested a few dozen hours in assessment of a candidate, what happens to that assessment? Well, for most candidates, say 95%, the answer is “no hire”. This means that another company does exactly the same thing (pick a good school, ask simplistic questions, etc). Basically all the information gained in the first interview is thrown away. In total a candidate may go through 40 hours of interviews at different companies, but the coverage is terrible since all the companies ask the same questions and don’t share the results.

This problem doesn’t just impact companies, it impacts candidates. Candidates who are fantastic programmers but who lack the right degree, or went to the wrong school will not be given an interview at all. It is just too expensive to risk it because the rejection rate for that group, on average, is a little higher. My friend just went through this. He has a math degree from Harvard, and taught himself programming. After four years working as a concert cellist, he wanted to get into software engineering. The problem was, how to convince companies that you know what you know? They don’t have the time to let you prove that, and most won’t even return your calls. Meanwhile anyone with a Stanford CS degree has companies stalking them at home. This is an inefficient market. The Stanford CS kids are better, on average, but they aren’t that much better.

Now imagine that there is a central organization that does assessment. Let’s say that this assessment is granular (say one test per few classes) and let’s say that it is put together by real data people with a lot of effort to make the test material and the ranking itself high quality.

Naive thinking would lead you to believe that companies would hire by taking resumes, applying their random filtering, and then requesting test scores from this central organization for those resumes. But of course that isn’t how it would work at all. Instead you would just query and rank ALL candidates who met your standards on the skills you cared about.

This is the key to why testing is such a good business. It isn’t about charging test takers and competing with ETS. It is about being the sole entity with the ability to query a database that has all the skills of all the professionals and having a deep and well-calibrated assessment of that skill. There is no reason this testing should be limited to things currently taught in college classes, I think it could extend to any quantifiable skill.

If you believe that education will become very cheap as it moves from a non-scalable to a scalable model then this will result in lots of people who can learn things from these classes, but without the usual ability to certify their knowledge (e.g. a degree from Stanford). Of course the online education providers can try to provide this, but what does it mean to have a degree from Coursera or Udacity? I think this is just a digital imitation of the current (bad) practice.

Obviously testing like this wouldn’t replace interviews. But it would replace the part of interviews that companies are bad at (well calibrated assessment of basic skills) and give more time for assessing fit and personality.

Likely people would resent being tested and scored. But people don’t like being interviewed either, and at least this kind of model would mean shorter lower pressure interviews and the ability to “do over” if you happen to get tested on a bad day. Because the “query model” changes, the tests effectively apply you to all companies, rather than having to interview at each one.

This idea is only really easy to scale for quantitative ares. For math, engineering, and the sciences testing, when done right, can be very high quality. For these areas there is no reason for silly pre-computer relics like multiple choice, you can give open ended problems without a pre-defined set of answers. In computer programming you could actually have the person write a computer program.

Non-quantitative disciplines like english are harder to scale, but they are assessable. I think writing can be graded, and I think a really good writing certification could be a lot more useful then college literature classes (which focus on literary critique more than writing) for most uses. So the humanities could be assessed as well, but it would cost more since a human being would need to read the writing.

Its worth noticing the impact this would have on the world if it succeeded. First of all I think having a well-calibrated measurement would put a lot more focus on learning the material and much less on how you learned it. No one will care too much which book you read, which online class you took, or what exercises you did. Those are all just ways to learn. Second, this would truly democratize education–the self taught Bangladeshi is on equal footing with the legacy Harvard admittee.

Another way to say this is that testing, if it is good enough, commoditizes education. This sounds bad, since somehow commodities have gotten a bad wrap. But I mean this in the technical sense. A commodity is something that has a measurement of quality which is accurate enough that the details of the good’s production are irrelevant. If you know the ratings for a diamonds size, clarity, and color, you don’t need to worry about what mine it came from. In the absence of good measurements we are forced to rely on brands or other heuristics. But this is exactly how learning should work. If you learned linear algebra it shouldn’t somehow count for more because that learning happened in a Yale classroom instead of in your bedroom. All that should matter is how well you learned it.

Actually doing this would be a lot of work. Hopefully someone will steal this idea and do it.  

