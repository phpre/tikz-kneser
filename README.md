# tikz-kneser
A tikz-library for drawing Kneser graphs (that doesn't rely on `tikz-graphdrawing` or `LuaLatex`).

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

Also, the ladder graphs `K(2n,n)` get a special treatment.
Further, you may _color_ and _fill_ any of the Kneser graphs as well:

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
  \pic[style=11] at (0,0) {kneser=6/2};
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

Also check out the Kneser triangle (uncomment the last 3 lines if you like to see your TeX installation struggle):
``` Tex
\begin{tikzpicture}
    \pic {kneser=0/0};
    \foreach\j in {0,...,1} \pic at (-.5+\j, -.6) {kneser=1/\j};
    \foreach\j in {0,...,2} \pic at (-2+\j*2, -1.5) {kneser=2/\j};
    \foreach\j in {0,...,3} \pic at (-4.5+\j*3, -3.25) {kneser=3/\j};
    \foreach\j in {0,...,4} \pic at (-8+\j*4, -5.75) {kneser=4/\j};
    \foreach\j in {0,...,5} \pic at (-12.5+\j*5, -10) {kneser=5/\j};
    \foreach\j in {0,...,6} \pic at (-18+\j*6, -15.5) {kneser=6/\j};
    \pic at (-35, -25.5) {kneser=7/0};
    \pic at (35, -25.5) {kneser=7/7};
    \foreach\j in {1,...,6} \pic at (-38.5+\j*11, -25.5) {kneser=7/\j};
    %\pic at (-65, -40) {kneser=8/0};
    %\pic at (65, -40) {kneser=8/8};
    %\foreach\j in {1,...,7} \pic at (-72+\j*18, -40) {kneser=8/\j};
\end{tikzpicture}
```
![](https://github.com/PH111P/tikz-kneser/blob/master/pics/triangle.png)
