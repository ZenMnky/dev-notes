Clean Code

# Clean Code: A Handbook of Agile Software Craftsmanship
By Robert C. Martin  
(2009) Addison-Wesley

---------

## Foreword

### 5S Principles of Total Productive Maintenance (p. xx)

- Seiri, or organization ("sort")
    - Knowing where things are - using approaches such as suitable naming - is crucial. 
- Seiton, or tidiness ("systematize")
    - _"A place for everything, and everything in its place"_
    - A piece of code should be where you expect to find it - and if not, you should re-factor to get it there.
- Seiso, or cleaning ("shine")
    - Keep the workplace free of hanging wires, grease, scraps, and waste.
    - Code littered with comments and commented-out code lines that capture history or wishes for the future? Get rid of them.
- Seiketsu, or standardization
    - The group agrees about how to keep the workplace clean
    - Consistent coding style and set of practices within the group
- Shutsuke, or discipline ("self-discipline")
    - Having the discipline to follow the practice and to frequently reflect on one's work and be willing to change.

'-----

- _Cleanliness is next to godliness_
- _He who is faithful in little, is faithful in much_
- _An ounce of prevention is worth a pound of cure_
- _Mighty oaks from little acorns grow_
- _A bad penny always shows up_

'-----

"Neither architecture nor clean code insist on perfection, only on honesty and doing the best we can. To err is human; to forgive, divine. In Scrum, we make everything visible. We air our dirty laundry. We are honest about the state of our code because code is never perfect. We become more fully human, more worthy of the divine, and closer to that greatness in the details" 
- James O. Coplien 
(Martin, Robert C. (2009). Clean Code: A Handbook of Agile Software Craftsmanship. pp xxii - xxiii)

## Chapter 1: Clean Code

Wading
"We wade through bad code.
We slog through a morass of tangled brambles and hidden pitfalls.
We struggle to find our way, hoping for some hint, some clue, of what is going on;
but all we see is more and more senseless code."
(p 3)

Bad Code
"- why did you write it?
Were you trying to go fast?
Were you in a rush?
Probably so.
Perhaps you felt that you didn't have time to do a good job; that your boss would be angry with you if you took the time to clean up your code.
Perhaps you were just tired of working on this program and wanted it to be over.
Or maybe you looked at the backlog of other stuff that you had promised to be done and realized that you need to slam this module together so you could move on to the next.
We've all done it.

We've all looked at the mess we've just made and then have chosen to leave it for another day. We've felt the relief of seeing our messy program work and deciding that a working mess is better than nothing. We've all said we'd go back and clean it up later. Of course, in those days we didn't know LeBlanc's law: Later equals never." (pp 3-4)

Bad Code
"But the fault, dear Dilbert, is not in our stars, but in ourselves. We are unprofessional.

This may be a bitter pill to swallow. How could this mess be _our_ fault? What about the requirements? What about the schedule? What about the stupid managers and the useless marketing types? Don't they bear some of the blame.

No. The managers and marketers look to _us_ for the information they need to make promises and commitments; and even when they don't look to us, we should not be shy about telling them what we think. The users look to us to validate the way the requirements will fit into the system. The project managers look to us to help work out the schedule. We are deeply complicit in the planning of the project and share a great deal of the responsibility for any failures; especially if those failures have to do with bad code!

'But wait!' you say. 'If I don't do what my manager says, I'll be fired.' Probably not. Most managers want the truth, even when they don't act like it. Most managers want good code, even when they are obsessing about the schedule. They may defend the schedule and requirements with passion; but that's their job. It's _your_ job to defend code with equal passion." (pp 5-6)


"All developers with more than a few years experience know that previous messes slow them down. And yet all developers feel the pressure to make messes in order to meet deadlines. In short, they don't take the time to go fast!

True professionals know that the second part of the conundrum is wrong. You will _not_ make the deadline by making the mess. Indeed, the mess will slow you down instantly, and will force you to miss the deadline. The _only_ way to make the deadline - the only way to go fast - is to keep the code as clean as possible at all times." (p 6)

### What Is Clean Code?
(pp 7-12)

- Elegant and efficient
    - straightforward logic
    - minimal dependencies
    - complete error handling
    - performance close to optimal

- simple and direct
    - crisp abstractions
    - reads like well-written prose

- readability by others
    - unit and acceptance tests
    - meaningful names
    - one way of doing things
    - minimal dependencies
    - clean and minimal API
    - literate code

- care
    - looks like it was written by someone who cares
    - nothing obvious that you can do to make it better

- simple
    - runs all the tests
    - contains no duplication
    - expressive
    - minimal
    - does one thing

- reasonable
    - each routine you read turns out to be pretty much what you expected
    - it makes it look like the language was made for the problem


_Leave the code better than when you found it_
- "If we all checked-in our code a little cleaner than when we checked it out, the code simply could not rot. The cleanup doesn't have to be something big. Change one variable name for the better, break up one function that's a little too large, eliminate one small bit of duplication, clean up one composite if-statement."
- "Can you imagine working on a project where the code _simply got better_ as time passed? Do you believe that any other option is professional? Indeed, isn't continuous improvement an intrinsic part of professionalism?" (p 14)

## Chapter 2 - Meaningful Names

**Use Intention-Revealing Names**   
The name of a variable, function, or class, should answer all the big questions: why it exists, what it does, and how it is used.

