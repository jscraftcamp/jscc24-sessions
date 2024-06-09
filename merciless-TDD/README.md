# Merciless TDD 

Ran by [@wolframkriesing](https://codeberg.org/wolframkriesing).

This session took place on day 1 of #jscc24 with the pizza starting at dinner around 19:00 until 21:00 more or less.

We started choosing the task that we wanted to solve. We looked at the data coming back from `performance.getEntries()` 
the [Performance API](https://developer.mozilla.org/en-US/docs/Web/API/Performance) as available in all modern browsers.
The task we wanted to TDD was reading the ratio of successful and failing tests.

## Tools (for TDD)

While programming along Wolfram moderated and forced us to be very strict on TDDing. 
While doing so some "tools" for TDD [see c2 wiki](https://wiki.c2.com/?TestDrivenDevelopment) 
or testing in general had been underlined often, such as:
* do tiny simple steps (see also https://wiki.c2.com/?DoSimpleThings)
* which tests to write?
    * write a test for no data (at least you will "design" the API already)
    * write a test for 1 result (this advances your code)
    * many results (will make the code quite generic)
    * a lot of results (maybe you need pagination, data slicing, etc.)
    * and the error cases
* "As the tests get more specific, the code gets more generic" unknown quote origin 
* write a red test first, see it fail
* ensure test description is telling the story the test will implement, and asure to adjust if it diverges
* write just enough code to make the test pass (fake it until you make it)
* refactor your tests too
* name variables in a useful way
* if you copy paste, you copy waste
* refactor on green
* Ctrl-Z/undo when you refactor but the test start to fail, make tiny steps towards the solution
* ... please add what's missing...

## Finally
In our session we TDDed every little step, unfortunately there is only one commit
and this is only the final result after we TDDed the code.
We discussed naming, product requirements, etc. in depth and refactored a lot, etc.
The code is here https://codeberg.org/wolframkriesing/jslang-meetups/src/branch/main/jscc24-tdd/test.js

## More
This video is about more than TDD but in the middle [@jbrains](https://github.com/jbrains) explains TDD "quickly" https://www.youtube.com/watch?v=WSes_PexXcA
