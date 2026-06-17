# X Post Ideas

Ideas worth revisiting, refining, and potentially sharing publicly.

---

## A codebase is not an application

Many systems assume that a codebase directly describes an application.

I've increasingly found the opposite to be true.

A codebase is a collection of capabilities.

The application is whatever composition of those capabilities happens to be assembled.

The same codebase may power:

- a website
- a REST API
- a CLI tool
- a worker
- an administration panel

The capabilities remain largely the same.

The composition changes.

Still exploring this idea.

---

## Capability vs implementation style

A capability describes what something can do.

An implementation style describes how it is expressed.

These concepts are often treated as the same thing.

A middleware, for example, may be implemented as:

- a closure
- a function
- an invokable object
- a traditional class

The capability remains the same.

The implementation style changes.

Should abstractions describe capabilities rather than implementation styles?

---

## Classes should be available, not mandatory

Classes solve real problems.

They help organize state, dependencies, and reusable behavior.

Closures solve real problems too.

They can reduce ceremony, improve local composition, and make small behaviors easier to express.

Perhaps the goal is not choosing one over the other.

Perhaps the goal is designing abstractions that allow both.

---

## Explicit assembly vs implicit discovery

Many systems discover behavior through:

- scanning
- reflection
- conventions
- registration

This can be convenient.

It can also make application structure harder to reason about.

What if application assembly were explicit instead?

Could clarity be improved without sacrificing ergonomics?

---

## Reusable capabilities over reusable applications

Many frameworks encourage thinking in terms of applications.

In practice, I often find myself thinking in terms of capabilities.

Authentication.

Image processing.

Publishing.

Notifications.

User workflows.

Applications come and go.

Capabilities tend to survive much longer.

---

## What should be visible?

When opening an application definition, what should be visible immediately?

For me, the ideal answer is:

- execution flow
- routes
- middleware hierarchy
- dependencies
- configuration

The application should not need to be discovered.

It should describe itself.

---

## The cost of convenience

Many developer conveniences introduce runtime work.

Discovery.

Registration.

Assembly.

Configuration loading.

Reflection.

The tradeoff is often worth it.

But where is the line?

How much convenience is worth paying for repeatedly at runtime?

---

## Software as composition

A useful building block should not need to know whether it is used by:

- a website
- an API
- a CLI tool
- a worker

It should simply provide a capability.

The surrounding composition determines its role.

---

## Architecture as a form of compression

Good architecture compresses complexity.

It reduces the amount of information required to understand a system.

A useful question:

How much of the application can be understood from a single place?

---

## Questions worth exploring

- Can applications be assembled entirely through composition?
- Which constraints are truly necessary for interoperability?
- Which conventions are solving real problems?
- Which conventions are merely inherited?
- What is the smallest useful abstraction?
- What should remain explicit?
- What should remain flexible?
