# LaTeX数学公式汇总

## 0 介绍

LaTeX表达式是一种简单的、常见的一种数学公式表达形式。LaTeX表达式一般分为两种，一种是行内公式，一种是单独成行的公式。所有的LaTeX公式的书写形式都是在`$...$`之中，而单独成行的表达式则是在两对`$$...$$`之中。Typora插入公式的的方法：

* 点击段落->公式块
* 快捷键 Ctrl + Shift + m
* $$ + 回车

## 1 希腊字母

- 希腊字母小写本质上就是转义符号\\+希腊字母的英文**(首字母小写)**;
- 希腊字母大写本质上就是转义符号\\+希腊字母的英文**(首字母大写)**；

| 序号 | LaTeX表达式 | 对应希腊字母 | LaTeX表达式 | 对应希腊字母 |           读音            |
| :--: | :---------: | :----------: | :---------: | :----------: | :-----------------------: |
|  1   |   \alpha    |   $\alpha$   |   \Alpha    |   $\Alpha$   |          /'ælfə/          |
|  2   |    \beta    |   $\beta$    |    \Beta    |   $\Beta$    |    /'bi:tə/or/'beɪtə/     |
|  3   |   \gamma    |   $\gamma$   |   \Gamma    |   $\Gamma$   |          /'gæmə/          |
|  4   |   \delta    |   $\delta$   |   \Delta​    |   $\Delta$   |         /'deltə/          |
|  5   |  \epsilon   |  $\epsilon$  |  \Epsilon   |  $\Epsilon$  |        /'epsɪlɒn/         |
|  6   |    \zeta    |   $\zeta$    |    \Zeta    |   $\Zeta$    |         /'zi:tə/          |
|  7   |    \eta     |    $\eta$    |    \Eta     |    $\Eta$    |          /'i:tə/          |
|  8   |   \theta    |   $\theta$   |   \Theta    | **$\Theta$** |         /'θi:tə/          |
|  9   |    \iota    |   $\iota$    |    \Iota    |   $\Iota$    |         /aɪ’əʊtə/         |
|  10  |   \kappa    |   $\kappa$   |   \Kappa    |   $\Kappa$   |          /'kæpə/          |
|  11  |   \lambda   |  $\lambda$   |   \Lambda   |  $\Lambda$   |         /'læmdə/          |
|  12  |     \mu     |    $\mu$     |     \Mu     |    $\Mu$     |          /mju:/           |
|  13  |     \nu     |    $\nu$     |     \Nu     |    $\Nu$     |          /nju:/           |
|  14  |     \xi     |    $\xi$     |     \Xi     |    $\Xi$     |  /ksi/or/'zaɪ/or/'ksaɪ/   |
|  15  |  \omicron   |  $\omicron$  |  \Omicron   |  $\Omicron$  | /əu’maikrən/or/'ɑmɪ,krɑn/ |
|  16  |     \pi     |    $\pi$     |     \Pi     |    $\Pi$     |           /paɪ/           |
|  17  |    \rho     |    $\rho$    |    \Rho     |    $\Rho$    |           /rəʊ/           |
|  18  |   \sigma    |   $\sigma$   |   \Sigma    |   $\Sigma$   |         /'sɪɡmə/          |
|  19  |    \tau     |    $\tau$    |    \Tau     |    $\Tau$    |       /tɔ:/or/taʊ/        |
|  20  |  \upsilon   |  $\upsilon$  |  \Upsilon   |  $\Upsilon$  |  /'ipsilon/or/'ʌpsilɒn/   |
|  21  |   \varphi   |  $\varphi$   |    \Phi     |    $\Phi$    |           /faɪ/           |
|  21  |    \phi     |    $\phi$    |    \Phi     |    $\Phi$    |           /faɪ/           |
|  22  |    \chi     |    $\chi$    |    \Chi     |    $\Chi$    |           /kaɪ/           |
|  23  |    \psi     |    $\psi$    |    \Psi     |    $\Psi$    |          /psaɪ/           |
|  24  |   \omega    |   $\omega$   |   \Omega    |   $\Omega$   |   /'əʊmɪɡə/or/oʊ’meɡə/    |

* 注意序号为21的$\phi$和$\varphi$的区别，多了一个var；
* $\epsilon$和$\varepsilon$也有区别；

* 常用梯度符合$\nabla$的LaTeX公式为`\nobla`；

