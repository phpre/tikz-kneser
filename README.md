# tikz-kneser
A tikz-library for drawing Kneser graphs.

Include this library via
``` Tex
\usetikzlibrary{kneser}
```

And drawing kneser graphs becomes as easy as
``` Tex
\begin{tikzpicture}
  \pic {kneser=9/2};
\end{tikzpicture}
```
![](https://github.com/PH111P/tikz-kneser/blob/master/pics/K_9_2.png)


Limitations
--

Due to limitations of TeX, currently only the Kneser graphs `K(n,k)` for `n ≤ 9` can be generated; 
starting from `n ≥ 8` computing the graphs takes rather long though.

Examples
---

The Petersen Graph gets a special treatment:

``` Tex
\begin{tikzpicture}
  \pic {kneser=5/2};
\end{tikzpicture}
```
![](https://github.com/PH111P/tikz-kneser/blob/master/pics/K_5_2.png)


The graphs `K(n,1)` and `K(n,n-1)` get a special treatment as well:

``` Tex
\begin{tikzpicture}
  \pic at (-2.5,0) {kneser=7/1};
  \pic at (2.5,0) {kneser=7/6};
\end{tikzpicture}
```
![](https://github.com/PH111P/tikz-kneser/blob/master/pics/K_7_1_7_6.png)

Also, the ladder graphs `K(2n,n)` get a special treatment; you may _color_ and _fill_ the graphs as well:

``` Tex
\begin{tikzpicture}
  \pic[blue] at (-7,0) {kneser=4/2};
  \pic[fill=blue] at (-2.75,0) {kneser=6/3};
  \pic[white,fill=blue] at (7,0) {kneser=8/4};
\end{tikzpicture}
```
![](https://github.com/PH111P/tikz-kneser/blob/master/pics/ladders.png)

If you prefer sets as nodes, the library has you covered, too (`style` may be one of `11`, `12` or `13`):

``` Tex
\begin{tikzpicture}
  \pic[style=10] at (-7,0) {kneser=6/2};
  \pic[style=11] at (-2,0) {kneser=6/2};
  \pic[style=12] at (7,0) {kneser=6/2};
\end{tikzpicture}
```
![](https://github.com/PH111P/tikz-kneser/blob/master/pics/styles.png)

If you're only interested in these fancy representations of sets, just use the picture `kneserset`, 
which takes the length and the elements (as a bitstring) as arguments (and styles work as well):

``` Tex
\begin{tikzpicture}
    \pic[style=11,fill=yellow] at (1,0) {kneserset=2/1};
    \pic at (2,0) {kneserset=3/1};
    \pic[blue,dashed,style=11] at (3.5,0) {kneserset=14/1};
    \pic[white,fill=black,style=11] at (5.5,0) {kneserset=14/111};
    \pic[white,fill=black,style=21] at (5.5,-2.5) {kneserset=14/11111111111111};
    \pic[white,fill=black,style=10] at (7.5,0) {kneserset=14/11};
    \pic[white,fill=black,style=12] at (9.5,0) {kneserset=14/11};
\end{tikzpicture}
```
![](https://github.com/PH111P/tikz-kneser/blob/master/pics/kneserset.png)
