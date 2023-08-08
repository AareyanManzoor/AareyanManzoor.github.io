---
layout  : posts
toc     : false
comments: true
classes : wide
---

<p> Recently I was a counselor at <a href="https://rossprogram.org/">the Ross math program</a> where quadratic reciprocity was one of the main things we built up to. (as a side note, I seriously recommend this job, some of the most fun I have had.) Quadratic reciprocity has always been mysterious to me. It is a simple enough statement: knowing when \(p\) is a QR mod \(q\) can be determined if we know when \(q\) is a QR mod \(p\). However this has led itself to 246 published proofs somehow, which always suggested to me something deep should be embedded into the statement. However before last month I could not really convince myself of this being a deep statement. A lot of proofs of it is often just e.g. counting or doing a computation and it just comes out.</p>

<p> We will look at in this blog, one of Gauss' \(8\) proof of this. The proof by so called Gauss sums. This is a common proof presented in many elementary number theory class. but usually without any intuition: its just computation. We will assume some Field theory and Galois theory, basically just know the Galois correspondence. Also for our intents and purposes, \(2\) doesn't exist!</p>

<h2>When is -3 a quadratic residue?</h2>

<p>We start of with a simple question, when is \(-3\) a quadratic residue? So we are asking, let \(p\) be prime, does there exist \(x\) such that 
\[x^2 = -3 \pmod{p}?\]
To do this, we will do a trick. Often you can figure out something for \(\mathbb{F}_p\) by thinking about it in \(\mathbb{C}\) first, or vice versa. An example of this is proving \(\mathbb{F}_p\) has cyclic multiplicative group by counting elements of order \(p\) in \(\mathbb{C}^\times\). Consider \(\omega\) to be a third root of unity, say
\[ \omega = \dfrac{-1+\sqrt{-3}}{2}.\]
Notice that you can hence write \(\sqrt{-3}\) interms of third roots of unity, lets say \(\sqrt{-3} = \omega-\omega^2\). So if I have the analogue of a third root of unity in \(\mathbb{F}_p\), then i expect \(-3\) to be a square root. Well there is an element of order \(3\) if and only if \(3|p-1\), i.e if \(p\equiv 1 \pmod{3}\).
</p>

<p>
Let \(p\equiv 1 \pmod{3}\), and \(z\) an element of order \(3\) in \(\mathbb{F}_p\). Then we claim, motivated by the complex case, that \((z-z^2)^2 = -3\). Indeed, this is a simple computation:
\[ (z-z^2)^2 = z^2-2z^3+z^4 = z^2-2+z = (z^2+z+1)-3 = -3.\]
So actually we just proved that if \(p\equiv 1\pmod{3}\), then \(-3\) is a quadratic residue mod \(p\).
</p>

<p>
What about when \(p\equiv 2 \pmod{3}\)? We do not have an element of order \(3\) so we cannot do this nice trick. But what we can do is adjoint an element of order 3, i.e look at \(\mathbb{F}_p[z]\) where \(z\) is a root of \(z^2+z+1=0\). In this case, we also have \((z-z^2)^2 = -3\). Since this is a field, the equation \(x^2=-3\) can only have two solutions, i.e \(z-z^2\) and its negative. So the question now: is \(z-z^2\) actually in the basefield \(\mathbb{F}_p\)? Here we will use some light Galois theory: notice \(z\mapsto z^2\) is an automorphism but doesnt fix \(z-z^2\). This means \(z-z^2\) isnt in the base field, i.e \(-3\) has no square root.
</p>

<p>
The trick we did for \(p\equiv 2\pmod{3}\) will not generalize unfortunately. The reason is that we do not easily know what the minimum polynomial of \(z\), an element of order \(q\), is in \(\mathbb{F}_p\). So we do not know which \(z\mapsto z^a\) are the correct automorphisms to consider!
However, once we look at the general case, actually an even nicer trick will help us.
</p>

<h2>Gauss sums</h2>

<p>
We managed to completely classify when \(-3\) is a quadratic residue mod \(p\) by writing its square root interms of roots of unity. We will try to ask a more general question, when is \(\sqrt{n}\in \mathbb{Q}(\zeta_p)\) where \(\zeta_p\) is a primitive \(p\)th root of unity. Is there even such an element in the field? Actually the answer is yes. To see this all we need is some Galois theory. Note 
\[\Gal(\mathbb{Q}(\zeta_p)/\mathbb{Q}) = \{\sigma_j| j \text{  coprime to  } p\} \cong \left(\mathbb{Z}/p\mathbb{Z}\right)^\ast \cong \mathbb{Z}/(p-1)\mathbb{Z}, \quad \sigma^j(\zeta_p) = \zeta_p^j. \]
And since \(2\) isnt a prime, this is an even cyclic group and hence has a subgroup of index \(2\). The fixed field of this is hence of degree 2, i.e a quadratic extension \(\mathbb{Q}(\sqrt{n})\) so in particular, some square root is in the cyclotomic field. Note the subgroup of index \(2\) will be all things of the form \(\\sigma_{j^2}\}\). 
</p>

