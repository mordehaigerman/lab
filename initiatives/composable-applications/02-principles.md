# Principles

This document captures the principles that guide experiments within this initiative.

Implementations may change.

These principles should remain relatively stable.

---

## Applications emerge from composition

A codebase is a collection of reusable building blocks.

An application is the composition of those building blocks.

The codebase should not determine:

* how many applications exist
* how applications are assembled
* which components participate

The composition determines the application.

The codebase merely provides the parts.

---

## Capabilities are more important than implementation styles

When defining abstractions, the primary concern should be capability.

Questions such as:

* What can this do?
* How does it participate?
* What guarantees does it provide?

are often more important than:

* How is it implemented?
* Which construct expresses it?
* Which pattern was chosen?

Implementation details should not become unnecessary constraints.

---

## Prefer the smallest useful abstraction

Abstractions should exist only when they provide meaningful value.

A larger abstraction should not be introduced solely to satisfy a convention.

Whenever possible, software should be expressed using the smallest abstraction capable of solving the problem.

---

## Flexibility should emerge naturally

Supporting multiple use cases should not require supporting every possible implementation pattern.

Instead, a small number of carefully designed concepts should naturally enable multiple styles of usage.

Flexibility is not measured by the number of features.

Flexibility is measured by the range of problems that can be solved with a small set of concepts.

---

## Performance is a feature

Performance is not an afterthought.

Performance affects:

* developer experience
* operational costs
* scalability
* user experience

Solutions should avoid unnecessary runtime work whenever practical.

Performance considerations should be part of architectural design from the beginning.

---

## Explicit composition over implicit discovery

Composition should be visible.

System structure should be understandable without requiring extensive discovery mechanisms.

Configuration, assembly, and composition should remain easy to reason about.

Convenience is valuable.

Visibility is valuable too.

The tradeoff should be considered intentionally.

---

## Libraries over frameworks

Libraries provide capabilities.

Frameworks often provide structure.

Structure can be useful.

However, structure should not become mandatory.

Components should remain usable independently whenever practical.

The goal is to provide building blocks rather than dictate architecture.

---

## Native solutions first

Before introducing a custom abstraction, consider whether existing language capabilities already provide an appropriate solution.

Built-in mechanisms are often:

* easier to understand
* easier to debug
* easier to maintain

Language features should be preferred when they adequately solve the problem.

---

## Uniform composition

Concepts that participate in the same execution model should ideally compose in similar ways.

Special cases should be minimized.

A system becomes easier to understand when similar concepts behave similarly.

---

## Practicality over purity

Architectural purity is not a goal by itself.

Ideas should be evaluated by their practical consequences.

The preferred solution is often the one that:

* remains understandable
* remains maintainable
* performs well
* solves the problem with the least complexity

rather than the one that is theoretically perfect.
