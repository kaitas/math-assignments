# こどもに数学の問題を学校のテストに近い雰囲気で解いてもらうサンプル

『数学の試験がよろしくなかった……』そんな時に大事なのは、演習問題の徹底した復習ですが、実際に自分のノートだけで復習がしっかりやれるようなら、数学の勉強で詰まったりはしないでしょう。

ここは「ビジュアル的に数学の試験っぽい演習問題」を、「時間内で解けたか？」「向上したか」を家庭学習でチェックアップしていくための無料のツールについて検討しています。

## サクッと数式を画像化したい！

まず、GitHubでは2022年5月19日以降 markdownにおいて LaTeX的な数式が利用できるようになっています。

使い方は簡単、ドル記号で囲えばいいです。注意としては、ドル記号の後にスペースなど入れないこと。

[公式による例](https://github.blog/2022-05-19-math-support-in-markdown/)

> When $a \ne 0$, there are two solutions to $(ax^2 + bx + c = 0)$ and they are 
$$ x = {-b \pm \sqrt{b^2-4ac} \over 2a} $$

これで、お子さんが貰ってきたテスト問題をひたすらLaTeX書式で打ち込んでいけばOK。

多少間違えたり順番を入れ替えたりすれば、演習にもなります。

## テスト形式でプリントをつくりたい！

LaTeXを使いたい場合は[CloudLaTex](https://cloudlatex.io/)に「数学問題」というテンプレがあるので使うとこんな感じの「数学の試験っぽい演習問題」が生成できます。

![image](https://github.com/kaitas/math-assignments/assets/5110708/7396efc2-7dbe-45a7-83d3-d4dcc69e850e)


前半はこんな感じ（テンプレそのまま＋マクロを追加）
```
\documentclass[paper=a4, dvipdfmx, fleqn,twocolumn, uplatex]{jlreq}
\usepackage{amsmath, amssymb,ascmac}
\usepackage{bxpapersize}
\usepackage{tikz}
\usepackage{multicol}
\usepackage[top=18truemm,bottom=20truemm,left=18truemm,right=18truemm]{geometry}
\usepackage{okumacro}
\usepackage{tcolorbox}
\usepackage{graphicx,xcolor}
\usepackage{ceo}
\tcbuselibrary{skins}
\usetikzlibrary{patterns}
\renewcommand{\labelenumi}{(\theenumi)\ }
\newcommand{\spc}{{\vspace{1cm}}}
\newcommand{\spcval}{{\vspace{4cm}}値域：　　　　　　　定義域：\\}
\newcommand{\ctext}[1]{\raise0.2ex\hbox{\textcircled{\scriptsize{#1}}}}
\setlength{\columnseprule}{0.8pt}
\begin{document}
```


基礎数学I 特訓問題　（　　　月　　　日）\\

開始：　　　　終了：　　　　　得点：\\

1. 次の関数は $y = \frac{1}{x}$ のグラフをどのように平行移動したグラフの関数か．

(1) $y=\frac{1}{x-2}-3$

\spc

(2) $y = \frac{2x+1}{x+1}$

\spc

2. 次の関数のグラフをかけ．また，その定義域，値域および漸近線を求めよ．\\

\kangaekata\ \ 
定義域，値域，領域を図示して検算する．\\

(1) $y = -\frac{3}{x}$

\spcval

(2) $y = \frac{2}{x+1}$

\spcval

(3) $y = -\frac{2}{x}+3$

\spcval

(4) $y = \frac{1}{x+2}-1$

\spcval

(5) $y = -\frac{1}{x+1}+5$

\spcval

(6) $y = -\frac{1}{2x-2}$

\spcval

(7) $y = \frac{x-1}{x=2}$

\spcval

(8) $y = \frac{x}{x+3}$

\spcval

(9) $y = -\frac{x}{x+1}$

\spcval

(10) $y = \frac{2x-1}{2x-2}$

\spcval

3. 次の関数のグラフをかけ．また，その定義域，値域を求めよ．\\

(1) $y = \frac{2x-3}{x-2}$

\spcval

(2) $y = \frac{x + 3}{x + 1}$

\spcval


(3) $y = \frac{2x+3}{2x-2}$

\spcval

(4) $y = \frac{-x-4}{x-2}$

\spcval

5) $y = \frac{x+1}{2x+1}$


\spcval


6) $y = \frac{-3x-4}{2x+1}$

\spcval

最後に 
```
\end{document}
```
するのをわすれずに

ビルドすると、こんな感じに出力されます。

![image](https://github.com/kaitas/math-assignments/assets/5110708/97805b01-4386-4e30-ab38-dd25d015c533)



なお、回答編は GeoGebraを使ってセルフで解いてもらうといいと思います。

[https://www.geogebra.org/calculator](https://www.geogebra.org/calculator)

数式のところに上記のドルマークで囲われたところを貼り付けると、簡単に描けます。

![image](https://github.com/kaitas/math-assignments/assets/5110708/0c822dba-58de-4876-bccc-f75e4cabb8e7)

![image](https://github.com/kaitas/math-assignments/assets/5110708/2d41fd7f-8325-4aaf-b1e0-3da27ef144e1)

![image](https://github.com/kaitas/math-assignments/assets/5110708/df185ac3-26cc-409a-9e7f-cab9fd07279a)

`Asymptote()` を使えば漸近線も求められます

![image](https://github.com/kaitas/math-assignments/assets/5110708/8622aaf4-b98e-44c6-afee-acd4b8a7dad2)

## もっと色々やりたい人へ


- GeoGebraを使った日本語数学教材については[明治大学総合数理学部阿原研究室](http://www.aharalab.sakura.ne.jp/geogebra/index.php)

- [基本操作覚書](https://usidesu.hatenablog.com/entry/2020/01/01/000000)

- [分数関数の可視化](https://www.geogebra.org/m/VK8XHfRv)
