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

\end{document}
```

ビルドすると、こんな感じに出力されます。

![image](https://github.com/kaitas/math-assignments/assets/5110708/97805b01-4386-4e30-ab38-dd25d015c533)

## ChatGPTに問題を生成させる

上記のLaTeXをChatGPT4に渡して
- 日本語のLaTeXで演習問題を生成してください
- \itemではなく (1), (2),... という形で列挙し、各問題の下に空白を入れてください
といった感じでフォーマットも指定していきます聞きます。


![image](https://github.com/kaitas/math-assignments/assets/5110708/75f9e562-6391-48c5-8c8f-acb9737c43f9)

> 了解しました。それぞれの問題を (1), (2), ... の形式で列挙し、各問題の下に適切なスペースを追加するように修正したLaTeXコードを以下に示します。

![image](https://github.com/kaitas/math-assignments/assets/5110708/603ff9d3-aef0-4dbf-bac8-df28bf913d74)



```
\documentclass[12pt]{article}
\usepackage[a4paper, margin=1in]{geometry}
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
\usepackage{graphicx}
\usepackage[utf8]{inputenc}
\usepackage[japanese]{babel}
\usepackage{enumitem}

\begin{document}

\title{数学の演習問題}
\author{}
\date{}
\maketitle

\section*{演習問題}

1. 次の関数は $y = \frac{1}{x}$ のグラフをどのように平行移動したグラフの関数か述べよ。

\begin{enumerate}[label=(\arabic*)]
\item $y=\frac{1}{x-2}-3$ \vspace{2em}
\item $y = \frac{2x+1}{x+1}$ \vspace{2em}
\end{enumerate}

2. 次の関数のグラフを描き、その定義域、値域および漸近線を求めよ。

\begin{enumerate}[label=(\arabic*)]
\item $y = -\frac{3}{x}$ \vspace{2em}
\item $y = \frac{2}{x+1}$ \vspace{2em}
\item $y = -\frac{2}{x}+3$ \vspace{2em}
\item $y = \frac{1}{x+2}-1$ \vspace{2em}
\item $y = -\frac{1}{x+1}+5$ \vspace{2em}
\item $y = -\frac{1}{2x-2}$ \vspace{2em}
\item $y = \frac{x-1}{x+2}$ \vspace{2em}
\item $y = \frac{x}{x+3}$ \vspace{2em}
\item $y = -\frac{x}{x+1}$ \vspace{2em}
\item $y = \frac{2x-1}{2x-2}$ \vspace{2em}
\end{enumerate}

3. 新しい関数のグラフを描き、その定義域および値域を求めよ。

\begin{enumerate}[label=(\arabic*)]
\item $y = -\frac{2}{x-3} + 4$ \vspace{2em}
\end{enumerate}

\end{document}

```

CloudLaTeXにそのまま新規ファイル作成してコンパイルできました。


![image](https://github.com/kaitas/math-assignments/assets/5110708/996f67b3-f2a9-41c7-b8c0-e1ad0b2ffb8f)

新規ファイル作成して右クリック「ターゲット設定」してからコンパイルです。

![image](https://github.com/kaitas/math-assignments/assets/5110708/72226e6c-fd56-42d1-8157-7f260a9e9c28)


学校のテストっぽく整形したい場合は最初のソースとうまく融合させてあげてください・


さて解けるかな～～～！？
（そんなに難しくはなさそう）

## 解答例を生成させる

調子に乗って解答例も生成させる。

- 上記の問題の回答編を追加したTeXを生成してください
- 正答と解答例はすべての問題に対して出力してください。

いい感じの解答解説が生成される雰囲気はありますが、途中で力尽きます。

![image](https://github.com/kaitas/math-assignments/assets/5110708/1d43bee6-2cbd-4fd6-b283-dc56ed8e2840)


![image](https://github.com/kaitas/math-assignments/assets/5110708/a1fa6a35-851b-4239-a0ad-8c3151184f98)

あってるかどうか微妙ですし、
そもそも解を持つかどうかも微妙な問題が混ざっている可能性もありますので、回答は人間と計算機の力を使いましょう。

## 正しい回答を GeoGebra を使って自分で確認させる

回答編は GeoGebraを使ってセルフで解いてもらうといいと思います。

- [https://www.geogebra.org/calculator](https://www.geogebra.org/calculator)

[https://www.geogebra.org/calculator](https://www.geogebra.org/calculator)

自分で数式を退部してもいいですし、TeXが書けるなら
数式のところに上記のドルマークで囲われたところを貼り付けると、簡単に描けます。

![image](https://github.com/kaitas/math-assignments/assets/5110708/0c822dba-58de-4876-bccc-f75e4cabb8e7)

![image](https://github.com/kaitas/math-assignments/assets/5110708/2d41fd7f-8325-4aaf-b1e0-3da27ef144e1)

![image](https://github.com/kaitas/math-assignments/assets/5110708/df185ac3-26cc-409a-9e7f-cab9fd07279a)

`Asymptote()` を使えば漸近線も求められます

![image](https://github.com/kaitas/math-assignments/assets/5110708/8622aaf4-b98e-44c6-afee-acd4b8a7dad2)

ちなみにChatGPT4+Wolframプラグインに訊いてみます。

![image](https://github.com/kaitas/math-assignments/assets/5110708/3f48133a-7b0e-4a82-900a-287426698895)


![image](https://github.com/kaitas/math-assignments/assets/5110708/aee5fedb-2fdf-4aae-bc08-0117d5d69984)

え・・・？もしかしてゼロ除算に弱い？？

![image](https://github.com/kaitas/math-assignments/assets/5110708/9e5c9f76-c473-451b-9e9e-4cea5098f0c8)

何回やっても、[分数関数の一般式](https://www.geogebra.org/m/VK8XHfRv)が解けません。私の問い方が悪いのでしょうか？

$y=\frac{k}{x-p}+q$


![image](https://github.com/kaitas/math-assignments/assets/5110708/ac0ba55d-d840-41b4-8b2e-1df4caf6a3ce)

![image](https://github.com/kaitas/math-assignments/assets/5110708/9ac2c02b-da51-4175-b207-73bce42bb183)

ここは自力で解けたお子さんを褒めてあげていいところですね！


GeoGebraでは ``=Asymptote(((2 x+1)/(x+1)))`` として簡単に漸近線を得ることができます。

![image](https://github.com/kaitas/math-assignments/assets/5110708/06a2e5a1-a37a-451e-a3be-71670a082e4a)


## もっと色々やりたい人へ


- GeoGebraを使った日本語数学教材については[明治大学総合数理学部阿原研究室](http://www.aharalab.sakura.ne.jp/geogebra/index.php)

- [基本操作覚書](https://usidesu.hatenablog.com/entry/2020/01/01/000000)

- [分数関数の可視化](https://www.geogebra.org/m/VK8XHfRv)