<p>
But lets not get too lost in the Galois theory, and lets say simply that we have
\[\tau = \sum_{i=0}^{p-1} a_i \zeta_p^i = \sqrt{n}\]
for some \(n\). Then since an automorphism sends \(\sqrt{n}\) to one of its conjugates, i.e itself or its negation, we would have \(\sigma_j(\tau) =\pm \tau\). But in either case, we could just apply \(\sigma_j\) again to have \(\sigma_{j^2} (\tau) = \tau\). If we expand this out, it says
\[\sigma_{j^2}(\tau) = \sum_{i=0}^{p-1} a_i \zeta_p^{j^2i} = \tau = \sum_{i=0}^{p-1} a_i \zeta_p^i.\]
Comparing the coefficient of \(\zeta_p^{j^2}\), we have \(a_1 = a_{j^2}\). So this tells us that all quadratic residues have the same coefficient. Since \(\tau\) isnt fixed by everything, for non-residues we should have \(\sigma_{j}(\tau) = -\tau\), i.e \(a_j=-a_1\) and \(a_0=0\). We can just divide by \(a_1\) and hence we can assume \(a_1=1\). So the coefficient of \(\zeta^j\) is +1 or -1 depending on wether it is a quadratic residue or not. I.e
\[\tau = \sum_{i=1}^{p-1}\left(\dfrac{i}{p}\right) \zeta_p^i.\]
Now we compute 
\[\begin{aligned}
\tau^2 &= \sum_{(i,i')\in \mathbb{F}_p^2} \left(\dfrac{ii'}{p}\right) \zeta_p^{i+i'} \\
	&= \sum_{(i,k)\in \mathbb{F}_p^2} \left(\dfrac{i(ki)}{p}\right) \zeta_p^{i+ki}\\
	&= \sum_{(i,k)\in \mathbb{F}_p^2} \left(\dfrac{k}{p}\right) \zeta_p^{i(k+1))}\\
	&= \sum_{k\in \mathbb{F}_p} \left(\dfrac{k}{p}\right) \sum_{i \in \mathbb{F}_p} \zeta_p^{i(k+1)}\\
	&= (p-1)\left(\dfrac{-1}{p}\right) + \sum_{k\in \mathbb{F}_p-\{-1\}}  \left(\dfrac{k}{p}\right) \sum_{s \in \mathbb{F}_p} \zeta_p^{s}\\
	&= (p-1)\left(\dfrac{-1}{p}\right) + \sum_{k\in \mathbb{F}_p-\{-1\}}  \left(\dfrac{k}{p}\right)(-1)\\
	&= p\left(\dfrac{-1}{p}\right) -\sum_{k\in \mathbb{F}_p} \left(\dfrac{k}{p}\right)\\
	&= p\left(\dfrac{-1}{p}\right). 
\end{aligned}
\]
We used several time that whenever \(i\neq 0\), we have \(k\mapsto ki\) is a bijetion of \(\mathbb{F}_p^\times\). We already knew \(\tau^2\) was going to be a rational, so its great to see it is actually just \(\pm 3\). Ofcourse when \(p=3\), this is the case we already worked out. Also recall that \(\tau\) is fixed by \(\sigma_q\) only when \(q\) is a quadratic residue mod \(p\). So
\[\sigma_q(\tau) = \sum_{i=1}^{p-1}\left(\dfrac{i}{p}\right) \zeta_p^{qi} = \left(\dfrac{q}{p}\right) \tau.\]
Unfortunately there is no nice way to finish this off in \(\mathbb{C}\), so we move down to finite fields as we did for \(p=3\).
</p>

<p>
Now consider \(\mathbb{F}_q\), and the question is wether \(p\) is a quadratic residue mod \(q\). Again, consider an extension \(\mathbb{F}_q(z)\), so we have an element of order \(p\). We know
\[\tau =  \sum_{i=1}^{p-1}\left(\dfrac{i}{p}\right) z^i\implies \tau^2 =  p\left(\dfrac{-1}{p}\right).\]
The computation would be the same but also one might argue using polynomials, the min poly of \(\zeta_p\) in \(\mathbb{C}\) is \(\Phi_p\) and it must divide \(\tau^2-p\), and the min poly of \(z\) mod \(q\) divides \(\Phi_p\). Note that if we define \(\sigma_q\) the same way as before, sending \(z\mapsto z^q\), its not necessarily an automorphism but it does still satisfy \(\sigma_q(z) = \left(\dfrac{q}{p}\right) \tau.\). Since \((a+b)^q = a^q+b^q\) in this field, we have
\[\tau^q = \sigma_q(\tau) =  \left(\dfrac{q}{p}\right) \tau.\]
As we know \(\tau \in \mathbb{F}_q\) if and only if \(\tau^q = \tau\). So actually we already know the answer, \(p\left(\dfrac{-1}{p}\right)\) is a quadratic residue mod \(q\) iff \(q\) is a quadratic residue mod \(p\). We have already accomplished our goal, we know how to relate \(p\) being a quadratic residue mod \(q\) to the other way around. But lets write an equation down with this and say
\[\tau^q = \tau (\tau^2)^{(q-1)/2} = \tau \left(\dfrac{-1}{p}\right)^{(q-1)/2} p^{(q-1)/2} = \left(\dfrac{-1}{p}\right)\left(\dfrac{-1}{q}\right)\left(\dfrac{p}{q}\right)\tau.\]
Equating we'd have
\[\left(\dfrac{-1}{p}\right)\left(\dfrac{-1}{q}\right)\left(\dfrac{p}{q}\right) = \left(\dfrac{q}{p}\right),\]
which we can write nicely as
\[\left(\dfrac{-1}{p}\right)\left(\dfrac{-1}{q}\right)=\left(\dfrac{p}{q}\right) \left(\dfrac{q}{p}\right).\]
</p>

<h2>conclusion</h2>
<p>
Hopefully this injected some intuition into the idea of the Gauss sums. Basically, Gauss sums are a way to capture quadratic Kronecker-Weber, that we can write every \(\sqrt{n}\) interms of roots of unities. And this was enough to solve quadratic reciprocity. This idea can be generalized to higher reciprocity laws also. Infact the full statement of Kronecker-Weber says that every abelian extension(i.e Galois group over \(\mathbb{Q}\) is abelian) is a subfield of a cyclotomic extension. And basically this allows one to write down all such higher reciprocity laws. This is the content of Class field theory.
</p>
