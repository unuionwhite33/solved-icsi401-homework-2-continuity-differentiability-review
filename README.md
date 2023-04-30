Download Link: https://assignmentchef.com/product/solved-icsi401-homework-2-continuity-differentiability-review
<br>
<h1>2.1        Continuity, differentiability review</h1>

<ul>

 <li>Give an example of a function <em>f </em>: R → R that is continuous everywhere on its domain but has at least one point at which it is not differentiable.</li>

 <li>Give an example of a function <em>f </em>: R → R that is not continuous at 0.</li>

</ul>

Hint for both of these: You can define piecewise functions (i.e., you can think of a function that has some form on one interval and then a different form on another interval). The purpose of this problem is for you to recall intuitively/graphically what continuity and differentiability mean.

<h1>2.2         Floating point and related topics</h1>

<ol>

 <li>Write down the binary expansion of 50<em>.</em></li>

 <li>Consider the gaps between representable floating point numbers. Which of the following has the larger gap between it and the next larger representable floating point number?

  <ul>

   <li>2</li>

   <li>201</li>

  </ul></li>

</ol>

Just a definition and not a problem that you have to solve: we say that <em>x </em>is an accurate approximation to <em>y </em>to <em>k </em>decimal places if |<em>x </em>− <em>y</em>| <em>&lt; </em>5 × 10<sup>−<em>k</em>−1</sup>. For example, if we want 4 decimal places of accuracy, then |<em>x </em>− <em>y</em>| <em>&lt; </em>5 × 10<sup>−5</sup>. You should use this definition in the problems below.

2-1

2-2                                                   Homework 2: ICSI 401 – Numerical Methods

<h1>2.3       Bisection search</h1>

1.3 In Matlab, implement a function that performs a bisection search. It should take the following parameters:

<ul>

 <li>F: A function (assumed to be continuous) whose roots you want to find,</li>

 <li>a: A floating point number giving the left endpoint of the initial interval in which you want to search for a root of <em>F</em>.</li>

 <li>b: A floating point number giving the right endpoint of the initial interval.</li>

 <li>delta: A non-negative floating point number giving the acceptable proximity of the output to a root of <em>F</em>.</li>

</ul>

Your function should first check <em>a </em>and <em>b </em>to determine whether or not they satisfy the condition given by the Intermediate Value Theorem that allows us to conclude that [<em>a,b</em>] contains a root of <em>F</em>. If this condition is not satisfied, return NaN (Matlab for “Not a number”). If the condition is satisfied, your function should perform a bisection search until it finds a number <em>z </em>that it can guarantee satisfies |<em>x</em>−<em>x</em><sub>∗</sub>| <em>&lt; </em>delta, for <em>some </em>real-valued root <em>x</em><sub>∗ </sub>of <em>F</em>. It should return <em>z</em>.

<ol start="2">

 <li>Use the Matlab function that you wrote to find a real-valued root of the function <em>F</em>(<em>x</em>) = <em>x</em><sup>5</sup>+<em>x</em>+1, with accuracy to 4 decimal places (this last requirement will determine your choice of delta).</li>

</ol>

A fun fact: You know about the quadratic formula, which gives the roots of a quadratic function in terms of its coefficients. It turns out that there exist similar formulas for polynomial functions of degree 3 and 4, but <em>not </em>for 5 or more (formally, such equations are not <em>solvable by radicals</em>). This is a result by Niels Henrik Abel, and the proof uses what is called <em>Galois theory </em>(sometimes covered in classes on abstract algebra). The fact that no such simple formula exists for the roots is a pretty good motivation for numerical methods.

<ol start="3">

 <li>Suppose that you use bisection search to find a root of <em>F</em>(<em>x</em>) = sin<em>x</em>, with <em>a </em>= −<em>π/</em>2<em>,b </em>= 5<em>π/</em></li>

</ol>

To which root will the bisection search converge?

<h1>2.4        Newton’s method</h1>

<ol>

 <li>Write a Matlab function that implements Newton’s method. It should take the following parameters:

  <ul>

   <li><em>F</em>: A function whose roots you want to find,</li>

   <li>Fprime: The derivative of <em>F</em>,</li>

   <li><em>w</em><sub>0</sub>: An initial point at which <em>F </em>is differentiable,</li>

   <li><em>k</em>: A positive integer giving the number of iterations to execute.</li>

  </ul></li>

</ol>

Your function should execute <em>k </em>iterations of Newton’s method using the parameter functions <em>F </em>and Fprime and output the resulting number, <em>w<sub>k</sub></em>.

<ol start="2">

 <li>Suppose that you want to find the points at which the graphs of two functions <em>f</em>(<em>x</em>) and <em>g</em>(<em>x</em>) intersect. Write down a function <em>H</em>(<em>x</em>) such that <em>f</em>(<em>x</em>) and <em>g</em>(<em>x</em>) intersect at a point <em>z </em>if and only if <em>H</em>(<em>z</em>) = 0.</li>

</ol>

Homework 2: ICSI 401 – Numerical Methods                                                   2-3

<ol start="3">

 <li>Find the point of intersection of <em>f</em>(<em>x</em>) = <em>x </em>and <em>g</em>(<em>x</em>) = <em>x</em>log<em>x</em>:

  <ul>

   <li>Write down a function <em>H</em>(<em>x</em>) as above, such that the roots of <em>H</em>(<em>x</em>) are exactly the points of intersection of <em>x </em>and <em>x</em>log<em>x</em>.</li>

   <li>Write down the Newton iteration equation (i.e., <em>w<sub>k</sub></em><sub>+1 </sub>in terms of <em>w<sub>k</sub></em>, <em>H</em>(<em>x</em>), and <em>H</em><sup>0</sup>(<em>x</em>)) that you would use to find roots of <em>H</em>(<em>x</em>).</li>

   <li>Use your Matlab implementation of Newton’s method with <em>k </em>= 50 and some appropriate starting point <em>w</em><sub>0 </sub>to find an approximation <em>w<sub>k </sub></em>to the root <em>x</em><sub>∗ </sub>of <em>H</em>(<em>x</em>). In order to choose <em>w</em><sub>0</sub>, you can plot <em>H</em>(<em>x</em>) and identify a point visually close to <em>x</em><sub>∗</sub>.</li>

  </ul></li>

</ol>