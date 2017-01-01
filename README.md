# Go Tour Notes
## My obligatory introductory blather
The readme serves as the description of what I'm doing as well as the notes themselves.

My intention is to stick to the outline set up in the Table of Contents on the actual
tour itself. I can't guarantee any updates as the outline changes, since these are notes
mainly for my use only. The tour is a really useful tool for devs coming from other
languages or are coming back to Go after a time away, both of which apply to me. As the
tour goes along, I find myself wondering about this or that and these notes are to
capture my thoughts.

I prefer running the tour locally, so I can do this anywhere, regardless of an existing
connection to the internet. Instructions on how to do that can be found [here][1]. If
you're confident about your internet availability, or just don't want to hassle with
getting it set up locally, you can do the tour [here][2]. 

I'm flattered if anyone finds this document useful, but really the value comes in doing
it yourself. Clone or flat out steal the doc, I don't care what, but I'm really liking
the things I've been doing with Go.

---------

- Basics
  - Packages, Variables and Functions
    - (Variables with initializers) This bit is super handy: `var i, j int = 1, 2` if a
    bit terse. It took me a bit of noodling around to figure out wth  `var c, python,
    java = true, false, "no!"` was actually doing, although I have to admit to getting
    a little distracted with the variable names. What I missed in the second example
    is the type inference going on, where in the first example, the type was being
    declared explicitly. The doc sums it up well: "[A var declaration can include 
    initializers, one per variable ... If an initializer is present, the type can be
    omitted...][3]"
    - (Basic types) Quite a bit in this chunk: Module level variables with the `var()`
    construct, use of the `%T` in `fmt.Printf` (and presumably `fmt.Println`) to get
    the variable's type. I notice there's no equivalent of C#'s `.MaxValue` which is
    inconvenient.
     
- Methods and Interfaces
- Concurrency


---------

[1]: https://github.com/golang/tour
[2]: https://tour.golang.org/
[3]: https://tour.golang.org/basics/9
