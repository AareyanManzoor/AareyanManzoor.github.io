---
layout: posts
toc: true
comments: true
---
<p>There is an isomorphism theorem of Gelfand, detailed in the next paragraph. It ends up giving an (anti)-equivalence of categories between \(C^\ast\)-algebras and the category of locally compact haussdorf spaces. It gives rise to the philosophy that \(C^\ast\) algebras are really the study of "non-commutative topology". One of the ideas here is that phenomena in topology should have their counterparts in \(C^\ast\)-algebras. One of the most important examples of this is the extension of \(K\)-theory to \(C^\ast\)-algebras. Today, we do something simpler but still very much striking. We talk about compactifications and their analogues, and how we can use this interplay between topology and \(C^\ast\)-algebras to learn more about compactifications. </p>


## The Gelfand Isomorphism

<p>
Recall a Banach space is a normed \(\bb{C}\)-vector space complete under the induced metric. A Banach algebra in turn is a Banach space with a multiplication, such that \(\norm{ab}\leq \norm{a}\norm{b}\). The simplest such objects to study are the abelian Banach algebras. For each unital abelian Banach algebra \(A\), take \(\Spec(A)\) to be the space of characters, i.e homomorphisms \(A\lra{\gamma}\bb{C}\). We can give \(\Spec(A)\) the <a href="https://mathworld.wolfram.com/Weak-StarTopology.html"> weak*-topology</a> and its easy to check due after applying the  Banach-Alaoglu theorem that this is infact a compact space. Now we get a representation 
\[\Gamma: A \lra{} C(\Spec(A)),\quad \Gamma(a)(\gamma) = \gamma(a)\]
The norm on \(C(X)\) for compact haussdorf \(X\), the space of continous functions \(X\lra{}\bb{C}\), is \(\norm{f}_\infty= \mathrm{sup}_{x\in X} |f(x)|\). We call this the Gelfand representation. Note we could have asked for \(A\) to be non-unital, and then the character space would have been locally compact haussdorf. We would have to use \(C_0(\Spec(A))\) then, the space of continous functions like before but they go to zero at infinity (think about infinity by thinking about the one point compactification.).
</p>

<p>
A \(C^\ast\) algebra is an algebra with an involution \(\ast\) such that \(\norm{a^\ast a} = \norm{a}^2\). Note that if pointwise complex conjugation is the involution, both \(C(Y)\) and \(C_0(X)\) are \(C^\ast\)-algebras.Now the big theorem due to Gelfand is that for commutative \(C^\ast\) algebras, the Gelfand representation is an isomorphism. This tells us each non-unital commutative \(C^\ast\)-algebra is dual to some LCH space, and that every unital commutative is dual to some compact haussdorf space. A lot of \(C^\ast\) theory now is to see how much of this isomorphism theorem we can translate over to the non-commutative case. So in a sense \(C^\ast\)-algebra is the study of non-commutative topology. With that being said, we expect concepts in topology to carry over to \(C^\ast\)-algebras and vice versa. We will see that for compactification today.
</p>

<p>
I should mention that this really is an (anti-)equivalence of categories between commutative \(C^\ast\) algebras and the category of LCH spaces with continuous maps. Send a space to its \(C_0\) and a commutative algebra to its spectrum.
</p>
## Unitizations and Compactifications 
<p>We shall say compact \(Y\) is a compactification of LCH \(X\) (non-compact) if
<li>There is an embedding \(\iota: X \hookrightarrow Y\) </li>
<li> The image \(\iota(X)\) is dense in \(Y\) </li> </p>

<p>
The easiest example of this is \(\opc{X}\), the one point compactification. This is just adding a single point to \(X\), call it \(\infty\), to make it compact. We can also write it by its universal property, that any compactification of \(X\) maps into \(\opc{X}\), i.e \(\opc{X}\) is the "smallest" compactificaiton. 
</p>
<p>

As mentioned before, the philosophy is that every topological concept should have an analogue in operator theory. So lets look at \(C(\opc{X})\) towards that end. Notice that we have a map \(C(\opc{X})\lra{\cong} C_0(X) \oplus \bb{C}\) sending  \(f\mapsto ((f-f(\infty))\mid_{X},f(\infty))\). It is easy to see this is an isomorphism. So adjoining a unit like this is the analogue of the one-point compactification. Lets try to find the analogues for compactifications in general. There is a unique norm on each \(C^\ast\)-algebra that satisfies the \(C^\ast\) identity, I leave it as an exercise to figure out the norm on \(C_0(X)\oplus \bb{C}\) making it a \(C^\ast\)-algebra. 
</p>

<p>
Let \(X\lra{\iota}Y\) be a compactification of \(X\). Consider \(f\in C_0(X)\), then it extends to a \(\opc{f} \in C(\opc{X})\). We can combine the map \(Y\lra{}\opc{X}\) given by the universal property of \(\opc{X}\) and \(\opc{f}\)  to get an element of \(C(Y)\).
 <center>
