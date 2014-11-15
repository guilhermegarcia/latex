## Tableaux and tables

This is not simply about making *tableaux*. There's a package for that, and you can actually make one yourself without the package. The problem is this: if you have tables **and** tableaux in your paper/thesis/dissertation, presumably you want two things: (1) you want each tableau to be numbered as **'Tableau 1:...'**; (2) you (may) want to have a list of tables and a **separate** list of tableaux. If you've tried that already, you know this won't happen automatically. So what I do here is (a) build a tableau form scratch (no package) and (b) make (1) and (2) above happen. Just follow the code and comment if you have suggestions, please.

### Basic tableau-like table

Here's a basic table with some OT features. This will yield a '**Table 1:...**' caption.

```{latex}
...
\usepackage{multicol,array,arydshln,caption,tipa,bbding}
...

\begin{document}
\begin{table}[h]\caption{An example}

\centering
\def\arraystretch{1.5} % spacing 
\begin{tabular}[c]{|rll || c : c | c |} 
\hline 
\multicolumn{3}{|r||}{/input/} \\ 
\hline 
\hline
\HandRight & a & [candidate 1] &  &  &    \\ 
\hline
& b & [candidate 2] &  &  &    \\
\hline
& c & [candidate 3] &  &  &    \\
\hline
\end{tabular}
\label{table:OT Tableau} 
\end{table}
```

You probably don't want to change the ```type``` of tables here, since you might have **both** trables and tableaux in your document. One solution is to elaborate a new float and give it a new type, namely, ```tableau```.

```{latex}
...
\usepackage{cast-of} % this allows us to add a new argument to float captions
\usepackage{tocbasic}
\DeclareNewTOC[
  type=tableau,
  types=tableaux,
  float,
  floattype=4,
  name=Tableau,
  listname={List of Tableaux}
]{lop}
```

Finally, you every tableau in your document will begin with ```\begin{table}[h]\captionof{tableau}{An example}```, so that all tableaux have their own caption. This will keep tables and tableaux separated.

 
