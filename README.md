# Quartz

What I have after a bunch of design work.
Funny how long it takes to arrive at such a seemingly obvious solution.

## Traditional Theory Realization

- Theories are **never** reified in their entirety.
- Once you "have" a theory, you **manually** create hundreds of thousands of entries that "satisfy" that theory.
- You then collect them into a dictionary.

This leads to dictionaries that are:
- **Static**
- Bulky
- **Vestigial**
- Perpetually Incomplete
- Thoroughly **Inconsistent**
- **Poorly Documented**
- Unstable
- **Unmaintainable**

There is no presence of your theory in the end dictionary. This becomes very apparent as soon as you try to change your theory in any meaningful way (get to work).

## Python Dicts?

- **Bespoke** theory representation
  - Completely reified! (yay)
  - Not inherently well documented
- **Manual** transformations (not fun)
- Dynamic! (mostly)

I think there's a reason nobody has built an entire theory dictionary in python. They are fairly primitive.

## Froj?

- Still produces **static** json dicts.
  - Bulky, context-unaware, etc.
- Built on theory rules!
  - This is a fantastically good idea
  - Theory rules **are** documentation!
  - Auto-generated outlines!
- Poor format for theory rules, in my opinion

Froj never claims to build an entire dictionary for you, which is probably reasonable if you're a normal person.
Unlike python dicts, you can absolutely build a full theory dictionary like this.

## Quartz

What properties might quartz have?

- Reified theory
  - No vestigiality
  - Documentation!
- Go **directly** from theory to dictionary
- **Dynamism** and **context-aware(ness)**!
- **Stability**
- **Discrete** theory rule application

### How?

Quartz goes **directly** from theory to dictionary. No "manually write a hundred fifty thousand entries, and then spend the rest of your life maintaining them" step.

#### Dictionary

A dictionary is not necessarily a tangible thing. This idea is where theory staticness comes from, among other things.
In the case of Quartz, a dictionary is just a lookup function. This lookup function takes an outline and your entire theory, and returns the translation after applying all theory rules to the outline.

#### Theory Rules

Theory rules are very abstract. Sometimes we write them down (never in their entirety), but it's very imprecise, and has no coordination with your dictionary.

The theory rule format I've been working with (making simple orthospelling dicts) has 2 parts: a match predicate and an application function.
That is, whether an rule applies to an entry, and then the transformation of the entry, or the application of the theory rule.
Essentially, theory rules continuously modify the translation, and that's **all** they do.

(if you're reading this you should star the repo so I know how many people actually care)

### Problems

#### Syntactic Rules

Syntactic rules are rules in which the order of their application matters.
Take a rule such as "capitalize the translation if it starts with an A".
This rule **must** come after the translation has been determined.

Rule application order matters. This is seemingly fine, but I haven't found a good way to express this on the user side.

#### Greedy Rules

Rules that want to match forever!

#### Impure Re-execution

Impure matching functions (such as getting the current focused application) could return different results if a rule needs to backtrack.

#### ALL Rules

Modeling theory rules effectively, and how they interact.
This is mostly what I've been working recently.


I'll write down more problems later but I'm tired
There won't be code here for a while.