## 2 运算符

普通字符在数学公式中含义一样，除了 # $ % & ~ _ ^ \ { } 若要在数学环境中表示这些符号# $ $ % & _ { }，需要分别表示为`\# \$ \% \& \_ \{ \}`，即在个字符前加上\ ，表示转义。

|  LaTeX表达式   |       效果       |   LaTeX表达式    |        效果        |
| :------------: | :--------------: | :--------------: | :----------------: |
|       +        |       $+$        |        -         |        $-$         |
|     \times     |     $\times$     |      \cdot       |      $\cdot$       |
|      \div      |      $\div$      |        /         |        $/$         |
| \divideontimes | $\divideontimes$ |     \dotplus     |     $\dotplus$     |
|      \pm       |      $\pm$       |       \mp        |       $\mp$        |
|       >        |       $>$        |        <         |        $<$         |
|      \gt       |      $\gt$       |       \lt        |       $\lt$        |
|      \ge       |      $\ge$       |       \le        |       $\le$        |
|      \geq      |      $\geq$      |       \leq       |       $\leq$       |
|     \geqq      |     $\geqq$      |      \leqq       |      $\leqq$       |
|   \geqslant    |   $\geqslant$    |    \leqslant     |    $\leqslant$     |
|      \gg       |      $\gg$       |       \ll        |       $\ll$        |
|      \ggg      |      $\ggg$      |       \lll       |       $\lll$       |
|      \neq      |      $\neq$      |     \not\lt      |     $\not\lt$      |
|      \ne       |      $\ne$       |     \approx      |     $\approx$      |
|     \equiv     |     $\equiv$     |   \varnothing    |   $\varnothing$    |
|      \cap      |      $\cap$      |       \cup       |       $\cup$       |
|      \in       |      $\in$       |      \notin      |      $\notin$      |
|      \ni       |      $\ni$       |     \not\ni      |     $\not\ni$      |
|   \setminus    |   $\setminus$    |    \emptyset     |    $\emptyset$     |
|    \supset     |    $\supset$     |     \subset      |     $\subset$      |
|   \supseteq    |   $\supseteq$    |    \subseteq     |    $\subseteq$     |
|  \supsetneqq   |  $\supsetneqq$   |   \subsetneqq    |   $\subsetneqq$    |
|   \nsupseteq   |   $\nsupseteq$   |    \nsubseteq    |    $\nsubseteq$    |
|   \triangleq   |   $\triangleq$   |      \angle      |      $\angle$      |
|    \forall     |    $\forall$     |     \exists      |     $\exists$      |
|    \nexists    |    $\nexists$    |       \Z_+       |       $\Z_+$       |
|   \mathbb R    |   $\mathbb R$    |        \R        |        $\R$        |
|       \Q       |       $\Q$       |        \N        |        $\N$        |
|    \because    |    $\because$    |   \thererfore    |    $\therefore$    |
|   \mathcal F   |   $\mathcal F$   |    \mathscr F    |    $\mathscr F$    |
|     \cdots     |     $\cdots$     |      \vdots      |      $\vdots$      |
|     \ddots     |     $\ddots$     |      \ldots      |      $\ldots$      |
|       ∂        |       $∂$        |     \partial     |     $\partial$     |
|     \nabla     |     $\nabla$     |     \propto      |     $\propto$      |
|     \not a     |     $\not a$     | {n+1 \choose 2k} | ${n+1 \choose 2k}$ |
|      \\#       |       $\#$       | \binom{n+1}{2k}  | $\binom{n+1}{2k}$  |
|      \\$       |       $\$$       |     \degree      |     $\degree$      |
|       \%       |       $\%$       |                  |                    |
|      \\&       |       $\&$       |       \And       |       $\And$       |
|      \\_       |       $\_$       |                  |                    |
|      \\{       |       $\{$       |                  |                    |
|      \\}       |       $\}$       |                  |                    |

* $\ldots$和$\cdots$有区别；

