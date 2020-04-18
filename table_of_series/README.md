<head>
<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>
</head>

$$ d $$

\[ f(x) = \sum_{n = 0}^{\infty} \dfrac{f^{(n)}(x - a)}{n!} (x - a)^n  \]

\[ f(x) = \sum_{n = 0}^{\infty} \dfrac{f^{(n)}(x)}{n!} x^n  \]

## 常用麦克劳林级数
\[ e^x = \sum_{n = 0}^{\infty} \dfrac{x^n}{n!}\]

\[ \ln(1 - x) = - \sum_{n = 0}^{\infty} \dfrac{x^{n+1}}{n + 1} \] 

\[ \ln(1 + x) = \sum_{n = 0}^{\infty} (-1)^n \dfrac{x^{n+1}}{n + 1} \]

\[ \dfrac{1}{1 - x} = \sum_{n = 0}^{\infty} x^n \]

\[ \dfrac{1}{1 + x} = \sum_{n = 0}^{\infty} (-1)^n x^n \]

\[ \dfrac{1}{(1 - x)^2} = \sum_{n = 0}^{\infty} (n + 1)x^n \]

\[ (1 + x)^\alpha = \sum_{n = 0}^{\infty} \binom\alpha n x^n \]

\[ \sin x = \sum_{n = 0}^{\infty}(-1)^n\dfrac{x^{2n + 1}}{(2n+1)!} \] 

\[ \cos x = \sum_{n = 0}^{\infty} (-1)^n \dfrac{x^{2n}}{(2n)!} \] 

## 常用泰勒展开式
红色部分为常见等价无穷小.
\[ e^x = {\color{red} 1 + x} + \dfrac{x^2}{2!} + \dfrac{x^3}{3!} + o(x^3) \]

\[ \ln (1 - x) = - x - \dfrac{x^2}{2} - \dfrac{x^3}{3} - o(x^3) \]             

\[ \ln (1 + x) = {\color{red} x} - \dfrac{x^2}{2} + \dfrac{x^3}{3} - o(x^3) \]

\[ \dfrac{1}{1 - x} = 1 + x + x^2 + x^3 + o(x^3) \]

\[ \dfrac{1}{(1 - x)^2} = 1 + 2 x + 3 x^2 + 4 x^3 + o(x^3) \]

\[ (1 + x)^\alpha = 1 + \alpha x + \dfrac{\alpha(1 - \alpha)}{2}x^2 + o(x^2) \]

\[ \sin x = {\color{red} x} - \dfrac{x^3}{3!} + \dfrac{x^5}{5!} - o(x^5) \]

\[ \cos x = {\color{red} 1 - \dfrac{x^2}{2!}} + \dfrac{x^4}{4!} - o(x^4) \]

\[ \tan x = {\color{red} x} + \dfrac{x^3}{3} + \dfrac{2 x^5}{15} + o(x^5) \]

\[ \arcsin x = {\color{red} x} + \dfrac{x^3}{6} + o(x^3) \]

\[ \arccos x = \dfrac{\pi}{2} - \arcsin x = \dfrac{\pi}{2} - x - \dfrac{x^3}{6} - o(x^3) \]

\[ \arctan x = {\color{red} x} - \dfrac{x^3}{3} + \dfrac{x^5}{5} + o(x^5) \]
