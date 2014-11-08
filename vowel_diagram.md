# How to draw a vowel diagram in LaTeX

The package ```vowel``` is what you need. The documentation is quite good, and it should be fairly straightforward to derive
diagrams once you take a look at the package. Here, I list three vowel inventories, namely, English, Portuguese and French.
At the end, I also provide the full diagram, so you can derive any other inventory (this is found in the documentation pdf).


```{latex}
% English

% preamble
\usepackage{tipa,vowel}

\begin{center}
{\Large
\begin{vowel}
 \putcvowel[l]{i}{1}
 \putvowel[l]{i}{0pt}{0pt}
 \putcvowel[l]{e}{2}
 \putcvowel[l]{\textipa{E}}{3}
 \putcvowel[l]{a}{4}
 \putcvowel[l]{\textipa{A}}{5}
 \putcvowel[r]{\textipa{6}}{5}
 \putcvowel[l]{\textipa{2}}{6}
 \putcvowel[r]{\textipa{O}}{6}
 \putcvowel[r]{o}{7}
 \putcvowel[r]{u}{8}
 \putcvowel[l]{\textipa{1}}{9}
 \putcvowel{\textipa{@}}{11}
 \putcvowel[l]{\textipa{3}}{12}
 \putcvowel{\textipa{I}}{13}
 \putcvowel{\textipa{U}}{14}
 \putcvowel{\ae}{16}
\end{vowel}
}
\end{center}

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% Portuguese

% preamble
\usepackage{tipa,vowel}

\begin{center}
{\Large
\begin{vowel}
 \putcvowel[l]{i}{1}
 \putcvowel[l]{e}{2}
 \putcvowel[l]{\textipa{E}}{3}
 \putcvowel[l]{a}{4} % posição default IPA
 \putcvowel[r]{\textipa{O}}{6}
 \putcvowel[r]{o}{7}
 \putcvowel[r]{u}{8}
\end{vowel}
}
\end{center}

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% French

% preamble
\usepackage{tipa,vowel}

\begin{center}
\begin{vowel}
 \putcvowel[l]{i}{1}
 \putvowel[l]{i}{0pt}{0pt}
 \putcvowel[r]{y}{1}
 \putcvowel[l]{e}{2}
 \putcvowel[r]{\textipa{\o}}{2}
 \putcvowel[l]{\textipa{E}}{3}
 \putcvowel[r]{\textipa{\oe}}{3}
 \putcvowel[l]{\textipa{a}}{4}
 \putcvowel[r]{\textipa{O}}{6}
 \putcvowel[r]{\textipa{o}}{7}
 \putcvowel[r]{\textipa{u}}{8}
 \putcvowel{\textipa{@}}{11}
\end{vowel}
}
\end{center}


%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% Complete diagram


\usepackage{tipa,vowel}


\begin{center}
{\Large
\begin{vowel}
 \putcvowel[l]{i}{1}
 \putvowel[l]{i}{0pt}{0pt}
 \putcvowel[r]{y}{1}
 \putcvowel[l]{e}{2}
 \putcvowel[r]{\textipa{\o}}{2}
 \putcvowel[l]{\textipa{E}}{3}
 \putcvowel[r]{\textipa{\oe}}{3}
 \putcvowel[l]{\textipa{a}}{4}
 \putcvowel[r]{\textscoelig}{4}
 \putcvowel[l]{\textipa{A}}{5}
 \putcvowel[r]{\textipa{6}}{5}
 \putcvowel[l]{\textipa{6}}{6}
 \putcvowel[r]{\textipa{O}}{6}
 \putcvowel[l]{\textipa{7}}{7}
 \putcvowel[r]{\textipa{o}}{7}
 \putcvowel[l]{\textipa{W}}{8}
 \putcvowel[r]{\textipa{u}}{8}
 \putcvowel[l]{\textipa{1}}{9}
 \putcvowel[r]{\textipa{0}}{9}
 \putcvowel[l]{\textipa{9}}{10}
 \putcvowel[r]{\textipa{8}}{10}
 \putcvowel{\textipa{@}}{11}
 \putcvowel[l]{\textipa{3}}{12}
 \putcvowel[r]{\textcloserevepsilon}{12}
 \putcvowel{\textipa{I}\ \textipa{Y}}{13}
 \putcvowel{\textipa{U}}{14}
 \putcvowel{\textipa{5}}{15}
 \putcvowel{\textipa{\ae}}{16}
\end{vowel}
}
\end{center}

```
