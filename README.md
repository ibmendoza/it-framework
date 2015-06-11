IT Framework
============

<h2>About</h2>

Imagine an IT marketplace where supply and demand speak a common language and common stack. This is not about lock-in. It is about finding a common ground so that when a developer creates something and leaves, anyone can step up and finish off the task.

This is about putting the fun back to computing where anything objective can be falsifiable, and where anything subjective is best left to each individual. No need for flame wars.

<h2>Author</h2>

Copyright (c) 2015 by Isagani Mendoza (http://itjumpstart.wordpress.com)


<h2>Requirements Gathering</h2>

- Specification by Example by Gojko Adzic

Why?

Here is a quote from his book:

I first want to explain why I chose Specification by Example as the overall name for the whole set of practices, as opposed to agile acceptance testing, Behavior-Driven Development, or Acceptance Test-Driven Development.

During the Domain Driven Design eXchange 2010 conference in London, Eric Evans argued that  agile  as a term has lost all meaning because anything can be called agile now. Unfortunately, he’s right. I’ve seen too many teams who tried to implement a process that was obviously broken but slapped the name agile  on it as if that would magically make it better. This is in spite of a huge body of available literature on how to properly implement XP, Scrum, and other less-popular agile processes.

To get around this meaningless ambiguity and arguing whether agile works or not (and what it is), I avoid using the term  agile  in this book as much as I can. I use it only when referring to teams that started implementing well-defined processes built on the principles outlined in the Agile Manifesto. So without being able to mention agile in every second sentence, agile acceptance testing as a name is out of the question.

The practices described here don’t form a fully fledged software development methodology. They supplement other methodologies —both iteration and flow based— to provide rigor in specifications and testing, enhance communication between various stakeholders and members of software development teams, reduce unnecessary rework, and facilitate change. So I don’t want to use any of the “Driven Development” names. Especially not Behavior-Driven Development (BDD). Don’t take this as a sign that I have anything against BDD. Quite the contrary, I love BDD and consider most of what this book is about actually a central part of BDD. But BDD suffers from the naming problem as well.

What BDD actually means changes all the time. Dan North, the central authority on what BDD is and what it is not, said that BDD is a  methodology  at the Agile Specifications, BDD, and Testing Exchange 2009. (Actually he called it “a second-generation, outside-in, pull-based, multiple-stakeholder, multiple-scale, high-automation, agile methodology.”) To avoid any confusion and ambiguity between what North calls BDD and what I consider BDD, I don’t want to use that name. This book is about a precise set of practices, which you can use within a range of methodologies, BDD included (if you accept that BDD is a methodology).

I also want to avoid using the word  test  too much. Many managers and business users unfortunately consider testing as a technical supplementary activity, not something that they want to get involved in. After all, they have dedicated testers to handle that. Specification by Example requires an active participation of stakeholders and delivery team members, including developers, testers, and analysts. Without putting  tests  in the
title, story testing, agile acceptance testing, and similar names are out.

This leaves Specification by Example as the most meaningful name with the least amount of negative baggage.


<h2>UNIX Philosophy</h2>


- Separate building engines (complexity) from interface (simplicity) and user experience (usability)
- Leave building engines to the experts (engine rule)
- Create minimal and well-defined interface for devs and ops (interface rule)
- Build “don’t-make-me-think” user experience for end-users (usability rule)


<h2>Three-Tier Architecture</h2>


**Presentation Tier**

- Use JWT, not cookies
- Use libraries, not frameworks
- Use functional programming where appropriate
- Use CommonJS for JS modules
- Use static pages, not MVC
- No class-based OOP
- Use JSON as data transport

**Application Tier**

- No RPC. Use REST/HTTP
- No UML. Visualize graph of interfaces
- Break down logic into units that focus on doing one thing well
- Use interface, not dependency injection
- Application logic, not data logic

**Storage Tier**

- Use SQL, not ORM
- Minimize data logic (stored procs, triggers, UDFs in RDBMS)
- No three-valued logic. Use sensible default instead of "null"
- Enforce foreign key constraints at the application tier
- Do not abuse relational model. Use non-relational model where appropriate


<h2>SCRAP for Quality</h2>

https://itjumpstart.wordpress.com/2015/04/13/scrap-framework

Courtesy of [Tyler Treat] (http://bravenewgeek.com/writing-good-code/) and some references from Scalability Rules book

Scalability (plan for growth)

- Use homogeneous networks. Don’t mix vendor networking gear
- If you can’t split it, you can’t scale it (Randy Shoup)
- Sharding is one way to scale data stores
- Master/slave replication has trade-off (master SPOF)
- Scale out and concurrency are antidotes to Moore’s law

Complexity (plan for humans)

- Break down complexity into units (engines)
- Focus on essential complexity, not accidental complexity
- Break down scope into minimum viable functionality
- Design until you have no more features to eliminate
- Visualize graph of interfaces, not UML

Resiliency (plan for failure)

- Use commodity hardware (goldfish, not thoroughbreds)
- Actively use log files
- Recreate data from transaction logs
- Use version control for change management
- Master your emergency drills
- Avoid single points of failure

 

API (plan for integration)

- Hide complexity behind a simple and minimal interface
- Move data, not logic
- Composition over inheritance
- Service (verb) is for writes. Resource (noun) is for reads
- Design interface with replaceable components (wire on/wire off)

Performance (plan for execution)

- Reduce DNS lookups
- Reduce objects where possible
- Use caching where appropriate
- Firewalls may be unnecessary hop for intranet IPC
- Measure twice and cut once (unnecessary error checking)
- Use asynchronous operation, no two-phase commit


<h2>12-Rule Ops</h2>

https://itjumpstart.wordpress.com/12-rule-ops

1. You cannot implement what you barely understand
2. Take note of the “fallacies of distributed computing“
3. Replication is not backup. Backup is not replication
4. Give unto RDBMS what is relational, unto NoSQL what is non-relational
5. Scale out the logic tier (VMs and containers), scale up the storage tier
6. Configuration management is about orchestration of CLI-based programs
7. Systems software must be broken into tools following the UNIX philosophy
8. You cannot automate if the process is barely in place
9. Security is a process, not a product
10. Operation is about which process requires automation or manual intervention
11. Hide the complexity of an engine behind a simple and minimal interface
12. Do not confuse usability (user experience) from simplicity (interface) and complexity (engine)


<h2>12-Rule App</h2>

https://itjumpstart.wordpress.com/12-rule-app

1. Export services via port binding
2. Minimize control logic, maximize application logic
3. Concurrency is not parallelism
4. Use interface, not leaky abstraction
5. Business logic is to app tier what data logic is to storage tier
6. Use sensible default, not “null” in RDBMS
7. Separate control from data
8. Software development is “anything goes”
9. Encrypt-then-MAC, not MAC-then-encrypt
10. Understand the problem domain first
11. RPC creates more problems than it solves
12. Bind to an interface, not implementation




<h2>Documentation</h2>

Use Markdown specifically GitHub-Flavored Markdown. See https://github.com/ibmendoza/ezdocs