---
title: "Cargo Cult Migration, or Why I’m Okay Being Left Behind"
tags: [ember, ruby, rails, testing, oo]
---

For a while I’ve been discouraged about the move in the software development industry away from some things I value:

- From batteries-included frameworks like Rails to build-your-own-framework library ecosystems like React’s
- From implicit conventions to explicit wiring
- From object-oriented programming (OOP) to functional programming (FP)
- From dynamically-typed languages to statically-typed languages
- From test-driven development (TDD) for safety and refactoring, to relying primarily on a type system for those benefits

I’m getting old, so of course I have an inherent bias against change. Beyond that, though, I also have a “conservative” bent: I would rather move slowly, fitting new ideas into my existing toolset and mindset, instead of abandoning what I know and starting over. This seems to me to make it less likely to swing the pendulum and forget lessons we’ve learned in the past.

But is there in fact *any* benefit to the “old” ways I listed above: large frameworks, conventions, OOP, dynamic languages, and TDD? Listening to the discourse today, you wouldn’t think so. And this itself was worrying to me. I’m much more likely to take someone’s recommendation if they can articulate both sides of the issue and show an understanding of the pros and cons. Even if a new direction is all upside, they should at least be able to argue why in the past people chose another option, and why that logic has been superseded. I mean, were people foolish to *ever* use dynamically-typed languages? Did large frameworks *never* provide any benefit?

This line of thinking has left me pretty discouraged about the state of the software industry. **But something clicked when I started to see a pattern in the “old ways” I prefer: all of them support iterative development.** In this approach, instead of deciding in advance what you’re going to build, you build a little at a time, release it, get feedback, and then decide what to build next in response. Here’s how those “old ways” support iterative development:

- Frameworks give you everything you need for the 90% case out of the box, so you can get right to building features for your application without a lot of setup.
- Implicit conventions mean that there is little wiring code that needs to change when you move things around.
- Object-oriented programming is all about controlling dependencies so that changes won’t ripple through your system, the cost of change increasing exponentially.
- Dynamically-typed languages covered by tests allow you to precisely define the behavior of your system while keeping the implementation flexible, so that it can easily be changed.

When I realized that all of the “old ways” I prefer support iterative development, it pretty quickly became clear why many companies are moving away from them: most companies aren’t doing iterative development. They may be applying an “agile methodology,” but they certainly aren’t releasing frequently and changing what they are building based on feedback. They have a product roadmap, a plan to build a huge system, and they are going to build it no matter what. (This, incidentally, is one of the things folks in the agile community mean when they say companies are not really being agile at all.)

If a company isn’t doing iterative development, then using any of those “old ways” is really a kind of [cargo cult](https://en.wikipedia.org/wiki/Cargo_cult_programming). They aren’t really benefitting from a batteries-included framework, conventions, OOP, a dynamic type system, or TDD. They adopted them because they heard they were supposed to (“startups use Rails”, “professionals do TDD”) or simply because it was the only option (most widely-used languages were object-oriented until a few years ago). But they incurred the costs and risks of them without getting any of the benefit.

For such companies, it’s entirely positive to move away from these old ways. If you’re a large enterprise doing waterfall development (whether you call it “agile” or not), then static types will help your many teams of many developers avoid breaking each other’s code. If you’ve already decided you know what you need to build, and you aren’t open to any feedback on it, then TDD’s design input is a waste of time. If your code is going to be highly-coupled anyway then OOP just makes the coupling harder to see.

(Sorry, I couldn’t resist indulging a few jabs there. To be clear, I don’t at all mean that everybody using static types, functional programming, or build-your-own-framework ecosystems is doing development poorly. There are plenty of positives, and FP in particular seems absolutely necessary for our highly-connected and concurrent future. What I mean is, for the companies that *are* doing development poorly, it seems that they will derive more benefits from static types and functional programming than from dynamic types and OOP, for example.)

It’s also a positive for the industry as a whole for companies to stop cargo-culting these “old ways.” This means that when you’re job searching you can have a greater and greater chance that a company using TDD or OOP is using them for their intended purpose. If nobody adopts OOP or TDD by default, then anyone using them probably has a specific reason for doing so, so it at least increases your chances that they really understand what they’re for.

And I think this realization may give me a more productive way to try to share what I know about the “old ways” and engage with the “new ways.” I don’t  have to simultaneously try to convince people to use Rails, OOP, TDD, and dynamically-typed languages. Instead, I can simply talk to people about iterative development and the benefits it could provide. Focusing on one topic is simpler for me, and it gets at the root of why most developers don’t care about these “old ways,” so it’s more likely to make a difference. Also, as I continue to try to overcome my old-man bias and be open to new things, this approach gives me a simple question I can ask about any new way: how will this impact my ability to do iterative development? It quickly gets to the heart of the issue, raises a productive conversation, and it makes room for us to politely disagree: if I care about iterative development and you don’t, then no wonder we will have different assessments of a technology!

This doesn’t mean that talking with people about iterative development will be easy. Heck, I chose that term for this post instead of “agile” because of the train wreck of how the latter has become misused. So maybe in the end I won’t find much comfort in focusing on iterative development. But, if nothing else, it gives me an understanding for my own sake of why the industry is going the direction it’s going.

And it’s okay to be the little guy. Ruby took off in the US when nobody could get a job working in it; it just made developers happy to use it. TDD took off after the Smalltalk market died and all the Smalltalkers moved to Java. Maybe we will find a “killer app” the way Rails did where taking an iterative approach provides undeniable wins over the waterfall approach. Or maybe it will just be quiet wins. As I described in my talk [“How I Learned to Stop Worrying and Love Development”](https://youtu.be/CxO8VCdkrpU), I came to agile development in despair when I gave up on the hope that a new language or framework would solve the problems in software development that filled my life with stress. It seems like many, many developers are experiencing that same stress. I hope more of them will come to see that there’s a better way. Ultimately, it’s up to them to decide to try something new. My role is to articulate the alternative, and I think I can do that more clearly now.

If you’d like to learn more about iterative development, Ron Jeffries’ recent book [_The Nature of Software Development_](https://pragprog.com/book/rjnsd/the-nature-of-software-development) is one of the best summaries I’ve found.
