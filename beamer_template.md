#### My beamer template (```Malmoe``` theme)

This is the beamer template I use. It's an all-black version of the ```Malmoe``` theme, and I've also adapted the footline to include
the frame number. There are some other subtle/minor differences as well.

```{latex}
\documentclass[xcolor=dvipsnames]{beamer}
\usecolortheme[named=Black]{structure}
\usepackage{tipa}
\usepackage{multicol}
\usepackage{color}
\usepackage{qtree}
\usepackage{booktabs}
\usepackage{arydshln}
%\usefonttheme{professionalfonts}
%\usefonttheme{serif}
%\usepackage{fontspec}
%\setmainfont{CMU Serif}

\usetheme{Malmoe}               

%\beamertemplatenavigationsymbolsempty  % To remove navigation controls


\title{Title}

\subtitle{Subtitle}

\author[Person (Institution)]{Author}

%\titlegraphic{\includegraphics[width=1cm]{your_logo_here.jpg}} % A logo

\institute[University] 
{
  Blah University\\
  \href{link_to_website}{\ttfamily your_website}
}



\date{Event X}




\subject{Linguistics}


\setbeamertemplate{footline}
{
  \leavevmode%
  \hbox{%
  \begin{beamercolorbox}[wd=.25\paperwidth,ht=2.25ex,dp=1ex,center]{author in head/foot}%
    \usebeamerfont{author in head/foot}{\color{black!20}{\insertshortauthor}}
  \end{beamercolorbox}%
  \begin{beamercolorbox}[wd=.6\paperwidth,ht=2.25ex,dp=1ex,center]{title in head/foot}%
    \usebeamerfont{title in head/foot}{\color{black!20}{\insertshorttitle}}\end{beamercolorbox}%
  \begin{beamercolorbox}[wd=.15\paperwidth,ht=2.25ex,dp=1ex,center]{title in head/foot}%
    {\color{black!20}{\insertframenumber{} / \inserttotalframenumber}}
  \end{beamercolorbox}}%
  \vskip0pt%
}



\begin{document}

\begin{frame}
  \titlepage
\end{frame}

\begin{frame}{}
  \tableofcontents
  % You might wish to add the option [pausesections]
\end{frame}


%%%%%%%%%%%%%%%%%%% PART I %%%%%%%%%%%%%%%%%%%

\section{Part I}

\subsection{Subsection I}

\begin{frame}{Title}%{Optional Subtitle}

\begin{itemize}
	\item Example
  
  \end{itemize}

\end{frame}

\section{Part II}
\subsection{Subsection I}

\begin{frame}{Title}

	Example
	
\end{frame}


\section{Part III}
\subsection{Subsection I}

\begin{frame}{Title}

	Example
	
\end{frame}


\end{document}

```

