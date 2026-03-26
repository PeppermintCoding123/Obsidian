- propositional
## propositional tableau calculus $\mathcal{T}_0$
$$\frac{(A \wedge B)^T}
{\begin{array} _A^T \\ B^T\end{array}}
\mathcal{T}_0\wedge \quad

\frac{(A \wedge B)^F}
{\begin{array} _A^F & | & B^T\end{array}}
\mathcal{T}_0\vee
$$
$$\frac{\neg A^T}{A^F}\mathcal{T}_0\neg^T \quad
\frac{A^F}{(A)^T}\mathcal{T}_0\neg^F
$$
$$\frac{\begin{array} _(A)^\alpha \\ (B)^\beta\end{array} \quad \alpha \neq \beta}{\bot}\mathcal{T}_0\bot 
$$
saturated = no new rule adds new material
closed branch = ends in $\bot$ 
closed tableau = all branches are closed
## derivable inference rule $\mathcal{T}_0$

$$\frac{(A\Rightarrow B)^T}
{\begin{array} _A^F &|& B^T\end{array}}
\quad
\frac{\begin{array} _A^T \\ (A\Rightarrow B)^T \end{array}}{B^T}
\quad
\frac{(A\Rightarrow B)^F}
{\begin{array} _A^T \\ B^F\end{array}}$$
$$\frac{(A \vee B)^T}
{\begin{array} _A^T & | & B^T\end{array}}
\quad
\frac{(A \vee B)^F}
{\begin{array} _A^F \\ B^F\end{array}}
$$
$$\frac{(A \Leftrightarrow B)^T}
{\begin{array} _A^T & | & A^F \\ B^T & | & B^F \end{array}}
\quad
\frac{(A \Leftrightarrow B)^F}
{\begin{array} _A^T & | & A^F \\ B^F & | & B^T\end{array}}
$$

Blatt 8 Übung



[[Tableaux Soundness]]