|   LaTeX表达式    |        效果        | LaTeX表达式 |    效果    |
| :--------------: | :----------------: | :---------: | :--------: |
|      \land       |      $\land$       |    \lor     |   $\lor$   |
|      \lnot       |      $\lnot$       |    \top     |   $\top$   |
|       \bot       |       $\bot$       |   \vdash    |  $\vdash$  |
|      \vDash      |      $\vDash$      |    \star    |  $\star$   |
|      \star       |      $\star$       |    \ast     |   $\ast$   |
|      \oplus      |      $\oplus$      |    \circ    |  $\circ$   |
|     \bullet      |     $\bullet$      |    \sim     |   $\sim$   |
|      \simeq      |      $\simeq$      |    \cong    |  $\cong$   |
|     \ominus      |     $\ominus$      |    \prec    |  $\prec$   |
|     \otimes      |     $\otimes$      |   \oslash   | $\oslash$  |
|      \odot       |      $\odot$       |             |            |
|       \lhd       |       $\lhd$       |  \aleph_0   | $\aleph_0$ |
|       \lm        |       $\lm$        |     \Re     |   $\Re$    |
| a\equiv b\pmod n | $a\equiv b\pmod n$ |    \ell     |   $\ell$   |
|                  |                    |             |            |



* !应该也需要转义；
* `\not`放在前面，给几乎所有的符号画出一个斜线；

## 3 空格

> 固定空格

- **转义字符\\+字母的组合，需要在后面打空格，用来把它看成一个整体。**这个空格不会显示出来，表示命令的结束；
- **转义符 + 标点 的组合，原则上不要在前后加空格。**原因是：这种组合中前后加的空格会被识别为常规空格。常规空格在LaTeX中会适应排版进行调整，会造成空格长度不固定；

| 序号 |    LaTeX表达式    |        效果         | 空格长度 |
| :--: | :---------------: | :-----------------: | :------: |
|  1   |    a \qquad b     |    $a \qquad b$     |   2 em   |
|  2   |     a \quad b     |     $a \quad b$     |   1 em   |
|  3   |   a \enspace b    |   $a \enspace b$    |  0.5 em  |
|  4   |       a\ b        |       $a\ b$        |          |
|  5   |       a\, b       |       $a\, b$       |          |
|  6   |  a \thinspace b   |  $a \thinspace b$   | 3/18 em  |
|  7   |       a\\!b       |       $a\!b$        | -3/18 em |
|  8   | a \negthinspace b | $a \negthinspace b$ | -3/18 em |

- 上述空格如若有无显示的问题，可能是缺少了amsmath包。

> 自定义长度空格

* \hspace{<space_width>}用于水平方向；

* \vspace{<space_width>}用于垂直方向，用于行间距的微调，包括但不限于图表和标题之间、图表和正文之间、标题和正文之间的距离调整。（此为LaTeX排版部分的内容）

其中的参数space_width为你所期望的长度

## 4 换行符和对齐

换行用`\\`，对齐用`&`(用在等号之前)。

```
\begin{aligned}
y \hspace{0.2 em} & = ax + b \\
& = bx + c \\
& = cx + d
\end{aligned}
```


$$
\begin{aligned}
y \hspace{0.2 em} & = ax + b \\
& = bx + c \\
& = cx + d
\end{aligned}
$$

## 5 上下标

下标使用**下划线**表示“ _ ” ，上标使用 “ ^ ”表示。比如$x_i^2$的LaTeX表达式为`$x_i^2$`。

LaTex表达式中的上下标可以叠加的，就比如${x^y}^z$的表达式为`${x^y}^z$`或者`$x^{y^z}$`。

* LaTex表达式默认的是 “ _ ” “ ^ ” 之后的一位才是上下标的内容；
* 对于超过一个字母的上下标需要使用 { } 将它括起来，比如$x_{2i}^{2+b}$的LaTeX表达式为`$x_{2i}^{2+b}$`；
* 前置上下标：${}^2_1\!X^3_4$的LaTeX表达式为`${}^2_1\!X^3_4$`；
* `\text`用于将斜体变量转为直体；

