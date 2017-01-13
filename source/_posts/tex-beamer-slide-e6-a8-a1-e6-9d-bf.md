---
title: Tex Beamer Slide模板
tags:
  - Beamer
  - LaTex
  - Tex
id: 598
categories:
  - HOWTO
  - Tex
  - 文档创作
date: 2012-06-26 14:59:59
---

  

[tex]
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% 
% 26/06/2012
% edited by sunchunman 
%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%% 
\documentclass[compress,CJK,blue]{beamer}
\mode&lt;presentation&gt;

\usetheme{CambridgeUS}
% other themes: AnnArbor, Antibes, Bergen, Berkeley, Berlin, Boadilla, boxes, CambridgeUS, Copenhagen, Darmstadt, default, Dresden, Frankfurt, Goettingen,
% Hannover, Ilmenau, JuanLesPins, Luebeck, Madrid, Maloe, Marburg, Montpellier, PaloAlto, Pittsburg, Rochester, Singapore, Szeged, classic

\usecolortheme{whale}
% color themes: albatross, beaver, beetle, crane, default, dolphin, dov, fly, lily, orchid, rose, seagull, seahorse, sidebartab, structure, whale, wolverine

%\usefonttheme{professionalfonts}
% font themes: default, professionalfonts, serif, structurebold, structureitalicserif, structuresmallcapsserif

% pdf is displayed in full screen mode automatically
%\hypersetup{pdfpagemode=FullScreen}

% define your own colours:
\definecolor{Red}{rgb}{1,0,0}
\definecolor{Blue}{rgb}{0,0,1}
\definecolor{Green}{rgb}{0,1,0}
\definecolor{magenta}{rgb}{1,0,.6}
\definecolor{lightblue}{rgb}{0,.5,1}
\definecolor{lightpurple}{rgb}{.6,.4,1}
\definecolor{gold}{rgb}{.6,.5,0}
\definecolor{orange}{rgb}{1,0.4,0}
\definecolor{hotpink}{rgb}{1,0,0.5}
\definecolor{newcolor2}{rgb}{.5,.3,.5}
\definecolor{newcolor}{rgb}{0,.3,1}
\definecolor{newcolor3}{rgb}{1,0,.35}
\definecolor{darkgreen1}{rgb}{0, .35, 0}
\definecolor{darkgreen}{rgb}{0, .6, 0}
\definecolor{darkred}{rgb}{.75,0,0}

\xdefinecolor{olive}{cmyk}{0.64,0,0.95,0.4}
\xdefinecolor{purpleish}{cmyk}{0.75,0.75,0,0}

% \usepackage{beamerinnertheme_______}
% inner themes include circles, default, inmargin, rectangles, rounded

%\usepackage{beamerouterthemesmoothbars}
% outer themes include default, infolines, miniframes, shadow, sidebar, smoothbars, smoothtree, split, tree

\useinnertheme[]{rounded}
\useoutertheme[]{smoothtree}

% to have the same footer on all slides
%\setbeamertemplate{footline}[text language=&quot;line&quot;][/text]{xxx xxx xxx}
%\setbeamertemplate{footline}[text language=&quot;line&quot;][/text]{} % or empty footer

% include packages
\usepackage{subfigure}
\usepackage{multicol}
\usepackage{amsmath}
\usepackage{epsfig}
\usepackage{graphicx}
\usepackage[all,knot]{xy}
\xyoption{arc}
\usepackage{url}
\usepackage{multimedia}
\usepackage{hyperref}
\usepackage{setspace}

\usepackage{CJK}

\begin{document}
\begin{CJK}{UTF8}{gbsn}

\title{标题}
\subtitle{副标题}
\author{作者}
\institute{ 指导教师:***}
\vspace{4cm}
\date{\scriptsize ****大学 **学院 ***系  \\ \vspace{.10cm}May 25, 2012}

\titlepage

\section[Outline]{}
\frame{
\tableofcontents
}

\section{总标题}
\subsection{子标题1}
\frame{\frametitle{frame标题1}
}

\frame{\frametitle{frame标题2}
}

\subsection{子标题1}
\frame{\frametitle{frame标题}
}

\end{CJK}
\end{document} 
[/tex] 