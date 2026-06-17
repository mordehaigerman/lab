# Callables vs Mandatory Abstractions

## Observation

Many executable capabilities are naturally represented as simple callables.

Examples include:

* middleware
* handlers
* actions
* commands
* pipeline stages

Despite this, many systems require these capabilities to be expressed through dedicated interfaces and classes.

This raises a question:

> Does the capability require the abstraction, or does the abstraction merely prescribe an implementation style?

---

## Example

Consider a middleware pipeline.

A middleware fundamentally needs to:

1. Accept a request.
2. Perform its own work.
3. Optionally invoke the next middleware.
4. Return a response.

One possible representation is:

```php
fn(Request $request, Closure $next): Response
```

Another is:

```php
class SomeMiddleware implements MiddlewareInterface
{
    public function process(
        Request $request,
        RequestHandlerInterface $handler
    ): Response {
        return $handler->handle($request);
    }
}
```

Both representations describe the same capability.

The primary difference is the implementation style.

---

## Potential Benefits of Callable-First Composition

### Fewer implementation constraints

A callable-first model allows executable behavior to be represented through:

* closures
* functions
* invokable objects
* static methods
* traditional classes

without forcing a single approach.

### Easier local composition

Not every middleware is intended to become a reusable package.

Some middleware exists solely for a single route, group, or application.

Allowing inline composition can reduce ceremony for these cases.

### Reduced coupling

A callable often depends only on the types that are meaningful to the capability itself.

Additional interfaces and abstractions may become optional rather than mandatory.

### Simpler experimentation

Small behaviors can be expressed quickly and modified easily during exploration.

---

## Why Classes Still Matter

Classes provide meaningful benefits.

Examples include:

* encapsulating state
* managing dependencies
* grouping related behavior
* improving discoverability
* creating reusable components

A callable-first model should not eliminate classes.

Instead, classes become one valid implementation choice among several.

---

## Questions

### Which constraints are essential?

Which requirements genuinely improve interoperability?

Which requirements merely enforce a preferred implementation style?

### Can interoperability be preserved?

Can multiple implementation styles coexist while maintaining shared contracts?

### What are the tradeoffs?

Potential areas to evaluate:

* readability
* maintainability
* testing
* debugging
* static analysis
* dependency injection

### Where should flexibility stop?

A system that supports every possible style may become more complicated than the problem it is solving.

How much flexibility is useful before it becomes a burden?

---

## Current Hypothesis

Executable capabilities should be defined primarily by what they do rather than how they are implemented.

Classes remain valuable.

Closures remain valuable.

Functions remain valuable.

The most useful abstraction may be the one that allows multiple implementation styles while preserving a clear contract.