| LaTeX表达式 |     效果     |  LaTeX表达式  |      效果       |
| :---------: | :----------: | :-----------: | :-------------: |
|    x_i^2    |   $x_i^2$    | x_{2i}^{a+b}  | $x_{2i}^{a+b}$  |
|   p_{ij}    |   $p_{ij}$   |     p_ij      |     $p_ij$      |
|     x_i     |    $x_i$     |  x_{\text i}  |  $x_{\text i}$  |
| \text{A B}  | $\text{A B}$ |   \rm{A B}    |   $\rm{A B}$    |
|  \text A B  | $\text A B$  |    \rm A B    |    $\rm A B$    |
|  {\rm A} B  | ${\rm A} B$  |    \text e    |    $\text e$    |
|   \hat{a}   |  $\hat{a}$   |   \acute{a}   |   $\acute{a}$   |
|  \grave{a}  | $\grave{a}$  |   \breve{a}   |   $\breve{a}$   |
|   \bar{a}   |  $\bar{a}$   | \widetilde{a} | $\widetilde{a}$ |
|  \check{a}  | $\check{a}$  |   \tilde{a}   |   $\tilde{a}$   |
|   \dot{a}   |  $\dot{a}$   |   \ddot{a}    |   $\ddot{a}$    |
|   \vec{a}   |  $\vec{a}$   |  \widehat{a}  |  $\widehat{a}$  |
|  f^\prime   |  $f^\prime$  |     x^{'}     |     $x^{'}$     |
|  \nabla f   |  $\nabla f$  |  \mathrm{d}x  |  $\mathrm{d}x$  |
| \partial x  | $\partial x$ |               |                 |

## 6 对数

$\log$的表达式会稍微简单点，`$\log$` 就是它的LaTex表达式，同样的对于需要下标的同样使用下划线表示 “ _ ” ， 对于多个字符组成的需要添加 { } 将其包括。

|  LaTeX表达式   |       效果       |
| :------------: | :--------------: |
|    \log_2 x    |    $\log_2 x$    |
|     \ln x      |     $\ln x$      |
|     \lg x      |     $\lg x$      |
| \log_{21} {xy} | $\log_{21} {xy}$ |

## 7 括号与定界符

LaTex表达式中的 ( ) 、 [ ] 均可以正常使用，但是对于 { } 需要使用转义字符使用，即使用 “\\{” 和 “\\}” 表示 { }。

|              LaTeX表达式              |                  效果                   |             LaTeX表达式              |                 效果                  |
| :-----------------------------------: | :-------------------------------------: | :----------------------------------: | :-----------------------------------: |
|                  ()                   |                  $()$                   |                  []                  |                 $[]$                  |
|                  \\{                  |                  $\{$                   |                 \\}                  |                 $\}$                  |
|                 \|\|                  |                  $||$                   |                                      |                                       |
|                 \vert                 |                 $\vert$                 |                \Vert                 |                $\Vert$                |
|                \langle                |                $\langle$                |               \rangle                |               $\rangle$               |
|                \lceil                 |                $\lceil$                 |                \rceil                |               $\rceil$                |
|                \lfloor                |                $\lfloor$                |               \rfloor                |               $\rfloor$               |
|             \vert x \vert             |            $$\vert x \vert$$            |                                      |                                       |
|            (\dfrac{1}{2})             |            $(\dfrac{1}{2})$             |      \left(\dfrac{1}{2}\right)       |      $\left(\dfrac{1}{2}\right)$      |
| \left\lfloor\dfrac{1}{2}\right\rfloor | $\left\lfloor\dfrac{1}{2}\right\rfloor$ | \left\lfceil\dfrac{1}{2}\right\rceil | $\left\lceil\dfrac{1}{2}\right\rceil$ |
|       \left(0,\frac 1 a\right]        |       $\left(0,\frac 1 a\right]$        |  \left.\frac {∂f}{∂x}\right\|_{x=0}  |  $\left.\frac {∂f}{∂x}\right|_{x=0}$  |

多行公式：
$$
\begin{align}

a&=b+c+d\\
&=e+f

\end{align}
$$

$$
f(x)=

\begin{cases}

\sin x, & -π\le x \le π\\
0,& \text{其他}

\end{cases}
$$

$$
f(x)=
\begin{cases} 
0 &\text{x=0}\\
1 &\text{x!=0}
\end{cases}
$$

$$
f(x)=
\begin{cases} 
x = \cos(t) \\
y = \sin(t) \\ 
z = \frac xy 
\end{cases}
$$





|                       LaTeX表达式                       |                           效果                            |
| :-----------------------------------------------------: | :-------------------------------------------------------: |
| \Biggl(\biggl(\Bigl(\bigl((x)\bigr)\Bigr)\biggr)\Biggr) | $\Biggl(\biggl(\Bigl(\bigl((x)\bigr)\Bigr)\biggr)\Biggr)$ |

* 对于个别符号，如 ()、[]等，如果想要变大，可以在 这些符号前面添加即可。

```
\Biggl \biggl \Bigl \bigl  左符号
\Biggr \biggr \Bigr \bigr  右符号
```

