---
title: "Función gamma"
author: "R"
date: "1/3/2022"
output:
  html_document: 
    toc: yes
    number_sections: yes
    keep_md: yes
  word_document:
    toc: yes
  pdf_document: 
    toc: yes
    number_sections: yes
    keep_tex: yes
linkcolor: red
header-includes: \renewcommand{\contentsname}{Contenidos}
citecolor: blue
toccolor: blue
urlcolor: blue 
---




# Lab2

En esta asignatura entrenaremos *cosas* de matemáticas y sus amigos.

## La función Gamma

La función Gamma $\Gamma$ tiene diversas definiciones en la matemática.
La definición que utilizaremos es:

$$ \Gamma(z)= \int_0^{\infty} x^{z-1} \cdot e^{-x}dx, \mbox{ donde } z\in \mathbb{R}.$$



Resolvamos esta integral en el caso    $\Gamma(z+1)$ con  $z\in \mathbb{R}$. Recordemos que  la fórmula integración por partes en este caso es:


$$\int_{0}^{\infty} u \cdot d v =\left[u\cdot v \right]_0^\infty-\int_0^{\infty} v \cdot du.$$

Apliquemos el método de integración por partes a la función $\Gamma$

$$
\begin{aligned}
\Gamma(z+1) &=  \int_0^{\infty} x^{z} \cdot e^{-x}dx= 
\left|
\begin{matrix} u=x^{z}  & dv= e^{-x}\cdot  dx 
\\ du= z \cdot x^(z+1)  & v=-e^{-x} 
\end{matrix}
\right|
\\
&=\left[-x^z\cdot e^{-x}\right]_0^\infty
-\int_0^{\infty} z\cdot x^{z-1} \cdot \left(-e^{-x}\right)\cdot  dx
\\
&=
\lim_{x\to\infty}\left(-x^z\cdot e^{-x}\right)
+
z\cdot \int_0^{\infty} x^{z-1} \cdot e^{-x}\cdot dx.
\end{aligned}
$$

como

$$\lim_{x\to\infty}\left(-x^z\cdot e^{-x}\right)=0$$

tenemos que 

$$\Gamma(z+1)= 
z\cdot \int_0^{\infty} x^{z-1} \cdot e^{-x}\cdot  dx.
$$

Por lo que hemos encontrado una fórmula recurrente, en al que si queremos saber $\Gamma(z+1)$ tenemos que  saber que vale $\Gamma(z)$ y utilizar la fórmula anterior. 

## Las fórmulas recursivas


La fórmulas recursivas son las que dependen de un valor anterior al que se calcula. La más popular es el factorial



La definición de factorial de un un número natural $n\in\mathbb{N}$,  es ¡¡obviamente!! recursiva

$$
\begin{aligned}
\verb+factorial+ = n!: & \mathbb{N} \longrightarrow  \mathbb{N}\\
& n \longrightarrow  n\cdot (n-1)\cdot (n-2) \ldots \cdot 3\cdot 2\cdot 1.
\end{aligned}
$$

Se define con estas reglas:


1. `factorial(0)`=$0!=1$. 
2. `factorial(n+1)=`$(n+1)!=(n+1)*factorial(n).$


En la notación matemática, como ya sabéis el factorial se representa con  el símbolo de exclamación/admiración; así 


1. `factorial(0)`:= $0!=1$.
2. `factorial(n+1)`:= $(n+1)!=(n+1)\cdot n!$.


Así tenemos que 

* $0!=1.$
* $1!=1.$
* $2!= 2\cdot 1= 2.$
* $3!=3\cdot 2\cdot 1= 6.$
* $4!=4\cdot 3\cdot 2\cdot 1 =24.$
* $\ldots \ldots$
* $n!= n\cdot (n-1) \cdot (n-2) \cdots 3\cdot 2\cdot 1.$
* $(n+1)!=  (n+1)\cdot n!= (n+1)\cdot n\cdot (n-1) \cdot (n-2) \cdots 3\cdot 2\cdot 1.$







# Gráfica función Gamma en los reales





```r
curve(gamma(x),xlim=c(1,10),col="red",ylab="Gamma(x)",lwd=2,frame.plot=TRUE,main="Función Gamma")
```

![](gamma_files/figure-html/unnamed-chunk-1-1.png)<!-- -->

















