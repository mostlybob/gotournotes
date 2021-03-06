# Go Tour Notes
## My obligatory introductory blather
The readme serves as the description of what I'm doing as well as the notes themselves.

My intention is to stick to the outline set up in the Table of Contents on the actual tour itself. I can't guarantee any updates as the outline changes, since these are notes mainly for my use only. The tour is a really useful tool for devs coming from other languages or are coming back to Go after a time away, both of which apply to me. As the tour goes along, I find myself wondering about this or that and these notes are to capture my thoughts.

I prefer running the tour locally, so I can do this anywhere, regardless of an existing connection to the internet. Instructions on how to do that can be found [here][1]. If you're confident about your internet availability, or just don't want to hassle with getting it set up locally, you can do the tour [here][2]. The shortcut, when you have it installed locally is to run `$ gotour` in a terminal. If you `go get` the source, it installs at `$GOPATH/src/golang.org/x/tour/` 

My notes don't make much attempt to abstract out my working environment, which is Linux (at time of writing [Korora][4] 24 to be specific), but I pretty much follow the conventions in the tour. I've noodled a bit with Go under Windows and not at all under Mac. Your mileage may vary, but I think Go does a decent job of staying platform agnostic. I'm still pretty new at it, so there may be some differences down in the guts. This doc, by intent, is pretty rudimentary in nature.

I'm flattered if anyone finds this document useful, but really the value comes in doing it yourself. Clone or flat out steal the doc, I don't care what, but I'm really liking the things I've been doing with Go.

---------

- Basics
  - Packages, Variables and Functions
    - (Variables with initializers) This bit is super handy: `var i, j int = 1, 2` if a bit terse. It took me a bit of noodling around to figure out wth  `var c, python, java = true, false, "no!"` was actually doing, although I have to admit to getting a little distracted with the variable names. What I missed in the second example is the type inference going on, where in the first example, the type was being declared explicitly. The doc sums it up well: "[A var declaration can include initializers, one per variable ... If an initializer is present, the type can be omitted...][3]"
    - (Basic types) Quite a bit in this chunk: Module level variables with the `var()` construct, use of the `%T` in `fmt.Printf` (and presumably `fmt.Println`) to get the variable's type. I notice there's no equivalent of C#'s `.MaxValue` which is inconvenient.
    - (Type Conversions) is more like type coercion in that the types need to be natively compatible e.g. going from `int` to `float64`. I tried this:
    
    ``` golang
    var s string ="6"
    var six = int(s)
    fmt.Println(six)
    ```
    and got:

    ```
    cannot convert s (type string) to type int
    ```

    I would think there are methods that would handle this sort of conversion.
  - Flow control statements: for, if, else, switch and defer
    - "Go has only one looping construct, the `for` loop."
    - The `for` structure looks familiar, minus the `()`
    - nice shortcut to dispense with unnecessary init variables:

    ``` golang
    sum := 1
    for ; sum < 1000; {
      sum += sum
    }
    fmt.Println(sum)
    ```

    - and apparently, it gets even more terse i.e. [For is Go's "while"][5]
    
    ```
    sum := 1
    for sum < 1000 {
        sum += sum
    }
    fmt.Println(sum)
    ```

    - and yet one more level of terseness to get an infinite loop (might be handy if I get into some hardware work with [GoBot][6] or maybe even game programming?)

    ```
    for {
    }
    ```

    - (yep, that's it - handy!)
    - not sure I care for how terse the `if` statement can be with having initialization in the same line as the conditional:
    
    ```
    if v := math.Pow(x, n); v < lim {
        return v
    }
    return lim
    ```

    - too much terseness starts to muddy the functionality, IMO, although I guess having the variable declaration right beside its conditional test *is* kinda handy 

- Methods and Interfaces
- Concurrency


---------

[1]: https://github.com/golang/tour
[2]: https://tour.golang.org/
[3]: https://tour.golang.org/basics/9
[4]: https://kororaproject.org/
[5]: https://tour.golang.org/flowcontrol/3
[6]: [https://gobot.io/]