* 括号自适应问题，在左右括号前分别加上\left和\right，可以实现。

## 8 矩阵

LaTeX矩阵共有4类。分别是matrix、pmatrix、bmatrix和vmatrix。

|                  LaTeX表达式                  |                      效果                       |
| :-------------------------------------------: | :---------------------------------------------: |
|  \begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix}   |  $\begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix}$   |
| \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} | $\begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}$ |
| \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} | $\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$ |
| \begin{Bmatrix} 1 & 0 \\ 0 & -1 \end{Bmatrix} | $\begin{Bmatrix} 1 & 0 \\ 0 & -1 \end{Bmatrix}$ |
| \begin{vmatrix} a & b \\ c & d \end{vmatrix}  | $\begin{vmatrix} a & b \\ c & d \end{vmatrix}$  |
| \begin{Vmatrix} i & 0 \\ 0 & -i \end{Vmatrix} | $\begin{Vmatrix} i & 0 \\ 0 & -i \end{Vmatrix}$ |
|                     \bf A                     |                     $\bf A$                     |
|                 \bf B^{\rm T}                 |                 $\bf B^{\rm T}$                 |

$$
\begin{matrix}

a & b & \cdots & c \\
\vdots& \vdots & \ddots & \vdots \\
e & f& \cdots & g

\end{matrix}
$$

$$
\begin{bmatrix}

a & b & \cdots & c \\
\vdots& \vdots & \ddots & \vdots \\
e & f& \cdots & g

\end{bmatrix}

\begin{pmatrix}

a & b & \cdots & c \\
\vdots& \vdots & \ddots & \vdots \\
e & f& \cdots & g

\end{pmatrix}

\begin{vmatrix}

a & b & \cdots & c \\
\vdots& \vdots & \ddots & \vdots \\
e & f& \cdots & g

\end{vmatrix}
$$



## 9 求和连乘

* `limits`用于将上下包从求和连乘符合右上、右下挪到上方和下方；

|                       LaTeX表达式                        |                            效果                            |
| :------------------------------------------------------: | :--------------------------------------------------------: |
|                           \sum                           |                           $\sum$                           |
|                           \int                           |                           $\int$                           |
|                          \prod                           |                          $\prod$                           |
|                         \sum_1^n                         |                         $\sum_1^n$                         |
|               \sum\limits_{i=0}^\infty i^2               |               $\sum\limits_{i=0}^\infty i^2$               |
|                   \prod_{k=1}^n k = n!                   |                   $\prod_{k=1}^n k = n!$                   |
|                          \infty                          |                          $\infty$                          |
| \frac{\sum\limits_{i=1}^n x_i}{\prod\limits_{i=1}^n x_i} | $\frac{\sum\limits_{i=1}^n x_i}{\prod\limits_{i=1}^n x_i}$ |
|                                                          |                                                            |

## 10 根式

|    LaTeX表达式     |         效果         | LaTeX表达式 |     效果      |
| :----------------: | :------------------: | :---------: | :-----------: |
|      \sqrt 2       |      $\sqrt 2$       |    \surd    |    $\surd$    |
|    \sqrt {x+y}     |     $\sqrt{x+y}$     | \sqrt[n]{}  | $\sqrt[n]{}$  |
|     \sqrt{x^3}     |     $\sqrt{x^3}$     | \sqrt[n]{x} | $\sqrt[n]{x}$ |
| \sqrt[3]{\frac xy} | $\sqrt[3]{\frac xy}$ |             |               |
|    \sqrt[n]{x}     |    $\sqrt[n]{x}$     |             |               |
|                    |                      |             |               |
|                    |                      |             |               |



##  11 分数

|              LaTeX表达式               |                   效果                   |
| :------------------------------------: | :--------------------------------------: |
|                \frac ab                |                $\frac ab$                |
|              \frac {a}{b}              |              $\frac{a}{b}$               |
|             \frac 1 {b+1}              |             $\frac 1 {b+1}$              |
|            \frac{a+1}{b+1}             |            $\frac{a+1}{b+1}$             |
|             {a+1\over b+1}             |             ${a+1\over b+1}$             |
|      \frac {\frac 1 x + 1}{y + 1}      |      $\frac {\frac 1 x + 1}{y + 1}$      |
|     \dfrac {\dfrac 1 x + 1}{y + 1}     |     $\dfrac {\dfrac 1 x + 1}{y + 1}$     |
|     \tfrac {\tfrac 1 x + 1}{y + 1}     |     $\tfrac {\tfrac 1 x + 1}{y + 1}$     |
|              \cfrac{a}{b}              |              $\cfrac{a}{b}$              |
| \cfrac{2}{1+\cfrac{2}{1+\cfrac{2}{1}}}​ | $\cfrac{2}{1+\cfrac{2}{1+\cfrac{2}{1}}}$ |