**Avoid Disinformation**    
Avoid leaving false clues that obscure the meaning of code.
Avoid words whose entrenched meanings vary from our intended meaning.

**Make Meaningful Distinctions**    
Don't write code solely to satisfy a compiler or interpreter.
Distinguish names in such a way that hte reader knows what the differences offer.

**Use Pronounceable Names**     
If you can't pronounce it, you can't discuss it without sounding like an idiot

**Use Searchable Names**    
- Longer names trump shorter names (like 'e'), and any searchable name trumps a constant in code
- The length of a name should correspond to the size of its scope
    - single-letter names are only to be used as local variables inside short methods.
- If a variable or constant might be seen or used in multiple places in a body of code, it is imperative to give it a search-friendly name.


**Avoid Mental Mapping**    
In general, programmers are pretty smart people. Smart people sometimes like to show off their smarts by demonstrating their mental juggling abilities. After all, if you can reliably remember that 'r' is the lower-cased version of the url with the host and scheme removed, then you must clearly be very smart.
One difference between a smart programmer and a professional programmer is that the professional understands that _clarity is king_. Professionals use their powers for good and write code that others can understand.

**Class Names**     
Classes and objects should have noun or noun phrase names. They should not be a verb.

**Method Names**
- Methods should have verb or verb phrase names
- Accessors, mutators, and predicates should be named for their value and prefixed with `get`, `set`, and `is`


## Chapter 3 - Functions

Aim to make functions easy to read and understand, so that a casual reader could intuit the intent

### Small
First rule of functions: they should be small   
Second rule of functions: they should be smaller than that

Functions should be short, transparently obvious, tell a story, and each lead you to the next in a compelling order

Descriptively named functions also add documentary value

### Do One Thing
> Functions should do one thing.    
> They should do it well.   
> They should do it only.   

If a function is doing one thing, we can describe it as a brief 'TO' paragraph, with steps of the function that are one level of abstraction below the stated name of the function

```
TO RenderPageWithSetupsAndTeardowns, we check to see whether the page is a test page and if so, we include the setups and teardowns. In either case we render the page in HTML
```

### One Level of Abstraction per Function

👉 "Separating levels of abstraction is one of the most important functions of refactoring, and it's one of the hardest to do well" (p 305)

Keep concepts and details separated

### The Stepdown Rule

The code should read like a top-down narrative
Every function should be followed by those at the next level of abstraction so that we can read the program, descending one level of abstraction at a time as we read down the list of functions

Said differently, the program should able to be read as a set of TO paragraphs, each of which is describing the current level of abstraction and referencing subsequent TO paragraphs at the next level down

```
TO include the setups and teardowns, we include setups, then we include the test page content, and then we include the teardowns
    TO include the setups, we include the suite setup if this is a suite, then we include the regular step
    TO include the suite setup, we search the parent hierarchy for ....
    TO search teh parent ...
```

👉 This is key to keeping functions short and making sure they do "one thing"

### Use Descriptive names
- Ward's principle: "You know you are working on clean code when each routine turns out to be pretty much what you expected"
- "Don't be afraid to make a name long. A long descriptive name is better than a short enigmatic name. A long descriptive name is better than a long descriptive comment" (p 39)
- "choosing descriptive names will clarify the design of the module in your mind and help you to improve it. It is not at all uncommon that hunting for a good name results in a favorable restructuring of the code" (p 40)

### Function Arguments
- "The ideal number of arguments for a function is zero (niladic). Next comes one (monadic), followed closely by two (dyadic). Three arguments (triadic) should be avoided where possible. More than three (polyadic) requires very special justification - and then shouldn't be used anyway." (p 40)


## Chapter 9 - Unit Tests

"Tests are as important to the health of a project as the production code is. Perhaps they are even more important, because tests preserve and enhance the flexibility, maintainability, and reusability of the production code. So keep your tests constantly clean. Work to make them expressive and succinct." (p133)

Without a test suite, we loose the ability to make sure changes to our code base work as expected. 
We loose the ability to ensure that changes to one part of our system do not break other parts of our system.
Our defect rate will rise, and there will be increased reluctance to make changes to and/or clean production code.
The production code will rot, and we'll be left with tangled and bug-riddled production code and frustrated customers.

Test code is just as important as production code. It requires thought, design, and care. It must be kept as clean as production code.


**Three Laws of Test Driven Development**
- First Law: You may not write production code until you have written a failing unit test.
- Second Law: You may not write more of a unit test than is sufficient to fail, and not compiling is failing.
- Third Law: You may not write more production code than is sufficient to pass the currently failing test.

**Clean Tests**
Three things that make for a clean test:
- Readability
- Readability
- Readability

What makes for readable code? Clarity, simplicity, and density of expression.


**Build-Operate-Check**     
acceptance test pattern
- Build up the test data
- Operate on that test data
- Check that the operation yielded the expected results

**F.I.R.S.T**   
Clean tests follow five other rules:

- **Fast**
    - Tests should run quickly. When tests run slow, we won't want to run them frequently and eventually the code will begin to rot
- **Independent**
    - Tests should not depend on each other. Each test should be able to run independently and in any order we'd like.
- **Repeatable**  
    - Tests should be repeatable in any environment.
- **Self-Validating**  
    - Tests should have a boolean output. Either they pass or fail.
- **Timely**  
    - Tests need to be written in a timely fashion. Unit tests should be written just before the production code that makes them pass.


