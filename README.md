# Spies

Package `spies` provides a testing spy framework for Go.
It is heavily influenced by
(testify/mock.)[https://github.com/stretchr/testify#mock-package]

Roughly speaking,
you implement an interface against a spy,
then you can use the internal `Spy` object to record
responses to return,
and then assert calls against the spy.

## Motivation

Why this package and not `testify/mock`?
I personally find that Spies are more flexbile,
and encourage you to actually test the things
that need to be tested.
For instance,
often a test double needs to return
a value in response to a query
(e.g. `wehave.HowManyBananas()` returns 0).
If the code under test changes
and no longer needs to make that query,
there's no reason that the tests should break.

## Future Work

It'd be keen to have code generation for spies,
since they wind up usually being very standard structures.
However, I've often found it handy
to extend from the basic patterns
with little utility methods
on the control struct.

It might also be nice to have a few extra
methods related to selecting and
inspecting calls,
since that can get a little hairy.