* \tfrac：设置分式为textstyle，主要用于行内分式，将分式字号设置为普通字号大小，压缩分式高度，不改变行间距；
* \dfrac：设置分式为displaystyle，单行模式中推荐使用；
* \frac：根据上下文决定使用\tfrac还是\dfrac，会自动选择；
* \cfrac：用于表示连续分式，单个分式是连续分式的特例；

## 12 极限

|              LaTeX表达式              |                   效果                   |
| :-----------------------------------: | :--------------------------------------: |
|                 \lim                  |                  $\lim$                  |
|             \lim_{x\to 0}             |             $\lim_{x\to 0}$              |
| \lim\limits_{x\to 0} \frac {x}{\sinx} | $\lim\limits_{x\to 0} \frac {x}{\sin x}$ |
|                                       |                                          |
|                 max x                 |                 $\max x$                 |
|             \text{MSE}(x)             |             $\text{MSE}(x)$              |
|                \infty                 |                 $\infty$                 |

## 13 三角函数

| LaTeX表达式 |   效果   |
| :---------: | :------: |
|    \sin     |  $\sin$  |
|    \cos     |  $\cos$  |
|   \sin x    | $\sin x$ |
|   \cos x    | $\cos x$ |
|   \sec x    | $\sec x$ |
|             |          |

## 14 积分

* `\,`用于增加间距，如多重积分内dx和dy之间，积分函数和dx之间，增加一个小空格，使之更规范；
* `\!`用于减小间距，如在两个积分号之间，使之更美观；
* `\text`用于将变量体改为直体格式，如积分中dx中的d；

|             LaTeX表达式             |                 效果                  |
| :---------------------------------: | :-----------------------------------: |
|                \int                 |                $\int$                 |
|               \iiint                |               $\iiint$                |
|                \iint                |                $\iint$                |
|                \oint                |                $\oint$                |
|               \oiint                |               $\oiint$                |
|       \int x dx 或 \int{x}dx        |              $\int x dx$              |
|        \int_{1}^{2}{x}\, dx         |        $\int_{1}^{2}{x}\, dx$         |
|      \int_a^b f(x) \, \text dx      |      $\int_a^b f(x) \, \text dx$      |
| \int_0^{+\infty} x^n e^{-x} dx = n! | $\int_0^{+\infty} x^n e^{-x} dx = n!$ |
|  \int_{-\infty}^0 f(x)\,\text d x   |  $\int_{-\infty}^0 f(x)\,\text d x$   |
|                                     |                                       |
|                                     |                                       |

## 15 标注符号

|           LaTeX表达式           |               效果                |       LaTeX表达式       |           效果            |
| :-----------------------------: | :-------------------------------: | :---------------------: | :-----------------------: |
|             \vec x              |             $\vec x$              |   \overrightarrow{AB}   |   $\overrightarrow{AB}$   |
|          \widehat{xy}           |          $\widehat{xy}$           |   \overrightarrow{AB}   |   $\overleftarrow{AB}$    |
|             \bar x              |             $\bar x$              |      \overline{AB}      |      $\overline{AB}$      |
|             \dot x              |             $\dot x$              | \overleftrightarrow{AB} | $\overleftrightarrow{AB}$ |
|             \ddot x             |             $\ddot x$             |     \underline{ABC}     |     $\underline{ABC}$     |
| \stackrel{F.T}{\longrightarrow} | $\stackrel{F.T}{\longrightarrow}$ |  \underrightarrow{AB}   |  $\underrightarrow{AB}$   |
|          \pmb{a}  加粗          |             $\pmb{a}$             | \boldsymbol{a} 加粗斜体 |     $\boldsymbol{a}$      |

## 16 箭头