<img src = "/assets/images/cd/C0(X)intoC(Y).png" alt = "" width = "300" height = "300">
</center>
Hence we have defined an embedding \(C_0(X) \lra{} C(Y)\). Note that this entire arguement only required \(Y\) to be compact, i.e we did not use the density of \(X\) in \(Y\). Here is how we translate that, take an ideal \(0\neq I\subset C(Y)\), then notice that \(C_0(X)\cap C(Y)\neq 0\). This is because if \(g\in C(Y)\), then \(gC_0(X)=0\) would mean \(g\) is \(0\) on \(X\) and hence by density, on \(Y\). So we collect these to get the dual concept of compactification for \(C^\ast\) algebras.
</p>

<p>
A unitization of a \(C^\ast\)-algebra \(A\) is:
<li> An embedding into an unital \(C^\ast\)-algebra \(B\), i.e \(A\lra{}B\) </li>
<li> the image of \(A\) in \(B\) is a (two-sided) essential ideal, i.e for every ideal \(I\subset B\), \(A\cap I \neq 0\).</li>
</p>

<p>
I have already shown compactifications lead to unitizations.I leave it as an exercise to show the converse. 
</p>

## Multiplier Algebras.
<p>
The Stone-Čech compactification of a LCH space \(X\), \(\beta X\), is the biggest compactification of \(X\). As we saw above, we expect this to correspond to the biggest unitization of a non-unital \(C^\ast\)-algebra \(A\). The advantage of thinking in these terms is that for \(C^\ast\) algebras this is quite explicit. Indeed, the biggest unitization of \(A\), called \(M(A)\)(its multiplier algebra) is given as follows:
</p>
<p> 
\(M(A)\) is the set of double centralizers \((L,R)\) on \(A\). This means:
<li> \(L,R\) are bounded linear maps \(A\lra{} A\)</li>
 <li> \(aL(b) = R(a)b\)</li>
<li> \(\lambda(L,R) +(L',R') = (\lambda L+L', \lambda R+R')\) for \(\lambda\in \bb{C}\) </li>
<li> \((L,R)(L',R')=(LL',R'R)\)</li>
<li> Its unit is \((1_A,1_A)\)</li>
<li>  One can check from this that under the operator norm, \(\norm{L}=\norm{R}\), so naturally we define the norm \(\norm{(L,R)} = \norm{L}\)</li>
<li> \((L,R)^\ast= (R^\ast, L^\ast)\), where \(T^\ast(a) = T(a^\ast)^\ast\) for any bounded operator \(T\) on \(A\) and \(a\in A\).</li>
For \(c\in A\), we can define the double centralizer \((L_c,R_c)\), where \(L_c\) is left translation by \(c\) and \(R_c\) right translation. This gives an isometric embedding \(A\lra{} M(A)\). I leave it as an exercise to show that \(A\) is essential in \(M(A)\).
</p>

<p>
Suppose \(B\) contains \(A\) as an ideal. Then notice we have a map \(\psi:B\lra{}M(A)\), by sending \(c\mapsto (L_c,R_c)\) again and using the fact that \(A\) is an ideal. This extends the cannonical map \(A\lra{} M(A)\). This is infact unique, for say \(\phi:B\lra{} M(A)\) also extended it. Then for \(b\in B, a\in A\), we would have \[\psi(b) (L_a,R_a) = \psi(ba) = (L_{ba},R_{ba}) =\phi(ba) = \phi(b) (L_a,R_a)\] So that \( (\phi(a)-\psi(a)) A =0\) in \(M(A)\), but \(A\) is essential in \(M(A)\) so \(\phi(a)=\psi(a)\). Finally suppose \(A\) is essential in \(B\), then if \(b\in \ker(\psi)\) then \(L_b(A) = bA=0\), so that \(b=0\). Hence the map is injective.
</p>

<p>
To summarize, whenever \(B\) contains \(A\) as an essential ideal, \(B\) has a unique embedding into \(M(A)\). So \(M(A)\) is the biggest unitization as promised. We will get to the commutative case in the next section, but a good example for now is that if \(A=K(H)\), compact operators on some hilbert space, then \(M(A) = B(H)\), bounded operators on that hilbert space.</p>

## Stone-Čech Compactification 

<p>
The Stone-Čech Compactification, \(\beta X\),is the biggest compactification of a space, i.e if \(Y\) is a compactification than \(\beta X\) uniquely maps into \(Y\) making the obvious diagram commute. This is literally the dual condition of the multiplier algebra, so we just need to figure out what \(M(C_0(X))\) is. Luckily for us, the answer is easy: \(C_b(X)\), bounded continuous functions on \(X\) with sup norm. One can easily check that \(C_0(X)\) is essential in \(C_b(X)\), so that there is a injective map \(\psi: C_b(X) \lra{} M(C_0(X))\). All we need to do is show surjection, which is easily done but the proof I know is a bit annoying and uses some other tools (like approximate units). I will hence refer the user to Gerard Murphy's book on the topic, page 83.
</p>

<p> 
By the Gelfand Isomorphism, we know that \(C_b(X)\cong C(\beta X)\) for some \(\beta X\), and by the universal property discussed before, this \(\beta X\) is indeed the Stone-Čech compactification of \(X\). This proves that such a compactification exists in the first place but also gives a very nice explicit form for what the space should be. 
</p>

