# Infinite Compositions

This is a document exploring infinite composition of functions.

Terminology I will use:

- $f(x)$ or $f$
  -  is the initial function.
- $g(x)$ or $g$
  -  is the final function that is produced after infinite compositions of $f$.
- A stable point is where $g(x)=x$
  - This also implies that $f(x)=x$
  - Also, stable points can be defined as $r(x)=0$
  - Stable points are attractors if $r'(x)<0$
- An attractor point is where $g(d)=c$  where $d$ is a certain interval like: $a<d<b$.
  - All attractors are stable points, **but not vise versa**.
  - Note that the interval does not need to be symmetric!
  - An attractor has at least one slide around it, **but not vise versa**.
    - Given that $f$ is continuous, an attractor will have two slides around it
  - An attractor is defined by: $r(x)=0$ and $r'(x)<0$.
- $r(x)$ or $r$
  - $r(x)$ is the residual function, which tells us how the function will change the next recursion.
    - $dx=r(x)$
  - It is defined as: $r(x)=f(x)-x$
- Slides
  - A slide is an range where $r(b)>0$ or $r(b)<0$ defined by the range $a<b<c$.
  - A slide goes down, or to the left if $r(b)<0$ 
  - A slide goes up, or to the right if $r(b)>0$ 
- $sign(x)=\left\{
  \begin{array}{ll}
        -1 & x < 0 \\ 1 & x>0
  \end{array} 
  \right.$

#### Baby Steps

##### Interpreting Graphs of $f$ and finding $g$.

Let’s get a feel for how these functions work!

Let’s consider the function: $f(x)=x^2$. When the function intersects the line $y=x$, it will have a stable point. This is because: $f(x)=x$ at that point:

<img src="img\1.png" alt="1"  />

So the function $f(x)=x^2$, has two stable points: $x=0,1$.

Now, let’s figure out the $g$ function.

- Using the knowledge that: 
  - $|x^n|<|x|$ given that $|x|<1$. 
  - Which means $\lim_{n \to \infty} x^{n}= 0$, given that $|x|<1$ 
  - We can prove, that $x=0$ is an attractor with its range being $(-1, 1)$. 
- However, we know that if $\lim_{n \to \infty} x^{2n}= \infty$, given $|x|>1$.
- And the final component, $x^n=1$, given that $x=1$

So with all of that we can define $g(x)$:

$g(x)=\left\{
\begin{array}{ll}
      0 & |x|< 1 \\ 1 & |x|=1 \\ \infty & |x|>1
\end{array} 
\right.$

To visually verify this, we can just graph a ton of compositions of $f$ and see if they approach our function:

<img src="img\2.png" alt="2"  />

As we can see, they start forming a ‘bucket,‘ where all of the sides pass through the point $(1,1)$ and then both ranges $(-\infty,-1)$ and $(1,\infty)$ go to $\infty$. 

##### Considering $r$

![3](img\3.png)

The new green function is $r(x)$, which in our case is $r(x)=x^2-x$. The roots of $r$ represent all the stable points of our function. Another way to think of $r$ is that it is the change of x given one composition. Obviously, if $y=x$ is above our function $f(x)$, then $r(x)<0$ and we are on a downward slide. And, if $y=x$ is below our function $f(x)$, then $r(x)>0$ and we are on a upward slide.

#### Simple Polynomials

Given a simple polynomial like: $f(x)=x^n$

Given the rules:

- $|x^n|<|x|$ given that $|x|<1$. 
  - Which means $\lim_{n \to \infty} x^{n}= 0$, given that $|x|< 1$ 
  - We can prove, that $x=0$ is an attractor with its range being $(-1, 1)$. 
- If $n$ is even:
  - $g(x)=\left\{
    \begin{array}{ll}
          0 & |x|< 1 \\ 1 & |x|=1 \\ \infty & |x|>1
    \end{array} 
    \right.$
- If $n$ is odd:
  - $g(x)=\left\{
    \begin{array}{ll}
          0 & |x|< 1 \\ sign(x) & |x|=1 \\ sign(x) \cdot \infty & |x|>1
    \end{array} 
    \right.$

##### Another rule can be made for negatives:

Given a simple polynomial like: $f(x)=kx^n$, where $k∈\{-1,1\}$.

- If $n$ is even:
  - $g(x)=\left\{
    \begin{array}{ll}
          0 & |x|< 1 \\ k & |x|=1 \\ k\cdot\infty & |x|>1
    \end{array} 
    \right.$
- If $n$ is odd:
  - $k=-1$:
    - $g(x)=\left\{
      \begin{array}{ll}
            0 & |x|< 1
      \end{array} 
      \right.$
  - $k=1$:
    - $g(x)=\left\{
      \begin{array}{ll}
            0 & |x|< 1 \\ sign(x) & |x|=1 \\ sign(x) \cdot \infty & |x|>1
      \end{array} 
      \right.$

#### Intriguing Functions

One intriguing choice of $f$ is:

$f(x)=\frac{sin(2\pi x)}{2\pi} +x$

![3](img\4.png)

Now, if we plot $y=x$:

![3](img\5.png)

We can see that $f(x)$ has slides, and if we graph a bunch of compositions, we see that it forms plateaus.

![3](img\6.png)

The actual formula for $g$ is $g(x)=floor(x)+\frac{1}{2}$.