|    LaTeX表达式    |        效果         |    LaTeX表达式     |         效果         |     LaTeX表达式      |          效果          |
| :---------------: | :-----------------: | :----------------: | :------------------: | :------------------: | :--------------------: |
|                   |                     |        \to         |        $\to$         |       \uparrow       |       $\uparrow$       |
|    \leftarrow     |    $\leftarrow$     |    \rightarrow     |    $\rightarrow$     |      \downarrow      |      $\downarrow$      |
|    \Leftarrow     |    $\Leftarrow$     |    \Rightarrow     |    $\Rightarrow$     |       \Uparrow       |       $\Uparrow$       |
|  \longleftarrow   |  $\longleftarrow$   |  \longrightarrow   |  $\longrightarrow$   |      \Downarrow      |      $\Downarrow$      |
|  \Longleftarrow   |  $\Longleftarrow$   |  \Longrightarrow   |  $\Longrightarrow$   |     \updownarrow     |     $\updownarrow$     |
|                   |                     |      \leadsto      |      $\leadsto$      |     \Updownarrow     |     $\Updownarrow$     |
|                   |                     |  \rightsquigarrow  |  $\rightsquigarrow$  |     \upuparrows      |     $\upuparrows$      |
|  \hookleftarrow   |  $\hookleftarrow$   |  \hookrightarrow   |  $\hookrightarrow$   |   \downdownarrows    |   $\downdownarrows$    |
|  \leftharpoonup   |  $\leftharpoonup$   |  \rightharpoonup   |  $\rightharpoonup$   |   \leftrightarrow    |   $\leftrightarrow$    |
| \leftharpoondown  | $\leftharpoondown$  | \rightharpoondown  | $\rightharpoondown$  |   \Leftrightarrow    |   $\Leftrightarrow$    |
|                   |                     |      \mapsto       |      $\mapsto$       |   \nleftrightarrow   |   $\nleftrightarrow$   |
|                   |                     |    \longmapsto     |    $\longmapsto$     |   \nLeftrightarrow   |   $\nLeftrightarrow$   |
|     \swarrow      |     $\swarrow$      |      \nearrow      |      $\nearrow$      |   \circlearrowleft   |   $\circlearrowleft$   |
|     \nwarrow      |     $\nwarrow$      |      \searrow      |      $\searrow$      |  \circlearrowright   |  $\circlearrowright$   |
|    \nleftarrow    |    $\nleftarrow$    |    \nrightarrow    |    $\nrightarrow$    | \longleftrightarrow  | $\longleftrightarrow$  |
|    \nLeftarrow    |    $\nLeftarrow$    |    \nRightarrow    |    $\nRightarrow$    | \Longleftrightarrow  | $\Longleftrightarrow$  |
|  \dashleftarrow   |  $\dashleftarrow$   |  \dashrightarrow   |  $\dashrightarrow$   |  \rightleftharpoons  |  $\rightleftharpoons$  |
|  \leftleftarrows  |  $\leftleftarrows$  | \rightrightarrows  | $\rightrightarrows$  |  \leftrightharpoons  |  $\leftrightharpoons$  |
|    \Lleftarrow    |    $\Lleftarrow$    |    \Rrightarrow    |    $\Rrightarrow$    |   \leftrightarrows   |   $\leftrightarrows$   |
| \twoheadleftarrow | $\twoheadleftarrow$ | \twoheadrightarrow | $\twoheadrightarrow$ |   \rightleftarrows   |   $\rightleftarrows$   |
|  \leftarrowtail   |  $\leftarrowtail$   |  \rightarrowtail   |  $\rightarrowtail$   |                      |                        |
|  \looparrowleft   |  $\looparrowleft$   |  \looparrowright   |  $\looparrowright$   |                      |                        |
|  \curvearrowleft  |  $\curvearrowleft$  |  \curvearrowright  |  $\curvearrowright$  |                      |                        |
|       \Lsh        |       $\Lsh$        |        \Rsh        |        $\Rsh$        |                      |                        |
|  \upharpoonleft   |  $\upharpoonleft$   |  \upharpoonright   |  $\upharpoonright$   |      \multimap       |      $\multimap$       |
| \downharpoonleft  | $\downharpoonleft$  | \downharpoonright  | $\downharpoonright$  | \leftrightsquigarrow | $\leftrightsquigarrow$ |

## 17 文字颜色

* 颜色的格式为：\color{xxx}ab，设置字符ab的颜色为xxx，xxx可选为Blue、Red、green等颜色单词；

```
x = \dfrac{-b\pm\sqrt{\color{Red}b^2-4ac}}{\color{Blue}2a}
```

