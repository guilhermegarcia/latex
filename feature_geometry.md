# Feature geometry in LaTeX

### From feature to utterance

If you're a phonologist typesetting a document, feature geometry might be one of the most time-consuming non-linear representations. OK, you rarely need to lay out the whole structure in a paper, but you might want to have it for class handouts/slides, for example. Also, having the *whole thing* is the quickest way to get different parts later on.

The idea here is to use the ```tikz``` package, which is way more intuitive than ```pst-asr``` (the same goes for the documentation). If you're familiar with ```tikz```, you probably know that you can create symmetric or asymmetric structures, which allows you to typeset syntax and prosody, respectively (the ```\draw``` function is great for prosodic representations). The 'problem' is that connecting lines in asymmetric representations do not meet at a single point. The structure below resolves the problem by manually setting coordinates so that all lines *meet*—as you'd expect in a syntactic tree.

Finally, you'll notice I link feature geometry to prosody here. This is, again, aimed at students, who may find it clarifying as far as representations go.


```{latex}
% Created by Guilherme D. Garcia (McGill)

\documentclass[10pt]{article}

\usepackage{tikz-qtree,qtree,tikz}
\usepackage{caption,tipa}
\usepackage{multicol}
\usepackage{booktabs}
\usepackage{array}
\usepackage{geometry}
\usepackage{hyperref}

\geometry{textheight=10in}


    
\title{Prosody \& Feature Geometry in {\LaTeX}}
\date{}
\author{\href{http://www.guilherme.ca}{Guilherme D. Garcia}\\ \emph{McGill University}}
\begin{document}
\maketitle
\thispagestyle{empty}

\begin{center}
\begin{tikzpicture}
\path (4,16) node (-9) {U};
\path (4,15) node (-8) {IP};
\path (4,14) node (-7) {PPh};
\path (4,13) node (-6) {CG};
\path (4,12) node (-5) {$\omega$};
\path (4,11) node (-4) {$\Sigma$};
\path (4,10) node (-3) {$\sigma$};
\path (4,9) node (-2) {$\mu$};
\path (4,8) node (-1) {N};
\path (4,7) node (0) {$\times$};

\path (4,6) node (1) {\fbox{\tt Root}};
\path (1,4.5) node (2) {\tt{laryngeal}};
\path (3.5,4) node (3) {\tt{[nasal]}};
\path (7,4) node (4) {\tt{Oral cavity}};

\path (-0.5,3.5) node (5) {\tt{[spread]}};
\path (0.8,3) node (6) {\tt{[constr]}};
\path (2,2.5) node (7) {\tt{[voice]}};

\path (9,3) node (8) {\tt{[cont]}};
\path (7,2.5) node (9) {\tt{C-place}};
\path (7,1.5) node (10) {\tt{vocalic}};

\path (9,0.5) node (11) {\tt{aperture}};
\path (4,0) node (12) {\tt{V-place}};

\path (2,-1) node (13) {\tt{[labial]}};
\path (3.5,-2) node (14) {\tt{[coronal]}};
\path (5,-1.2) node (15) {\tt{[dorsal]}};

\path (2.5,-3.5) node (16) {\tt{[anterior]}};
\path (4.8,-4) node (17) {\tt{[distributed]}};

\path (6,-2.2) node (18) {\tt{[ATR]}};

\path (8,-0.5) node (19) {\tt{[open$_1$]}};
\path (9.5,-1) node (20) {\tt{[open$_2$]}};
\path (11,-0.5) node (21) {\tt{[open$_3$]}};

\draw (4,5.6) -- (2) ;
\draw (4,5.6) -- (3) ;
\draw (4,5.6) -- (4) ;
\draw (1,4.3) -- (5) ;
\draw (1,4.3) -- (6) ;
\draw (1,4.3) -- (7) ;
\draw (7,3.8) -- (8) ;
\draw (7,3.8) -- (9) ;
\draw (9) -- (10) ;
\draw (7,1.3) -- (11) ;
\draw (7,1.3) -- (12) ;
\draw (9,0.3) -- (19) ;
\draw (9,0.3) -- (20) ;
\draw (9,0.3) -- (21) ;
\draw (4,-0.2) -- (13) ;
\draw (4,-0.2) -- (14) ;
\draw (4,-0.2) -- (15) ;
\draw (15) -- (18) ;
\draw (3.5,-2.2) -- (16) ;
\draw (3.5,-2.2) -- (17) ;

\draw (1) -- (0) ;
\draw (0) -- (-1) ;
\draw (-1) -- (-2) ;
\draw (-2) -- (-3) ;
\draw[dotted] (-3) -- (-4) ;
\draw[dotted] (-4) -- (-5) ;
\draw[dotted] (-5) -- (-6) ;
\draw[dotted] (-6) -- (-7) ;
\draw[dotted] (-7) -- (-8) ;
\draw[dotted] (-8) -- (-9) ;

\end{tikzpicture}
\end{center}
\end{document}

```
