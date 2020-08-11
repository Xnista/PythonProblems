<!-- Copy and paste the converted output. -->

<!-----
NEW: Check the "Suppress top comment" option to remove this info from the output.

Conversion time: 22.157 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β29
* Tue Aug 11 2020 04:57:49 GMT-0700 (PDT)
* Source doc: Copy of 109 Python Problems for CCPS 109
* Tables are currently converted to HTML tables.
----->



# **109 Python Problems for CCPS 109**

This document contains the specifications for the **graded lab problems** for the course **CCPS 109 Computer Science I**, as taught by [Ilkka Kokkarinen](http://www.scs.ryerson.ca/~ikokkari/). All computer science learners and teachers are free to use and adapt this material for their own courses as they see fit, with proper attribution. The author has compiled these problems over time from a gallimaufry of sources ranging from the lab and exam problems of his old Java version of this course to a multitude of programming puzzle and code challenge sites such as [LeetCode](https://leetcode.com/problemset/all/), [CodeAbbey](http://www.codeabbey.com/index/task_list), [Stack Exchange Code Golf](https://codegolf.stackexchange.com/), and [Wolfram Programming Challenges](https://challenges.wolfram.com/). Recreational mathematics columns by Martin Gardner and his spiritual disciples have also inspired many problems both old and new.

For the purposes of submission and grading, you **must implement all these functions in a single Python source code file** that **must** be named `labs109.py`. **Do not submit the individual functions as you go, but submit these labs all in one file at the end of the course**. Until then, make sure to regularly back up your precious work in at least two separate locations!

You can run the `tester109.py` script at any time to execute the tests for the functions that you have completed so far. These tests are executed in the same order that your functions appear in the `labs109.py` file. The test battery for each individual function should take at most a couple of seconds to complete. If some test takes a minute or more, your code is too slow and its logic desperately needs to be streamlined, usually by shaving off one level of nesting from your loops.

**[SILENCE IS GOLDEN](http://www.catb.org/~esr/writings/taoup/html/ch11s09.html). When called, none of your functions should ever print anything on the console**, but silently return the expected result. You can do some debugging outputs during the development, but remember to comment them out before submission. Also, unless explicitly requested to do so by the problem specification, **these functions should never mutate the lists and other sequences that they receive as arguments**.

**Your functions may assume that the arguments given by the automated tester are legal and valid as given in the problem specification. **Your functions do not need to perform any error detection or recovery from nonsensical arguments. Note that zero integers and empty lists are often legitimate arguments, and your functions must handle them correctly in such cases. 

Past students **Shu Zhu Su**, **Mohammed Waqas** and **Zhouqin He** deserve thanks for going far above and beyond the call of duty in completing solutions that either revealed several errors in the original problem specifications or the private model solutions, or independently agreed with the original solution and this way raised the confidence to its correctness. All remaining errors, ambiguities and inconsistencies are the sole responsibility of Ilkka Kokkarinen. Report them to `ilkka.kokkarinen@gmail.com` to help nudge (or budge) this document one step closer to the perfection that it still is _n_ steps away from, the exact value or even the scale of _n_ still unknown.


## **Ryerson letter grade** 


```
def ryerson_letter_grade(pct):
```


Given the percentage grade for the course, calculate and return the letter grade that would appear in the Ryerson grades transcript, as defined on the page [Ryerson Grade Scales](https://www.ryerson.ca/registrar/faculty/grading/gradescales_ugrad/). The letter grade should be returned as a string that consists of the uppercase letter followed by the possible modifier `'+'` or `'-'`. The function should work correctly for all values of `pct` from 0 to 150.

Same as all other programming problems that follow this problem, this can be solved in various different ways. At this point of your studies, the simplest way to solve this problem would probably be just to use an **if-else ladder**. The file <code>[labs109.py](https://github.com/ikokkari/PythonProblems/blob/master/labs109.py)</code> given in the repository <code>[ikokkari/PythonProblems](https://github.com/ikokkari/PythonProblems)</code> already contains an implementation of this function so that you can run the tester script <code>[tester109.py](https://github.com/ikokkari/PythonProblems/blob/master/tester109.py)</code> and verify that it is working correctly. 


<table>
  <tr>
   <td><code>pct</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>45</code>
   </td>
   <td><code>'F'</code>
   </td>
  </tr>
  <tr>
   <td><code>62</code>
   </td>
   <td><code>'C-'</code>
   </td>
  </tr>
  <tr>
   <td><code>89</code>
   </td>
   <td><code>'A'</code>
   </td>
  </tr>
  <tr>
   <td><code>107</code>
   </td>
   <td><code>'A+'</code>
   </td>
  </tr>
</table>


As you learn more Python and techniques to perform computations within it, you may think up other ways to solve this problem. Some of these would be appropriate for actual productive tasks  done in a professional coding environment, whereas others are intended to be taken in jest as a kind of conceptual performance art. A popular genre in all programming languages is to solve some straightforward problem with an algorithmic equivalent of a needlessly complicated [Rube Goldberg machine](https://en.wikipedia.org/wiki/Rube_Goldberg_machine), to demonstrate the universality and unity of all computation.


## **Ascending list**


```
def is_ascending(items):
```


Determine whether the sequence of `items` is **strictly ascending** so that each element is **strictly larger** (not just merely equal to) than the element that precedes it. Return `True` if the list of `items` is strictly ascending, and return `False` otherwise. Note that the empty sequence is ascending, as is also every one-element sequence, so be careful that your function returns the correct answers in these seemingly insignificant **edge cases** of this problem. (If these sequences were not ascending, pray tell, what would be the two elements that violate the requirement and make that particular sequence not be ascending?)


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[]</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>[-5, 10, 99, 123456]</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>[2, 3, 3, 4, 5]</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>[-99]</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>[4, 5, 6, 7, 3, 7, 9]</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 1, 1, 1]</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
</table>


In the same spirit, note how every possible universal claim made about the elements of an empty sequence is trivially true. For example, if `seq` is the empty sequence, the two claims "All elements of `seq` are odd" and "All elements of `seq` are even" are both equally true, as is also the claim "All elements of `seq` are [colourless green ideas that sleep furiously](https://en.wikipedia.org/wiki/Colorless_green_ideas_sleep_furiously)". For some reason, many people find this highly counterintuitive or even paradoxical, but it is a consequence of the fact that any logical formula of the form "_A_ implies _B_" is automatically true whenever _A_ is false.


## **Riffle**


```
def riffle(items, out=True):
```


Given a list of `items` whose length is guaranteed to be even (notice here that "oddly" enough, zero is an even number), create and return a list produced by performing a perfect **riffle** to the `items` by interleaving the items of the two halves of the list in an alternating fashion.

When performing a perfect riffle, also known as the [Faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle), the list of `items` is split in two equal sized halves, either conceptually or in actuality. The first two elements of the result are then the first elements of those halves. The next two elements of the result are the second elements of those halves, followed by the third elements of those halves, and so on up to the last elements of those halves. The parameter `out` determines whether this function performs an [out shuffle](https://en.wikipedia.org/wiki/Out_shuffle) or an [in shuffle](https://en.wikipedia.org/wiki/In_shuffle) that determines which half of the deck the alternating card is first taken from.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td><code>out</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3, 4, 5, 6, 7, 8]</code>
   </td>
   <td><code>True</code>
   </td>
   <td><code>[1, 5, 2, 6, 3, 7, 4, 8]</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3, 4, 5, 6, 7, 8]</code>
   </td>
   <td><code>False</code>
   </td>
   <td><code>[5, 1, 6, 2, 7, 3, 8, 4]</code>
   </td>
  </tr>
  <tr>
   <td><code>[]</code>
   </td>
   <td><code>True</code>
   </td>
   <td><code>[]</code>
   </td>
  </tr>
  <tr>
   <td><code>['bob', 'jack']</code>
   </td>
   <td><code>True</code>
   </td>
   <td><code>['bob', 'jack']</code>
   </td>
  </tr>
  <tr>
   <td><code>['bob', 'jack']</code>
   </td>
   <td><code>False</code>
   </td>
   <td><code>['jack', 'bob']</code>
   </td>
  </tr>
</table>





## **Only odd digits**


```
def only_odd_digits(n):
```


Check that the given positive integer `n` contains only odd digits (1, 3, 5, 7 and 9) when it is written out. Return `True` if this is the case, and `False` otherwise. Note that this question is not asking whether the number `n` itself is odd or even. You therefore will have to look at every digit of the given number before you can proclaim that the number contains no odd digits.

Hint: to extract the lowest digit of a positive integer `n`, use the expression `n % 10`. To chop off the lowest digit and keep the rest of the digits, use the expression `n // 10`. Or, if you don't want to be this fancy, convert the number into a string first and work from there with string operations.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>8</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>1357975313579</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>42</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>71358</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>0</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
</table>





## **Cyclops numbers**


```
def is_cyclops(n):
```


A nonnegative integer is said to be a **cyclops number** if it consists of an **odd number of digits** so that the middle (more poetically, the "eye") digit is a zero, and all other digits of that number are nonzero. This function should determine whether its parameter integer `n` is a cyclops number, and return either `True` or `False` accordingly.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>0</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>101</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>98053</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>777888999</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>1056</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>675409820</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
</table>


As an extra challenge, you can try to solve this problem using only loops, conditions and integer arithmetic operations, without first converting the integer into a string and working from there. Dividing an integer by 10 effectively chops off its last digit, whereas the remainder operator `%` can be used to extract that last digit. These operations allow us to iterate through the digits of an integer one by one almost as if it were some kind of lazy sequence.

(Even better, this operation doesn't work merely for the familiar base ten, but it works for any base by using that base as the divisor. Especially using two as the divisor allows you to iterate through the **bits** of the **binary representation** of any integer, which will come handy in problems in later courses that need to manipulate these individual bits.)


## **Domino cycle**


```
def domino_cycle(tiles):
```


A single **domino tile** is represented as a two-tuple of its **pip values**, such as `(2, 5)` or `(6, 6)`. This function should determine whether the given list of `tiles` forms a **cycle** so that each tile in the list ends with the exact same pip value that its successor tile starts with, the successor of the last tile being the first tile of the list since this is supposed to be a cycle instead of a chain. Return `True` if the given list of domino tiles form such a cycle, and `False` otherwise.


<table>
  <tr>
   <td><code>tiles</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[(3, 5), (5, 2), (2, 3)]</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>[(4, 4)]</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>[]</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>[(2, 6)]</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>[(5, 2), (2, 3), (4, 5)]</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>[(4, 3), (3, 1)]</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
</table>





## **Count dominators**


```
def count_dominators(items):
```


An element of `items` is said to be a dominator if **every** element to its right (and not just the one that is immediate to its right) is strictly smaller than it. This function should count how many elements in `items` are dominators, and return that count. By this definition, the last item of the list is automatically a dominator. For example, dominators of `[42, 7, 12, 9, 13, 5]` would be the elements 42, 13 and 5.

Before starting to write any code for this function, please read and think about the tale of "[Shlemiel the painter](http://wiki.c2.com/?ShlemielThePainter)" and how this seemingly silly little tale from a far simpler time might relate to today's computational problems for lists, strings and other sequences. This problem will be the first of many that you will encounter during and after this course to illustrate the important principle of using only one loop to achieve in a tiny fraction of time the same end result that Shlemiel needs two nested full loops to achieve, your workload therefore increasing only **linearly** with respect to the number of `items` instead of **quadratically** (that is, as a function of the **square** of the number of items), same as how Shlemiel's task of running back and forth will increase as the function of the square of the length of the fence, so that doubling the length of the fence will quadruple the amount of running...


<table>
  <tr>
   <td>items
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[42, 7, 12, 9, 2, 5]</code>
   </td>
   <td><code>4</code>
   </td>
  </tr>
  <tr>
   <td><code>[]</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>[99]</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
  <tr>
   <td><code>[42, 42, 42, 42]</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
  <tr>
   <td><code>range(10**7)</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
  <tr>
   <td><code>range(10**7, 0, -1)</code>
   </td>
   <td><code>10000000</code>
   </td>
  </tr>
</table>


Hiding the linear-time inner loop of some Shlemiel algorithm inside a function call (including Python built-ins such as `max` and slicing) does not prevent the Gods of Compubook Headings from returning with tumult to claim their lion's share of execution time.


## **Extract increasing integers from digit string**


```
def extract_increasing(digits):
```


Given a string of digits guaranteed to only contain ordinary integer digit characters 0 to 9, create and return the list of increasing integers acquired from reading these digits in order from left to right. The first integer in the result list is made up from the first digit of the string. After that, each element is an integer that consists of as many following consecutive digits as are needed to make that integer **strictly larger** than the previous integer. The leftover digits at the end of the digit string that do not form a sufficiently large integer are discarded.

This problem can be solved elegantly with only one for-loop through the `digits` that looks at each digit exactly once regardless of the position of that digit in the beginning, end or middle of the string. Keep track of the `current` number (initially zero) and the `previous` number to beat (initially minus one). Each digit `d` then updates `current = 10*current+d` to tack that digit to the end of `current`. 


<table>
  <tr>
   <td><code>digits</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'045349'</code>
   </td>
   <td><code>[0, 4, 5, 34]</code>
   </td>
  </tr>
  <tr>
   <td><code>'77777777777777777777777'</code>
   </td>
   <td><code>[7, 77, 777, 7777, 77777, 777777]</code>
   </td>
  </tr>
  <tr>
   <td><code>'122333444455555666666'</code>
   </td>
   <td><code>[1, 2, 23, 33, 44, 445, 555, 566, 666]</code>
   </td>
  </tr>
  <tr>
   <td><code>'1234567890987654321'</code>
   </td>
   <td><code>[1, 2, 3, 4, 5, 6, 7, 8, 9, 98, 765, 4321]</code>
   </td>
  </tr>
  <tr>
   <td><code>'3141592653589793238462643383279502884'</code>
   </td>
   <td><code>[3, 14, 15, 92, 653, 5897, 9323, 84626, 433832, 795028]</code>
   </td>
  </tr>
  <tr>
   <td><code>'2718281828459045235360287471352662497757247093699959574966967627724076630353547594571382178525166427427466391932003059921817413596629043572900334295260'</code>
   </td>
   <td><code>[2, 7, 18, 28, 182, 845, 904, 5235, 36028, 74713, 526624, 977572, 4709369, 9959574, 96696762, 772407663, 3535475945, 7138217852, 51664274274, 66391932003, 599218174135, 966290435729]</code>
   </td>
  </tr>
  <tr>
   <td><code>'123456789' * 100</code>
   </td>
   <td>A list that contains 75 elements, the last one of which equals <code>34567891234567891234567891</code>
   </td>
  </tr>
</table>



## 


## **Words that contain given letter sequence**


```
def words_with_letters(words, letters):
```


This might be a good place to bring in some general discrete math terminology that makes our problem specifications less ambiguous. A **substring** of a string consists of characters taken **in order** from consecutive positions. Contrast this with the similar concept of **subsequence** of characters still taken in order, but not necessarily at consecutive positions. For example, the strings `""`, `"e"`, `"put"`, `"ompu"` and `"computer"` are both substrings and subsequences of `"computer"`, whereas `"cper"` and "`out`" are subsequences of that word, but not substrings.

Note that the empty string is automatically a substring of every possible string. Every string is its own substring, although not a **proper substring** the same way how all other substrings are proper. Concepts of **sublist** and **subsequence** are defined for lists in an analogous manner. Since **sets** have no internal order on top of the element membership in that set, sets can meaningfully have both proper and improper subsets. However, the concept of subsequence would be nonsensical for sets and dictionaries.

Now that you know all that, given a list of `words` sorted in alphabetical order, and a string of required `letters`, find and return the list of words that contain `letters` as a sub_sequence_.


<table>
  <tr>
   <td><code>letters</code>
   </td>
   <td>Expected result (using the wordlist <code>words_sorted.txt</code>)
   </td>
  </tr>
  <tr>
   <td><code>'klore'</code>
   </td>
   <td><code>['booklore', 'booklores', 'folklore', 'folklores', 'kaliborite', 'kenlore', 'kiloampere', 'kilocalorie', 'kilocurie', 'kilogramme', 'kilogrammetre', 'kilolitre', 'kilometrage', 'kilometre', 'kilooersted', 'kiloparsec', 'kilostere', 'kiloware']</code>
   </td>
  </tr>
  <tr>
   <td><code>'brohiic'</code>
   </td>
   <td><code>['bronchiectatic', 'bronchiogenic', 'bronchitic', 'ombrophilic', 'timbrophilic']</code>
   </td>
  </tr>
  <tr>
   <td><code>'azaz'</code>
   </td>
   <td><code>['azazel', 'azotetrazole', 'azoxazole', 'diazoaminobenzene', 'hazardize', 'razzmatazz']</code>
   </td>
  </tr>
</table>





## **Taxi zum zum**


```
def taxi_zum_zum(moves):
```


A Manhattan taxicab starts at the origin point `(0, 0)` of the two-dimensional grid of integers, initially heading north. It then executes the given sequence of `moves`, given as a string made up of the characters `'L' `for turning 90 degrees left (while standing in place), `'R'` for turning 90 degrees right (ditto), and '`F`' for moving one step forward towards its present heading. This function should return the final position of the taxicab in the integer grid coordinates of Manhattan.


<table>
  <tr>
   <td><code>moves</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'RFRL'</code>
   </td>
   <td><code>(1, 0)</code>
   </td>
  </tr>
  <tr>
   <td><code>'LLFLFLRLFR'</code>
   </td>
   <td><code>(1, 0)</code>
   </td>
  </tr>
  <tr>
   <td><code>'FR' * 1000</code>
   </td>
   <td><code>(0, 0)</code>
   </td>
  </tr>
  <tr>
   <td><code>'FFLLLFRLFLRFRLRRL'</code>
   </td>
   <td><code>(3, 2)</code>
   </td>
  </tr>
</table>


As an aside, why do these problems always seem to take place in Manhattan instead of, say, Denver where the street grid is rotated 45 degrees from the main compass axes to equalize the amount of daily sunlight on streets heading towards both orientations? That ought to make for an interesting variation to many problems of this spirit. (Then again, diagonal moves always maintain the total **parity** of the coordinates, which makes it impossible to reach any coordinates of the opposite parity in this manner, somewhat like in that old joke with the punchline "Gee... I don't think that you can get there from here.") 




## **Giving back change**


```
def give_change(amount, coins):
```


Given the `amount` of money (expressed as an integer as the total number of cents, one dollar being equal to 100 cents) and the list of available denominations of `coins` (similarly expressed as cents), create and return a list of coins that add up to `amount` using the **greedy approach** where you use as many of the highest denomination coins when possible before moving on to the next lower denomination. The list of coin denominations is guaranteed to be given in descending sorted order, as should your returned result also be.


<table>
  <tr>
   <td><code>amount</code>
   </td>
   <td><code>coins</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>64</code>
   </td>
   <td><code>[50, 25, 10, 5, 1]</code>
   </td>
   <td><code>[50, 10, 1, 1, 1, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>123</code>
   </td>
   <td><code>[100, 25, 10, 5, 1]</code>
   </td>
   <td><code>[100, 10, 10, 1, 1, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>100</code>
   </td>
   <td><code>[42, 17, 11, 6, 1]</code>
   </td>
   <td><code>[42, 42, 11, 1, 1, 1, 1, 1]</code>
   </td>
  </tr>
</table>


This problem, along with its countless variations, is a computer science classic when modified to minimize the total number of returned coins. The above greedy approach then no longer produces the optimal result for all possible coin denominations. For example, for simple coin denominations of `[50, 30, 1]` kopecs and the amount of sixty kopecs to be exchanged, the greedy solution `[50, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]` ends up using eleven coins by its unfortunate choice that prevents it from using the 30-kopec coins, whereas the optimal solution `[30, 30]` needs only two coins! A more advanced **recursive** algorithm examines both sides of the "take it or leave it" decision for each coin and chooses the choice that ultimately leads to a superior outcome. The intermediate results of this recursion should then be **memoized** to avoid blowing up the running time exponentially.


## **Rooks on a rampage**


```
def safe_squares_rooks(n, rooks):
```


On a generalized _n_-by-_n_ chessboard, there are some number of **rooks**, each one represented as a two-tuple `(row, column)` of the row and the column of the square that the rook is in. Since we are again computer programmers instead of chess players and other normal folks, these rows and columns are numbered from 0 to _n_ - 1. A chess rook covers all squares that are in the same row or in the same column as that rook. Given the board size `n` and the list of `rooks` on that board, count the number of empty squares that are safe, that is, are not covered by any rook.

Hint: count separately how many rows and columns on the board are safe from any rook. The result is simply the product of these two counts. Because permuting the rows and columns does not change the answer to this question, we can imagine all these safe rows and columns to have been permuted to form a rectangle at the top left corner of the board. The area of that safe rectangle is the product of its known width and height, of course.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>rooks</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>[]</code>
   </td>
   <td><code>100</code>
   </td>
  </tr>
  <tr>
   <td><code>4</code>
   </td>
   <td><code>[(2, 3), (0, 1)]</code>
   </td>
   <td><code>4</code>
   </td>
  </tr>
  <tr>
   <td><code>8</code>
   </td>
   <td><code>[(1, 1), (3, 5), (7, 0), (7, 6)]</code>
   </td>
   <td><code>20</code>
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>[(1, 1)]</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
  <tr>
   <td><code>6</code>
   </td>
   <td><code>[(0, 0), (1, 1), (2, 2), (3, 3), (4, 4), (5, 5)]</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>100</code>
   </td>
   <td><code>[(r, (r*(r-1))%100) for r in range(0, 100, 2)]</code>
   </td>
   <td><code>3900</code>
   </td>
  </tr>
  <tr>
   <td><code>10**6</code>
   </td>
   <td><code>[(r, r) for r in range(10**6)]</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
</table>





## **Try a spatula**


```
def pancake_scramble(text):
```


Analogous to flipping a stack of pancakes by sticking a spatula inside the stack and flipping over the stack of pancakes resting on top of that spatula, a **pancake flip** of order _k_ performed for the `text` string reverses the prefix of first _k_ characters and keeps the rest of the string as it were. For example, the pancake flip of order 2 performed on the string `'ilkka'` would produce the string `'likka'`. The pancake flip of order 3 performed on the same string would produce `'klika'`.

A **pancake scramble**, as [defined in the excellent Wolfram Challenges programming problems site](https://challenges.wolfram.com/challenge/pancake-scramble), consists of the sequence of pancake flips of order 2, 3, ... , _n_ performed in this exact sequence for the given _n_-character `text` string. For example, the pancake scramble done to the string `'ilkka'` would step through the intermediate results `'likka'`, `'kilka'`, `'klika'` and `'akilk'`. This function should compute and return the pancake scramble of its parameter `text` string.


<table>
  <tr>
   <td><code>text</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'hello world'</code>
   </td>
   <td><code>'drwolhel ol'</code>
   </td>
  </tr>
  <tr>
   <td><code>'ilkka'</code>
   </td>
   <td><code>'akilk'</code>
   </td>
  </tr>
  <tr>
   <td><code>'pancake'</code>
   </td>
   <td><code>'eanpack'</code>
   </td>
  </tr>
  <tr>
   <td><code>'abcdefghijklmnopqrstuvwxyz'</code>
   </td>
   <td><code>'zxvtrpnljhfdbacegikmoqsuwy'</code>
   </td>
  </tr>
</table>


For those of you who are interested in this sort of stuff, the follow-up question "[How many times you need to pancake scramble the given string to get back the original string?](https://challenges.wolfram.com/challenge/pancake-scramble-period)" is also educational, especially once the strings get so long that the answer needs to be computed analytically (note that the answer depends only on the length of the string but not the content, as long as all characters are distinct) instead of actually performing these scrambles until the original string appears. A more famous problem of [pancake sorting](https://en.wikipedia.org/wiki/Pancake_sorting) asks for the shortest series of pancake flips whose application rearranges the elements of the given list in sorted order. 


## **Words with given shape**


```
def words_with_given_shape(words, shape):
```


The shape of the given word of length _n_ is a list of _n_ - 1 integers, each one either -1, 0 or +1 to indicate whether the next letter following the letter in that position comes later (+1), is the same (0) or comes earlier (-1) in the alphabetical order of English letters. For example, the shape of the word `'hello'` is `[-1, +1, 0, +1]`, whereas the shape of `'world'` is `[-1, +1, -1, -1]`. Find and return a list of all `words` that have that particular `shape`, listed in alphabetical order.

Note that your function, same as all the other functions specified in this document that operate on lists of words, should not itself try to read the wordlist file `words_sorted.txt`, even when Python makes this possible with just a couple of lines of code. The tester script already reads in the entire wordlist and builds the list of words from there. Your function should use this given list of `words` without even caring which particular file it came from. 


<table>
  <tr>
   <td><code>shape</code>
   </td>
   <td>Expected result (using wordlist <code>words_sorted.txt</code>)
   </td>
  </tr>
  <tr>
   <td><code>[1, -1, -1, -1, 0, -1]</code>
   </td>
   <td><code>['congeed', 'nutseed', 'outfeed', 'strolld']</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, -1, -1, 0, -1, 1]</code>
   </td>
   <td><code>['axseeds', 'brogger', 'cheddar', 'coiffes', 'crommel', 'djibbah', 'droller', 'fligger', 'frigger', 'frogger', 'griffes', 'grogger', 'grommet', 'prigger', 'proffer', 'progger', 'proller', 'quokkas', 'stiffen', 'stiffer', 'stollen', 'swigger', 'swollen', 'twiggen', 'twigger']</code>
   </td>
  </tr>
  <tr>
   <td><code>[0, 1, -1, 1]</code>
   </td>
   <td><code>['aargh', 'eeler', 'eemis', 'eeten', 'oopak', 'oozes', 'sstor']</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 1, 1, 1, 1, 1, 1]</code>
   </td>
   <td><code>['aegilops']</code>
   </td>
  </tr>
</table>


Motivated students can take on as an extra challenge to find the shape of length _n _- 1 that matches the largest number of words, for the possible values of _n_ from 3 to 20. Alternatively, try to count how many possible shapes of length _n _- 1 do not match any words of length _n_ at all. What is the shortest possible shape that does not match any words?


## **Running median of three** 


```
def running_median_of_three(items):
```


Given a list of `items` that are all guaranteed to be integers, create and return a new list whose first two elements are the same as they were in original `items`, after which each element equals the **median** of the three elements in the original list ending in that position. (If two out of these three elements are equal, then that element is the median of those three.)


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[5, 2, 9, 1, 7, 4, 6, 3, 8]</code>
   </td>
   <td><code>[5, 2, 5, 2, 7, 4, 6, 4, 6]</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3, 4, 5, 6, 7]</code>
   </td>
   <td><code>[1, 2, 2, 3, 4, 5, 6]</code>
   </td>
  </tr>
  <tr>
   <td><code>[3, 5, 5, 5, 3]</code>
   </td>
   <td><code>[3, 5, 5, 5, 5]</code>
   </td>
  </tr>
  <tr>
   <td><code>[22, 77]</code>
   </td>
   <td><code>[22, 77]</code>
   </td>
  </tr>
  <tr>
   <td><code>[42]</code>
   </td>
   <td><code>[42]</code>
   </td>
  </tr>
</table>





## **The card that wins the trick**


```
def winning_card(cards, trump=None):
```


Playing cards are again represented as tuples of `(rank, suit)` as in the <code>[cardproblems.py](https://github.com/ikokkari/PythonExamples/blob/master/cardproblems.py)</code> example program. In <strong>trick taking</strong> games such as <strong>whist</strong> or <strong>bridge</strong>, four players each play one card from their hand to the trick, putting their cards in the clockwise order from the player who plays first into the trick. The winner of the trick is determined by the following rules:



1. If one or more cards of the `trump` suit have been played to the trick, the trick is won by the highest ranking trump card, regardless of the other cards played.
2. If no trump cards have been played to the trick, the trick is won by the highest card of the suit of the first card played to the trick. Cards of any other suits, regardless of their rank, are powerless to win that trick.
3. Ace is the highest card in each suit.

Note that the order in which the cards are played to the trick greatly affects the outcome of that trick, since the first card played in the trick determines which suits have the potential to win the trick in the first place. Return the winning card for the list of `cards` played to the trick.


<table>
  <tr>
   <td><code>cards</code>
   </td>
   <td><code>trump</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[('three', 'spades'), ('ace', 'diamonds'), ('jack', 'spades'), ('eight', 'spades')]</code>
   </td>
   <td><code>None</code>
   </td>
   <td><code>('jack', 'spades')</code>
   </td>
  </tr>
  <tr>
   <td><code>[('ace', 'diamonds'), ('ace', 'hearts'), ('ace', 'spades'), ('two', 'clubs')]</code>
   </td>
   <td><code>'clubs'</code>
   </td>
   <td><code>('two', 'clubs')</code>
   </td>
  </tr>
  <tr>
   <td><code>[('two', 'clubs'), ('ace', 'diamonds'), ('ace', 'hearts'), ('ace', 'spades')]</code>
   </td>
   <td><code>None</code>
   </td>
   <td><code>('two', 'clubs')</code>
   </td>
  </tr>
</table>





## **Boustrophedon** 


```
def create_zigzag(rows, cols, start = 1):
```


This function creates **a list of lists** that represents a two-dimensional **grid** with the given number of `rows` and `cols`. This grid should contain the integers counting the `rows * cols` numbers from `start` in ascending order. However, similar to the way an ox slowly plows a field somewhere back in ancient Greece, the elements of every odd-numbered row must be listed in descending order. However you choose to enforce that discipline is up to you.

In all of the examples of the following table, the keyword parameter `start` is not given and therefore equals one. But your function must work correctly for arbitrary values of `start`.


<table>
  <tr>
   <td><code>rows</code>
   </td>
   <td><code>cols</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>3</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>[[1, 2, 3, 4, 5], [10, 9, 8, 7, 6], [11, 12, 13, 14, 15]]</code>
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>[[1], [2], [3], [4], [5], [6], [7], [8], [9], [10]]</code>
   </td>
  </tr>
  <tr>
   <td><code>4</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>[[1, 2], [4, 3], [5, 6], [8, 7]]</code>
   </td>
  </tr>
</table>





## **That's some mighty tall words, stranger**


```
def word_height(words, word):
```


The length of a word is easy enough to define and compute by counting its characters. For this problem, we shall define the **height** of the given `word` with a **recursive** rule that depends on how well the word can be split into two non empty pieces `left` and `right` that are also themselves words that could be split further into smaller pieces. 

Some words such as `'economite'` or `'vivid'` cannot be split into `left` and `right` pieces that are also words. The height of all such "atomic" words equals one, the base case of this recursion. Otherwise, the height of the word equals one plus the maximum of the heights of its `left` and `right` pieces. For example, `'blamability'` splits into two words `'blam'` and `'ability'` that are both atomic, so its height equals two. If a word can be split into `left` and `right` pieces in several ways (such as how `'illogician'` can be split into `'il'` and `'logician'`, or into `'illogic'` and `'ian'`), you must use the split that produces the largest height.

Since the list of `words` is sorted, you should use **binary search** (as implemented as the function `bisect_left` in the `bisect` module) to quickly determine whether some piece is a legitimate word. Be mindful of pieces that start with two or more letters `z`, though.


<table>
  <tr>
   <td><code>word</code>
   </td>
   <td>Expected result (using the wordlist <code>words_sorted.txt</code>)
   </td>
  </tr>
  <tr>
   <td><code>'chukker'</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
  <tr>
   <td><code>'asteroid'</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>'pedicured'</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
  <tr>
   <td><code>'quadrants'</code>
   </td>
   <td><code>4</code>
   </td>
  </tr>
  <tr>
   <td><code>'napthalin'</code>
   </td>
   <td><code>5</code>
   </td>
  </tr>
  <tr>
   <td><code>'undepressed'</code>
   </td>
   <td><code>7</code>
   </td>
  </tr>
</table>


Curiously enough, the tallest word found inside `words_sorted.txt` with a height of ten is [a well-known joke word](https://en.wikipedia.org/wiki/Antidisestablishmentarianism_(word)) that is also a solution of a classic recreational linguistics puzzle.



*   


## **Multidimensional knight moves**


```
def knight_jump(knight, start, end):
```


An ordinary [chess knight](https://en.wikipedia.org/wiki/Knight_(chess)) on a two-dimensional board of squares can make an "L-move" into up to eight possible neighbours. However, we can generalize the entire chessboard into _k_ dimensions from just the puny two. A natural extension of the knight's move to keep moves symmetric with respect to these dimensions is to define the possible moves as some _k_-tuple of **strictly decreasing** nonnegative integer offsets. Each one of these _k_ offsets must be used for exactly one dimension of your choice during the move, either as a positive or a negative version.

For example, the three-dimensional `(4, 3, 1)`-knight makes its way by first moving four steps along any one of the three dimensions, then three steps along any other dimension, and then one step along the remaining dimension, whichever dimensions that was. Once the knight has stepped along some dimension, it can no longer step along that same dimension within the same move. These steps are considered to be performed together as a single jump that does not visit or is blocked by any of the intermediate squares. Given the `start` and `end` positions as _k_-tuples of integer coordinates, determine whether the `knight` can get from `start` to `end` in one jump.


<table>
  <tr>
   <td><code>knight</code>
   </td>
   <td><code>start</code>
   </td>
   <td><code>end</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>(2, 1)</code>
   </td>
   <td><code>(12, 10)</code>
   </td>
   <td><code>(11, 12)</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>(7, 5, 1)</code>
   </td>
   <td><code>(15, 11, 16)</code>
   </td>
   <td><code>(8, 12, 11)</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>(9, 7, 6, 5, 1)</code>
   </td>
   <td><code>(19, 12, 14, 11, 20)</code>
   </td>
   <td><code>(24, 3, 20, 11, 13)</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
</table>


A quick combinatorial calculation reveals that exactly _k_! * 2<sup><em>k</em></sup> possible neighbours are reachable in a single move, assuming that none of these moves takes the knight outside the board. In this notation, the ordinary chess knight is a `(2, 1)`-knight that can reach 2! * 2<sup>2</sup> = 2 * 4 = 8 possible neighbouring squares in one jump. A 6-dimensional knight reaches a whopping 6! * 2<sup>6</sup> = 46080 different neighbours in one jump. Since the number of moves emanating from each position to its neighbours grows exponentially with respect to _k_, pretty much everything ends up being close to pretty much everything else in high-dimensional spaces. (Density in general is known to have both advantages and disadvantages in all walks of life.)




## **Sevens rule, zeros drool**


```
def seven_zero(n):
```


Seven is considered a lucky number in Western cultures, whereas [zero is what nobody wants to be](https://vimeo.com/6748255). To bring these two opposites briefly together, let us look at positive integers that start with some solid sequence of sevens, followed by some (possibly empty) solid sequence of zeros. For example, 7, 77777, 7700000, 77777700, or 70000000000000000. A surprising theorem proves that for any positive integer `n`, there exist infinitely many integers of such seven-zero form that are divisible by `n`. This function should find and return the **smallest** such seven-zero integer.

This exercise is about efficiently generating all numbers of the constrained form of sevens and zeros in strictly ascending order to guarantee finding the smallest working such number. This is perhaps best done with two nested loops. The outer loop should iterate through the number of digits `d` in the current number. The inner loop should iterate through all possible ways for `k` from one to `d` to create a number that begins with a solid block of `k` sevens, followed by a solid block of `d-k` zeroes. This could be written as a **generator** that `yield`s such numbers. When most of the work is done by this generator, the `seven_zero` function itself is short and sweet.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>17</code>
   </td>
   <td><code>7777777777777777</code>
   </td>
  </tr>
  <tr>
   <td><code>42</code>
   </td>
   <td><code>7770</code>
   </td>
  </tr>
  <tr>
   <td><code>101</code>
   </td>
   <td><code>7777</code>
   </td>
  </tr>
  <tr>
   <td><code>103</code>
   </td>
   <td><code>7777777777777777777777777777777777</code>
   </td>
  </tr>
  <tr>
   <td><code>2**50</code>
   </td>
   <td><code>700000000000000000000000000000000000000000000000000</code>
   </td>
  </tr>
  <tr>
   <td><code>12345</code>
   </td>
   <td>(a behemoth that consists of a total of 822 sevens, followed by a single zero)
   </td>
  </tr>
</table>


This problem is adapted from the excellent [MIT Open Courseware](https://ocw.mit.edu/index.htm) online textbook "_Mathematics for Computer Science_" ([PDF link](https://courses.csail.mit.edu/6.042/spring18/mcs.pdf) to the 2018 version for anybody interested) that, like so many other **non-constructive** combinatorial proofs, uses the [pigeonhole principle](https://en.wikipedia.org/wiki/Pigeonhole_principle) to prove that _some_ solution must exist for any integer `n`, but provides no clue about the exact value of such solution. Also as proven in that same textbook, whenever `n` is not divisible by either 2 or 5, the smallest such number will always consist of some solid sequence of sevens with no zero digits after them. This can speed up the search by an order of magnitude for such friendly values of `n`.


## **Fulcrum**


```
def can_balance(items):
```


Each element in `items` is considered to be a [physical weight](https://en.wikipedia.org/wiki/Mass_versus_weight), and guaranteed to be a positive integer. Your task is to find and return a **fulcrum** position in this list of weights so that when balanced on that position, the total [torque](https://en.wikipedia.org/wiki/Torque) of the items to the left of that position equals the total torque of the items to the right of that position. The item on the fulcrum is assumed to be centered symmetrically on the fulcrum, and does not participate in the torque calculation.

In physics, the torque of an item with respect to the fulcrum equals its weight times distance from the fulcrum. If a fulcrum position exists, return that position, otherwise return -1 to indicate that the given `items` cannot be balanced, at least not without rearranging them.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[6, 1, 10, 5, 4]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>[10, 3, 3, 2, 1]</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
  <tr>
   <td><code>[7, 3, 4, 2, 9, 7, 4]</code>
   </td>
   <td><code>-1</code>
   </td>
  </tr>
  <tr>
   <td><code>[42]</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
</table>


The problem of finding the fulcrum position when rearranging elements is allowed would be an interesting but a far more advanced problem normally suitable for a third year computer science course. However, this algorithm could be built in an effective (albeit not as efficient) **brute force** fashion around this function by using the generator `permutations` in the Python standard library module <code>[itertools](https://docs.python.org/3/library/itertools.html)</code> to try out all possible permutations in an outer loop until you find one permutation that works. In fact, quite a few problems of this style can be solved with this "<strong>generate and test</strong>" approach without the <strong>backtracking</strong> algorithms from third year courses.

(Yes, I pretty much wrote this problem only to get to say "fulcrum". What a cool word. And you know what is another really cool word? "[Phalanx](https://en.wikipedia.org/wiki/Phalanx)". That one even seems like something that could be turned into an interesting computational problem about lists of lists... and that is the _crux_ of that entire matter.)




## **Last man standing** 


```
def josephus(n, k):
```


In the ancient times back "🎶 when men were made of iron and their ships were made of wood 🎶", as seen in "300", "Spartacus", "Game of Thrones" and other [similar historical docudramas](https://www.overthinkingit.com/2011/06/28/blood-tits-and-scowling/) of swords and sandals, a group of [zealots](https://en.wikipedia.org/wiki/Zealots) (yes, _literally_) was surrounded by the overwhelming Roman enemy. To avoid capture and slow humiliating death by crucifixion, in their righteous zeal these men chose to commit mass suicide in a way that prevented any one of them from changing his mind. The zealots arranged themselves in a circle and used lots to choose a step size `k`. Starting from the first man, they repeatedly count `k` men ahead and quickly kill that man, removing his corpse from this grim circle. (Being normal people instead of computer scientists, they always start counting from one instead of zero, the concept of which didn't even exist for them back then anyway!)

This deadly game of eeny-meeny-miney-moe continues until only one man remains, expected to honorably fall on his own sword to join his fallen brothers. [Josephus](https://en.wikipedia.org/wiki/Josephus_problem) would very much prefer to be this last man since he has other ideas of surviving. Help him and his secret confederate survive with a function that, given `n` and `k`, returns the list of the execution order so that these men know which places let them be the last two survivors to walk away from this grim circle.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>k</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>4</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>[1, 2, 3, 4]</code>
   </td>
  </tr>
  <tr>
   <td><code>4</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>[2, 4, 3, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>[3, 6, 9, 2, 7, 1, 8, 5, 10, 4]</code>
   </td>
  </tr>
  <tr>
   <td><code>8</code>
   </td>
   <td><code>7</code>
   </td>
   <td><code>[7, 6, 8, 2, 5, 1, 3, 4]</code>
   </td>
  </tr>
  <tr>
   <td><code>30</code>
   </td>
   <td><code>4</code>
   </td>
   <td><code>[4, 8, 12, 16, 20, 24, 28, 2, 7, 13, 18, 23, 29, 5, 11, 19, 26, 3, 14, 22, 1, 15, 27, 10, 30, 21, 17, 25, 9, 6]</code>
   </td>
  </tr>
  <tr>
   <td><code>1000</code>
   </td>
   <td><code>99</code>
   </td>
   <td>(a sequence of 1000 elements whose first five elements are <code>[99, 198, 297, 396, 495]</code> and last five elements are <code>[183, 762, 380, 966, 219]</code>)
   </td>
  </tr>
</table>





## **Longest palindrome substring**


```
def longest_palindrome(text):
```


A string is said to be a **palindrome** if it reads the same both forward and backward, for example `'racecar'`. Given `text`, find and return the longest consecutive substring inside `text` that is a palindrome. If multiple palindromes exist with the same largest length, return the leftmost one.

Note that since you are looking for the longest palindrome, of course you should loop through these substrings in descending order of length, and the substrings of same length should be looped through left to right. This way you can simply return the first palindrome substring that you find, safe in the knowledge that the `text` does not contain any longer palindromic substrings.


<table>
  <tr>
   <td><code>text</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'saippuakauppias'</code>
   </td>
   <td><code>'saippuakauppias'</code>
   </td>
  </tr>
  <tr>
   <td><code>'abaababaaabbabaababababaa'</code>
   </td>
   <td><code>'aababababaa'</code>
   </td>
  </tr>
  <tr>
   <td><code>'xxzxxracecar'</code>
   </td>
   <td><code>'racecar'</code>
   </td>
  </tr>
  <tr>
   <td><code>'xyxracecaryxy'</code>
   </td>
   <td><code>'racecar'</code>
   </td>
  </tr>
</table>


The straightforward implementation of the trivial algorithm "loop through all possible substrings and check which ones are palindromes, remembering the longest palindrome that you have seen" should pass the test in a reasonably short time. However, as a curiosity, the real challenge in this problem is making this function at least an order of magnitude faster than this, which is why you might meet this one in a later course on algorithmic techniques. The students who are already piqued in this kind of algorithmic tweaking might want to check out the Wikipedia page "[Longest Palindromic Substring](https://en.wikipedia.org/wiki/Longest_palindromic_substring)", as the **dynamic programming** technique used to solve this problem is a key to solving a thousand other problems of similar combinatorial nature of **overlapping recursive subproblems**.


## **All your fractions are belong to base**


```
def group_and_skip(n, out, ins):
```


A pile of `n` identical coins lies on the table. In each move, the coins in the currently remaining pile are arranged into groups of exactly `out` coins each, where `out` is a positive integer greater than one. The `n % out` leftover coins that did not make a complete group of `out` elements are taken aside and recorded. From each complete group of `out` coins taken out, exactly `ins` coins are put back into the pile, and the rest of the coins of that group are discarded aside. Repeat this until the pile becomes empty, which must eventually happen whenever `out > ins`. Return a list that tells how many coins were taken aside in each step.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>out</code>
   </td>
   <td><code>ins</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>123456789</code>
   </td>
   <td><code>10</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>[9, 8, 7, 6, 5, 4, 3, 2, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>987654321</code>
   </td>
   <td><code>1000</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>[321, 654, 987]</code>
   </td>
  </tr>
  <tr>
   <td><code>255</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>[1, 1, 1, 1, 1, 1, 1, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>81</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>[1, 3, 2, 0, 4, 3]</code>
   </td>
  </tr>
  <tr>
   <td><code>10**9</code>
   </td>
   <td><code>13</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>[12, 1, 2, 0, 7, 9, 8, 11, 6, 8, 10, 5, 8, 3]</code>
   </td>
  </tr>
</table>


As you can see in the first three rows, this method produces the digits of `n` in base `out` in reverse order. So this entire setup turns out to be the cleverly disguised algorithm to construct the representation of integer `n` in base `out`. However, an improvement over the standard algorithm for such base conversion is that this version works not only for integer bases, but allows any fraction `out/ins` that satisfies `out > ins` and `gcd(out, ins) == 1` to be used as a base! For example, the familiar integer 42 would be written as 323122 in base 4/3.

(Yes, fractional bases are an actual thing. Take a deep breath to think about the implications, and then imagine trying to do your real world basic arithmetic in such a system. That certainly would have been some "[New Math](https://www.youtube.com/watch?v=UIKGV2cTgqA)" for the frustrated parents in the sixties for whom balancing their checkbooks in the familiar base ten was already an exasperating ordeal!)


## **Recamán's sequence** 


```
def recaman(n):
```


Compute and return the first `n` terms of the [Recamán's sequence](http://mathworld.wolfram.com/RecamansSequence.html), starting from the term _a<sub>1</sub>_ = 1. See the linked definition for this sequence as it is defined on [Wolfram Mathworld](http://mathworld.wolfram.com/).

Note how the definition for the current next element depends on whether a particular number is already part of the previously generated part of the sequence.  To allow your function to execute in a speedy fashion even when generating a sequence that contains millions of elements, you should use a `set` to keep track of which values are already part of the previously generated sequence. This way you can generate each element in constant time, instead of having to iterate through the entire previously generated list like some "[Shlemiel](http://wiki.c2.com/?ShlemielThePainter)" would have done. Your better technique that pays for time savings by using more memory can create this list arbitrarily far in linear time, and should therefore be fast even for millions of elements.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>[1, 3, 6, 2, 7, 13, 20, 12, 21, 11]</code>
   </td>
  </tr>
  <tr>
   <td><code>1000000</code>
   </td>
   <td>(a list of million elements whose last five elements are <code>[2057162, 1057165, 2057163, 1057164, 2057164]</code> )  
   </td>
  </tr>
</table>





## **Blocks in pyramid**


```
def pyramid_blocks(n, m, h):
```


Pyramids have fascinated humanity throughout the ages. They are basically the only feasible structure that can be built with the construction materials and the, ahem, _labour-intensive_ civil engineering techniques of antiquity, yet robust enough to survive the ravages of time while maintaining their aura of mystery through that entire timeline. This problem deals with ideal toy pyramids made of uniform cubic blocks, so that rather than the Egyptian style, they resemble more the [ancient Mesoamerican](https://en.wikipedia.org/wiki/Chichen_Itza#/media/File:Chichen_Itza_3.jpg) pyramids, although about only as much as the proverbial model of a spherical horse running in a vacuum is useful for successful off-track betting on the ponies.

Our toy pyramids are built from layers, each layer made out of a rectangle of identical cubic blocks. The top layer of the pyramid consists of `n` rows and `m` columns of such blocks, so there are `n * m` blocks in that top layer. The layer immediately below each layer contains one more row and one more column, all the way to the bottom layer of the pyramid. If the entire pyramid consists of `h` such layers, how many blocks does this pyramid contain in total?

This problem could be solved in a straightforward **brute force** fashion by simply looping through the `h` layers and adding up all the blocks along the way in each layer. With the current version of the automated tester, solving the test cases would take roughly one minute to complete, since all of these three arguments can get pretty big. However, with the application of some sums and discrete math can come up with an **analytical closed form formula** for the result and compute the answers _much_ faster that way. If you have taken such courses, you might want to derive this formula yourself (as a quick sanity check, note that the correct formula must necessarily be symmetric with respect to `n` and `m`), or use the resources on the Internet to find out how to solve such summation formulas. ([Wolfram Alpha](https://www.wolframalpha.com) is one pretty good free system to try out, and not only for the purposes of computer programming courses.)


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>m</code>
   </td>
   <td><code>h</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>6</code>
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>10</code>
   </td>
   <td><code>570</code>
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>11</code>
   </td>
   <td><code>12</code>
   </td>
   <td><code>3212</code>
   </td>
  </tr>
  <tr>
   <td><code>100</code>
   </td>
   <td><code>100</code>
   </td>
   <td><code>100</code>
   </td>
   <td><code>2318350</code>
   </td>
  </tr>
  <tr>
   <td><code>10**6</code>
   </td>
   <td><code>10**6</code>
   </td>
   <td><code>10**6</code>
   </td>
   <td><code>2333331833333500000</code>
   </td>
  </tr>
</table>



## **Count growlers**


```
def count_growlers(animals):
```


Let the strings `'cat'` and `'dog'` denote that kind of animal facing left, and `'tac'` and `'god'` denote that same kind of animal facing right. Each individual animal, regardless of its species, growls if it sees more dogs than cats to the direction that the animal is facing. Given a list of such `animals`, return the count of how many of these animals are growling.


<table>
  <tr>
   <td><code>animals</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>['cat', 'dog']</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>['god', 'cat', 'cat', 'tac', 'tac', 'dog', 'cat', 'god']</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>['dog', 'cat', 'dog', 'god', 'dog', 'god', 'dog', 'god', 'dog', 'dog', 'god', 'god', 'cat', 'dog', 'god', 'cat', 'tac']</code>
   </td>
   <td><code>11</code>
   </td>
  </tr>
  <tr>
   <td><code>['god', 'tac', 'tac', 'tac', 'tac', 'dog', 'dog', 'tac', 'cat', 'dog', 'god', 'cat', 'dog', 'cat', 'cat', 'tac']</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
</table>


I admit that I was high as a kite back when I originally thought up this problem, at least high enough to perceive the letter `'t'` as a tail of a happy cat held up high, and `'d'` as the snout and stand-up ears of a curious dog, perhaps some kind of spitz or a similar breed. (Yeah, good luck trying to unsee that now.) And yet for some reason, this problem is somehow more tricky than it would initially seem in a fair, predictable and just world, and does not seem to conveniently allow itself to be twisted into a clean and Pythonic solution. (Readers are welcome to suggest their best solutions to the author, should they come up with nifty ways to solve this problem.)




## **Bulgarian solitaire**


```
def bulgarian_solitaire(piles, k):
```


You are given a row of `piles` of pebbles, all identical, and a positive integer `k` so that the total number of pebbles in these piles equals `k*(k+1)//2`, the **arithmetic sum** formula that equals the sum of positive integers from `1` to `k`. As if an apt metaphor for the bleak daily life behind the Iron Curtain, all pebbles are identical and you don't get any choice in your moves. Each move picks up exactly one pebble from each pile (even if that makes the pile vanish), and creates a new pile from the resulting handful. For example, starting with `piles = [7, 4, 2, 1, 1]`, the first move turns this into `[6, 3, 1, 5]`. The next move turns that into `[5, 2, 4, 4]`, which then turns into `[4, 1, 3, 3, 4]`, and so on.

This function should count how many moves are needed to convert the given initial `piles` into the **goal state** where each number from `1` to `k` appears as the size of **exactly one pile**, and return that count. These numbers from `1` to `k` may appear in any order inside the list, not necessarily sorted. Note that applying the basic move to this goal state simply ends right back in that same state. (In mathematical lingo, the goal state is a **fixed point** of the transformation function between these configurations of pebbles.)


<table>
  <tr>
   <td><code>piles</code>
   </td>
   <td><code>k</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[1, 4, 3, 2]</code>
   </td>
   <td><code>4</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>[8, 3, 3, 1]</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>9</code>
   </td>
  </tr>
  <tr>
   <td><code>[10, 10, 10, 10, 10, 5]</code>
   </td>
   <td><code>10</code>
   </td>
   <td><code>74</code>
   </td>
  </tr>
  <tr>
   <td><code>[3000, 2050]</code>
   </td>
   <td><code>100</code>
   </td>
   <td><code>7325</code>
   </td>
  </tr>
  <tr>
   <td><code>[2*i-1 for i in range(171, 0, -2)]</code>
   </td>
   <td><code>171</code>
   </td>
   <td><code>28418</code>
   </td>
  </tr>
</table>


 

This problem hails from the [Martin Gardner](https://en.wikipedia.org/wiki/Martin_Gardner) column "Bulgarian Solitaire and Other Seemingly Endless Tasks", where it was used as an example of a while-loop where it is not immediately obvious that this loop will always eventually reach its goal and terminate, analogous to the behaviour of the Collatz 3_x_+1 problem that we saw back in <code>[mathproblems.py](https://github.com/ikokkari/PythonExamples/blob/master/mathproblems.py)</code>. However, unlike in that still famously open problem, a combinatorial proof shows that this game can never get stuck, but will terminate from any starting configuration after at most <em>k</em>(<em>k</em>-1)/2 steps.


## **Scylla or Charybdis?**


```
def scylla_or_charybdis(moves, n):
```


This problem was inspired by the article "[A Magical Answer to the 80-Year-Old Puzzle](https://www.wired.com/2015/10/a-magical-answer-to-an-80-year-old-puzzle/)" in [Quanta Magazine](https://www.quantamagazine.org/). Thanks to your recent cunning stunts, your [nemesis](https://en.wikipedia.org/wiki/Nemesis) in life is trapped inside a devious game where, for a refreshing change from the usual way of things, you get to be the Final Boss. (Everyone is the hero in their own story until they become a villain in somebody else's, after all.) This final level is a one-dimensional video game platform that reaches `n-1` steps from its center to both directions. At each end of this platform exactly `n` steps away from the center, your two lethal friends [Scylla and Charybdis](https://en.wikipedia.org/wiki/Between_Scylla_and_Charybdis) are licking their lips in anticipation of a tasty morsel.

Your nemesis starts at the center of this platform. She must immediately commit to her entire sequence of future `moves`, given to your function as a string made of characters `'+'` ("🎶 just a step to the ri-i-i-i-ight" 🎶) and `'-'` (move one step to the left).  Of course your nemesis will choose some series of moves that keeps her safely on the platform. Your **adversarial** task is to find a positive integer `k` so that executing every `k`:th step of `moves` (so this subsequence starts from position `k-1` and includes every `k`:th element from then on) makes your nemesis fall into one of the two possible dooms `n` steps away from the center.

This function should find and return the value of `k` that makes your hated nemesis fall off the platform in the smallest number of moves, to ensure that his allies who by now have surely become aware of his predicament won't have time to come rescue him. To ensure the existence of some solution, the given sequence of `moves` is guaranteed to end with the **suffix** of 2_n_ consecutive steps to the right, so `k=1` will always work whenever no larger step size leads to the faster doom. If several values of `k` work equally well, your function should return the smallest such `k`.


<table>
  <tr>
   <td><code>moves</code>
   </td>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'-++--++-++++'</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>'--++++---+-++-+++++++++++'</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>5</code>
   </td>
  </tr>
  <tr>
   <td><code>'+-++---+-+-++-+++----+++-++-+---+--++++++++++'</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>7</code>
   </td>
  </tr>
  <tr>
   <td><code>'+--++---+-++-+++------+++++---++-+--+++-+--++-++-++-+-++++++++++++++++++'</code>
   </td>
   <td><code>9</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
</table>





## **Arithmetic progression**


```
def arithmetic_progression(items):
```


An **arithmetic progression** is a numerical sequence so that the **stride** between each two consecutive elements is constant throughout the sequence. For example, `[4, 8, 12, 16, 20]` is an arithmetic progression of length 5, starting from the value 4 with a stride of 4.

Given a non-empty list `items` of positive integers in strictly ascending order, find and return the longest arithmetic progression whose all values exist somewhere in that sequence. Return the answer as a tuple `(start, stride, n)` of the values that define the progression. To ensure unique results to facilitate automated testing, if there exist several progressions of the same length, this function should return the one with the lowest `start`. If several progressions of equal length emanate from the lowest `start`, return the progression with the smallest `stride`.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[42]</code>
   </td>
   <td><code>(42, 0, 1)</code>
   </td>
  </tr>
  <tr>
   <td><code>[2, 4, 6, 7, 8, 12, 17]</code>
   </td>
   <td><code>(2, 2, 4)</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 36, 49, 50, 70, 75, 98, 104, 138, 146, 148, 172, 206, 221, 240, 274, 294, 367, 440]</code>
   </td>
   <td><code>(2, 34, 9)</code>
   </td>
  </tr>
  <tr>
   <td><code>[2, 3, 7, 20, 25, 26, 28, 30, 32, 34, 36, 41, 53, 57, 73, 89, 94, 103, 105, 121, 137, 181, 186, 268, 278, 355, 370, 442, 462, 529, 554, 616, 646, 703]</code>
   </td>
   <td><code>(7, 87, 9)</code>
   </td>
  </tr>
  <tr>
   <td><code>range(1000000)</code>
   </td>
   <td><code>(0, 1, 1000000)</code>
   </td>
  </tr>
</table>


(Bridge players like to distinguish between "best result possible" and "best possible result", which are not the same thing. In the same spirit, can you see the difference between the deceptively similar concepts "leftmost of longest" and "longest of leftmost" in this problem?)


## **Tukey's ninther**


```
def tukeys_ninthers(items):
```


Back in the day when computers were far slower and had a lot less RAM for our programs to burrow into, special techniques were necessary to achieve many [things that are trivial today with a couple of lines of code](https://prog21.dadgum.com/29.html). In this spirit, "[Tukey's ninther](https://www.johndcook.com/blog/2009/06/23/tukey-median-ninther/)" is an **approximation algorithm** from the seventies to quickly find some value that should be "reasonably close" to the **median element** of the given unsorted list. For the purposes of this problem, the median element of the list is defined to be the element that would end up in the middle position if that list were sorted. This makes the median unambiguous, regardless of the elements and their multiplicities. Note again that your function is not tasked to find the actual median, but the element that Tukey's ninther algorithm would return as its approximation of that actual median.

Tukey's algorithm splits the list into triplets of three elements, and finds the median element for each triplet. These medians-of-three are then collected into a new list that this same operation is applied to, until only one element remains. For simplicity, your function can assume that the length of `items` is always some power of three. In the following table, each row contains the result produced by applying one round of Tukey's algorithm to the list in the next row.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[15]</code>
   </td>
   <td><code>15</code>
   </td>
  </tr>
  <tr>
   <td><code>[42, 7, 15]</code>
   </td>
   <td><code>15</code>
   </td>
  </tr>
  <tr>
   <td><code>[99, 42, 17, 7, 1, 9, 12, 77, 15]</code>
   </td>
   <td><code>15</code>
   </td>
  </tr>
  <tr>
   <td><code>[55, 99, 131, 42, 88, 11, 17, 16, 104, 2, 8, 7, 0, 1, 69, 8, 93, 9, 12, 11, 16, 1, 77, 90, 15, 4, 123]</code>
   </td>
   <td><code>15</code>
   </td>
  </tr>
</table>


Tukey's algorithm is extremely **robust**, as can be appreciated by giving it a bunch of randomly shuffled lists of distinct numbers to operate on (these distinct numbers can even come from arbitrary distributions and scales, since this algorithm is **comparison-based** and never performs any arithmetic between elements), and plotting the histogram of results to admire how heavily centered around the actual median this distribution ends up being. (For example, the median of the last example list in the above table is really 15, pinky swear for grownup realsies.) Even better, if all `items` are distinct and the length of the list is some power of three, the returned result can never be from the true top or bottom third of the sorted elements, thus eliminating all risk of using some funky outlier as your approximation for the median.


## **Whenever they zig, you gotta zag**


```
def is_zigzag(n):
```


A positive integer `n` is called a **zigzag number** (also called "alternating number" in some material on combinatorics) if the series of differences between its consecutive digits strictly alternates between positive and negative steps. The step from the first digit to the second may be either positive or negative. The function should determine whether `n` is a zigzag number.

In the negative examples in the table below, the part of the number that violates the zigzag property is highlighted in red.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>7</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>25391</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>90817263545463728185</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>16329</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>104175101096715</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>49573912009</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
</table>





## **Crack the crag**


```
def crag_score(dice):
```


**Crag** (see [the Wikipedia page](https://en.wikipedia.org/wiki/Crag_(dice_game)) for the scoring table needed in this problem) is a dice game similar to the more popular games of [Yahtzee](https://en.wikipedia.org/wiki/Yahtzee) and [Poker dice](https://en.wikipedia.org/wiki/Poker_dice) in style and spirit, but with much simpler combinatorics of roll value calculation due to this game using only three dice. Players repeatedly roll three dice and assign the resulting patterns to **scoring categories** so that once some roll has been assigned to a category, that category is considered to have been spent and cannot be used again for any future roll. These tactical choices between safety and risk-taking give this game a little bit more tactical flair on top of merely relying on Lady Luck when rolling the bones.

Given the list of pips of the three dice of the first roll, this function should compute and return the highest possible score available when **all categories of the scoring table are still available for you to choose from**, and all that matters is maximizing the score for this first roll. Note that the examples on the Wikipedia page show the score that some dice would score **in that particular category**, which is not necessarily even close to the maximum score in principle attainable with that roll. For example, `[1, 1, 1]` used in the category "Ones" would indeed score only three points in that category, whereas that same roll would score a whopping 25 points in the category "Three of a kind". (The later problem "Optimal crag score" near the end of this collection makes you recursively assign multiple rolls into distinct categories to maximize the total score.)

This problem ought to be a straightforward exercise in if-else ladders combined with simple sequence management. Your function should be swift and sure to return the correct answer for every one of the 6<sup>3</sup> = 216 possible argument value combinations. However, surely you will design your if-else structures to handle entire equivalence classes of pip combinations in a single step, so that your entire ladder consists of _far_ fewer than 216 separate steps...

 


<table>
  <tr>
   <td><code>dice</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3]</code>
   </td>
   <td><code>20</code>
   </td>
  </tr>
  <tr>
   <td><code>[4, 5, 1]</code>
   </td>
   <td><code>5</code>
   </td>
  </tr>
  <tr>
   <td><code>[3, 3, 3]</code>
   </td>
   <td><code>25</code>
   </td>
  </tr>
  <tr>
   <td><code>[4, 5, 4]</code>
   </td>
   <td><code>50</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 1, 1]</code>
   </td>
   <td><code>25</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 1, 2]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
</table>





## **Three summers ago**


```
def three_summers(items, goal):
```


Given a list of positive integer `items` guaranteed to contain at least three elements with all of its **elements in sorted ascending order**, determine whether there **exist precisely three** separate `items` that together add up to the given positive integer `goal`, no more and no less.

You could, of course, solve this problem with three nested loops to go through all possible ways to choose three elements from `items`, checking for each triple whether it adds up to the `goal`. However, this approach would get rather slow as the number of elements in the list increases, and of course the automated tester used to grade this function will make those lists larger just to make such solutions reveal themselves with their excessive consumption of running time.

Since `items` are known to be sorted, better technique will find the answer significantly faster. See the new example function `two_summers` in <code>[listproblems.py](https://github.com/ikokkari/PythonExamples/blob/master/listproblems.py)</code> to quickly find two elements from the given sorted list that together add up to the given <code>goal</code>. You can simply use this function as a subroutine to speed up your search for three summing elements, once you realize that the list contains three elements that add up to <code>goal</code> if and only if it contains some element <code>x</code> so that the remaining list contains two elements that add up to <code>goal-x</code>. 


<table>
  <tr>
   <td>items
   </td>
   <td>goal
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[10, 11, 16, 18, 19]</code>
   </td>
   <td><code>40</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>[10, 11, 16, 18, 19]</code>
   </td>
   <td><code>41</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3]</code>
   </td>
   <td><code>6</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
</table>


For the general **subset sum problem** used as an example of inherently exponential branching recursion in that lecture, the question of whether the given list of integers contains some subset of _k_ elements that together add up to given `goal` can be determined by trying each element `x` in turn as the first element of this subset, and then recursively determining whether the remaining elements after `x` contain some subset of _k_ - 1 elements that adds up to `goal-x`. 


## **Count distinct sums and products**


```
def count_distinct_sums_and_products(items):
```


Given a list of distinct integers guaranteed to be in sorted ascending order, count how many different numbers can be constructed by either adding or multiplying two numbers from this list. (The two chosen numbers do not need to be distinct.) For example, given the list `[2, 3, 4]`, this function would return 8, since there exist a total of eight distinct numbers that can be constructed this way from 2, 3 and 4. Some of them can be constructed in several different ways, such as 6 that is either 4 + 2 = 3 + 3 = 3 * 2, but the number 6 should still be counted only once in the total tally.

This problem can be solved by simply looping through all possible ways to choose `a` and `b` from the given list. Maintain a `set` that remembers all sums `a+b` and products `a*b` that you have seen so far, and after having iterated through all possible such pairs, return the final size of that set.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[]</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>[42]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>[2, 3, 5, 7, 9, 11]</code>
   </td>
   <td><code>29</code>
   </td>
  </tr>
  <tr>
   <td><code>[x for x in range(1, 101)]</code>
   </td>
   <td><code>2927</code>
   </td>
  </tr>
  <tr>
   <td><code>[x*x for x in range(1, 101)]</code>
   </td>
   <td><code>6533</code>
   </td>
  </tr>
</table>


(This problem was inspired by the article "[How a Strange Grid Reveals Hidden Connections Between Simple Numbers](https://www.quantamagazine.org/the-sum-product-problem-shows-how-addition-and-multiplication-constrain-each-other-20190206/)" in _Quanta Magazine_.)


## **Sum of two squares**


```
def sum_of_two_squares(n):
```


Some positive integers can be expressed as a sum of two squares of some positive integers greater than zero. For example, 74 = 49 + 25  = 7<sup>2 </sup>+ 5<sup>2</sup>. This function should find and return a tuple of two positive integers whose squares together add up to `n`, or return `None` if the parameter `n` cannot be broken into a sum of two squares.

To facilitate the automated testing, the returned tuple must present the larger of its two numbers first. Furthermore, if some integer can be broken down to a sum of squares in different ways, return the breakdown that maximizes the larger number. For example, the number 85 allows two representations 7<sup>2</sup> + 6<sup>2</sup> and 9<sup>2</sup> + 2<sup>2</sup> , of which this function must therefore return `(9, 2)`.

The technique of **two approaching indices** that start from the beginning and end of a sequence, respectively, and approach each other until they meet somewhere, used in the function `two_summers` in one of our class examples, is directly applicable to this problem. In this problem, these indices crawl towards each other only one step at the time, whereas in **binary search**, one index would jump halfway towards the other one in every round.


<table>
  <tr>
   <td>n
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>1</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>(1, 1)</code>
   </td>
  </tr>
  <tr>
   <td><code>50</code>
   </td>
   <td><code>(7, 1)</code>
   </td>
  </tr>
  <tr>
   <td><code>8</code>
   </td>
   <td><code>(2, 2)</code>
   </td>
  </tr>
  <tr>
   <td><code>11</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
  <tr>
   <td><code>123**2 + 456**2</code>
   </td>
   <td><code>(456, 123)</code>
   </td>
  </tr>
  <tr>
   <td><code>55555**2 + 66666**2</code>
   </td>
   <td><code>(77235, 39566)</code>
   </td>
  </tr>
</table>





## **Carry on Pythonista**


```
def count_carries(a, b):
```


Two positive integers `a` and `b` can be added together to produce their sum with the usual integer column-wise addition algorithm that we all learned back when we were but wee little children. Instead of the sum `a+b` that the language could compute for you anyway, this problem asks you to count how many times there is a **carry** of one into the next column caused by adding the two digits in the current column (possibly including the carry from the previous column), and return that total count. Your function should be efficient even when the parameter integers `a` and `b` are enormous enough to require thousands of digits to write down.

Hint: to extract the lowest digit of a positive integer `n`, use the expression `n % 10`. To extract all other digits except the lowest one, use the expression `n // 10`. You can use these simple integer arithmetic operations to execute the steps of the column-wise integer addition so that you don't care about the actual result of the addition, but only the carry that is produced in each column.


<table>
  <tr>
   <td><code>a</code>
   </td>
   <td><code>b</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>99999</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>5</code>
   </td>
  </tr>
  <tr>
   <td><code>11111111111</code>
   </td>
   <td><code>2222222222</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>123456789</code>
   </td>
   <td><code>987654321</code>
   </td>
   <td><code>9</code>
   </td>
  </tr>
  <tr>
   <td><code>2**100</code>
   </td>
   <td><code>2**100 - 1</code>
   </td>
   <td><code>13</code>
   </td>
  </tr>
  <tr>
   <td><code>3**1000</code>
   </td>
   <td><code>3**1000 + 1</code>
   </td>
   <td><code>243</code>
   </td>
  </tr>
</table>





## **Expand positive integer intervals**


```
def expand_intervals(intervals):
```


An **interval** of consecutive positive integers can be succinctly described as a string that contains its first and last value, inclusive, separated by a minus sign. (This problem is restricted to positive integers so that there can be no ambiguity between the minus sign character used as a separator and an actual unary minus sign in front of an integer.) For example, the interval that contains the numbers 5, 6, 7, 8, 9 could be more concisely described as `'5-9'`. Multiple intervals can be described together by separating their descriptions with commas. An interval that contains only one value is given as only that value.

Given a string that contains one or more such comma-separated interval descriptions, guaranteed  to be given in sorted ascending order and never overlap with each other, create and return the list that contains all the integers contained inside these intervals. In solving this problem the same as any other problems, it is always best not to reinvent the wheel, but check out first whether the string objects have useful methods to make your job easier...


<table>
  <tr>
   <td><code>intervals</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>''</code>
   </td>
   <td><code>[]</code>
   </td>
  </tr>
  <tr>
   <td><code>'42'</code>
   </td>
   <td><code>[42]</code>
   </td>
  </tr>
  <tr>
   <td><code>'4-6,10-12,16'</code>
   </td>
   <td><code>[4, 5, 6, 10, 11, 12, 16]</code>
   </td>
  </tr>
  <tr>
   <td><code>'1,3-9,12-14,9999'</code>
   </td>
   <td><code>[1, 3, 4, 5, 6, 7, 8, 9, 12, 13, 14, 9999]</code>
   </td>
  </tr>
</table>





## **Collapse positive integer intervals** 


```
def collapse_intervals(items):
```


This function is the inverse of the previous question of expanding positive integer intervals. Given a nonempty list of positive integers that is guaranteed to be in sorted ascending order, create and return the unique description string where every maximal sublist of consecutive integers has been condensed to the notation `first-last`. If some maximal sublist consists of a single integer, it must be included in the result string just by itself without the minus sign separating it from the now redundant `last` number. Make sure that the string returned by your function does not contain any whitespace characters, and does not have a redundant comma in the end.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 4, 6, 7, 8, 9, 10, 12, 13]</code>
   </td>
   <td><code>'1-2,4,6-10,12-13'</code>
   </td>
  </tr>
  <tr>
   <td><code>[42]</code>
   </td>
   <td><code>'42'</code>
   </td>
  </tr>
  <tr>
   <td><code>[3, 5, 6, 7, 9, 11, 12, 13]</code>
   </td>
   <td><code>'3,5-7,9,11-13'</code>
   </td>
  </tr>
  <tr>
   <td><code>[]</code>
   </td>
   <td><code>''</code>
   </td>
  </tr>
  <tr>
   <td><code>range(1, 1000001)</code>
   </td>
   <td><code>'1-1000000'</code>
   </td>
  </tr>
</table>





## **Reversing the reversed**


```
def reverse_reversed(items):
```


Create and return a new list that contains the `items` in reverse, but so that whenever each item is itself a list, its elements are also reversed. This reversal of sublists must keep going on all the way down, no matter how deep the nesting of these lists, so you ought to use recursion to solve this problem. The base case handles any argument that is not a list. When the `items` parameter is a list ([use the Python function type or the isinstance operator to check this](https://stackoverflow.com/questions/1549801/what-are-the-differences-between-type-and-isinstance)), recursively reverse the elements that this nested list contains. (List comprehensions might come handy in doing this part of the problem.)

Note that this function must create and return a new list to represent the result, and should not rearrange or otherwise mutate the contents of the original list. This same principle should apply to all functions that receive a list argument. In your own programs that compute some important list that you pass to some function from the standard library, isn't it nice not to have to worry that that function might silently modify the contents of your list? 


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[1, [2, 3, 4, 'yeah'], 5]</code>
   </td>
   <td><code>[5, ['yeah', 4, 3, 2], 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>[[[[[[1, 2]]]]]]</code>
   </td>
   <td><code>[[[[[[2, 1]]]]]]</code>
   </td>
  </tr>
  <tr>
   <td><code>[42, [99, [17, [33, ['boo!']]]]]</code>
   </td>
   <td><code>[[[[['boo!'], 33], 17], 99], 42]</code>
   </td>
  </tr>
</table>





## **Count word dominators**


```
def count_word_dominators(words):
```


If you already solved the earlier `count_dominators` problem, you might notice that even though the problem was originally stated for lists of integers, the logic of domination did not depend on this fact in any way. As long as the individual elements can be compared with each other for order, the Pythonic spirit of **duck typing** allows the very same `count_dominators` function to handle a list of strings just as smoothly as it would handle a list of integers! For example, the function call `count_dominators(['dog', 'emu', 'cat', 'bee'])` would return 3, since `'emu'`, `'cat'` and `'bee'` dominate all words coming after them in the list when using the **lexicographic order** comparison. If your `count_dominators` does not pass this hurdle, try to rewrite it to contain no baked-in assumptions about elements being specifically integers.

However, things become more interesting if we define domination between words of equal length with a rule that says that for a word to dominate another word, for more than half of the positions the character in the first word is **strictly greater** than the corresponding character in the other word. Note also the intentional wording "_more_ than half" to break ties between words of even length such as `'aero'` and `'tram'`, so that no two words can ever both dominate each other.


<table>
  <tr>
   <td><code>words</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>['sky', 'yat']</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>['pun', 'ean', 'fiz', 'coe']</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>['toph', 'prow', 'koku', 'okey']</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>['ufo', 'hny', 'hun', 'ess', 'kab']</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>['cagit', 'libri', 'sured', 'birls', 'golgi', 'shank', 'bailo', 'senex', 'cavin', 'ajiva', 'babby']</code>
   </td>
   <td><code>5</code>
   </td>
  </tr>
</table>





## **Duplicate digit bonus**


```
def duplicate_digit_bonus(n):
```


Some people ascribe deep significance to numerical coincidences, so that consecutive repeated digits or other low description length patterns, such as a digital clock blinking `11:11`, seem special and personal to them. Such people then naturally find numbers with repeated digits to be more valuable and important than all the ordinary and pedestrian numbers without any obvious pattern. For example, getting into a taxicab flashing an exciting number such as 1234 or 6969 would be far more instagrammable than a more pedestrian taxicab adorned with some dull number such as 1729.

Assume that some such person assign a meaningfulness score to every positive integer so that every maximal block of `k` consecutive digits with `k > 1` scores `10**(k-2)` points for that block. A block of two digits scores one point, three digits score ten points, four digits score a hundred points, and so on. However, just to make this more interesting, there is also a special rule in effect that if this block of digits is at the lowest end of the number, that block scores twice as many points as it would in any other position. Given a positive integer `n > 0`, this function should compute and return its meaningfulness score as the sum of its individual block scores.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>43333</code>
   </td>
   <td><code>200</code>
   </td>
  </tr>
  <tr>
   <td><code>2223</code>
   </td>
   <td><code>10</code>
   </td>
  </tr>
  <tr>
   <td><code>777777777</code>
   </td>
   <td><code>20000000</code>
   </td>
  </tr>
  <tr>
   <td><code>3888882277777731</code>
   </td>
   <td><code>11001</code>
   </td>
  </tr>
  <tr>
   <td><code>2111111747111117777700</code>
   </td>
   <td><code>12002</code>
   </td>
  </tr>
  <tr>
   <td><code>9999997777774444488872222</code>
   </td>
   <td><code>21210</code>
   </td>
  </tr>
  <tr>
   <td><code>1234**5678</code>
   </td>
   <td><code>15418</code>
   </td>
  </tr>
</table>





## **Nearest smaller element**


```
def nearest_smaller(items):
```


Given a list of integer `items`, create and return a new list of the same length but where each element has been replaced with the nearest element in the original list whose value is smaller. If no smaller elements exist because that element is the minimum of the original list, the element in the result list should remain as that same minimum element.

If there exist smaller elements equidistant in both directions, you must resolve this by using the smaller of these two elements. This again makes the expected results unique for every possible argument value, which is necessary for having this problem to be part of our  automated testing framework.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[42, 42, 42]</code>
   </td>
   <td><code>[42, 42, 42]</code>
   </td>
  </tr>
  <tr>
   <td><code>[42, 1, 17]</code>
   </td>
   <td><code>[1, 1, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>[42, 17, 1]</code>
   </td>
   <td><code>[17, 1, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>[6, 9, 3, 2]</code>
   </td>
   <td><code>[3, 3, 2, 2]</code>
   </td>
  </tr>
  <tr>
   <td><code>[5, 2, 10, 1, 13, 15, 14, 5, 11, 19, 22]</code>
   </td>
   <td><code>[2, 1, 1, 1, 1, 13, 5, 1, 5, 11, 19]</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 3, 5, 7, 9, 11, 10, 8, 6, 4, 2]</code>
   </td>
   <td><code>[1, 1, 3, 5, 7, 9, 8, 6, 4, 2, 1]</code>
   </td>
  </tr>
</table>





## **Interesting, intersecting**


```
def squares_intersect(s1, s2):
```


A square on the two-dimensional plane can be defined as a tuple `(x, y, r)` where `(x, y)` are the coordinates of its **bottom left corner** and `r` is the length of the side of the square. Given two squares as tuples `(x1, y1, r1)` and `(x2, y2, r2)`, this function should determine whether these two squares **intersect**, that is, their **areas** have at least one point in common, even if that one point is merely the shared corner point when these two squares are placed kitty corner. This function **should not contain any loops or list comprehensions of any kind**, but should compute the result using only integer comparisons and conditional statements.

This problem showcases an idea that comes up with some problems of this nature; that it is actually easier to determine that the two squares do **not** intersect, and then just negate that answer. Two squares do not intersect if one of them ends in the horizontal direction before the other one begins, or if the same thing happens in the vertical direction. (This technique generalizes from rectangles lying on the flat two-dimensional plane to not only three-dimensional cuboids, but to hyperboxes of arbitrary high dimensions.)


<table>
  <tr>
   <td><code>s1</code>
   </td>
   <td><code>s2</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>(2, 2, 3)</code>
   </td>
   <td><code>(5, 5, 2)</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>(3, 6, 1)</code>
   </td>
   <td><code>(8, 3, 5)</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>(8, 3, 3)</code>
   </td>
   <td><code>(9, 6, 8)</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>(5, 4, 8)</code>
   </td>
   <td><code>(3, 5, 5)</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>(10, 6, 2)</code>
   </td>
   <td><code>(3, 10, 7)</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>(3000, 6000, 1000)</code>
   </td>
   <td><code>(8000, 3000, 5000)</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>(5*10**6, 4*10**6, 8*10**6)</code>
   </td>
   <td><code>(3*10**6, 5*10**6, 5*10**6)</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
</table>



## 


## **Keep doubling**


```
def double_until_all_digits(n, giveup=1000):
```


Given a positive integer `n`, keep multiplying it by two until the current number contains each of the digits 0 to 9 at least once. These ten digits can appear inside the number in any order and any number of times. Return the number of doublings that were necessary to reach this goal. If the number has been multiplied `giveup` times without reaching the goal, this function should give up and return -1.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>giveup</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>1</code>
   </td>
   <td><code>1000</code>
   </td>
   <td><code>68</code>
   </td>
  </tr>
  <tr>
   <td><code>1234567890</code>
   </td>
   <td><code>1000</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>555</code>
   </td>
   <td><code>10</code>
   </td>
   <td><code>-1</code>
   </td>
  </tr>
</table>





## **That's enough of you!**


```
def remove_after_kth(items, k=1):
```


Given a list of `items`, some of which may be duplicated, create and return a new list that is otherwise the same as `items`, but only up to `k` occurrences of each element are kept, and all occurrences of that element after those first `k` are discarded.

Hint: loop through the `items`, maintaining a dictionary that remembers how many times you have already seen each element. Update this count as you go, and append each element to the `result` list only if its count is still at most equal to `k`.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td><code>k</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[42, 42, 42, 42, 42, 42, 42]</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>[42, 42, 42]</code>
   </td>
  </tr>
  <tr>
   <td><code>['tom', 42, 'bob', 'bob', 99, 'bob', 'tom', 'tom', 99]</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>['tom', 42, 'bob', 'bob', 99, 'tom', 99]</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3, 4, 5, 4, 3, 2, 1, 2, 3, 4, 5, 4, 3, 2, 1]</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>[1, 2, 3, 4, 5]</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3, 4, 5, 4, 3, 2, 1, 2, 3, 4, 5, 4, 3, 2, 1, 2, 3, 4, 5]</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>[1, 2, 3, 4, 5, 4, 3, 2, 1, 2, 3, 4, 5, 1, 5]</code>
   </td>
  </tr>
  <tr>
   <td><code>[42, 42, 42, 99, 99, 17]</code>
   </td>
   <td><code>0</code>
   </td>
   <td><code>[]</code>
   </td>
  </tr>
</table>


Note the counterintuitive and yet completely legitimate edge case of `k==0` that has the well defined and unambiguously correct answer of an empty list! Once again, an often missed and yet very important part of becoming a programmer is learning to see zero as a number...


## **Count consecutive summers**


```
def count_consecutive_summers(n):
```


Positive integers can be expressed as sums of **consecutive** positive integers in various ways. For example, 42 can be expressed as such a sum in four different ways: (a) 3 + 4 + 5 + 6 + 7 + 8 + 9,  (b) 9 + 10 + 11 + 12, (c) 13 + 14 + 15 and (d) 42. As the last solution (d) shows, any positive integer can always be trivially expressed as a **singleton sum** that consists of that integer alone. Given a positive integer `n`, determine how many different ways it can be expressed as a sum of consecutive positive integers, and return that count.

The count of how many different ways a positive integer _n_ can be represented as a sum of consecutive integers is also called its [politeness](https://en.wikipedia.org/wiki/Polite_number), and can be alternatively computed by counting how many odd divisors that number has. However, note that the linked Wikipedia definition includes only sums that consist of at least two components, so according to their definition, the politeness of 42 equals 3 due to its odd divisors being 3, 7 and 21.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>42</code>
   </td>
   <td><code>4</code>
   </td>
  </tr>
  <tr>
   <td><code>99</code>
   </td>
   <td><code>6</code>
   </td>
  </tr>
  <tr>
   <td><code>92</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
</table>


Powers of two are therefore the least polite of all numbers. As a small exercise in combinatorics, how would you concisely characterize the "most polite" numbers that have more ways to be represented as sums of consecutive integers than any number lower than them?


## **McCulloch's second machine**


```
def mcculloch(digits):
```


[Esoteric programming languages](https://en.wikipedia.org/wiki/Esoteric_programming_language) should be appreciated as works of conceptual performance art. These tar pits are not designed to be any sort of practical programming tools, but demonstrate tongue-in-cheek how some deceptively simple (or merely cleverly disguised as such) mechanism unexpectedly grants its wielder the power of universal computation. Introduced by [Raymond Smullyan](https://en.wikipedia.org/wiki/Raymond_Smullyan) in one of his collections of clandestine brain teasers on logic and computability, [McCulloch's second machine](https://esolangs.org/wiki/McCulloch%27s_second_machine) is a **string rewriting** system that receives a string of `digits` between one and nine. The rewrite rule applied to the rest of the `digits` ( denoted by `X`) depends on the first digit. Rule 2 is applied to `X` whereas rules 3 to 5 are applied to `Y = mcculloch(X)`. The function should return `None` whenever `X` or `Y` is `None`.


<table>
  <tr>
   <td>Form of <code>digits</code>
   </td>
   <td>Expected result
   </td>
   <td>(computational operation)
   </td>
  </tr>
  <tr>
   <td><code>2X</code>
   </td>
   <td><code>X</code>
   </td>
   <td>quoting
   </td>
  </tr>
  <tr>
   <td><code>3X</code>
   </td>
   <td><code>Y + '2' + Y</code>
   </td>
   <td>concatenation with separator mark
   </td>
  </tr>
  <tr>
   <td><code>4X</code>
   </td>
   <td><code>Y[::-1]</code>
   </td>
   <td>reversal
   </td>
  </tr>
  <tr>
   <td><code>5X</code>
   </td>
   <td><code>Y + Y</code>
   </td>
   <td>concatenation
   </td>
  </tr>
  <tr>
   <td>anything else
   </td>
   <td><code>None</code>
   </td>
   <td>undefined
   </td>
  </tr>
</table>



<table>
  <tr>
   <td><code>digits</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'329'</code>
   </td>
   <td><code>'929'</code>
   </td>
  </tr>
  <tr>
   <td><code>'53231'</code>
   </td>
   <td><code>'3123131231'</code>
   </td>
  </tr>
  <tr>
   <td><code>'4524938'</code>
   </td>
   <td><code>'83948394'</code>
   </td>
  </tr>
  <tr>
   <td><code>'343424859355'</code>
   </td>
   <td><code>'4859355248593552485935524859355'</code>
   </td>
  </tr>
  <tr>
   <td><code>'433342717866'</code>
   </td>
   <td><code>'7178662717866271786627178662717866271786627178662717866'</code>
   </td>
  </tr>
</table>





## **That's enough for you!**


```
def first_preceded_by_smaller(items, k=1):
```


Given a list of `items`, find and return the value of the first element for which at least `k` smaller elements precede that element in `items`. If no such element exists inside the list, this function should return `None`.

Note that the required `k` smaller items do not need to be consecutive immediate predecessors of the current item, but they can be any `k` items before the current element.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td><code>k</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[4, 4, 5, 6]</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>5</code>
   </td>
  </tr>
  <tr>
   <td><code>[42, 99, 16, 55, 7, 32, 17, 18, 73]</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>18</code>
   </td>
  </tr>
  <tr>
   <td><code>[42, 99, 16, 55, 7, 32, 17, 18, 73]</code>
   </td>
   <td><code>8</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
  <tr>
   <td><code>['bob', 'carol', 'tina', 'alex', 'jack', 'emmy', 'tammy', 'sam', 'ted']</code>
   </td>
   <td><code>4</code>
   </td>
   <td><code>'tammy'</code>
   </td>
  </tr>
  <tr>
   <td><code>[9, 8, 7, 6, 5, 4, 3, 2, 1, 10]</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>10</code>
   </td>
  </tr>
  <tr>
   <td><code>[42, 99, 17, 3, 12]</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
</table>





## **Pull down your neighbours**


```
def eliminate_neighbours(items):
```


Given the sequence of integer `items` that are guaranteed to be some **permutation** of positive integers from 1 to `n` where `n` is the length of the list, find the smallest number among those that still remain in the list, and remove from the list both that number and whichever of its current immediate neighbours is larger. The function should repeat this basic operation until the largest number in the original list gets eliminated. Return the number of removal operations that were needed to achieve this goal.

For example, given the list `[5, 2, 1, 4, 6, 3]`, the operation would remove element `1` and its current larger neighbour `4`, resulting in the list `[5, 2, 6, 3]`. Applied again, that operation would remove `2` and its current larger neighbour `6`, thus reaching the goal in two steps.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[1, 6, 4, 2, 5, 3]</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
  <tr>
   <td><code>[8, 3, 4, 1, 7, 2, 6, 5]</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>[8, 5, 3, 1, 7, 2, 6, 4]</code>
   </td>
   <td><code>4</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]</code>
   </td>
   <td><code>5</code>
   </td>
  </tr>
  <tr>
   <td><code>range(1, 10001)</code>
   </td>
   <td><code>5000</code>
   </td>
  </tr>
  <tr>
   <td><code>[1000] + list(range(1, 1000))</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
</table>


The bottleneck of the running time is computing the new list that results from removing two elements from it. Try to think up some way to solve this problem that alleviates this expensive operation. Note again that the problem specification guarantees that the list elements cannot be just whatever, but are precisely the integers from 1 to _n_, which allows your function to loop through these elements in ascending order...


## **What do you hear, what do you say?**


```
def count_and_say(digits):
```


Given a string of digits that is guaranteed to contain only digit characters from `'0123456789'`, read that string "out loud" by saying how many times each digit occurs consecutively in the current bunch of digits, and then return the string of digits that you just said out loud. For example, given the digits `'222274444499966'`, we would read it out loud as "four twos, one seven, five fours, three nines, two sixes" for the result string `'4217543926'`.


<table>
  <tr>
   <td><code>digits</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'333388822211177'</code>
   </td>
   <td><code>'4338323127'</code>
   </td>
  </tr>
  <tr>
   <td><code>'11221122'</code>
   </td>
   <td><code>'21222122'</code>
   </td>
  </tr>
  <tr>
   <td><code>'123456789'</code>
   </td>
   <td><code>'111213141516171819'</code>
   </td>
  </tr>
  <tr>
   <td><code>'777777777777777'</code>
   </td>
   <td><code>'157'</code>
   </td>
  </tr>
  <tr>
   <td><code>''</code>
   </td>
   <td><code>''</code>
   </td>
  </tr>
  <tr>
   <td><code>'1'</code>
   </td>
   <td><code>'11'</code>
   </td>
  </tr>
</table>


This particular operation, executed on a list of items instead of a string, is usually called "[run-length encoding](https://en.wikipedia.org/wiki/Run-length_encoding)". When applied to a string of numerical digits, it leads to a cute little puzzle. Given the empty string, this function returns an empty string, and given the string `'22'` that contains two twos, this function returns the same string `'22'`. Do there exist any other digit strings that are **fixed points** of this function, so that the function returns the exact same string as result? Either construct another such digit string, or prove that no such string can exist.

(Interested students can also check out the related construct of the [Kolakoski sequence](https://en.wikipedia.org/wiki/Kolakoski_sequence) where only the lengths of each consecutive block of digits is stored, but not the actual digits.)


## **Bishops on a binge**


```
def safe_squares_bishops(n, bishops):
```


A generalized _n_-by-_n_ chessboard has some number of [bishops](https://en.wikipedia.org/wiki/Bishop_(chess)), each bishop represented as a tuple `(row, column)` of the row and the column of the square that bishop stands on. Same way as in the earlier version of this problem for rooks whose moves were axis-aligned, the rows and columns are numbered from 0 to _n_ - 1. A chess bishop covers all squares that are on the same **diagonal** with that bishop arbitrarily far into any of the four diagonal compass directions. Given the board size `n` and the list of `bishops` on that board, count the number of safe squares that are not covered by any bishop.

To quickly check whether two squares `(r1, c1)` and `(r2, c2)` are reachable from each other in one diagonal move, use `abs(r1-r2) == abs(c1-c2)` to determine whether the horizontal distance between those squares equals their vertical distance, which is both necessary and sufficient for those squares to lie on the same diagonal. This way you don't need to write the essentially identical block of logic separately for each of the four diagonal directions, but this one test handles all four diagonals in one swoop.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>bishops</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>[]</code>
   </td>
   <td><code>100</code>
   </td>
  </tr>
  <tr>
   <td><code>4</code>
   </td>
   <td><code>[(2, 3), (0, 1)]</code>
   </td>
   <td><code>11</code>
   </td>
  </tr>
  <tr>
   <td><code>8</code>
   </td>
   <td><code>[(1, 1), (3, 5), (7, 0), (7, 6)]</code>
   </td>
   <td><code>29</code>
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>[(1, 1)]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>6</code>
   </td>
   <td><code>[(0, 0), (1, 1), (2, 2), (3, 3), (4, 4), (5, 5)]</code>
   </td>
   <td><code>18</code>
   </td>
  </tr>
  <tr>
   <td><code>100</code>
   </td>
   <td><code>[(row, (row*row) % 100) for row in range(100)]</code>
   </td>
   <td><code>6666</code>
   </td>
  </tr>
</table>





## **Up for the count**


```
def counting_series(n):
```


The **counting series** `1234567891011121314151617181920212223`...  is an infinitely long string of digits made up of all positive integers written in ascending order without any separators between the individual numbers. This function should return the integer digit that is in the position `n` of the counting series, with positions starting from 0 as usual in computing.

Of course, the automated tester will try out values of `n` large enough that anybody trying to solve this problem by explicitly constructing the counting series as a string would run out of time and space long before receiving the answer. Instead, you should observe that the structure of this infinite sequence is quite straightforward, as it starts with 9 single-digit numbers, followed by 90 two-digit numbers, followed by 900 three-digit numbers, and so on. Such a predictable structure allows you to skip over prefixes of this series in exponentially widening leaps and bounds, until you reach the position `n` and find out the digit that is waiting for you there.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>0</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
  <tr>
   <td><code>100</code>
   </td>
   <td><code>5</code>
   </td>
  </tr>
  <tr>
   <td><code>10000</code>
   </td>
   <td><code>7</code>
   </td>
  </tr>
  <tr>
   <td><code>10**100</code>
   </td>
   <td><code>6</code>
   </td>
  </tr>
</table>


Out of curiosity, has the digit that was waiting for you in position `n` been waiting for you there since the dawn of time? Or did the answer come to existence the moment that somebody first posed this problem, or only when somebody solved this problem up to the position `n`? What is your intuitive stance on this thorny and ancient philosophical issue well above this author's pay grade? Do all mathematical structures and the answers to all possible questions about these structures already exist in the static and timeless Platonic plane of perfect forms for us to discover by means of reason? Or are at least some mathematical truths lazily created by social agreement so that the nature of their existence is similar to that of fictional characters such as Donald Duck and James Bond, woven into existence by the arbitrary decisions of their creators?




## **Revorse the vewels**


```
def reverse_vowels(text):
```


Given a `text` string, create and return a new string constructed by finding all its **vowels** (for simplicity, in this problem vowels are the letters found in the string `'aeiouAEIOU'`) and reversing their order, while keeping all other characters exactly as they were in their original positions. However, to make the result look prettier, the capitalization of each moved vowel must be the same as that of the vowel that was originally in the target position. For example, reversing the vowels of `'Ilkka'` should produce `'Alkki'` instead of `'alkkI'`.

Along with many possible other ways to perform this square dance, one straightforward way to reverse the vowels starts with collecting all vowels of `text` into a separate list, and initializing the `result` to an empty string. After that, iterate through all positions of the original `text`. Whenever the current position contains a vowel, take one from the end of the list of the vowels. Convert that vowel to either upper- or lowercase depending on the case of the vowel that was originally in that position, and append it to `result`. Otherwise, append the character from the same position of the original `text` to the `result` as it were.


<table>
  <tr>
   <td><code>text</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'Revorse the vewels'</code>
   </td>
   <td><code>'Reverse the vowels'</code>
   </td>
  </tr>
  <tr>
   <td><code>'Ilkka Markus Kokkarinen'</code>
   </td>
   <td><code>'Elkki Markos Kukkaranin'</code>
   </td>
  </tr>
  <tr>
   <td><code>'Hello world'</code>
   </td>
   <td><code>'Hollo werld'</code>
   </td>
  </tr>
  <tr>
   <td><code>'abcdefghijklmnopqrstuvwxyz'</code>
   </td>
   <td><code>'ubcdofghijklmnepqrstavwxyz'</code>
   </td>
  </tr>
  <tr>
   <td><code>'This is Computer Science I!'</code>
   </td>
   <td><code>'This es Cempiter Scuonci I!'</code>
   </td>
  </tr>
</table>



## 


## **Everybody come do the Scrooge Shuffle**


```
def spread_the_coins(piles, left, right):
```


Identical coins have been placed on the integer number line so that the position `i` initially contains `piles[i]` coins for positions `i` that are inside `piles`, that is,  `0 &lt;= i &lt; len(piles)`. All other positions on the integer line both ways towards the positive and negative infinity initially contain zero coins. After this, any position that contains at least `left+right` coins is **unstable**. As long as some position `i` is unstable, exactly `left` coins from position `i` spill into the predecessor position `i-1`, and exactly `right` coins spill into the successor position `i+1`.

The unique stable end state of this back-and-forth dance is guaranteed to be reached after a finite number of steps, regardless of the order in which unstable positions are processed in the interim. To speed up this process, whenever a pile contains `k*(left+right)` coins, you can scoop `k*left` coins into the predecessor and `k*right` coins into the successor pile in one move. This function should return this stable terminal position as tuple `(start, coins)` where `start` is the leftmost position that ends up with at least one coin spilling in (the first pile is initially in the zero position). The list of `coins` shows the coins in each final position, spanning the positions from `start` up to whatever position ends up being the highest non-empty position.

The brand new difficulty of this problem within this collection is handling the negative positions during computation, and finding some unstable position quickly to process. Yes, Kemosabe, Python lists can indeed be **prepended** from front, but that operation will be inefficient since it has to make room for the new element with a linear-time reorganization. But ordinary lists are basically special cases of **dictionaries** with indices restricted to natural numbers... 


<table>
  <tr>
   <td><code>piles</code>
   </td>
   <td><code>left</code>
   </td>
   <td><code>right</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[20]</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>(-4, [3, 1, 4, 2, 4, 2, 4])</code>
   </td>
  </tr>
  <tr>
   <td><code>[8, 4]</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>(-2, [3, 1, 3, 3, 2])</code>
   </td>
  </tr>
  <tr>
   <td><code>[111, 12, 12]</code>
   </td>
   <td><code>19</code>
   </td>
   <td><code>6</code>
   </td>
   <td><code>(-6, [19, 13, 13, 13, 13, 13, 10, 23, 18])</code>
   </td>
  </tr>
</table>





## **Calkin-Wilf sequence**


```
def calkin_wilf(n)
```


The nodes of the [Calkin-Wilf tree](https://en.wikipedia.org/wiki/Calkin%E2%80%93Wilf_tree), when read in **level order** so that the elements in each level are read from left to right, produce the linear sequence of all possible **positive rational numbers**. Almost as if by magic, this construction guarantees every positive integer fraction to appear exactly once in this sequence. Even more wonderfully, this construction makes every rational number to appear in its lowest reduced form! To perform the following calculations, you should `import` the data types `Fraction` and <code>[deque](https://docs.python.org/3.3/library/collections.html#collections.deque)</code> from the  <code>[fractions](https://docs.python.org/3/library/fractions.html)</code> and <code>[collections](https://docs.python.org/3.3/library/collections.html)</code> modules.

Your function should return the `n`:th element of this sequence. First, create a new instance of `deque` and `append` the first fraction `1/1` to "prime the pump", so to speak, to initiate the production of the values of this sequence. Then repeat the following procedure `n` times. Pop the fraction currently in front of the queue using the `deque` method `popleft`, extract its numerator and denominator `p` and `q`, and push the two new fractions `p/(p+q)` and `(p+q)/q` to the back of the queue, in this order. Return the fraction object that was popped in the final round. 


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>3/5</code>
   </td>
  </tr>
  <tr>
   <td><code>1000</code>
   </td>
   <td><code>11/39</code>
   </td>
  </tr>
  <tr>
   <td><code>100000</code>
   </td>
   <td><code>127/713</code>
   </td>
  </tr>
</table>


(Actually, once you reach the position `n//2+1`, the queue already contains the result you need, so you can stop pushing in any new values and that way save some significant memory.)


## **Hippity hoppity, abolish loopity**


```
def frog_collision_time(frog1, frog2):
```


A frog moving on the infinite two-dimensional grid of integers is represented as a 4-tuple of the form `(sx, sy, dx, dy)` where `(sx, sy)` is its **starting position** at time zero, and `(dx, dy)` is its constant **direction vector** for each hop. Time advances in discrete integer steps 0, 1, 2, 3, ... so that each frog makes one hop exactly at every tick of the clock. At time `t`, the position of that frog is given by the formula `(sx + t*dx, sy + t*dy)` that can be nimbly evaluated even for large `t`.

Given two frogs `frog1` and `frog2` that are guaranteed to initially stand on different squares, return the time when both frogs hop into the same square. If these two frogs never simultaneously arrive at the same square, return `None`.

**This function should not contain any loops whatsoever**. The result should be calculated using conditional statements and integer arithmetic. Perhaps the best way to get cracking is to first solve a simpler version of this problem with one-dimensional frogs restricted to hop along the one-dimensional line of integers. Once you get that function working correctly, including all its possible edge cases, use it to solve for `t` separately for the _x_- and _y_-dimensions in the original problem. Combine your two one-dimensional answers into your final answer.


<table>
  <tr>
   <td><code>frog1</code>
   </td>
   <td><code>frog2</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>(0, 0, 0, 2)</code>
   </td>
   <td><code>(0, 10, 0, 1)</code>
   </td>
   <td><code>10</code>
   </td>
  </tr>
  <tr>
   <td><code>(10, 10, -1, 0)</code>
   </td>
   <td><code>(0, 1, 0, 1)</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
  <tr>
   <td><code>(0, -7, 1, -1)</code>
   </td>
   <td><code>(-9, -16, 4, 2)</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>(-28, 9, 9, -4)</code>
   </td>
   <td><code>(-26, -5, 8, -2)</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
  <tr>
   <td><code>(-28, -6, 5, 1)</code>
   </td>
   <td><code>(-56, -55, 9, 8)</code>
   </td>
   <td><code>7</code>
   </td>
  </tr>
  <tr>
   <td><code>(620775675217287, -1862327025651882, -3, 9)</code>
   </td>
   <td><code>(413850450144856, 2069252250724307, -2, -10)</code>
   </td>
   <td><code>206925225072431</code>
   </td>
  </tr>
</table>





## **Double trouble**


```
def double_trouble(items, n):
```


Suppose, if just for the sake of argument, that the following operation is repeated `n` times for the given list of `items`: remove the first element, and append that same element twice to the end of `items`. Which one of the `items` would be removed and copied in the last operation performed?

Sure, this problem could be finger-quotes "solved" by actually performing that operation `n` times, but the point of this exercise is to come up with an analytical solution to compute the result much faster than actually going through that whole rigmarole. To gently nudge you towards thinking in symbolic and analytical solutions, the automated tester is designed so that anybody trying to **brute force** their way through this problem by performing all `n` operations one by one for real will run out of time and memory long before receiving the answer, as will the entire universe.

To come up with this analytical solution, tabulate some small cases (you can implement the brute force function to compute these) and try to spot the pattern that generalizes to arbitrarily large values of `n`. You can again also check out [Wolfram Alpha](https://www.wolframalpha.com) or similar systems capable of manipulation of symbolic formulas to simplify combinatorial and summing formulas.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>['joe', 'bob', 42]</code>
   </td>
   <td><code>10</code>
   </td>
   <td><code>'joe'</code>
   </td>
  </tr>
  <tr>
   <td><code>[17, 42, 99]</code>
   </td>
   <td><code>1000</code>
   </td>
   <td><code>17</code>
   </td>
  </tr>
  <tr>
   <td><code>[17, 42, 99]</code>
   </td>
   <td><code>10**20</code>
   </td>
   <td><code>99</code>
   </td>
  </tr>
  <tr>
   <td><code>['only', 'the', 'number', 'of', 'items', 'matters']</code>
   </td>
   <td><code>10**1000</code>
   </td>
   <td><code>'the'</code>
   </td>
  </tr>
</table>


The reason to pay attention in the discrete math and combinatorics courses is learning to derive symbolic solutions to problems of this nature so that you don't have to brute force their answers in a time that would be prohibitively long to ever be feasible. We met this very same theme back in the question that asked how many blocks make up the given pyramid shape...


## **Nearest polygonal number**


```
def nearest_polygonal_number(n, s):
```


Any positive integer _s_ > 2 defines an infinite sequence of **_s_-gonal numbers** whose _i_:th element is given by the formula ((_s _- 2) _i<sup>2</sup>_ - (_s _- 4) _i_) / 2, as explained on the Wikipedia page "[Polygonal Number](https://en.wikipedia.org/wiki/Polygonal_number)". In this formula, positions start from 1, not 0, and we use the letter _i_ for the position since we will be using the letter _n_ for something else. For example, the sequence of "[octagonal numbers](https://en.wikipedia.org/wiki/Octagonal_number)" that springs forth from _s_ = 8 starts with 1, 8, 21, 40, 65, 96, 133, 176... 

Given the number of sides `s` and an arbitrary integer `n`, this function should find and return the _s_-gonal integer that is closest to `n`. If `n` falls exactly halfway between two _s_-gonal numbers, return the smaller of those numbers. As you can see from the last row of the following table, this function must be efficient even for gargantuan values of `n`.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>s</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>5</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>6</code>
   </td>
  </tr>
  <tr>
   <td><code>27</code>
   </td>
   <td><code>4</code>
   </td>
   <td><code>25</code>
   </td>
  </tr>
  <tr>
   <td><code>450</code>
   </td>
   <td><code>9</code>
   </td>
   <td><code>474</code>
   </td>
  </tr>
  <tr>
   <td><code>10**10</code>
   </td>
   <td><code>42</code>
   </td>
   <td><code>9999861561</code>
   </td>
  </tr>
  <tr>
   <td><code>10**100</code>
   </td>
   <td><code>91</code>
   </td>
   <td><code>10000000000000000000000000000000000000000000000000416332753518329478897755794704334003003544212420356</code>
   </td>
  </tr>
</table>


The simplest way to make this function efficient is to harness the power of **repeated halving** to pull your wagon with a clever application of **binary search**. Start with two integers `a` and `b` wide enough that they satisfy `a &lt;= i &lt;= b` for the currently unknown position `i` that the nearest polygonal number is stored in. (Just initialize these as `a = 1` and `b = 2`, and keep squaring `b` until the number in that position gets too big. It's not like these initial bounds need to be accurate.) From there, compute the midpoint position `(a + b) // 2`, and look at the element in that position. Depending on how that midpoint element compares to `n`, bring either `b` or `a` to the midpoint position. Continue this until the gap has become small enough so that `b-a &lt; 2`, at which point one more final comparison tells you which element is the correct answer.


## **Postfix interpreter**


```
def postfix_evaluate(items):
```


When arithmetic expressions are given in the familiar infix notation 2 + 3 * 4, we need to use parentheses to force a different evaluation order than the usual **PEMDAS** order determined by _precedence_ and _associativity_. Writing arithmetic expressions in _postfix_ notation (also known as [Reverse Polish Notation](https://en.wikipedia.org/wiki/Reverse_Polish_notation)) may look strange to us humans accustomed to the conventional _infix_ notation, but is computationally far easier to handle, since postfix notation allows any evaluation order to be expressed unambiguously without using any parentheses at all! A postfix expression is given as a list of `items` that can be either individual integers or one of the strings `'+'`, `'-'`, `'*'` and `'/'` for the four possible arithmetic operators.

To evaluate a postfix expression using a simple linear loop, use a list as a **stack** that is initially empty. Loop through the `items` one by one, in order from left to right. Whenever the current item is an integer, just append it to the end of the list. Whenever the current item is one of the four arithmetic operations, remove two items from the end of the list, perform that operation on those items, and append the result to the list. Assuming that `items` is a legal postfix expression, which is guaranteed in this problem so that you don't need to do any error handling, once all items have been processed this way, the one number that remains in the stack is returned as the final answer. 

To avoid the intricacies of floating point arithmetic, you should perform the division operation using the Python integer division operator `//` that truncates the result to the integer part. Furthermore, to avoid the crash caused by dividing by zero, in this problem we shall artificially make up a rule that dividing anything by zero will simply evaluate to zero instead of crashing.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>(Equivalent infix)
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[2, 3, '+', 4, '*']</code> 
   </td>
   <td>(2+3) * 4 
   </td>
   <td><code>20</code>
   </td>
  </tr>
  <tr>
   <td><code>[2, 3, 4, '*', '+']</code>
   </td>
   <td>2 + (3*4)
   </td>
   <td><code>14</code>
   </td>
  </tr>
  <tr>
   <td><code>[3, 3, 3, '-', '/'] </code>
   </td>
   <td>3 / (3 - 3)
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>[7, 3, '/']</code>
   </td>
   <td>7 / 3
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3, 4, 5, 6, '*', '*', '*', '*', '*']</code>
   </td>
   <td>1 * 2 * 3 * 4 * 5 * 6
   </td>
   <td><code>720</code>
   </td>
  </tr>
</table>


(By adding more operators and another auxiliary stack, an entire programming language can be built around the idea of postfix evaluation. See the Wikipedia page "[Forth](https://en.wikipedia.org/wiki/Forth_(programming_language))", if interested.)


## **Fractran interpreter**


```
def fractran(n, prog, giveup=1000):
```


[John Conway,](https://en.wikipedia.org/wiki/John_Horton_Conway) who was quite a character among mathematicians, is best known for [The Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life), not to be confused with the classic board game with the same name. That one achievement eclipsed basically all other wacky and original creations of Conway, so we ought to give his less appreciated creations an occasional turn in the flashing lights of the red carpet fame.

This lab has you write an interpreter for the simple [esoteric programming language](https://en.wikipedia.org/wiki/Esoteric_programming_language) called [FRACTRAN](https://en.wikipedia.org/wiki/FRACTRAN), named as a pun of the word "fraction" and the [FORTRAN programming language](https://en.wikipedia.org/wiki/Fortran). (Things used to be in uppercase back in the day, with occasional dollar signs interspersed as separators.) A program written in such mysterious and hard-to-decipher form consists of nothing but a list of positive integer fractions, in this problem given as tuples of the numerator and the denominator. Of course, you are not merely allowed but encouraged to use the `Fraction` data type of the Python `fractions` module to simplify the computations inside your function.

Given a positive integer `n` as its start state, the next state is the product `n*f` for the first fraction listed in `prog` for which `n*f` is an exact integer. That integer then becomes the new state for the next round. Once `n*f` is not an integer for any of the fractions `f` listed in `prog`, the execution terminates. Your function should compute and return the sequence of integers produced by the given FRACTRAN program, with a forced termina... sorry, forced **halting** (after all, Conway was British) taking place after `giveup` steps, if the execution has not halted by then.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>prog</code>
   </td>
   <td><code>giveup</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>[(17, 91), (78, 85), (19, 51), (23, 38), (29, 33), (77, 29), (95, 23), (77, 19), (1, 17), (11, 13), (13, 11), (15, 2), (1, 7), (55, 1)]</code>
   </td>
   <td><code>20</code>
   </td>
   <td><code>[2, 15, 825, 725, 1925, 2275, 425, 390, 330, 290, 770, 910, 170, 156, 132, 116, 308, 364, 68, 4, 30]</code>
   </td>
  </tr>
  <tr>
   <td><code>9</code>
   </td>
   <td>(same as above)
   </td>
   <td><code>20</code>
   </td>
   <td><code>[9, 495, 435, 1155, 1015, 2695, 3185, 595, 546, 102, 38, 23, 95, 385, 455, 85, 78, 66, 58, 154, 182]</code>
   </td>
  </tr>
</table>



## 


## **Permutation cycles**


```
def permutation_cycles(perm):
```


In this problem, a **permutation** is a list of _n_ elements that contains every integer from 0 to _n_ - 1 exactly once. For example, `[5, 2, 0, 1, 4, 3]` is one of the 6! permutations for _n_ = 6. Each permutation can be considered a **bijective function** that maps each position 0 to _n_ - 1 into some unique position so that no two positions map to the same position. For example, the previous permutation maps the position 0 into 5, position 1 into 2, and so on.

A **cycle** of a permutation is a list of positions so that each position is mapped into the next position in the cycle, with the last element looping back to the first position of that cycle. Positions inside a cycle are treated in a "[necklace](https://en.wikipedia.org/wiki/Necklace_(combinatorics))" fashion so that `[1, 2, 3]`, `[2, 3, 1]` and `[3, 1, 2]` are simply different ways to represent that same cycle, distinct from another possible cycle of these three elements that could be given as `[1, 3, 2]`, `[3, 2, 1]` or `[2, 1, 3]`. To construct the cycle that the position `i` belongs to, start at `i` and keep moving from the current position `j` to its successor position `perm[j]` until you return to the original position `i`. The cycles of the above permutation are `[0, 5, 3, 1, 2]` and `[4]`, the second cycle a **singleton** as this permutation maps the position 4 back into itself.

This function should list each individual cycle starting from its highest element, and the cycles should be combined to the increasing order of their starting positions. For example, the previous example cycles `[4]` and `[5, 3, 1, 2, 0]` must be listed in this order, since 4 &lt; 5. Furthermore, instead of returning a list of cycles, these cycles must be encoded as a **flat list** permutation that simply lists its cycles without any separators such as square brackets. Amazingly, this run-on **standard representation** still allows unique reconstruction of the original cycles!


<table>
  <tr>
   <td><code>perm</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[0, 1, 2, 3]</code>
   </td>
   <td><code>[0, 1, 2, 3]</code>
   </td>
  </tr>
  <tr>
   <td><code>[3, 2, 1, 0]</code>
   </td>
   <td><code>[2, 1, 3, 0]</code>
   </td>
  </tr>
  <tr>
   <td><code>[5, 2, 0, 1, 4, 3]</code>
   </td>
   <td><code>[4, 5, 3, 1, 2, 0] </code>
   </td>
  </tr>
  <tr>
   <td><code>[2, 4, 6, 5, 3, 1, 0]</code>
   </td>
   <td><code>[5, 1, 4, 3, 6, 0, 2]</code>
   </td>
  </tr>
  <tr>
   <td><code>[5, 3, 0, 1, 4, 2, 6]</code>
   </td>
   <td><code>[3, 1, 4, 5, 2, 0, 6]</code>
   </td>
  </tr>
  <tr>
   <td><code>[0, 9, 7, 4, 2, 3, 8, 5, 1, 6]</code>
   </td>
   <td><code>[0, 7, 5, 3, 4, 2, 9, 6, 8, 1]</code>
   </td>
  </tr>
</table>





## **Squaring off**


```
def subtract_square(queries):
```


Two players play a game of "[Subtract a square](https://en.wikipedia.org/wiki/Subtract_a_square)", starting with a positive integer. On their turn to play, each player must subtract some **square number** (1, 4, 9, 16, 25, 36, 49, ...) from the current number so that the result does not become negative. Under the **normal play convention** of these games, the player who moves to zero wins, leaving his opponent stuck with no possible moves. (In the **misère** version of the game that has otherwise identical rules but where you win by losing the original game, these definitions would be adjusted accordingly.)

This and many similar [combinatorial games](https://en.wikipedia.org/wiki/Combinatorial_game_theory) can be modelled with recursive equations. This game is an example of an [impartial game](https://en.wikipedia.org/wiki/Impartial_game) since the moves available to both players are exactly the same, as opposed to "partisan games" such as chess where each player can only move pieces of one colour. A game state is therefore determined by the remaining number alone, but not by which player has to make the next move. A state is called "**hot**" ("winning") if it allows at least one move that is part of the winning line regardless of the opponent's response, under the assumption that the current player will then also continue making the best moves until the opponent says uncle. The game state is "**cold**" ("losing") if no winning move exists in that state.

Since the possible states of this game are the nonnegative integers, the base case for the recursion is that zero is cold. The state `n` is hot if there exists at least one move `m` so that `n-m*m` is cold, otherwise `n` is cold. Since the heat of each state `n` depends on heats of states lower than `n`, we might as well combine the computations of states to be as a "batch job". Given a list of `queries` so that each element is a state this function should return a list of results for those queries so that `True` means hot and `False` means cold. You should compute the heat values of states as a single list that you build up from left to right, so that the computation of the heat value of each state can simply read from this list the heat values of previous states that it needs.


<table>
  <tr>
   <td><code>queries</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[7, 12, 17, 24]</code>
   </td>
   <td><code>[False, False, False, True]</code>
   </td>
  </tr>
  <tr>
   <td><code>[2, 3, 6, 10, 14, 20, 29, 39, 57, 83, 111, 149, 220, 304, 455, 681]</code>
   </td>
   <td><code>[False, True, True, False, True, False, True, False, False, True, True, True, True, True, True, True]</code>
   </td>
  </tr>
  <tr>
   <td><code>[7, 12, 17, 23, 32, 45, 61, 84, 120, 172, 251, 345, 510, 722, 966, 1301, 1766, 2582, 3523, 5095, 7812, 10784, 14426, 20741]</code>
   </td>
   <td><code>[False, False, False, True, True, True, True, True, True, True, True, False, False, True, True, True, True, True, True, True, True, True, True, True]</code>
   </td>
  </tr>
</table>



## **ztalloc ecneuqes**


```
def ztalloc(shape):
```


The famous [Collatz sequence](https://en.wikipedia.org/wiki/Collatz_conjecture) was used in the lectures as an example of a situation that requires the use of a `while`-loop, since we cannot know beforehand how many steps are needed to get to the goal from the given starting value. The answer was given as the list of integers that the sequence visits before terminating at its goal. However, we can also look at this sequence in a binary fashion depending on whether each value steps **up** (3_x_ + 1) or **down** (_x_ // 2) from the previous value, denoting these steps with letter `'u'` and `'d'`, respectively. For example, starting from `n = 12`, the sequence `[12, 6, 3, 10, 5, 16, 8, 4, 2, 1]` would have the step shape `'ddududddd'`.

This function should, given the step `shape` as a string that is guaranteed to consist of only letters `u` and `d`, determine which starting value for the Collatz sequence produces that `shape`. However, this function must also recognize that some shape strings are impossible as entailed by the transition rules of Collatz problem, and correctly return `None` for all such shapes. You should start from the goal state 1, and perform the given transitions in reverse. Make sure that your function does not accept moves that would be illegal in the original forward Collatz sequence.


<table>
  <tr>
   <td><code>shape</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'ududududddddudddd'</code>
   </td>
   <td><code>15</code>
   </td>
  </tr>
  <tr>
   <td><code>'dudududdudddudddd'</code>
   </td>
   <td><code>14</code>
   </td>
  </tr>
  <tr>
   <td><code>'uduuudddd'</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
  <tr>
   <td><code>'d'</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>'uuududdddduuuuuuudddddd'</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
  <tr>
   <td><code>'duuudddddddd'</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
</table>





## **Reverse ascending sublists** 


```
def reverse_ascending_sublists(items):
```


Create and return a new list that contains the same elements as the argument `items` list, but reversing the order of the elements inside every **maximal** **strictly ascending** sublist. Note the modifier "strictly" used there to require each element to be greater than the previous element, not merely equal to it. As is the case with all functions unless otherwise specified, this function should not modify the contents of the original list, but create and return a brand new list object that contains the result, no matter how tempting it might be to perform this operation right there in the original list to "save some memory".

In the table below, different colours highlight the maximal strictly ascending sublists, and are not part of the actual argument object given to the Python function. (It's not like this is _Mathematica_ or some other high level **symbolic computation** system that deals directly with symbolic expressions in their unevaluated forms, allowing you to do things of such nature...)


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3, 4, 5]</code>
   </td>
   <td><code>[5, 4, 3, 2, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>[5, 7, 10, 4, 2, 7, 8, 1, 3]</code>
   </td>
   <td><code>[10, 7, 5, 4, 8, 7, 2, 3, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>[5, 4, 3, 2, 1]</code>
   </td>
   <td><code>[5, 4, 3, 2, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>[5, 5, 5, 5, 5]</code>
   </td>
   <td><code>[5, 5, 5, 5, 5]</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 2, 3]</code>
   </td>
   <td><code>[2, 1, 3, 2]</code>
   </td>
  </tr>
</table>



## 


## **Brangelina**


```
def brangelina(first, second):
```


The task of combining the first names of celebrity couples into a catchy shorthand for media consumption turns out to be surprisingly simple to automate. Start by counting how many **groups** of consecutive vowels (_aeiou_, since to keep this problem simple, the letter _y_ is always a consonant) there are inside the first name. For example, `'brad'` and `'jean'` have one vowel group, `'jeanie'` and `'britain'` have two, and `'angelina'` and `'alexander'` have four. Note that a vowel group can contain more than one vowel, as in `'queueing'` that has an entire fiver.

If the first name has only one vowel group, keep only the consonants before that group and throw away everything else. For example, `'ben'` becomes `'b'`, and `'brad'` becomes `'br'`. Otherwise, if the first word has _n_ > 1 vowel groups, keep everything before the **second last** vowel group _n_ - 1. For example, `'angelina'` becomes `'angel'` and `'alexander'` becomes `'alex'`. Concatenate that with the string you get by removing all consonants at the beginning of the second name. All names given to this function are guaranteed to consist of the 26 lowercase English letters only, and each name will have at least one vowel and one consonant somewhere in it.


<table>
  <tr>
   <td><code>first</code>
   </td>
   <td><code>second</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'brad'</code>
   </td>
   <td><code>'angelina'</code>
   </td>
   <td><code>'brangelina'</code>
   </td>
  </tr>
  <tr>
   <td><code>'angelina'</code>
   </td>
   <td><code>'brad'</code>
   </td>
   <td><code>'angelad'</code>
   </td>
  </tr>
  <tr>
   <td><code>'sheldon'</code>
   </td>
   <td><code>'amy'</code>
   </td>
   <td><code>'shamy'</code>
   </td>
  </tr>
  <tr>
   <td><code>'amy'</code>
   </td>
   <td><code>'sheldon'</code>
   </td>
   <td><code>'eldon'</code>
   </td>
  </tr>
  <tr>
   <td><code>'frank'</code>
   </td>
   <td><code>'ava'</code>
   </td>
   <td><code>'frava'</code>
   </td>
  </tr>
  <tr>
   <td><code>'britain'</code>
   </td>
   <td><code>'exit'</code>
   </td>
   <td><code>'brexit'</code>
   </td>
  </tr>
</table>


These simple rules do not always produce the most clever possible result. For example, `'ross'` and `'rachel'` meld into `'rachel'` instead of `'rochel'`, and `'joey'` and `'phoebe'` meld into `'joebe'` instead of `'joeybe'`. The reader is invited to think up more advanced rules that would cover a wider variety of name combinations and special cases. (Some truly advanced set of rules, trained with **deep learning** techniques to recognize the semantic content of words, might even combine `'donald'` and `'hillary'` into `'dollary'` instead of `'dillary'`...)




## **Line with most points**


```
def line_with_most_points(points):
```


A point on the two-dimensional grid of integers is given as a two-element tuple of _x_- and _y_-coordinates, for example `(2, 5)` or `(10, 1)`. [As originally postulated by Euclid](http://mathworld.wolfram.com/EuclidsPostulates.html), given any two distinct points on the plane, there exists **exactly one** straight line that goes through both points. (In differently shaped spaces, [different rules and their consequences apply](https://en.wikipedia.org/wiki/Non-Euclidean_geometry).) Of course, this same line, being shamelessly infinite to both directions, will also pass through an infinity of other points on the two-dimensional plane. 

Given a list of `points` on the integer grid, find the line that contains the largest number of points from this list. To guarantee the uniqueness of the expected result for every test case, this function should not return the line itself, but merely the count of how many of these `points` lie on that line. The list of `points` is guaranteed to contain at least two points and that all points in the list are distinct, but otherwise these points are not given in any specific order.


<table>
  <tr>
   <td><code>points</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[(42, 1), (7, 5)]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>[(1, 4), (2, 6), (3, 2), (4, 10)]</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>[(x, y) for x in range(10) for y in range(10)]</code>
   </td>
   <td><code>10</code>
   </td>
  </tr>
  <tr>
   <td><code>[(3, 5), (1, 4), (2, 6), (7, 7), (3, 8)]</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>[(5, 6), (7, 3), (7, 1), (2, 1), (7, 4), (2, 6), (7, 7)]</code>
   </td>
   <td><code>4</code>
   </td>
  </tr>
</table>


This problem can be brute forced with three nested loops, but the point (heh) of this problem is not to do too much more work than you really need to. To simplify your logic, consult the example program <code>[geometry.py](https://github.com/ikokkari/PythonExamples/blob/master/geometry.py)</code> for the <strong>cross product</strong> function that can be used to quickly determine whether three points are collinear.


## **Om nom nom**


```
def cookie(piles):
```


The beloved _Sesame Street_ character [Cookie Monster](https://en.wikipedia.org/wiki/Cookie_Monster) has stumbled upon a table with `piles` of cookies, each pile a distinct positive integer. However, the monomaniacal obsessiveness of [The Count](https://en.wikipedia.org/wiki/Count_von_Count) who set up this fiesta has recently escalated to a whole new level of severity. To allow the Cookie Monster to enjoy this crumbly fiesta, The Count insists that these cookies must be eaten in the smallest possible number of moves. Each move consists of the Cookie Monster choosing one of the remaining pile sizes `p`. This move removes `p` cookies from every pile that contains at least `p` cookies (thereby eradicating all piles whose size is exactly `p`), and leaves all smaller piles untouched as they were. This function should compute and return **the smallest number of moves** that allows Cookie Monster to scarf down these cookies. 


<table>
  <tr>
   <td><code>piles</code>
   </td>
   <td>Expected result
   </td>
   <td> (optimal moves)
   </td>
  </tr>
  <tr>
   <td><code>[1, 2, 3, 4, 5, 6]</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>[4, 2, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>[2, 3, 5, 8, 13, 21, 34, 55, 89]</code>
   </td>
   <td><code>5 </code>
   </td>
   <td><code>[55, 21, 8, 3, 2]</code>
   </td>
  </tr>
  <tr>
   <td><code>[1, 10, 17, 34, 43, 46]</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>[34, 9, 8, 3, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>[11, 26, 37, 44, 49, 52, 68, 75, 87, 102]</code>
   </td>
   <td><code>6</code>
   </td>
   <td><code>[37, 31, 15, 12, 7, 4]</code>
   </td>
  </tr>
  <tr>
   <td><code>[2**n for n in range(10)]</code>
   </td>
   <td><code>10</code>
   </td>
   <td><code>[512, 256, 128, 64, 32, 16, 8, 4, 2, 1]</code>
   </td>
  </tr>
</table>


This problem has a curious property that the moves in the optimal solution can be performed in any order, which is rare for combinatorial problems of this spirit. Without loss of generality, it suffices to examine only strictly descending move sequences. Even then, [this problem is far deeper than it would initially seem](https://arxiv.org/pdf/1309.5985.pdf). Various **greedy strategies** that would seem natural for the addiction-riddled brain of the Cookie Monster such as "choose `p` to maximize the number of cookies eaten at the current move" or "choose `p` to eliminate the largest possible number of piles" (yep, think about that one) do not always lead to the shortest possible sequence of moves.


## **Autocorrect for stubby fingers**


```
def autocorrect_word(word, words, df):
```


In this day and age all you whippersnappers are surely familiar with **autocorrect** that replaces a non-word with the "closest" real word in the dictionary. Many techniques exist to guess more accurately what the user intended to write. For many old people such as your instructor, baffled by technological doodads and thingamabobs, typos occur when they inadvertently press a virtual key next to the intended one. For example, when the non-existent word is `"cst"`, the intended word seems more likely to have been `"cat"` than `"cut"`, assuming that the text was entered using the ordinary QWERTY keyboard where the characters `a` and `s` are adjacent.

Given a `word`, a list of `words`, and a **distance** function `df` that tells how "far" the first argument is from the second (for example, `df('a','s') == 1` and `df('a', 'a') == 0`),  find and return the word in the list of `words` that have the same number of letters and whose distance, measured as the sum of the distances of the characters in the same position, is the smallest. If there exist several words equidistant from  `word`, return the first such word in the dictionary order.


<table>
  <tr>
   <td><code>word</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'qrc'</code>
   </td>
   <td><code>'arc'</code>
   </td>
  </tr>
  <tr>
   <td><code>'jqmbo'</code>
   </td>
   <td><code>'jambo'</code>
   </td>
  </tr>
  <tr>
   <td><code>'hello'</code>
   </td>
   <td><code>'hello'</code>
   </td>
  </tr>
  <tr>
   <td><code>'interokay'</code>
   </td>
   <td><code>'interplay'</code>
   </td>
  </tr>
</table>


More advanced autocorrect techniques use the surrounding context to suggest the best replacement, seeing that not all words are equally likely to be the intended word, given the rest of the sentence. For example, the misspelling `'urc'` should probably be corrected very differently in the sentence "The gateway consists of an urc of curved blocks" than in "The brave little hobbit swung his sword at the smelly urc."


## **Uambcsrlne the wrod**


```
def unscramble(words, word):
```


Smdboeoy nteoicd a few yreas ago taht the lretets isndie Eisgnlh wdors can be ronmaldy slmecbrad wouhtit antifecfg tiehr rlaibdiatey too mcuh, piovredd that you keep the frsit and the last lteters as tehy were. Gevin a lsit of `words` gtuaraened to be soterd, and one serlcmbad `wrod`, tihs fctounin shulod rterun the list of wrdos taht cloud hvae been the orgiianl word taht got seambclrd, and of csorue retrun taht lsit wtih its wdros sterod in apcabihaetll oerdr to enrsue the uaigntbmuiy of atematoud testing. In the vast maitjory of ceass, this list wlil catnoin only one wrod.


<table>
  <tr>
   <td><code>wrod</code>
   </td>
   <td>Etecxepd rssuelt (unsig the wrosldit <code>words_sorted.txt</code>)
   </td>
  </tr>
  <tr>
   <td><code>'tartnaas'</code>
   </td>
   <td><code>['tantaras', 'tarantas', 'tartanas']</code>
   </td>
  </tr>
  <tr>
   <td><code>'aierotsd'</code>
   </td>
   <td><code>['asteroid']</code>
   </td>
  </tr>
  <tr>
   <td><code>'ksmrseah'</code>
   </td>
   <td><code>['kersmash']</code>
   </td>
  </tr>
  <tr>
   <td><code>'bttilele'</code>
   </td>
   <td><code>['belittle', 'billette']</code>
   </td>
  </tr>
</table>


Writing the filter to transform the given plaintext to the above scrambled form is also a good little programming exercise in Python. This leads us to a useful estimation exercise: how long would the plaintext have to be for you to write such a filter yourself instead of scrambling the plaintext by hand as you would if you needed to scramble just one word? In general, how many times do you think you need to solve some particular problem until it becomes more efficient to design, write and debug a Python script to do it? Would your answer change if it turned out that millions of people around the world also have that same problem, silently screaming for a saviour to come and automate this repetitive and error-prone task for them?


## **Substitution words**


```
def substitution_words(pattern, words):
```


Given a list of `words` (once again, guaranteed to be in sorted order and each consist of the 26 lowercase English letters only) and a `pattern` that consists of uppercase English characters, this function should find and return a list of precisely those words that match the `pattern` in the sense that there exists a substitution from uppercase letters to lowercase letters that turns the `pattern` into the word. Furthermore, this substitution must be **injective**, meaning that no two different uppercase letters in the pattern are mapped to the same lowercase letter in that word.

For example, the word `'akin'` matches the pattern `'ABCD'` with the substitutions `A→a`, <code>B<strong>→</strong>k</code>, <code>C<strong>→</strong>i</code> and <code>D<strong>→</strong>n</code>. However, the word <code>'area'</code> would not match that same pattern, since the pattern characters <code>A</code> and <code>D</code> would both have to be mapped to the same letter <code>a</code>, against the rules.


<table>
  <tr>
   <td><code>pattern</code>
   </td>
   <td>Expected result (using the wordlist <code>words_sorted.txt</code>)
   </td>
  </tr>
  <tr>
   <td><code>'ABBA'</code>
   </td>
   <td><code>['abba', 'acca', 'adda', 'affa', 'akka', 'amma', 'anna', 'atta', 'boob', 'deed', 'ecce', 'elle', 'esse', 'goog', 'immi', 'keek', 'kook', 'maam', 'noon', 'otto', 'peep', 'poop', 'sees', 'teet', 'toot']</code>
   </td>
  </tr>
  <tr>
   <td><code>'ABABA'</code>
   </td>
   <td><code>['ajaja', 'alala', 'anana', 'arara', 'ululu']</code>
   </td>
  </tr>
  <tr>
   <td><code>'CEECEE'</code>
   </td>
   <td><code>['beebee', 'booboo', 'muumuu', 'seesee', 'soosoo', 'teetee', 'weewee', 'zoozoo']</code>
   </td>
  </tr>
  <tr>
   <td><code>'ABCDCBA'</code>
   </td>
   <td><code>['adinida', 'deified', 'hagigah', 'murdrum', 'reifier', 'repaper', 'reviver', 'rotator', 'senones']</code>
   </td>
  </tr>
  <tr>
   <td><code>'DEFDEF'</code>
   </td>
   <td>76 words, first three of which are <code>['akeake', 'atlatl', 'barbar']</code>
   </td>
  </tr>
  <tr>
   <td><code>'ABCDEFGIJKLM'</code>
   </td>
   <td>243 words, first three of which are <code>['absorptively', 'adjunctively', 'adsorptively']</code>
   </td>
  </tr>
</table>


(Extra math problem for the readers who are into combinatorics and discrete math: can you construct an encoding function from strings to natural numbers so that two strings map into the same number if and only if these two strings both match the same `pattern`?)


## **Manhattan skyline**


```
def manhattan_skyline(towers): 
```


This classic problem in [computational geometry](https://en.wikipedia.org/wiki/Computational_geometry) (essentially, geometry that can be done using only integer arithmetic; yes, that is an actual thing) is best illustrated by pictures and animations such as those on the page "[The Skyline problem](https://briangordon.github.io/2014/08/the-skyline-problem.html)", so you can first check that it out to get an idea of what is going on. Given a list of rectangular `towers` as tuples `(s, e, h)` where `s` and `e` are the start and end _x_-coordinates (`e > s`) and `h` is the height of that tower, compute and return the **total visible area of the towers**, being careful not to double count two or more towers that are partially overlapping. All towers share the same flat ground baseline at the height.

The classic solution illustrates the important [sweep line technique](https://en.wikipedia.org/wiki/Sweep_line_algorithm) that starts by creating a list of precisely those _x_-coordinate values where something relevant to the problem takes place. In this problem, the relevant _x_-coordinates are those where some tower either starts or ends. Next, loop through this list in ascending order, updating your computation for the interval between the current relevant _x_-coordinate and the previous one. In this particular problem, you need to maintain a **list of active towers** so that tower `(s, e, h)` becomes active when `x == s`, and becomes inactive again when `x == e`. Inside each interval, only the tallest active tower has any effect on the area computation.

The automated tester script will produce start and end coordinates from an increasing scale to prevent this problem being solved with the inferior method that builds up the list of all positions from zero up to the maximum end coordinate in `towers`, loops through the `towers` to update the tallest tower height at each position, and sums up these heights for the final area. 


<table>
  <tr>
   <td><code>towers</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[(2, 3, 39)]</code>
   </td>
   <td><code>39</code>
   </td>
  </tr>
  <tr>
   <td><code>[(6, 8, 56), (5, 14, 81), (3, 13, 71)]</code>
   </td>
   <td><code>871</code>
   </td>
  </tr>
  <tr>
   <td><code>[(6, 18, 95), (3, 20, 95), (14, 31, 22), (5, 12, 93)]</code>
   </td>
   <td><code>1857</code>
   </td>
  </tr>
  <tr>
   <td><code>[(16, 88, 20), (11, 75, 22), (43, 73, 27), (21, 42, 37), (20, 89, 12), (67, 68, 19), (1, 65, 24), (78, 91, 34), (65, 117, 9)]</code>
   </td>
   <td><code>2871</code>
   </td>
  </tr>
</table>





## **Count overlapping disks**


```
def count_overlapping_disks(disks): 
```


Right on the heels of the previous Manhattan skyline problem, here is another classic of similar spirit for us to solve efficiently with a **sweep line algorithm**. Given a list of `disks` on the two-dimensional plane as tuples `(x, y, r)` so that `(x, y)` is the center point and `r` is the radius of that disk, count how many pairs of disks **intersect** each other in that their areas have at least one point in common. To test whether disks `(x1, y1, r1)` and `(x2, y2, r2)` intersect, use the Pythagorean formula `(x2-x1)**2 + (y2-y1)**2 &lt;= (r1+r2)**2`. Note again how this precise formula needs only integer arithmetic whenever the individual components are integers, with no square roots or any other irrational numbers gumming up the works with the infinite decimals that we can only approximate.

For this problem, crudely looping through all possible pairs of disks would work but be horrendously inefficient as the list grows larger. However, a sweep line algorithm** **can solve this problem by looking at a far fewer pairs of disks. Again, sweep through the space from left to right for all relevant _x_-coordinate values and maintain **the set of active disks** at the moment. Each individual disk `(x, y, r)` enters the active set when the vertical sweep line reaches the _x_-coordinate `x-r`, and leaves the active set when the sweep line reaches `x+r`. When a disk enters the active set, check for an intersection only between that disk and the disks in the active set.


<table>
  <tr>
   <td><code>disks</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[(0, 0, 3), (6, 0, 3), (6, 6, 3), (0, 6, 3)]</code>
   </td>
   <td><code>4</code>
   </td>
  </tr>
  <tr>
   <td><code>[(4, -1, 3), (-3, 3, 2), (-3, 4, 2), (3, 1, 4)]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>[(-10, 6, 2), (6, -4, 5), (6, 3, 5), (-9, -8, 1), (1, -5, 3)]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>[(x, x, x // 2) for x in range(2, 101)]</code>
   </td>
   <td><code>2563</code>
   </td>
  </tr>
</table>





## **An unordinary ordering of ordinary cardinals**


```
def sort_by_digit_count(items):
```


Sorting can be done according to arbitrarily chosen comparison criteria, as long as they satisfy the mathematical requirements of a **total ordering** relation. To play around with this concept, let us define a wacky ordering comparison of positive integers so that for any two integers, the one that contains the digit 9 more times than the other is considered to be larger, regardless of the magnitude and other digits of these numbers. For example, 99 > 12345678987654321 > 10<sup>1000</sup> in this ordering. If both integers contain the digit 9 the same number of times, the comparison proceeds to the next lower digit 8, and so on, until the first distinguishing digit has been discovered. If both integers contain every digit from 9 to 0 pairwise the same number of times, the ordinary integer order comparison will determine their mutual ordering.


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[9876, 19, 4321, 99, 73, 241, 111111, 563, 33]</code>
   </td>
   <td><code>[111111, 33, 241, 4321, 563, 73, 19, 9876, 99]</code>
   </td>
  </tr>
  <tr>
   <td><code>[111, 19, 919, 1199, 911, 999]</code>
   </td>
   <td><code>[111, 19, 911, 919, 1199, 999]</code>
   </td>
  </tr>
  <tr>
   <td><code>[1234, 4321, 3214, 2413]</code>
   </td>
   <td><code>[1234, 2413, 3214, 4321]</code>
   </td>
  </tr>
  <tr>
   <td><code>list(range(100000))</code>
   </td>
   <td>(a list of 100,000 elements whose first five elements are <code>[0, 1, 10, 100, 1000]</code> and the last five are <code>[98999, 99899, 99989, 99998, 99999]</code> )
   </td>
  </tr>
</table>


As explained in discrete math courses, the above relation is transitive and antisymmetric, and therefore a legal ordering relation for integers. Outside its entertainment value it is very nearly useless, though, since it is hard to imagine any useful integer arithmetic operation that would preserve equal values as equals under our wacky equivalence. The ordinary ordering for ordinals (how is that for a name for a hipster indie band?) that we unthinkingly take as some sort of law of nature is useful because it is compatible with useful arithmetic operations in the previous sense, and makes these operations therefore immensely more powerful. 


## **Count divisibles in range**


```
def count_divisibles_in_range(start, end, n):
```


Let us take a breather by tackling a problem simple enough that its solution needs only a couple of conditional statements and some arithmetic, but not even one loop or anything even more fancy. The difficulty is coming up with the conditions that cover all possible cases of this problem exactly right, including all of the potentially tricksy **edge and corner cases**, without being **off-by-one**. Given three integers `start`, `end` and `n` so that `start &lt;= end`, count and return how many integers between `start` and `end`, inclusive, are divisible by `n`. Sure, you _could_ solve this problem with the list comprehension


```
return len([x for x in range(start, end+1) if x % n == 0])
```


but of course the automated tester is designed so that anybody trying to solve this problem in such a blunt and brutish fashion will soon run out of both time and space! Your code should have no loops at all but use integer arithmetic and conditional statements only. Also, be careful with various edge cases and off-by-one pitfalls lurking in the bushes. Note that either `start` or `end` can be negative or zero, but `n` is guaranteed to be greater than zero.


<table>
  <tr>
   <td><code>start</code>
   </td>
   <td><code>end</code>
   </td>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>7</code>
   </td>
   <td><code>28</code>
   </td>
   <td><code>4</code>
   </td>
   <td><code>6</code>
   </td>
  </tr>
  <tr>
   <td><code>-77</code>
   </td>
   <td><code>19</code>
   </td>
   <td><code>10</code>
   </td>
   <td><code>9</code>
   </td>
  </tr>
  <tr>
   <td><code>-19</code>
   </td>
   <td><code>-13</code>
   </td>
   <td><code>10</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>1</code>
   </td>
   <td><code>10**12 - 1</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>199999999999</code>
   </td>
  </tr>
  <tr>
   <td><code>0</code>
   </td>
   <td><code>10**12 - 1</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>200000000000</code>
   </td>
  </tr>
  <tr>
   <td><code>0</code>
   </td>
   <td><code>10**12</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>200000000001</code>
   </td>
  </tr>
  <tr>
   <td><code>-10**12</code>
   </td>
   <td><code>10**12</code>
   </td>
   <td><code>12345</code>
   </td>
   <td><code>162008911</code>
   </td>
  </tr>
</table>



## 


## **Bridge hand shape**


```
def bridge_hand_shape(hand):
```


In the card game of [bridge](https://en.wikipedia.org/wiki/Contract_bridge), each player receives a hand of exactly thirteen cards. The _shape_ of the hand is the distribution of these cards into the four suits in the exact order of **spades, hearts, diamonds, and clubs.** Given a bridge `hand` encoded as in the example script <code>[cardproblems.py](https://github.com/ikokkari/PythonExamples/blob/master/cardproblems.py)</code>, return the list of these four numbers. For example, given a <code>hand</code> that contains five spades, no hearts, five diamonds and three clubs, this function should return <code>[5, 0, 5, 3]</code>. Note that the cards in <code>hand</code> can be given to your function in any order, since in this question the player has not yet manually sorted his hand. Your answer still must list all four suits in their canonical order, so that other players will also know what you are talking about.


<table>
  <tr>
   <td><code>hand</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[('eight', 'spades'), ('king', 'diamonds'), ('ten', 'diamonds'), ('three', 'diamonds'), ('seven', 'spades'), ('five', 'diamonds'), ('two', 'hearts'), ('king', 'spades'), ('jack', 'spades'), ('ten', 'clubs'), ('ace', 'clubs'), ('six', 'diamonds'), ('three', 'hearts')]</code>
   </td>
   <td><code>[4, 2, 5, 2]</code>
   </td>
  </tr>
  <tr>
   <td><code>[('ace', 'spades'), ('six', 'hearts'), ('nine', 'spades'), ('nine', 'diamonds'), ('ace', 'diamonds'), ('three', 'diamonds'), ('five', 'spades'), ('four', 'hearts'), ('three', 'spades'), ('seven', 'diamonds'), ('jack', 'diamonds'), ('queen', 'spades'), ('king', 'diamonds')]</code>
   </td>
   <td><code>[5, 2, 6, 0]</code>
   </td>
  </tr>
</table>





## **Milton Work point count**


```
def milton_work_point_count(hand, trump='notrump'):
```


Playing cards are again represented as tuples of form `(rank, suit)` as in the <code>[cardproblems.py](https://github.com/ikokkari/PythonExamples/blob/master/cardproblems.py)</code> example program. The trick taking power of a bridge hand is estimated with [Milton Work point count](https://en.wikipedia.org/wiki/Hand_evaluation), of which we shall implement a version that is simple enough for beginners of either Python or the game of bridge. Looking at a bridge hand that consists of thirteen cards, first give it 4 points for each ace, 3 points for each king, 2 points for each queen, and 1 point for each jack. That should be simple enough. This <strong>raw point count</strong> is then adjusted with the following rules:



*   If the hand contains one four-card suit and three three-card suits, subtract one point for being **flat**. (Flat hands rarely play as well as non-flat hands with the same point count.)
*   Add 1 point for every suit that has five cards, 2 points for every suit that has six cards, and 3 points for every suit with seven cards or longer. (Shape is power in offense.)
*   If the `trump` suit is anything other than `'notrump'`, add 5 points for every **void** (that is, suit without any cards in it) and 3 points for every **singleton** (that is, a suit with exactly one card) for any other suit than the `trump` suit. (Voids and singletons are great when you are playing a suit contract, but very bad when you are playing a notrump contract. Being void in the trump suit is, of course, extremely bad in that suit contract!)

<table>
  <tr>
   <td>
<code>hand</code> (each hand below has been sorted by suits for readability, but your function can receive these 13 cards from the tester in any order)
   </td>
   <td><code>trump</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[('four', 'spades'), ('five', 'spades'), ('ten', 'hearts'), ('six', 'hearts'), ('queen', 'hearts'), ('jack', 'hearts'), ('four', 'hearts'), ('two', 'hearts'), ('three', 'diamonds'), ('seven', 'diamonds'), ('four', 'diamonds'), ('two', 'diamonds'), ('four', 'clubs')]</code>
   </td>
   <td><code>'diamonds'</code>
   </td>
   <td><code>8</code>
   </td>
  </tr>
  <tr>
   <td><code>[('three', 'spades'), ('queen', 'hearts'), ('jack', 'hearts'), ('eight', 'hearts'), ('six', 'diamonds'), ('nine', 'diamonds'), ('jack', 'diamonds'), ('ace', 'diamonds'), ('nine', 'clubs'), ('king', 'clubs'), ('jack', 'clubs'), ('five', 'clubs'), ('ace', 'clubs')]</code>
   </td>
   <td><code>'clubs'</code>
   </td>
   <td><code>20</code>
   </td>
  </tr>
  <tr>
   <td><code>[('three', 'spades'), ('seven', 'spades'), ('two', 'spades'), ('three', 'hearts'), ('queen', 'hearts'), ('nine', 'hearts'), ('ten', 'diamonds'), ('six', 'diamonds'), ('queen', 'diamonds'), ('ace', 'diamonds'), ('nine', 'clubs'), ('four', 'clubs'), ('five', 'clubs')]</code>
   </td>
   <td><code>'notrump'</code>
   </td>
   <td><code>7</code>
   </td>
  </tr>
</table>





## **Never the twain shall meet**


```
def hitting_integer_powers(a, b, tolerance=100):
```


Integer powers of the given base such as 7 in the series 7, 49, 393, 2401, 16807, 117649, ... will soon blow up too large to be of much use in our daily lives. Outside time and space, all alone with no human minds to watch over their journey that is paradoxically both infinite and instantaneous, these exponentially growing sequences of powers probe through the infinite space of positive integers with exponentially increasing gaps that eventually contain entire universes inside them. Fortunately, Python allows us to play around with integer powers whose millions of digits make them unimaginable for us and yet its mechanical binary decisions inerrantly probe through and dissect these behemoths that our minds could not begin to visualize.

Except in cases when the prime factors of `a` and `b` fit nicely such as one of these numbers being a power of the other, the iron hand of the [Fundamental Theorem of Arithmetic](https://en.wikipedia.org/wiki/Fundamental_theorem_of_arithmetic) dictates that the integer powers `a**pa` and `b**pb` can never be exactly equal for any positive integer exponents `pa` and `pb`. However, in the jovial spirit of "close enough for government work", we consider such powers to "hit" if their absolute difference `abs(a**pa - b**bp)` multiplied by the desired `tolerance` is at most equal to the smaller of those two powers. For example, `tolerance=100` requires their difference to be at most 1%. (This definition intentionally avoids division to keep it accurate for arbitrarily large integers.)

Given the positive integers `a` and `b` and your desired `tolerance`, find and return the tuple of the smallest integer exponents `(p1, p2)` that satisfy this tolerance requirement.


<table>
  <tr>
   <td><code>a</code>
   </td>
   <td><code>b</code>
   </td>
   <td><code>tolerance</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>4</code>
   </td>
   <td><code>100</code>
   </td>
   <td><code>(2, 1)</code>
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>7</code>
   </td>
   <td><code>100</code>
   </td>
   <td><code>(73, 26)</code>
   </td>
  </tr>
  <tr>
   <td><code>3</code>
   </td>
   <td><code>6</code>
   </td>
   <td><code>100</code>
   </td>
   <td><code>(137, 84)</code>
   </td>
  </tr>
  <tr>
   <td><code>4</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>1000</code>
   </td>
   <td><code>(916, 789)</code>
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>11</code>
   </td>
   <td><code>1000</code>
   </td>
   <td><code>(1107, 1063)</code>
   </td>
  </tr>
  <tr>
   <td><code>42</code>
   </td>
   <td><code>99</code>
   </td>
   <td><code>100000</code>
   </td>
   <td><code>(33896, 27571)</code>
   </td>
  </tr>
</table>


(This problem was inspired by the Riddler Express problem in the column "[Can you get another haircut already?](https://fivethirtyeight.com/features/can-you-get-another-haircut-already/)" of [Riddler](https://fivethirtyeight.com/tag/the-riddler/), an excellent source of problems of this kind of general spirit.)




## **Bridge hand shorthand form**


```
def bridge_hand_shorthand(hand):
```


In literature on the game of **contract bridge**, hands are often given in abbreviated form that makes their relevant aspects easier to visualize at a glance. In this abbreviated shorthand form, suits are always listed** in the exact order of spades, hearts, diamonds and clubs**, so no special symbols are needed to show which suit is which. The ranks in each suit are listed as letters from `'AKQJ'` for **aces and faces**, and all **spot cards** lower than jack are written out as the same letter `'x'` to indicate that its exact spot value is irrelevant for the play mechanics of that hand. These letters must be listed in descending order of ranks `AKQJx`. If some suit is **void**, that is, the hand contains no cards of that suit, that suit is abbreviated with a single minus sign character `'-'`. The shorthand forms for the individual suits are separated using single spaces in the result string, without any trailing whitespace. 


<table>
  <tr>
   <td><code>hand</code> (each hand below is sorted by suits for readability, but your function can receive these 13 cards from the tester in any order)
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[('four', 'spades'), ('five', 'spades'), ('ten', 'hearts'), ('six', 'hearts'), ('queen', 'hearts'), ('jack', 'hearts'), ('four', 'hearts'), ('two', 'hearts'), ('three', 'diamonds'), ('seven', 'diamonds'), ('four', 'diamonds'), ('two', 'diamonds'), ('four', 'clubs')]</code>
   </td>
   <td><code>'xx QJxxxx xxxx x'</code>
   </td>
  </tr>
  <tr>
   <td><code>[('three', 'spades'), ('queen', 'hearts'), ('jack', 'hearts'), ('eight', 'hearts'), ('six', 'diamonds'), ('nine', 'diamonds'), ('jack', 'diamonds'), ('ace', 'diamonds'), ('nine', 'clubs'), ('king', 'clubs'), ('jack', 'clubs'), ('five', 'clubs'), ('ace', 'clubs')]</code>
   </td>
   <td><code>'x QJx AJxx AKJxx'</code>
   </td>
  </tr>
  <tr>
   <td><code>[('three', 'spades'), ('seven', 'spades'), ('two', 'spades'), ('three', 'hearts'), ('queen', 'hearts'), ('nine', 'hearts'), ('ten', 'diamonds'), ('six', 'diamonds'), ('queen', 'diamonds'), ('ace', 'diamonds'), ('nine', 'clubs'), ('four', 'clubs'), ('five', 'clubs')]</code>
   </td>
   <td><code>'xxx Qxx AQxx xxx'</code>
   </td>
  </tr>
  <tr>
   <td><code>[('ace', 'spades'), ('king', 'spades'), ('queen', 'spades'), ('jack', 'spades'), ('ten', 'spades'), ('nine', 'spades'), ('eight', 'spades'), (seven, 'spades'), ('six', 'spades'), ('five', 'spades'), ('four', 'spades'), ('three', 'spades'), ('two', 'diamonds')]</code>
   </td>
   <td><code>'AKQJxxxxxxxx - x -'</code>
   </td>
  </tr>
</table>


(Then again, the author once saw a play problem where a freaking _eight_ was a relevant rank...)


## **Losing trick count of a bridge hand**


```
def losing_trick_count(hand):
```


The [Milton Work point count](https://en.wikipedia.org/wiki/Hand_evaluation) that we saw in an earlier problem is the first baby step in estimating the playing power of a bridge hand. Once the partnership discovers they have a good trump fit, hand evaluation continues more accurately using some form of [losing trick count](https://en.wikipedia.org/wiki/Losing-Trick_Count). For example, a small slam in spades with `'AKxxxxx - Kxxx xx'` facing `'xxxx xxxxx AQx -'` is a lock despite possessing only 16 of the 40 high card points in the deck, assuming that the opponents looking at their own massive shapes let you play that slam instead of making a great sacrifice by bidding seven of their suit (yes, advanced partnerships are able to judge these things that accurately from what has been bid, and especially what had _not_ been bid. On the other hand (heh), any slam is dead in the water with the `'QJxxx xx AKx QJx'` facing `'AKxxx QJ QJx AKx'`, thanks to the horrendous duplication of useful cards. ("If it quacks like a duck...")

In this problem, we compute the basic losing trick count as given in step 1 of "[Methodology](https://en.wikipedia.org/wiki/Losing-Trick_Count#Methodology)" section of the Wikipedia page "[Losing Trick Count](https://en.wikipedia.org/wiki/Losing-Trick_Count)" without any finer refinements. Keep in mind that no suit can have more losers than it has cards, and never more than three losers even if there were ten cards of that suit in their hand! The following dictionary (composed by student Shu Zhu Su during the Fall 2018 term) might also come handy for the combinations whose losing trick count differs from the string length, once you convert each `J` of the shorthand form into an `x` :


```
{'-':0,'A':0,'x':1,'Q':1,'K':1,'AK':0,'AQ':1,'Ax':1,'KQ':1,'Kx':1,'Qx':2,'xx':2, 'AKQ':0, 'AKx':1, 'AQx':1,'Axx':2, 'Kxx':2, 'KQx':1, 'Qxx':2, 'xxx':3}



<table>
  <tr>
   <td>```

<code>hand</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[('ten', 'clubs'), ('two', 'clubs'), ('five', 'clubs'), ('queen', 'hearts'), ('four', 'spades'), ('three', 'spades'), ('ten', 'diamonds'), ('king', 'spades'), ('five', 'diamonds'), ('nine', 'hearts'), ('ace', 'spades'), ('queen', 'spades'), ('six', 'spades')]</code>
   </td>
   <td><code>7</code>
   </td>
  </tr>
  <tr>
   <td><code>[('eight', 'hearts'), ('queen', 'spades'), ('jack', 'hearts'), ('queen', 'hearts'), ('six', 'spades'), ('ten', 'hearts'), ('five', 'clubs'), ('jack', 'spades'), ('five', 'diamonds'), ('queen', 'diamonds'), ('six', 'diamonds'), ('three', 'spades'), ('nine', 'clubs')]</code>
   </td>
   <td><code>8</code>
   </td>
  </tr>
</table>





## **Bulls and cows**


```
def bulls_and_cows(guesses):
```


In the old two-player game of "[Bulls and Cows](https://en.wikipedia.org/wiki/Bulls_and_Cows)" (reincarnated in the seventies with pretty colours under the name "[Mastermind](https://en.wikipedia.org/wiki/Mastermind_(board_game))") the first player thinks up a four-digit secret number whose each digit must be different, for example 8723 or 9425. (For simplicity, we will not use the digit zero in this problem.) The second player tries to find this secret number by repeatedly guessing some four-digit number. After each guess, the first player reveals how many "bulls", the right digit in the right position, and "cows", the right digit but in the wrong position, that guess contains. For example, if the secret number is 1729, the guess 5791 contains one bull (the digit 7) and two cows (the digits 9 and 1). The guess 4385, on the other hand, contains no bulls or cows. 

This function should determine which numbers could still be the secret number. Given a list of `guesses` that have been completed, each individual guess given as a three-tuple `(guess, bulls, cows)`, this function should return the list of all four-digit numbers that are consistent with all these guesses, sorted in ascending order. Note that it is very much possible for the result list to be empty, if no four-digit integer is consistent with all of the `guesses`.

Start by creating a list of all four-digit numbers that do not contain any repeated digits. Loop through the individual guesses given, and for each guess, use a list comprehension to create a list of numbers that were in the previous list and are still consistent with the current guess. After you have done all that, oi jolly well then, old chap, "_When you have eliminated all which is impossible, then whatever remains, however improbable, must be the truth._" —Sherlock Holmes


<table>
  <tr>
   <td><code>guesses</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[(1234, 2, 2)]</code>
   </td>
   <td><code>[1243, 1324, 1432, 2134, 3214, 4231]</code>
   </td>
  </tr>
  <tr>
   <td><code>[(8765, 1, 0), (1234, 2, 1)]</code>
   </td>
   <td><code>[1245, 1263, 1364, 1435, 1724, 1732, 2734, 3264, 4235, 8134, 8214, 8231]</code>
   </td>
  </tr>
  <tr>
   <td><code>[(1234, 2, 2), (4321, 1, 3)]</code>
   </td>
   <td><code>[]</code>
   </td>
  </tr>
  <tr>
   <td><code>[(3127, 0, 1), (5723, 1, 0), (7361, 0, 2), (1236, 1, 0)]</code>
   </td>
   <td><code>[4786, 4796, 8746, 8796, 9746, 9786]</code>
   </td>
  </tr>
</table>


This problem and its myriad generalizations to an exponentially larger number of possibilities (for example, [otherwise the same game but played with English words](https://github.com/ikokkari/BullsAndCows)) can be solved in more clever and efficient ways than the above **brute force** enumeration. However, let that one remain a topic for a later course on advanced algorithms.


## **Sort list by element frequency**


```
def frequency_sort(items):
```


Sort the given list of integer `items` so that its elements end up in the order of **decreasing** **frequency**, that is, the number of times that they appear in `items`. If two elements occur with the same frequency, they should end up in the **ascending** order of their element values with respect to each other, as is the standard practice in sorting things.

The best way to solve this problem is to "Let George do it", or whichever way you wish to put this concept of passing the buck, by having the Python `sort` function perform the sorting against custom sorting criterion, as done in the example script <code>[countries.py](https://github.com/ikokkari/PythonExamples/blob/master/countries.py)</code>. Start by creating a dictionary to keep track of how many times each element occurs inside the array. Then, use these counts stored in that dictionary as the <strong>sorting key</strong> of the actual array elements, breaking ties on the frequency by using the actual element value.

(If you also happen to remember that the order comparison of Python tuples is **lexicographic**, you don't even have to exhaust yourself with the work needed to break these ties between two equally frequent values...)


<table>
  <tr>
   <td><code>items</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[4, 6, 2, 2, 6, 4, 4, 4]</code>
   </td>
   <td><code>[4, 4, 4, 4, 2, 2, 6, 6]</code>
   </td>
  </tr>
  <tr>
   <td><code>[4, 6, 1, 2, 2, 1, 1, 6, 1, 1, 6, 4, 4, 1]</code>
   </td>
   <td><code>[1, 1, 1, 1, 1, 1, 4, 4, 4, 6, 6, 6, 2, 2]</code>
   </td>
  </tr>
  <tr>
   <td><code>[17, 99, 42]</code>
   </td>
   <td><code>[17, 42, 99]</code>
   </td>
  </tr>
  <tr>
   <td><code>['bob','bob','carl','alex','bob']</code>
   </td>
   <td><code>['bob','bob','bob','alex','carl']</code>
   </td>
  </tr>
</table>





## **Calling all units, B-and-E in progress**


```
def is_perfect_power(n):
```


A positive integer `n` is a [perfect power](https://en.wikipedia.org/wiki/Perfect_power) if it can be expressed as the power `b**e` for some two integers `b` and `e` that are both **greater than one**. (Any positive integer `n` can always be expressed as the trivial power `n**1`, so we don't care about those.) For example, the integers 32, 125 and 441 are perfect powers since they equal `2**5`, `5**3` and `21**2`, respectively.

This function should determine whether the given positive integer `n` is a perfect power. Your function needs to somehow iterate through a sufficient number of possible combinations of `b` and `e` that could work, returning `True` right away when you find some `b` and `e` that satisfy `b**e == n`, and returning `False` when all possibilities for `b` and `e` have been tried and found wanting. Since `n` can get pretty large, your function should not examine too many combinations of `b` and `e` above and beyond those that are both necessary and sufficient to reliably determine the answer. Achieving this efficiency is the central educational point of this problem.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>42</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
  <tr>
   <td><code>441</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>469097433</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>12**34</code>
   </td>
   <td><code>True</code>
   </td>
  </tr>
  <tr>
   <td><code>12**34 - 1</code>
   </td>
   <td><code>False</code>
   </td>
  </tr>
</table>


The automated tester for this problem is based on the mathematical theorem about perfect powers that says that after the special case of two consecutive perfect powers 8 and 9, whenever the positive integer `n` is a perfect power, `n-1` cannot be a perfect power. This theorem makes it easy to generate pseudorandom test cases with known answers, both positive and negative. For example, we don't have to slog through all possible ways to express the number as an integer power to know right away that the behemoth `1234**5678 - 1` is not a perfect power.


## **The MD problem**


```
def md(a, b, n):
```


Consider an infinite series that starts with the value 1 at the first position 0, since in this problem we are again wearing the hats of computer scientists and our counting from zero, instead of starting counting from one like those dastardly mathematicians. Let `v` be the most recent element in the sequence. If the value of the integer division `v//a` is nonzero and has not appeared in the sequence so far, the next element of the sequence equals `v//a`. Otherwise the next element equals `b*v`. For example, when trying out parameter values `a=2` and `b=3` in spirit of the Collatz sequence, this sequence would start off as `[1, 3, 9, 4, 2, 6, 18, 54]`. 

Whenever the parameters `a` and `b` are positive and have no common factors higher than 1, this sequence can be proven to produce every positive integer exactly once, the values bouncing up and down in a chaotic spirit again very much reminiscent of the Collatz sequence. This function should return the position in the sequence where `n` makes its appearance.


<table>
  <tr>
   <td><code>a</code>
   </td>
   <td><code>b</code>
   </td>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>18</code>
   </td>
   <td><code>6</code>
   </td>
  </tr>
  <tr>
   <td><code>3</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>18</code>
   </td>
   <td><code>20</code>
   </td>
  </tr>
  <tr>
   <td><code>3</code>
   </td>
   <td><code>13</code>
   </td>
   <td><code>231</code>
   </td>
   <td><code>181</code>
   </td>
  </tr>
  <tr>
   <td><code>2</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>100000</code>
   </td>
   <td><code>175221</code>
   </td>
  </tr>
</table>


This problem was inspired by the page "[Unsolved Problems and Rewards](https://faculty.evansville.edu/ck6/integer/unsolved.html)" by Clark Kimberling. The "unsolved" part there was proving that every positive integer will appear exactly once, but then some guy proved that back in 2004 so that we all can just rely on that fact from now on. The goal of object-oriented design and programming is for us to become "mathematicians in spirit" so that **no problem would ever need to be solved twice**. Once some thorny problem has been successfully solved by somebody, it is sufficient to **reduce** your current problem into that problem to also declare your problem now solved. Furthermore, that same problem can be solved not just once but any number of times, just by placing a sufficiently strong for-loop around the code to solve it once...


## **Distribution of abstract bridge hand shapes**


```
def hand_shape_distribution(hands):
```


This is a continuation of the earlier "Bridge hand shape" problem that asked you to compute the shape of one given bridge hand. In that problem, the shapes `[6, 3, 2, 2]` and `[2, 3, 6, 2]` were considered different, as they very much would be in the actual bidding and play of the hand. However, in this combinatorial generalized version of this problem, we shall consider two hand shapes like these two to be the same _abstract shape_ if they are equal when we care only about the sorted counts of the suits, but don't care which particular suits they happen to be.

Given a list of bridge `hands`, each hand given as a list of 13 cards encoded the same way as in all of the previous card problems, create and return a Python dictionary that contains all abstract shapes that occur within `hands`, each shape mapped to its count of occurrences in `hands`. Note that Python dictionary keys cannot be lists (Python lists are mutable, and changing the contents of a dictionary key would break the internal ordering of the dictionary) so you need to represent the abstract hand shapes as immutable **tuples** that can be used as keys inside your dictionary.

As tabulated on "[Suit distributions](http://www.durangobill.com/BrSuitStats.html)" in "[Durango Bill's Bridge Probabilities and Combinatorics](http://www.durangobill.com/Bridge.html)", there exist precisely 39 possible abstract shapes of thirteen cards, the most common of which is 4-4-3-2, followed by the shape 5-3-3-2. Contrary to intuition, the most balanced possible hand shape 4-3-3-3 turns out to be surprisingly unlikely, trailing behind even the less balanced shapes 5-4-3-1 and 5-4-2-2 that one might have intuitively assumed to be far less frequent. ([Understanding why randomness tends to produce variance rather than converging to complete uniformity](https://en.wikipedia.org/wiki/Gambler%27s_fallacy) is a great aid in understanding many other counterintuitive truths about the behaviour of random processes in computer science and mathematics.)

For example, if it were somehow possible to give to your function the list of all 635,013,559,600 possible bridge hands and not run out of the heap memory in the Python virtual machine, the returned dictionary would contain 39 entries for the 39 possible hand shapes, two examples of these entries being `(4,3,3,3):66905856160` and `(6,5,1,1):4478821776`. (Our automated tester will try out your function with a much smaller list of pseudo-randomly generated bridge hands, but at least for the common hand types that you might expect to see every day at the daily duplicate of the local bridge club, [the percentage proportions really ought not be that different](https://en.wikipedia.org/wiki/Chebyshev%27s_inequality) from the exact answers if measured over a sufficiently large number of random hands.)


## **Flip of time**


```
def hourglass_flips(glasses, t):
```


An hourglass is given as a tuple `(u,l)` (the second character is the lowercase letter `L`, not the digit one) for the number of minutes in the upper and lower chamber. After `m` minutes have elapsed, the state of that hourglass will be `(u-min(u,m),l+min(u,m))` so that the total amount of sand remains constant inside the same hourglass, and neither chamber ever contains any negative anti-sand. Flipping the hourglass `(u,l)` produces the hourglass `(l,u)`, of course.

Given a list of `glasses`, each of form `(u,0)` so that all sand is initially in the upper chamber, and the amount of time `t` to be measured, you can only wait for the first hourglass to run out of time after its `u` minutes, since any eyeball estimation of hourglasses during these measurements is not allowed. Once the time in the chosen hourglass runs out, you may instantaneously flip **any subset** of these glasses (note that this subset can be empty as you are not required to flip any glasses, not even the one that just ran out of sand) to continue to measure the remaining time `t-u`.

This function should return **the smallest possible number of individual hourglass flips** that can exactly measure `t` minutes, or `None` if this task is impossible. The base cases of recursion are when `t` equals zero or exactly `t` minutes remain in some hourglass (no flips are needed), or when `t` is smaller than the time remaining in any hourglass (no solution is possible). Otherwise, wait for the first hourglass to run out after its `u` minutes, and loop through all possible subsets of your hourglasses, recursively trying each flipped subset to best measure the remaining `t-u` minutes.


<table>
  <tr>
   <td><code>glasses</code>
   </td>
   <td><code>t</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[(7, 0), (11, 0)]</code>
   </td>
   <td><code>15</code>
   </td>
   <td><code>2</code> (<a href="https://www.popularmechanics.com/science/math/a27496/riddle-of-the-week-33-the-hourglass-problem/">see here</a>)
   </td>
  </tr>
  <tr>
   <td><code>[(4, 0), (6, 0)]</code>
   </td>
   <td><code>11</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
  <tr>
   <td><code>[(7, 0), (4, 0), (11, 0)]</code>
   </td>
   <td><code>20</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>[(16, 0), (21, 0)]</code>
   </td>
   <td><code>36</code>
   </td>
   <td><code>6</code>
   </td>
  </tr>
  <tr>
   <td><code>[(5, 0), (8, 0), (13, 0)]</code>
   </td>
   <td><code>89</code>
   </td>
   <td><code>7</code>
   </td>
  </tr>
</table>


(Hint: the handy generator `itertools.product([0, 1], repeat=n)` produces all 2<sup><em>n</em></sup> possible `n`-element tuples made of `[0, 1]` to represent the possible subsets of `n` individual `glasses` that will be flipped for the recursive call.)


## **Fibonacci sum**


```
def fibonacci_sum(n):
```


[Fibonacci numbers](https://en.wikipedia.org/wiki/Fibonacci_number) are a cliché in introductory computer science, especially in teaching recursion where this famous combinatorial series is mainly used to reinforce the belief that recursion is silly... but all clichés became clichés in the first place because they were so good that everyone and their brother kept using them! Let us therefore rather traipse around the [Zeckendorf's theorem](https://en.wikipedia.org/wiki/Zeckendorf%27s_theorem), a more amazing property of these famous numbers: **every positive integer can be expressed exactly one way as a sum of distinct non-consecutive Fibonacci numbers**.

The simple **greedy algorithm** can be proven to always produce the desired breakdown of `n` into a sum of distinct non-consecutive Fibonacci numbers: always add into the list the largest possible Fibonacci number `f` that is at most equal to `n`. Then convert the rest given by `n-f` in this same manner, until nothing remains to be converted. To allow for automated testing, the list of Fibonacci numbers must be returned sorted in **descending** order. 


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>[8, 2]</code>
   </td>
  </tr>
  <tr>
   <td><code>100</code>
   </td>
   <td><code>[89, 8, 3]</code>
   </td>
  </tr>
  <tr>
   <td><code>1234567</code>
   </td>
   <td><code>[832040, 317811, 75025, 6765, 2584, 233, 89, 13, 5, 2]</code>
   </td>
  </tr>
  <tr>
   <td><code>10**10</code>
   </td>
   <td><code>[7778742049, 1836311903, 267914296, 102334155, 9227465, 3524578, 1346269, 514229, 75025, 6765, 2584, 610, 55, 13, 3, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>10**100</code>
   </td>
   <td>(a list of 137 terms, the largest of which starts with digits <code>921684571</code>)
   </td>
  </tr>
</table>


Note how this greedy construction guarantees that the chosen Fibonacci numbers are distinct and cannot contain two consecutive Fibonacci numbers _F<sub>i</sub>_ and _F<sub>i+1</sub>_, since otherwise also their sum _F<sub>i+2</sub>_ would have fit inside _n_ and been used instead of _F<sub>i+1</sub>_ and thus would have prevented the use of _F<sub>i+1</sub>_ with the same argument. A curious kind of proof of **infinite ascent** towards the unknown but finite upper bound _n_ in a "well-topped" sequence...


## **Wythoff array**


```
def wythoff_array(n):
```


[Wythoff array](https://mathworld.wolfram.com/WythoffArray.html) (see [the Wikipedia article](https://en.wikipedia.org/wiki/Wythoff_array) for illustration) is an infinite two-dimensional grid of integers that is seeded with one and two to start the first row. In each row, each element equals the sum of the previous two elements, so the first row contains precisely the Fibonacci numbers.

The first element of each later row is **the smallest integer <code>c</code> that does not appear anywhere in the previous rows</strong>. Since every row is strictly ascending, you can find this out without having to slog through an infinite number of elements. To determine the second element of that row, let <code>a</code> and <code>b</code> be the first two elements of the previous row. If the difference <code>c-a</code> equals two, the second element of that row equals <code>b+3</code>, and otherwise that element equals <code>b+5</code>. This construction guarantees the Wythoff array to be an <strong>interspersion</strong> of positive integers; every positive integer will appear <strong>exactly once</strong> in this infinite grid, with no gaps or duplicates! (This result nicely highlights the deeper combinatorial importance of the deceptively simple Fibonacci numbers as potential building blocks of other integers and integer sequences.)

The difficulty in this problem is determining the first two elements in each row after the first row, since once you know those first two values, the rest of the row is utterly trivial to generate as far as you need. This function should return the position of `n` inside the Wythoff array as a tuple of form `(row, column)`, both row and column numbers starting from zero. 


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>21</code>
   </td>
   <td><code>(0, 6)</code>
   </td>
  </tr>
  <tr>
   <td><code>47</code>
   </td>
   <td><code>(1, 5)</code>
   </td>
  </tr>
  <tr>
   <td><code>1042</code>
   </td>
   <td><code>(8, 8)</code>
   </td>
  </tr>
  <tr>
   <td><code>424242</code>
   </td>
   <td><code>(9030, 6)</code>
   </td>
  </tr>
  <tr>
   <td><code>39088169</code>
   </td>
   <td><code>(0, 36)</code>
   </td>
  </tr>
  <tr>
   <td><code>39088170</code>
   </td>
   <td><code>(14930352, 0)</code>
   </td>
  </tr>
</table>





## **Rooks with friends**


```
def rooks_with_friends(n, friends, enemies):
```


Those dastardly rooks have once again gone on a rampage on a generalized _n_-by-_n_ chessboard, just like in the earlier problem of counting how many squares were safe from their occupants being pulverized into dust under the rolling wrath of these lumbering juggernauts. Each rook is again represented as a tuple `(row, column)` of the coordinates of the square it stands on. However, in this version of the problem, some of these rooks are your **friends** (same colour as you) while the others are your **enemies** (the opposite colour from you).

Friendly rooks protect the chess squares by standing between them and any enemy rooks that might want to threaten those squares. An enemy rook can attack only those squares in the same row or column that do not enjoy the protection of any friendly rook standing between them. Given the board size `n` and the lists of `friends` and `enemies`, count how many empty squares on the board are safe from the enemy rooks. 


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>friends</code>
   </td>
   <td><code>enemies</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>4</code>
   </td>
   <td><code>[(2,2), (0,1), (3,1)]</code>
   </td>
   <td><code>[(3,0), (1,2), (2,3)]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>4</code>
   </td>
   <td><code>[(3,0), (1,2), (2,3)]</code>
   </td>
   <td><code>[(2,2), (0,1), (3,1)]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>8</code>
   </td>
   <td><code>[(3,3), (4,4)]</code>
   </td>
   <td><code>[(3,4), (4,3)]</code>
   </td>
   <td><code>48</code>
   </td>
  </tr>
  <tr>
   <td><code>100</code>
   </td>
   <td><code>[(r, (3*r+5) % 100) for r in range(1, 100, 2)]</code>
   </td>
   <td><code>[(r, (4*r+32) % 100) for r in range(0, 100, 2)]</code>
   </td>
   <td><code>3811</code>
   </td>
  </tr>
</table>


 


## **Possible words in Hangman**


```
def possible_words(words, pattern):
```


Given a list of possible `words`, and a `pattern` string that is guaranteed to contain only lowercase English letters `a` to `z` and asterisk characters `*`, create and return a sorted list of words that match the `pattern` in the sense of the famous pen-and-paper guessing game of [Hangman](https://en.wikipedia.org/wiki/Hangman_(game)).

Any `pattern` can only match words of the exact same length. In all positions where the `pattern` contains some letter, the word must contain that same letter. In positions where the `pattern` contains an asterisk, the word character in that position may not be any of the letters that explicitly occur inside the pattern. In the game of Hangman, all occurrences of such a letter would have already been revealed in the earlier round where that letter was the current guess.

For example, the words `'bridge'` and `'smudge'` both match the pattern `'***dg*'`. However, the words `'grudge'` and '`dredge`' would **not** match that same pattern, since the first asterisk may not be matched with either of the letters `'g'` or `'d'` that appear inside the `pattern`.


<table>
  <tr>
   <td><code>pattern</code>
   </td>
   <td>Expected result (using wordlist <code>words_sorted.txt</code>)
   </td>
  </tr>
  <tr>
   <td><code>'***dg*'</code>
   </td>
   <td><code>['abedge', 'aridge', 'bludge', 'bridge', 'cledge', 'cledgy', 'cradge', 'fledge', 'fledgy', 'flidge', 'flodge', 'fridge', 'kludge', 'pledge', 'plodge', 'scodgy', 'skedge', 'sledge', 'slodge', 'sludge', 'sludgy', 'smidge', 'smudge', 'smudgy', 'snudge', 'soudge', 'soudgy', 'squdge', 'squdgy', 'stodge', 'stodgy', 'swedge', 'swidge', 'trudge', 'unedge']</code>
   </td>
  </tr>
  <tr>
   <td><code>'*t*t*t*'</code>
   </td>
   <td><code>['statute']</code>
   </td>
  </tr>
  <tr>
   <td><code>'a**s**a'</code>
   </td>
   <td><code>['acystia', 'acushla', 'anosmia']</code>
   </td>
  </tr>
  <tr>
   <td><code>'*ikk**'</code>
   </td>
   <td><code>['dikkop', 'likker', 'nikkud', 'tikker', 'tikkun']</code>
   </td>
  </tr>
</table>





## **Factoring factorials**


```
def factoring_factorial(n):
```


The [fundamental theorem of arithmetic](https://en.wikipedia.org/wiki/Fundamental_theorem_of_arithmetic) tells us that every positive integer can be broken down to the product of its **prime factors **in exactly one way. Given a positive integer `n > 1`, create and return a list that contains all prime factors of `n!`, the product of all positive integers up to `n`, along with their exponents in the prime factorization. These prime factors should be listed in ascending order, each prime factor given as tuple `(p, e)` where `p` is the prime factor and `e` its exponent.

Since `n` will get into the thousands in the automated tester, you should accumulate the prime factors of `n!` separately for each individual term of the factorial as you go, rather than first computing the entire `n!` and only then chopping down that gargantuan beast back into its prime factors.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>5</code>
   </td>
   <td><code>[(2, 3), (3, 1), (5, 1)]</code>
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>[(2, 8), (3, 4), (5, 2), (7, 1)]</code>
   </td>
  </tr>
  <tr>
   <td><code>20</code>
   </td>
   <td><code>[(2, 18), (3, 8), (5, 4), (7, 2), (11, 1), (13, 1), (17, 1), (19, 1)]</code>
   </td>
  </tr>
  <tr>
   <td><code>100</code>
   </td>
   <td><code>[(2, 97), (3, 48), (5, 24), (7, 16), (11, 9), (13, 7), (17, 5), (19, 5), (23, 4), (29, 3), (31, 3), (37, 2), (41, 2), (43, 2), (47, 2), (53, 1), (59, 1), (61, 1), (67, 1), (71, 1), (73, 1), (79, 1), (83, 1), (89, 1), (97, 1)]</code>
   </td>
  </tr>
  <tr>
   <td><code>1000</code>
   </td>
   <td>(a list that contains a total of 168 terms, the first five of which are <code>[(2, 994), (3, 498), (5, 249), (7, 164), (11, 98)]</code>)
   </td>
  </tr>
  <tr>
   <td><code>10000</code>
   </td>
   <td>(a list that contains a total of 1229 terms, the first five of which are <code>[(2, 9995), (3, 4996), (5, 2499), (7, 1665), (11, 998)]</code> ) 
   </td>
  </tr>
</table>





## **Aliquot sequence**


```
def aliquot_sequence(n, giveup=100):
```


The **proper divisors** of a positive integer `n` are those positive integers that exactly divide `n` and are strictly less than `n`. For example, the proper divisors of 12 are 1, 2, 3, 4 and 6. The [Aliquot sequence](https://en.wikipedia.org/wiki/Aliquot_sequence) for the positive integer `n` starts from `n`, after which each term equals the sum of the proper divisors of the previous term. For example, starting from 12, the next term in this sequence would be 1 + 2 + 3 + 4 + 6 = 16. The next term after that is computed by adding up the proper divisors of 16, giving us 1 + 2 + 4 + 8 = 15, and so on.

The Aliquot sequence terminates either when it reaches zero, or at the appearance of some term that has already shown up earlier in that same sequence, after which the sequence would simply continue forever in that same cycle. Both possibilities can be achieved with a suitable choice of `n`. In the same spirit as the more famous [Collatz sequence](https://en.wikipedia.org/wiki/Collatz_conjecture) previously seen in the <code>[mathproblems.py](https://github.com/ikokkari/PythonExamples/blob/master/mathproblems.py)</code> in-class example, it is currently unknown whether there exists some starting number <code>n</code> for which this sequence will go on forever without ever repeating itself. Just to be safe, this function should stop once the sequence length becomes equal to <code>giveup</code>.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>giveup</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>12</code>
   </td>
   <td><code>100</code>
   </td>
   <td><code>[12, 16, 15, 9, 4, 3, 1, 0]</code>
   </td>
  </tr>
  <tr>
   <td><code>34</code>
   </td>
   <td><code>100</code>
   </td>
   <td><code>[34, 20, 22, 14, 10, 8, 7, 1, 0]</code>
   </td>
  </tr>
  <tr>
   <td><code>34</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>[34, 20]</code>
   </td>
  </tr>
</table>





## **All paths lead to Rome**


```
def lattice_paths(x, y, tabu):
```


You are standing on the point `(x, y)` in the **lattice grid** of pairs of nonnegative integers, and wish to make your way to the **origin** point `(0, 0)`. At any given point, you are only allowed to move either one step left or one step down. Furthermore, you are never allowed to step into any of the points in the `tabu` list. This function should add up the number of different paths that lead from the point `(x, y)` to the origin `(0, 0)` under these constraints.

This constrained variation of the classic combinatorial problem turns out to have a reasonably straightforward recursive solution. As the base case, the number of paths from the origin `(0, 0)` to itself `(0, 0)` equals one, for the empty path. If the point `(x, y)` is in the `tabu` list, the number of paths from that point `(x, y)` to the origin equals zero. The same holds for all points whose either coordinate `x` or `y` is negative. Otherwise, the number of paths from the point `(x, y)` to origin `(0, 0)` equals the sum of paths from the two neighbours `(x-1, y)` and `(x, y-1)`.

However, this simple recursion branches into an exponential number of possibilities and would therefore be far too slow for us to execute. Therefore, you should either **memoize** the recursion, or even better, build up a two-dimensional list whose entries are the individual subproblem solutions, and fill this list with two `for`-loops instead of recursion, these loops filling the list in order that when these loops arrive at position `[x][y]`, the results for positions `[x-1][y]` and `[x][y-1]` have already been computed. (This idea to use loops to fill out the memoization tables with for-oops instead of recursion is called **dynamic programming**.)


<table>
  <tr>
   <td><code>x</code>
   </td>
   <td><code>y</code>
   </td>
   <td><code>tabu</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>3</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>[]</code>
   </td>
   <td><code>20</code>
   </td>
  </tr>
  <tr>
   <td><code>3</code>
   </td>
   <td><code>4</code>
   </td>
   <td><code>[(2,2)]</code>
   </td>
   <td><code>17</code>
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>[(6, 1), (2, 3)]</code>
   </td>
   <td><code>2063</code>
   </td>
  </tr>
  <tr>
   <td><code>6</code>
   </td>
   <td><code>8</code>
   </td>
   <td><code>[(4,3), (7,3), (7,7), (1,5)]</code>
   </td>
   <td><code>1932</code>
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>10</code>
   </td>
   <td><code>[(0,1)]</code>
   </td>
   <td><code>92378</code>
   </td>
  </tr>
  <tr>
   <td><code>100</code>
   </td>
   <td><code>100</code>
   </td>
   <td><code>[(0,1), (1,0)]</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
</table>





## **Be there or be square**


```
def count_squares(points):
```


This problem is adapted from "[Count the Number of Squares](https://challenges.wolfram.com/challenge/count-the-number-of-squares)" at [Wolfram Challenges](https://challenges.wolfram.com/), so you might first want to check that page out for some illustrative visualizations of this problem.

Your function is given a `set` of `points`, each point a two-tuple `(x, y)` where `x` and `y` are positive integers. This function should count how many **squares** these points define so that all four corners of the square belong to the given set of `points`, and return this count. Note that these squares are not required to be **axis-aligned** so that their sides would have to be either horizontal and vertical. As long as all four sides have the exact same length, be that length an exact integer or some ir_ratio_nal number, well, that makes us "square" at least in my book, pardner.

To identify four points that constitute a square, note how every square has **bottom left corner** point `(x, y)` and **direction vector** `(dx, dy)` towards its upper left corner point that satisfies the constraints `dx >= 0` and `dy > 0`, so that the three points `(x+dx, y+dy)`, `(x+dy, y-dx)` and `(x+dx+dy, y-dx+dy)` are the top left, bottom right and top right corners of that square, respectively, all these included in `points`. You can therefore loop through all possibilities for the bottom left point `(x, y)` and direction vector `(dx, dy)` to find all squares in the grid. Try to be economical in these loops to make this function sweep up all these squares swiftly.


<table>
  <tr>
   <td><code>points</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[(0,0), (1,0), (2,0), (0,1), (1,1), (2,1), (0,2), (1,2), (2,2)]</code>
   </td>
   <td><code>6</code>
   </td>
  </tr>
  <tr>
   <td><code>[(4,3), (1,1), (5,3), (2,3), (3,2), (3,1), (4,2), (2,1), (3,3), (1,2), (5,2)]</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>[(x, y) for x in range(1, 10) for y in range(1, 10)]</code>
   </td>
   <td><code>540</code>
   </td>
  </tr>
  <tr>
   <td><code>[(3,4), (1,2), (3,2), (4,5), (4,2), (5,3), (4,1), (5,4), (3, 5), (2,4), (2,2), (1,1), (4,4), (2,5), (1,5), (2,1), (2,3), (4, 3)]</code>
   </td>
   <td><code>15</code>
   </td>
  </tr>
</table>





## **Split within perimeter bound**


```
def perimeter_limit_split(a, b, p):
```


Rectangles are represented as tuples `(a, b)` where `a` and `b` are positive integers. A rectangle can be cut into two smaller rectangles with the same total area using either a straight horizontal or a straight vertical cut along the integer axis of your choice. For example, one way among all possible ways to cut the rectangle `(5, 8)` is to cut it into `(2, 8)` and `(3, 8)` in the first dimension. Another way would be to cut it into `(5, 4)` and `(5, 4)` in the second dimension. These smaller pieces can then be further cut into smaller pieces, as long as the length of the side being cut is at least two. Also, at the risk of disappointing any lateral thinkers reading this, you are not allowed to cut multiple pieces in one cutting motion by stacking those pieces on top of each other. 

Your task is to cut the given initial rectangle `(a, b)` into smaller pieces until the **perimeter** of each individual piece `2*(a+b)` is at most equal to `p`, the maximum allowed perimeter length. Since the optimal cuts are not generally unique, this function should compute and return the minimum number of cuts necessary to achieve some optimum result.

This problem is best solved with recursion. If the perimeter of the current piece is within the limit `p`, return zero. Otherwise, loop through all possible ways to cut this piece into two smaller pieces, and recursively compute the best possible ways to cut up the resulting two pieces with `m1` and `m2` moves, respectively. Return the smallest value that you see for `1 + m1 + m2`. Since this branching recursion will visit its subproblems an exponential number of times, you might want to sprinkle some `@lru_cache` memoization on top of it, to rein in that exponential tangle a bit.


<table>
  <tr>
   <td><code>a</code>
   </td>
   <td><code>b</code>
   </td>
   <td><code>p</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>11</code>
   </td>
   <td><code>1</code>
   </td>
   <td><code>12</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>9</code>
   </td>
   <td><code>13</code>
   </td>
   <td><code>5</code>
   </td>
   <td><code>116</code>
   </td>
  </tr>
  <tr>
   <td><code>8</code>
   </td>
   <td><code>31</code>
   </td>
   <td><code>14</code>
   </td>
   <td><code>20</code>
   </td>
  </tr>
  <tr>
   <td><code>91</code>
   </td>
   <td><code>21</code>
   </td>
   <td><code>54</code>
   </td>
   <td><code>11</code>
   </td>
  </tr>
  <tr>
   <td><code>201</code>
   </td>
   <td><code>217</code>
   </td>
   <td><code>307</code>
   </td>
   <td><code>7</code>
   </td>
  </tr>
</table>





## **Sum of distinct cubes**


```
def sum_of_distinct_cubes(n):
```


Positive integers can often be expressed as sums of **distinct** cubes of **positive** integers, many of them even in multiple ways. This function should find and return the list of distinct cubes whose sum equals the given positive integer `n`. Should `n` allow several breakdowns into sums of distinct cubes, this function must return the **lexicographically highest** solution that starts with the largest possible first number `a` and is from there followed by the lexicographically largest representation of the rest of the number `n-a*a*a`. For example, when called with `n = 1072`, this function should return `[10, 4, 2]` instead of `[9, 7]`. Whenever it is impossible to break the parameter `n` into a sum of distinct cubes, return `None`.

Unlike in the earlier, much simpler question of expressing `n` as a sum of exactly two squares, the result can now contain any number of distinct terms. This problem, like almost all such problems that cause an exponential blowup of two-way "take it or leave it" decisions, is usually best solved with recursion that examines both branches of each such decision and returns the one that gives a better result. The base case is when `n` itself is a cube. Otherwise, loop down through all possible values of the first element `a` in the result list, and for each such `a`, break down the remaining number `n-a*a*a` into a sum of distinct cubes using only integers that are smaller than your current `a`. Again, to make your function gleam these cubes efficiently even for large `n`, it might be good to prepare something that allows you to quickly determine whether the given integer is a cube, and whenever it is not, to find the largest integer whose cube is smaller...


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>8</code>
   </td>
   <td><code>[2]</code>
   </td>
  </tr>
  <tr>
   <td><code>11</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
  <tr>
   <td><code>855</code>
   </td>
   <td><code>[9, 5, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>sum([x*x*x for x in range(11)]</code>
   </td>
   <td><code>[14, 6, 4, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>sum([x*x*x for x in range(1001)])</code>
   </td>
   <td><code>[6303, 457, 75, 14, 9, 7, 5, 4]</code>
   </td>
  </tr>
</table>


This problem is intentionally restricted to positive integers to keep the number of possibilities to iterate finite. Since the cube of a negative number is also negative, a finite upper bound for search no longer exists if negative numbers are allowed, and breaking some small and simple number into a sum of exactly three cubes can suddenly blow up to a [highly nontrivial problem...](https://www.quantamagazine.org/sum-of-three-cubes-problem-solved-for-stubborn-number-33-20190326/)


## **Fractional fit**


```
def fractional_fit(fs):
```


You are given a list of integer two-tuples `(a, b)` so that `0 &lt;= a &lt; b`. When interpreted as an integer fraction from the expression `f = fraction(a, b)`, these values fall within the unit interval. Given the list `fs` of available fractions, find the length of the longest possible list that can be constructed from those fractions under the following series of constraints:



*   The first _two_ fractions must lie in different _halves_ of the unit interval. That is, one of them must satisfy `0 &lt;= f &lt; 1/2`, and the other one must satisfy `1/2 &lt;= f &lt; 1`.
*   The first _three_ fractions must all lie in different _thirds_ of the unit interval.
*   The first _four_ fractions must all lie in different _quarters_ of the unit interval.
*   The first _five_ fractions must all lie in different _fifths_...  and so on!

Your function should return the length of the longest possible such list. Note how the order of your chosen fractions in this list is important. For example, `[(1, 4), (8, 9), (3, 7)]` works, but the order `[(3, 7), (1, 4), (8, 9)]` does not work, since both fractions 3/7 and 1/4 lie on the first half of the unit interval.


<table>
  <tr>
   <td><code>fs</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[(6, 12), (0, 5), (5, 7), (4, 11)]</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>[(5, 15), (0, 5), (7, 19), (17, 23), (5, 18), (10, 11)]</code>
   </td>
   <td><code>4</code>
   </td>
  </tr>
  <tr>
   <td><code>[(34, 52), (61, 82), (71, 80), (36, 76), (15, 84), (36, 53), (79, 80), (5, 67), (31, 62), (15, 57)]</code>
   </td>
   <td><code>6</code>
   </td>
  </tr>
  <tr>
   <td><code>[(171, 202), (41, 42), (43, 85), (164, 221), (97, 130), (12, 23), (15, 62), (41, 128), (11, 25), (31, 49), (6, 35), (85, 137), (16, 241), (82, 225), (11, 26), (74, 149), (127, 203)]</code>
   </td>
   <td><code>10</code>
   </td>
  </tr>
</table>


The Martin Gardner column from the Bulgarian solitaire problem also discussed this puzzle, but as an example of a seemingly unlimited process where it turns out that even if you were allowed to freely choose your fractions, every such sequence will inevitably paint itself into a corner after at most 17 steps. No matter how you twist and turn, two of these fractions will inevitably fall on the same 1/18th of the unit interval, thus making your next chosen fraction, if you pardon a dad joke better suited for a "[Jumble](https://en.wikipedia.org/wiki/Jumble)" newspaper puzzle, a "moot point".


## **Followed by its square**

`def square_follows(it)`:

Unlike our previous functions that receive entire lists as parameters, this function receives some Python **iterator** guaranteed to produce some finite sequence of **strictly increasing positive integers**, but gives no guarantees of how long that sequence will be, and how large the numbers inside it or the gaps between them could grow to be. This iterator **is not a list** that would allow you **random access** to any element based on its position and this way lets you jump back and forth as your heart desires. Therefore, processing the elements given by this iterator must be done in a strictly sequential fashion, although you can use any available Python data structures to keep track of whatever intermediate results you need to store for your future decisions.

This function should create and return an ordinary Python list that contains, in ascending order, precisely those elements inside the sequence produced by the parameter iterator `it` whose square also appears somewhere later in that sequence. 


<table>
  <tr>
   <td><code>it</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>iter([3, 4, 6, 8, 11, 13, 18])</code>
   </td>
   <td><code>[]</code>
   </td>
  </tr>
  <tr>
   <td><code>iter([2, 3, 4, 5, 8, 9, 11, 16])</code>
   </td>
   <td><code>[3, 4]</code>
   </td>
  </tr>
  <tr>
   <td><code>iter(range(1, 10**6))</code>
   </td>
   <td>(a list that consists of exactly 998 elements, the first five of which are <code>[2, 3, 4, 5, 6]</code> and the last five are <code>[995, 996, 997, 998, 999]</code>)
   </td>
  </tr>
  <tr>
   <td><code>iter([x*x for x in range(1, 1000)])</code>
   </td>
   <td><code>[4, 9, 16, 25, 36, 49, 64, 81, 100, 121, 144, 169, 196, 225, 256, 289, 324, 361, 400, 441, 484, 529, 576, 625, 676, 729, 784, 841, 900, 961]</code>
   </td>
  </tr>
  <tr>
   <td><code>iter([x**10 for x in range(1, 100)])</code>
   </td>
   <td><code>[1024, 59049, 1048576, 9765625, 60466176, 282475249, 1073741824, 3486784401]</code>
   </td>
  </tr>
</table>





## **Count maximal layers**


```
def count_maximal_layers(points):
```


A point `(x1, y1)` on the two-dimensional plane **dominates** another point `(x2, y2)` if both inequalities `x1 > x2` and `y1 > y2` hold. A point inside the given list of `points` is **maximal** if it is not dominated by any other point in the list. A maximal point does not need to dominate every other point; there can even exist maximal points that do not dominate any other point in the list! Unlike in one dimension, a list of points on the two-dimensional plane can contain any number of maximal points, which then form the **maximal layer** for that particular list of points. For example, the points `(3, 10)` and `(9, 2)` are the maximal layer for the five points `[(1, 5), (8, 1), (3, 10), (2, 1), (9, 2)]`. 

Given a list of `points` from the upper right quadrant of the infinite two-dimensional plane so that all coordinates are guaranteed to be nonnegative, this function should compute how many times one would have to remove every point in the current maximal layer from the list for that list to become empty, and return that count.


<table>
  <tr>
   <td><code>points</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[(1, 3), (2, 2), (3, 1)]</code>
   </td>
   <td><code>1</code>
   </td>
  </tr>
  <tr>
   <td><code>[(1, 5), (3, 10), (2, 1), (9, 2)]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>[(x, y) for x in range(10) for y in range(10)]</code>
   </td>
   <td><code>10</code>
   </td>
  </tr>
  <tr>
   <td><code>[(x, x**2) for x in range(100)]</code>
   </td>
   <td><code>100</code>
   </td>
  </tr>
  <tr>
   <td><code>[(x, x**2 % 91) for x in range(1000)]</code>
   </td>
   <td><code>28</code>
   </td>
  </tr>
  <tr>
   <td><code>[((x**3) % 891, (x**2) % 913) for x in range(10000)] </code>
   </td>
   <td><code>124</code>
   </td>
  </tr>
</table>


This is again one of those problems whose point (heh) and motivation is making this function fast enough to finish reasonably quickly even for a large list of points, and not do too much more work than necessary to identify and remove the current maximal points. Start by noticing that each point can potentially be dominated only by those points whose distance from the origin `(0, 0)` is strictly larger. It doesn't even matter which particular distance metric you use...


## **Maximum checkers capture**


```
def max_checkers_capture(n, x, y, pieces):
```


Even though we again find ourselves on a generalized _n_-by-_n_ chessboard, this time we are playing a variation of [checkers](https://en.wikipedia.org/wiki/Draughts) so that your lone **king **currently stands at the coordinates `(x, y)`, and the parameter `pieces` is a `set` that contains the positions of all of the opponent's pawn pieces. This function should compute and return the maximum number of pieces that your king could potentially capture in a single move.

Some variants of checkers allow **leaping kings** that can capture pieces across arbitrary distances. For simplicity, our humble kings can capture a piece only one step away to the four **diagonal directions** (the list `[(-1, 1), (1, 1), (1, -1), (-1, -1)]` might come handy) when the square behind the opponent piece in that diagonal direction exists and is vacant. Your king can then capture that piece by jumping over it into that vacant square, **immediately removing the captured piece from the board**. However, unlike in chess where each move can capture at most one enemy piece, the chain of captures continues from the square that your king jumps into, as long as more opponent pieces are available for capture.

The maximum number of pieces available for capture in one move is best computed with a method that locally loops through the four diagonal directions from the current position of the king. For each such direction that contains an opponent piece with a vacant space behind it, remove that opponent piece from the board, and **recursively** compute the number of pieces that can be captured from the vacant square that your king jumps into. Once that recursive call has returned, restore the first captured piece on the board, and continue looping to the next diagonal direction. Return the largest number that can be achieved from the four possible directions for the first capture, plus one for the piece captured first.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td><code>x</code>
   </td>
   <td><code>y</code>
   </td>
   <td><code>pieces</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>5</code>
   </td>
   <td><code>0</code>
   </td>
   <td><code>2</code>
   </td>
   <td><code>set([(1,1), (3,1), (1,3)]</code>
   </td>
   <td><code>2</code>
   </td>
  </tr>
  <tr>
   <td><code>7</code>
   </td>
   <td><code>0</code>
   </td>
   <td><code>0</code>
   </td>
   <td><code>set([(1,1), (1,3), (3,3), (2,4), (1,5)])</code>
   </td>
   <td><code>3</code>
   </td>
  </tr>
  <tr>
   <td><code>8</code>
   </td>
   <td><code>7</code>
   </td>
   <td><code>0</code>
   </td>
   <td><code>set([(x, y) for x in range(2, 8, 2) for y in range(1, 7, 2)])</code>
   </td>
   <td><code>9</code>
   </td>
  </tr>
</table>





## **Collatzy distance**


```
def collatzy_distance(start, end):
```


Let us make up a rule that says that from a positive integer `n`, you are allowed to move in a single step into either integer `3*n+1` or `n//2`. Even though these formulas were obviously inspired by the [Collatz conjecture](https://en.wikipedia.org/wiki/Collatz_conjecture) that we encountered in class and some earlier problems, in this problem the parity of `n` does not restrict you to deterministically use just one of these formulas, but you may use either formula regardless of whether your current `n` is odd or even. This function should determine how many steps are needed to get from `start` to `end`, assuming that you wisely choose each step to minimize the total number of steps in the path.

This problem can be solved with **breadth-first search** the following way, given here as a sneaky preview for the later course that explains that and other **graph traversal** algorithms. For the given `start` value, the zeroth **layer** is the singleton list `[start]`. Once you have computed layer `k`, the next layer `k+1` consists of all integers `3*n+1` and `n//2` where `n` goes through all numbers in the previous layer `k`. For example, if `start = 4`, the first four layers numbered from zero to three would be `[4]`, `[13, 2]`, `[40, 6, 7, 1]` and `[121, 20, 19, 3, 22, 0]`, the elements inside each layer possibly listed in some other order as your code found them.

Then, keep generating layers from the previous layer inside a while-loop until the goal number `end` appears, at which point you can immediately return the current layer number as the answer.


<table>
  <tr>
   <td><code>start</code>
   </td>
   <td><code>end</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>20</code>
   </td>
   <td><code>7</code>
   </td>
  </tr>
  <tr>
   <td><code>42</code>
   </td>
   <td><code>42</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>42</code>
   </td>
   <td><code>43</code>
   </td>
   <td><code>13</code>
   </td>
  </tr>
  <tr>
   <td><code>76</code>
   </td>
   <td><code>93</code>
   </td>
   <td><code>23</code>
   </td>
  </tr>
  <tr>
   <td><code>1000</code>
   </td>
   <td><code>10</code>
   </td>
   <td><code>9</code>
   </td>
  </tr>
</table>


Once you get this function to work correctly, you can think up clever ways to speed up its execution. For starters, notice that any integers that have already made an appearance in an earlier layer before the current layer can be ignored while constructing the current layer.


## **Van Eck sequence**


```
def van_eck(n):
```


Compute and return the _n_:th term of the [Van Eck sequence](https://oeis.org/A181391). The first term in the first position _i_ = 0 equals zero. The term in later position _i_ is determined by the term _x_ in the previous position _i_ - 1:



*   If the position _i_ - 1 was the first appearance of that term _x_, the term in the current position _i_ equals zero.
*   Otherwise, if the previous term _x_ has now appeared at least twice in the sequence, the term in the current position _i_ is given by the position difference _i_ - 1 - _j_, where _j_ is the position of the second most recent appearance of the term _x_.

The sequence begins with 0, 0, 1, 0, 2, 0, 2, 2, 1, 6, 0, 5, 0, 2, 6, 5, 4, 0, 5, 3, 0, 3, 2, 9, ... so you see how terms start making repeated appearances right away, especially the zero that automatically follows the first appearance of each term.

In the same spirit as in the earlier problem that asked you to generate terms of the [Recamán's sequence](http://mathworld.wolfram.com/RecamansSequence.html), unless you want to spend the rest of your day waiting for the automated tester to finish, this function should not repeatedly loop backwards through the already generated sequence to look for the most recent occurrence of each term that it generates. You should rather use a Python dictionary to remember the terms already seen in the sequence, mapped to the positions of their most recent appearance. With this dictionary, you don't need to explicitly store the entire sequence, but only the previous terms and positions that are relevant for the future.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>0</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>1000</code>
   </td>
   <td><code>61</code>
   </td>
  </tr>
  <tr>
   <td><code>10**6</code>
   </td>
   <td><code>8199</code>
   </td>
  </tr>
  <tr>
   <td><code>10**8</code>
   </td>
   <td><code>5522779</code>
   </td>
  </tr>
</table>





## **Next higher zigzag**


```
def next_zigzag(n):
```


The definition of **zigzag numbers** is exactly the same as in the earlier problem that asked you to identify whether the given number is a zigzag number. In this problem, the function is given a positive integer `n` that **is guaranteed to be a zigzag number**. This function should return the positive integer `m > n` that is **the next higher zigzag number** up the line, so that none of the numbers strictly between `n` and `m` is a zigzag number.

This problem could in principle be solved by counting up from `n+1` and using your earlier `is_zigzag` function to determine whether you have reached the next higher zigzag number. Unfortunately, as you can see in the table below, the gaps between consecutive zigzag numbers grow up to become arbitrarily large, so you need some more analytical approach based on the digit pattern found at the end of the number. This digit pattern might also be arbitrarily long before it allows you to decide where the next zigzag number lies, but that is why loops exist...


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>801</code>
   </td>
   <td><code>802</code>
   </td>
  </tr>
  <tr>
   <td><code>1082845</code>
   </td>
   <td><code>1082846</code>
   </td>
  </tr>
  <tr>
   <td><code>92398</code>
   </td>
   <td><code>92401</code>
   </td>
  </tr>
  <tr>
   <td><code>27398</code>
   </td>
   <td><code>27450</code>
   </td>
  </tr>
  <tr>
   <td><code>89292523198989898</code>
   </td>
   <td><code>89292523230101010</code>
   </td>
  </tr>
</table>





## **Tips and trips**


```
def trips_fill(words3, pattern, tabu):
```


Define a string of lowercase letters in English whose length is three or more to be **trip-filled** if every 3-substring (a "trip") inside it is a three-letter word from `words3`, the list of such words in sorted order. Some trip-filled strings would be `'pacepad'`, `'baganami'` and `'udianaahunat'`, provided that we get to use the more obscure words from `words_sorted.txt`. Given a `pattern` of lowercase letters and asterisks, this function should find and return **the lexicographically lowest trip-filled string** that can be constructed by replacing each asterisk of `pattern` with some letter. Furthermore, **no individual trip may appear in the solution more than once.** If no solution exists for the given `pattern`, return `None`. 

This problem is best solved with recursion similar to `decode_morse` in the <code>[morse.py](https://github.com/ikokkari/PythonExamples/blob/master/morse.py)</code> example. This function should loop through all trips that "fit into" the first three characters of <code>pattern</code>. (Let <code>bisect_left</code> be your friend in your time of need.) For each fitting trip, recursively find the lexicographically lowest way to fill in the rest of the <code>pattern</code> from position 1 onwards, with your currently chosen trip "stamped" into the first three characters of that <code>pattern</code>. As this function needs to return only the first complete solution instead of generating all of them, it needs only ordinary recursion instead of being a recursive generator. To enforce the uniqueness of the chosen trips, this recursion should <code>append</code> each trip into the <code>tabu</code> list on the way down, and then <code>pop</code> that trip out of the <code>tabu</code> list immediately after returning. (In the top level calls inside the tester, <code>tabu</code> is guaranteed to be an empty list.)


<table>
  <tr>
   <td><code>pattern</code>
   </td>
   <td>Expected result (using the wordlist <code>words_sorted.txt</code>)
   </td>
  </tr>
  <tr>
   <td><code>'**q'</code>
   </td>
   <td><code>'aeq'</code>
   </td>
  </tr>
  <tr>
   <td><code>'*yo***'</code>
   </td>
   <td><code>'iyobaa'</code>
   </td>
  </tr>
  <tr>
   <td><code>'*m*gv**o'</code>
   </td>
   <td><code>None</code>
   </td>
  </tr>
  <tr>
   <td><code>'*ef***da**s'</code>
   </td>
   <td><code>'befloadabas'</code>
   </td>
  </tr>
  <tr>
   <td><code>'**l**a*l*ai*'</code>
   </td>
   <td><code>'ablobaalcaid'</code>
   </td>
  </tr>
  <tr>
   <td><code>'*e' * 8</code>
   </td>
   <td><code>'lekereseyewemeve'</code>
   </td>
  </tr>
  <tr>
   <td><code>'*' * 100</code>
   </td>
   <td><code>'aaahabaalabbloadabcdfthadcabdeaddtdryadebbsfmtgnubcfibabeamablschaeraboafbibobaccmlxxiseanaambdspace'</code>
   </td>
  </tr>
</table>


 




## **Balanced ternary**


```
def balanced_ternary(n):
```


The integer two and its powers abound all over computing whereas the number three seems to be mostly absent, at least until we get to the **theory of computation** and **NP-complete problems** where the number three turns out to be a very different thing from two not only quantitatively, but qualitatively. Stepping from two to three is where the computational complexity truly begins.

We normally represent integers in base 10, each digit giving the coefficient of some power of 10. Since every positive integer can equally well be uniquely represented as a sum of powers of two, computers internally encode those same integers in the simpler (for machines) binary. Both of these schemes need [special tricks to represent negative numbers](https://en.wikipedia.org/wiki/Two%27s_complement) in the absence of an explicit negation sign. The [balanced ternary](https://en.wikipedia.org/wiki/Balanced_ternary) representation of integers uses the base three instead of two, with **signed** coefficients from three possibilities -1, 0 and +1. Every integer (positive or negative) can be broken down into a sum of signed powers of three exactly one way. Furthermore, the balanced ternary representation is perfectly symmetric around zero; the representation for -_n_ can be constructed simply by flipping the signs of the terms of the representation of +_n_. 

Given an integer `n`, return the unique list of signed powers of three that add up to `n`, listing these powers in the descending order of their absolute values. This problem can be solved in a couple of different ways. The page "[Balanced ternary](https://cp-algorithms.com/algebra/balanced-ternary.html)" shows one way to do so by first converting the number to unbalanced ternary (base three using coefficients 0, 1 and 2) and converting from there. Another way is to first find _p_, the highest power of 3 that is less than equal to _n_. Then, depending on the value of _n_ - _p_, you either take _p_ to the result and convert _n_ - _p_ for the rest, or take 3_p_ to the result and convert _n_ - _3p_ for the rest. All roads lead to Rome.


<table>
  <tr>
   <td><code>n</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>5</code>
   </td>
   <td><code>[9, -3, -1]</code>
   </td>
  </tr>
  <tr>
   <td><code>-5</code>
   </td>
   <td><code>[-9, 3, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>42</code>
   </td>
   <td><code>[81, -27, -9, -3]</code>
   </td>
  </tr>
  <tr>
   <td><code>-42</code>
   </td>
   <td><code>[-81, 27, 9, 3]</code>
   </td>
  </tr>
  <tr>
   <td><code>100</code>
   </td>
   <td><code>[81, 27, -9, 1]</code>
   </td>
  </tr>
  <tr>
   <td><code>10**6</code>
   </td>
   <td><code>[1594323, -531441, -59049, -6561, 2187, 729, -243, 81, -27, 1]</code>
   </td>
  </tr>
</table>



## **Lords of Midnight**


```
def midnight(dice):
```


**Midnight** (see [the Wikipedia page](https://en.wikipedia.org/wiki/Midnight_(game)) for the rules) is a dice game where the player has to choose which of the six dice to keep and which to reroll to maximize his final score. However, all your hard work with the previous problems has now mysteriously rewarded you with the gift of perfect foresight (as the French might say, you might be a descendant of [Madame de Thèbes](https://en.wikipedia.org/wiki/Madame_de_Th%C3%A8bes)) that allows you to predict what pip values each individual die will produce in its entire sequence of future rolls, expressed as a sequence such as `[2, 5, 5, 1, 6, 3]`. Aided with this foresight, your task is to return the maximum total score that could be achieved with the given dice rolls.

The argument `dice` is a list whose each element is a sequence of the pip values that particular die will produce when rolled. (Since this game will necessarily end after at most six rolls, this given future sequence needs to be only six elements long.) Note that the rules require you to keep at least one die in each roll, which is why the trivial algorithm "First choose the two dice that you will use to get the 1 and 4, and add up the maximum pip values for the four remaining dice" does not work, as demonstrated by the first row of the following table.


<table>
  <tr>
   <td><code>dice</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[[3, 4, 6, 6, 6, 2], [3, 2, 6, 2, 3, 3], [2, 2, 2, 2, 2, 3], [6, 1, 4, 2, 2, 2], [2, 2, 2, 3, 2, 3], [2, 3, 3, 3, 3, 2]]</code>
   </td>
   <td><code>14</code>
   </td>
  </tr>
  <tr>
   <td><code>[[2, 6, 2, 5, 2, 5], [5, 3, 3, 2, 5, 3], [2, 2, 2, 2, 5, 2], [3, 6, 3, 2, 2, 5], [6, 2, 2, 6, 3, 2], [2, 2, 3, 2, 2, 2]]</code>
   </td>
   <td><code>0</code>
   </td>
  </tr>
  <tr>
   <td><code>[[2, 6, 2, 1, 3, 3], [2, 2, 2, 2, 2, 3], [2, 2, 4, 3, 6, 6], [4, 5, 6, 3, 2, 5], [2, 4, 2, 6, 5, 3], [2, 2, 2, 2, 2, 3]]</code>
   </td>
   <td><code>17</code>
   </td>
  </tr>
  <tr>
   <td><code>[[3, 4, 6, 6, 6, 2], [3, 2, 6, 2, 3, 3], [2, 2, 2, 2, 2, 3], [6, 1, 4, 2, 2, 2], [2, 2, 2, 3, 2, 3], [2, 3, 3, 3, 3, 2]]</code>
   </td>
   <td><code>14</code>
   </td>
  </tr>
  <tr>
   <td><code>[[2, 3, 5, 3, 2, 2], [1, 3, 2, 3, 6, 4], [3, 2, 3, 3, 3, 5], [3, 6, 4, 6, 2, 3], [2, 3, 3, 2, 3, 2], [3, 5, 3, 5, 1, 2]]</code>
   </td>
   <td><code>17</code>
   </td>
  </tr>
</table>


 

To make the test cases more interesting, the automated tester is programmed to produce fewer ones, fours and sixes than the probabilities of fair dice would normally yield. No law of nature or man stands against that sort of tactical placement of your thumb on the scales...


## **Optimal crag score**


```
def optimal_crag_score(rolls):
```


Way back near when we started doing these problems, one particular problem asked you to compute the best possible score for a single roll in the dice game of [crag](https://en.wikipedia.org/wiki/Crag). In this problem, we will now play the game for real, again aided with the same gift of perfect foresight as in the previous problem "Lords of Midnight" so that given the knowledge of the entire future sequence of `rolls`, this function should return the highest possible score that could be achieved with those rolls under the constraint that **the same category cannot be used more than once**.

This problem will require recursive search, and the techniques that you might come up with to speed up its execution by pruning away search branches that cannot lead to optimal solutions will be highly important for your future algorithms courses. Note that the greedy algorithm "sort the rolls in the descending order of their maximum possible individual score, and then use each roll for its highest scoring remaining category" does not work, since several rolls might fit in the same category, and yet are not equally good choices with respect to the remaining categories.


<table>
  <tr>
   <td><code>rolls</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>[(1, 6, 6), (2, 5, 6), (4, 5, 6), (2, 3, 5)]</code>
   </td>
   <td><code>101</code>
   </td>
  </tr>
  <tr>
   <td><code>[(3, 1, 2), (1, 4, 2)]</code>
   </td>
   <td><code>24</code>
   </td>
  </tr>
  <tr>
   <td><code>[(5, 1, 1), (3, 5, 2), (2, 3, 2), (4, 3, 6), (6, 4, 6), (4, 5, 2), (6, 4, 5)]</code>
   </td>
   <td><code>74</code>
   </td>
  </tr>
  <tr>
   <td><code>[(3, 1, 2), (1, 4, 2), (5, 2, 3), (5, 5, 3), (2, 6, 3), (1, 1, 1), (5, 2, 5)]</code>
   </td>
   <td><code>118</code>
   </td>
  </tr>
  <tr>
   <td><code>[(1, 5, 1), (5, 5, 6), (3, 2, 4), (4, 6, 1), (4, 4, 1), (3, 2, 4), (3, 4, 5), (1, 2, 2)]</code>
   </td>
   <td><code>33</code>
   </td>
  </tr>
</table>





## **Forbidden substrings**


```
def forbidden_substrings(letters, n, tabu):
```


This function should construct and return a list of all _n_-character strings that consists of given `letters` under the constraint that a string may not contain any of the substrings in the `tabu` list. The list of strings should be returned in sorted alphabetical order. This problem also needs some branching recursion to work out the potentially exponential number of possible combinations.


<table>
  <tr>
   <td><code>letters</code>
   </td>
   <td><code>n</code>
   </td>
   <td><code>tabu</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>'AB'</code>
   </td>
   <td><code>4</code>
   </td>
   <td><code>['AA']</code>
   </td>
   <td><code>['ABAB', 'ABBA', 'ABBB', 'BABA', 'BABB', 'BBAB', 'BBBA', 'BBBB']</code>
   </td>
  </tr>
  <tr>
   <td><code>'ABC'</code>
   </td>
   <td><code>3</code>
   </td>
   <td><code>['AC', 'AA']</code>
   </td>
   <td><code>['ABA', 'ABB', 'ABC', 'BAB', 'BBA', 'BBB', 'BBC', 'BCA', 'BCB', 'BCC', 'CAB', 'CBA', 'CBB', 'CBC', 'CCA', 'CCB', 'CCC']</code>
   </td>
  </tr>
  <tr>
   <td><code>'ABC'</code>
   </td>
   <td><code>6</code>
   </td>
   <td><code>['BB', 'CCCA', 'CB', 'CA', 'CBBCC', 'BA']</code>
   </td>
   <td><code>['AAAAAA', 'AAAAAB', 'AAAAAC', 'AAAABC', 'AAAACC', 'AAABCC', 'AAACCC', 'AABCCC', 'AACCCC', 'ABCCCC', 'ACCCCC', 'BCCCCC', 'CCCCCC']</code>
   </td>
  </tr>
  <tr>
   <td><code>'ABCD' </code>
   </td>
   <td><code>7</code>
   </td>
   <td><code>['DBBD', 'CB', 'BBCC', 'DB']</code>
   </td>
   <td>(a list that contains a total of 6436 words)
   </td>
  </tr>
  <tr>
   <td><code>'Z'</code>
   </td>
   <td><code>10**100</code>
   </td>
   <td><code>['ZZZ']</code>
   </td>
   <td><code>[]</code> (and that answer needs to come out right away instead of after about 10**80 years)
   </td>
  </tr>
</table>





## **Go for the Grand: Infinite Fibonacci word**


```
def fibonacci_word(k):
```


[Fibonacci words](https://en.wikipedia.org/wiki/Fibonacci_word) are strings defined analogously to [Fibonacci numbers](https://en.wikipedia.org/wiki/Fibonacci_number). The recursive definition starts with two base cases _S<sub>0</sub>_ = `'0'` and _S<sub>1</sub>_ = `'01'`, followed by the recursive rule _S<sub>n</sub>_ = _S<sub>n-1</sub>S<sub>n-2</sub>_ that concatenates the two previous Fibonacci words. See the Wikipedia page for more examples. Especially importantly for this problem, notice how the length of each Fibonacci word equals that particular Fibonacci number. Even though we cannot actually generate the infinite Fibonacci word _S<sub>∞ </sub>_because it would be infinitely long, we can construct the character at any particular position _k_ of _S<sub>∞</sub>_ in a finite number of steps by realizing that after generating some word _S<sub>n</sub>_ that is longer than _k_, every longer word _S<sub>m</sub>_ for _m_ > _n_, and therefore also the infinite word _S<sub>∞</sub>_, must start with the exact same prefix _S<sub>n</sub>_ and therefore contain that asked character in the position _k_.

This function should compute the _k_:th character of the infinite Fibonacci word, the position counting done again starting from zero as usual. Since this is the last problem of this entire course, to symbolize your reach towards the infinite as you realize that you can simply ignore any arbitrary limits imposed by the laws of man and **go for the grand**, your function must be able to work for such unimaginably large values of _k_ that they make even one googol `10**100` seem like you could wait it out standing on your head. The entire universe would not have enough atoms to encode the entire string _S<sub>n</sub>_ for such a large _n_ to allow you to look up its _k_:th character. Instead, you need to apply the recursive formula, the list of Fibonacci numbers that you will dynamically compute as far as needed, and the [self-similar fractal nature of the infinite Fibonacci word](https://en.wikipedia.org/wiki/Fibonacci_word_fractal).


<table>
  <tr>
   <td><code>k</code>
   </td>
   <td>Expected result
   </td>
  </tr>
  <tr>
   <td><code>0</code>
   </td>
   <td><code>'0'</code>
   </td>
  </tr>
  <tr>
   <td><code>1</code>
   </td>
   <td><code>'1'</code>
   </td>
  </tr>
  <tr>
   <td><code>10</code>
   </td>
   <td><code>'0'</code>
   </td>
  </tr>
  <tr>
   <td><code>10**6</code>
   </td>
   <td><code>'0'</code>
   </td>
  </tr>
  <tr>
   <td><code>10**100</code>
   </td>
   <td><code>'0'</code>
   </td>
  </tr>
  <tr>
   <td><code>10**100 + 1</code>
   </td>
   <td><code>'1'</code>
   </td>
  </tr>
  <tr>
   <td><code>10**10000</code>
   </td>
   <td><code>'0'</code>
   </td>
  </tr>
</table>