$$
x = \dfrac{-b\pm\sqrt{\color{Red}b^2-4ac}}{\color{Blue}2a}
$$

$$
x = \dfrac{-b\pm\sqrt{\color{green}b^2-4ac}}{\color{black}2a}
$$



## 18 序号

给公式添加序号，在公式后面添加\tag{...}。

```
$$ ... \tag1$$
$$ ... \tag{1.1}$$   # 多位序号需要用{}括起来
```

```
\int_0^{+\infty} x^n e^{-x} dx = n! \tag{19.1}
```


$$
\int_0^{+\infty} x^n e^{-x} dx = n! \tag{19.1}
$$

## 19 公式框

```
\int_0^{+\infty} x^n e^{-x} dx = n!
```

$$
\boxed{\int_0^{+\infty} x^n e^{-x} dx = n!}
$$

## 20 文字

|   LaTeX表达式    |        效果        |   LaTeX表达式   |       效果        |
| :--------------: | :----------------: | :-------------: | :---------------: |
|  \mathbb{ABCDE}  |  $\mathbb{ABCDE}$  |  \Bbb{ABCDEF}   |  $\Bbb{ABCDEF}$   |
|  \mathbf{abcde}  |  $\mathbf{abcde}$  | \mathtt{ABCDE}  | $\mathtt{ABCDE}$  |
|  \mathrm{ABCDE}  |  $\mathrm{ABCDE}$  | \mathsf{ABCDE}  | $\mathsf{ABCDE}$  |
| \mathcal{ABCDE}  | $\mathcal{ABCDE}$  | \mathscr{ABCDE} | $\mathscr{ABCDE}$ |
| \mathfrak{ABCDE} | $\mathfrak{ABCDE}$ |     \bold B     |     $\bold B$     |
|      \it B       |      $\it B$       |      \rm B      |      $\rm B$      |
|      \pmb B      |      $\pmb B$      |                 |                   |



## 21 示例

$$
\int_{x^2 + y^2 \leq R^2}   f(x,y) dx dy = 
\int_{\theta=0}^{2\pi}    \int_{r=0}^R    f(r\cos\theta,r\sin\theta) r dr d\theta
$$

$$
\int \!\!\! \int_D f(x,y)dxdy  \int \int_D f(x,y)dxdy
$$

$$
i\hbar\frac{\partial \varphi } {\partial {t}} = \frac{-\hbar^2}{2m} 
\left( \frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2} + 
\frac{\partial^2}{\partial z^2} \right) \varphi  + V \varphi
$$

$$
\frac{d}{dt} \int \!\!\! \int \!\!\! \int_{\textbf{R}^3} 
\left | \varphi (r,t) \right|^2 dx dy dz = 0
$$


$$
f(x) = \frac 1 {\sqrt{2\pi} \sigma} {\rm e} ^ {-\frac {(x-\mu)^2}{2\sigma ^ 2}}\\
f(x) = \frac 1 {\sqrt{2\pi} \sigma} \exp \left[ {-\frac {(x-\mu)^2}{2\sigma ^ 2}}\right]
$$

$$
\lim\limits_{N\to \infty} P \left\{ \left| \frac {I\left( \alpha_i \right)}{N} - H(s) \right| < \varepsilon  \right\} = 1
$$

$$
x(n) = \frac 1 {2\pi} \int _{-π} ^ π X\left( {\rm e} ^ {{\rm j} \omega } \right) {\rm e} ^ {{\rm j} \omega n} \, {\rm d}\omega\\
$$

$$
\begin{align}

\vec B \left( \vec r \right) &= \frac {\mu_0}{4\pi}\oint_C \frac {I \, {\rm d} \vec l \times \vec R}{R^3}\\

&= \frac {\mu_0}{4\pi} \int_V \frac{\vec J_V \times \vec R}{R^3}\, {\rm d} V'

\end{align}
$$













## 【参考】

* https://blog.csdn.net/fuchenqianxiao/article/details/124088512
* https://blog.csdn.net/ViatorSun/article/details/82826664/?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-4--blog-124088512.235^v27^pc_relevant_3mothn_strategy_recovery&spm=1001.2101.3001.4242.3&utm_relevant_index=7
* https://blog.csdn.net/qq_37402392/article/details/121348504
* https://blog.csdn.net/qq_37402392/article/details/121348504







