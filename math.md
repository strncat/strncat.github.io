---
layout: page
title: Math
permalink: /math/
mathjax: true
---

<!------------------------------------------------------------------->  
  <h3> Real Analysis </h3>
  <ol type="1">
    <li><a href="/jekyll/update/2024/05/14/analysis-psquared-even-then-p-even.html">
          Prove that if \(p^2\) is even, then \(p\) is even.
	</a></li>
    <li><a href="/jekyll/update/2024/05/01/analysis-square-root-two-irrational.html">
          Prove that \(\sqrt{2}\) is irrational.
    </a></li>
    <li><a href="/jekyll/update/2024/05/15/analysis-square-root-three-irrational.html">
          Prove that \(\sqrt{3}\) is irrational.
    </a></li>
	<!--
    <li><a href="/jekyll/update/2024/05/29/analysis-square-root-3-5-irrational.html">
          Prove that \(\sqrt{3} + \sqrt{5}\) is irrational.
    </a></li>
	-->
    <li><a href="/jekyll/update/2024/05/02/analysis-epsilon-proof-for-equal-real-numbers.html">
          Two real numbers \(a\) and \(b\) are equal if and only if for every real number \(\epsilon > 0\) it follows that \(|a - b| < \epsilon\).   
    </a></li>
	<!---------------------------- The Absolute Value Function ------------------------------->
	<div style="background-color: #F3EEEA; padding: 15px 5px 5px 5px; border:0px solid black;">
		<h4><i>The Absolute Value Function</i></h4>
	</div>
	<br>
    <p><a href="/jekyll/update/2024/05/26/analysis-absolute-value-properties.html">
          Definition and Properties  
    </a></p>
    <li><a href="/jekyll/update/2024/04/25/analysis-absolute-value-pr1.html">
          Let \(x \in \mathbf{R}\), \(|x| \geq 0\).   
    </a></li>
    <li><a href="/jekyll/update/2024/04/26/analysis-absolute-value-pr2.html">
          Let \(x \in \mathbf{R}\), \(-|x| \leq x \leq |x|\).   
    </a></li>
    <li><a href="/jekyll/update/2024/05/13/analysis-absolute-value-max-x-y.html">
          For two real numbers \(x\) and \(y\), prove that \(\max(x,y) = \frac{1}{2}(x+y+|x - y|)\).   
    </a></li>
    <li><a href="/jekyll/update/2024/05/24/analysis-absolute-value-product.html">
          \(|ab| = |a|\cdot|b|\) holds for all real numbers \(a\) and \(b\).   
    </a></li>
    <li><a href="/jekyll/update/2024/05/25/analysis-absolute-value-triangle-inquality.html">
          \(|a+b| \leq |a|+|b|\) holds for all real numbers \(a\) and \(b\). 
    </a></li>
    <li><a href="/jekyll/update/2024/05/27/analysis-absolute-value-triangle-inquality-subtract.html">
          \(|a - c| \leq |a - b|+|b - c|\) holds for all real numbers \(a\), \(b\) and \(c\).   
    </a></li>
	<!-------------------------------------- Bounds --------------------------------------->
	<div style="background-color: #F3EEEA; padding: 15px 5px 5px 5px; border:0px solid black;">
		<h4><i>Bounded Sets</i></h4>
	</div>
	<br>
    <p><a href="/jekyll/update/2024/05/03/analysis-set-bounded.html">
          Bounded Sets Definitions
    </a></p>
    <li><a href="/jekyll/update/2024/05/05/analysis-least-upper-bound-epsilon.html">
          [Lemma 1.3.8] If \(s\) is an upper bound for \(A\), then \(s = \sup A\) if and only if for every choice of \(\epsilon > 0\), there exists an element \(a \in A\) satisfying \(s - \epsilon < a\).
    </a></li>
    <li><a href="/jekyll/update/2024/04/30/analysis-nested-internval-property.html">
          The Nested Interval Property
    </a></li>
    <li><a href="/jekyll/update/2024/05/16/analysis-archimedian-principle.html">
          The Archimedean Principle
    </a></li>
	<!--
    <li><a href="/jekyll/update/2024/05/19/analysis-bounds-alpha-n.html">
          Fix \(\alpha \in (0,1)\). Determine \(\inf(A)\) for \(A=\{\alpha^n: n \in \mathbf{N}\}\).
    </a></li>
    <li><a href="/jekyll/update/2024/05/10/analysis-least-upper-bound-1.3.7.html">
          (11) [1.3.7] If \(a\) is an upper bound for \(A\) and \(a \in A\), then \(a = \sup A\).
    </a></li>
	-->
    <li><a href="/jekyll/update/2024/05/20/analysis-density-of-q-in-r.html">
          [Density of \(\mathbf{Q}\) in \(\mathbf{R}\)] For every two real numbers \(a\) and \(b\) with \(a < b\), there exists a rational number \(r\) satisfying \(a < r < b\).
    </a></li>
    <p>
          Exercises
    </p>
    <li><a href="/jekyll/update/2024/05/04/analysis-least-upper-bound-constant.html">
          The set defined as \(c+A = \{c + a : a \in A\}\) where \(c\) is a constant has a least upper bound equal to \(c + sup A\).
    </a></li>
    <li><a href="/jekyll/update/2024/05/06/analysis-least-upper-bound-multiply.html">
          [1.3.5] The set defined as \(cA = \{ca : a \in A\}\) where \(c \geq 0\) has \(\sup cA = c\sup A\).
    </a></li>
    <li><a href="/jekyll/update/2024/05/07/analysis-least-upper-bound-sum.html">
          [1.3.6] The set defined as \(A + B = \{a + b: a \in A \text{ and } b \in B\}\) has \(\sup (A+B) = \sup A + \sup B\).
    </a></li>
    <li><a href="/jekyll/update/2024/05/08/analysis-least-upper-bound-sum-alternative.html">
          [1.3.6] The set defined as \(A + B = \{a + b: a \in A \text{ and } b \in B\}\) has \(\sup (A+B) = \sup A + \sup B\) (Alternative Proof).
    </a></li>
    <li><a href="/jekyll/update/2024/05/09/analysis-least-upper-bound-union.html">
          [1.3.4] Let \(A\) and \(B\) be nonempty and bounded above. Find a formula for \(\sup (A \cup B)\) and prove that it is correct.
    </a></li>
    <li><a href="/jekyll/update/2024/05/11/analysis-least-upper-bound-infb-infa-supb-supa.html">
          [1.3.11] If \(A\) and \(B\) are nonempty and bounded sets of real numbers such that \(A \subseteq B\) then \(\inf B \leq \inf A \leq \sup A \leq \sup B\).
    </a></li>
    <li><a href="/jekyll/update/2024/05/23/analysis-least-upper-bound-sup0.html">
          Let \(A = \{x \in \mathbf{R}: x < 0\}\). Then \(\sup(A) = 0\).
    </a></li>
    <li><a href="/jekyll/update/2024/05/17/analysis-archimedian-principle-inf-N.html">
          Show that \(\inf\big(\{\frac{1}{n}: n \in \mathbf{N}\} \big) = 0.\)
    </a></li>
    <li><a href="/jekyll/update/2024/05/18/analysis-archimedian-principle-sup-N.html">
          Show that \(\sup\big(\{\frac{1}{n}: n \in \mathbf{N}\} \big) = 1.\)
    </a></li>
	<!-------------------------------------- Cardinality --------------------------------------->
	<div style="background-color: #F3EEEA; padding: 15px 5px 5px 5px; border:0px solid black;">
		<h4><i>Cardinality</i></h4>
	</div>
	<br>
    <p><a href="/jekyll/update/2024/06/07/analysis-card-definitions.html">
          Definitions
    </a></p>
    <li><a href="/jekyll/update/2024/06/09/analysis-card-cantor-r-uncountable.html">
		  The open interval \((0,1) = \{x \in \mathbf{R}: 0 < x < 1\}\) is uncountable.
    </a></li>
	<!--
    <li><a href="/jekyll/update/2024/06/08/analysis-card-q-countable-r-uncountable.html">
		  The set \(\mathbf{Q}\) is countable and the set \(\mathbf{R}\) is uncountable.
    </a></li>
	-->
	<!-------------------------------------- Sequences --------------------------------------->
	<div style="background-color: #F3EEEA; padding: 15px 5px 5px 5px; border:0px solid black;">
		<h4><i>Sequences and Subsequences</i></h4>
	</div>
	<br>
    <p><a href="/jekyll/update/2024/05/21/analysis-seq-definitions.html">
          Sequences and Subsequences Definitions
    </a></p>
    <li><a href="/jekyll/update/2024/05/12/analysis-seq-limit-template.html">
          Show the Limit Template + Example \(\lim\big(\frac{1}{\sqrt{n}}\big)= 0\).
    </a></li>
    <li><a href="/jekyll/update/2024/04/27/analysis-seq-limits-unique.html">
          [Uniqueness of Limits (2.2.7)] The limit of a sequence, when it exists must be unique.
    </a></li>
    <li><a href="/jekyll/update/2024/06/03/analysis-seq-bounded.html">
          [Bounded Sequences (2.3.1)] A sequence \(x_n\) is bounded if there exists a number \(M > 0\) such that every term in the sequence \(|x_n| \leq M\) for all \(n \in \mathbf{N}\).
    </a></li>
    <li><a href="/jekyll/update/2024/06/12/analysis-seq-if-convergent-then-bounded.html">
          [Convergent Sequences (2.3.2)] Every convergent sequence is bounded.
    </a></li>
    <li><a href="/jekyll/update/2024/05/30/analysis-seq-algebraic-limit-theorem-i.html">
		  [The Algebraic Limit Theorem (2.3.3)] (i) \(\lim (ca_n) = ca\) for all \(c \in \mathbf{R}\).
    </a></li>
    <li><a href="/jekyll/update/2024/05/31/analysis-seq-algebraic-limit-theorem-ii.html">
		  [The Algebraic Limit Theorem (2.3.3)] (ii) \(\lim (a_n + b_n) = a + b\).
    </a></li>
    <li><a href="/jekyll/update/2024/06/01/analysis-seq-algebraic-limit-theorem-iii.html">
		  [The Algebraic Limit Theorem (2.3.3)] (iii) \(\lim (a_nb_n) = ab\).
    </a></li>
    <li><a href="/jekyll/update/2024/06/02/analysis-seq-order-limit-theorem.html">
		  [The Order Limit Theorem ((2.3.4)]
    </a></li>
    <li><a href="/jekyll/update/2024/04/29/analysis-seq-monotone-convergence-theorem.html">
		  [Monotone Convergence Theorem (2.4.2)] If a sequence is monotone and bounded, then it converges.
    </a></li>
    <li><a href="/jekyll/update/2024/06/11/analysis-seq-subseq-convergence.html">
		  [Convergence of Subsequence (2.5.2)] Subsequences of a convergent sequence converge to the same limit as the original sequence.
    </a></li>
    <li><a href="/jekyll/update/2024/06/14/analysis-seq-subseq-bolzano-weierstrass-theorem.html">
		  [Bolzano-Weierstrass Theorem (2.5.5)] Every bounded sequence contains a convergent subsequence.
    </a></li>
    <li><a href="/jekyll/update/2024/06/16/analysis-seq-cauchy-sequences-bounded.html">
		  (2.6.3) Cauchy Sequences are Bounded
    </a></li>
    <li><a href="/jekyll/update/2024/06/17/analysis-seq-convergent-sequences-are-cauchy.html">
		  Every convergent sequence is a Cauchy sequence
    </a></li>
    <li><a href="/jekyll/update/2024/06/18/analysis-seq-cauchy-critertion.html">
		  [Cauchy Criterion (2.6.4)] A sequence converges if and only if it is a Cauchy sequence.
    </a></li>
    <p>
          Exercises
    </p>
    <li><a href="/jekyll/update/2024/05/22/analysis-seq-limit-example.html">
          Show that \(\lim\big(\frac{n+1}{n}\big)= 1\).
    </a></li>
    <li><a href="/jekyll/update/2024/06/04/analysis-seq-sqrt.html">
		  Let \(x_n \geq 0\) for all \(n \in \mathbf{N}\). Show that if \((x_n) \longrightarrow x\), Then \((\sqrt{x_n}) \longrightarrow \sqrt{x}\).
    </a></li>
    <li><a href="/jekyll/update/2024/06/05/analysis-seq-squeeze-theorem.html">
		  [Squeeze Theorem] Show that if \(x_n \leq y_n \leq z_n\) for all \(n \in \mathbf{N}\), and if \(\lim x_n = \lim z_n = l\), then \(\lim y_n = l\) as well.
    </a></li>
    <li><a href="/jekyll/update/2024/06/06/analysis-seq-abs-value.html">
		  Show that if \((|x_n|) \rightarrow 0\) for all \(n \in \mathbf{N}\), then \(x_n \rightarrow 0\).
    </a></li>
    <li><a href="/jekyll/update/2024/06/15/analysis-seq-sqrt-2.html">
		  Show that \((\sqrt{n + 1} - \sqrt{n})\) converges to 0.
    </a></li>
    <li><a href="/jekyll/update/2024/06/13/analysis-seq-subseq-convergence-example.html">
		  Prove that \(b > b^2 > b^3 > b^4 > ... > 0\) converges to 0 if \(0 < b < 1\). (Example of 2.5.2).
    </a></li>
    <li><a href="/jekyll/update/2024/06/19/analysis-seq-subseq-convergence.html">
		  A sequence \(a_n\) converges to \(a\) if and only if every subsequence of \(a_n\) also converges to \(a\).
    </a></li>
    <li><a href="/jekyll/update/2024/06/20/analysis-seq-subseq-divergence.html">
		  If two subsequences of \(a_n\) converge to different limits, or if any subsequences of \(a_n\) diverges then \(a_n\) diverges.
    </a></li>
    <li><a href="/jekyll/update/2024/06/21/analysis-seq-1n-diverges.html">
		  Prove that \((a_n) = (-1)^n\) diverges.
    </a></li>
	<!-------------------------------------- Series --------------------------------------->
	<div style="background-color: #F3EEEA; padding: 15px 5px 5px 5px; border:0px solid black;">
		<h4><i>Series</i></h4>
	</div>
	<br>
    <p><a href="/jekyll/update/2024/06/10/analysis-series-definitions.html">
          Series Definitions
    </a></p>
    <li><a href="/jekyll/update/2024/02/08/analysis-series-cauchy-condensation-test.html">
		  (2.4.6) Cauchy Condensation Test
    </a></li>
    <li><a href="/jekyll/update/2024/02/01/analysis-series-algebraic-limit-theorem.html">
		  (2.7.1) The Algebraic Limit Theorem for Series
    </a></li>
    <li><a href="/jekyll/update/2024/02/02/analysis-series-cauchy-criteria.html">
		  (2.7.2) Cauchy Criterion for Series
    </a></li>
    <li><a href="/jekyll/update/2024/02/03/analysis-series-converges-zero.html">
		  (2.7.3) If the series \(\sum_{n=1}^{\infty} a_n\) converges then \((a_n) \rightarrow 0\).
    </a></li>
    <li><a href="/jekyll/update/2024/02/04/analysis-series-comparison-test.html">
		  (2.7.4) Comparison Test for Series
    </a></li>
    <li><a href="/jekyll/update/2024/02/05/analysis-series-geometric.html">
		  (2.7.5) The Geometric Series
    </a></li>
    <li><a href="/jekyll/update/2024/02/06/analysis-series-absolute-convergence-test.html">
		  (2.7.6) [The Absolute Convergence Test] If the series \(\sum_{n=1}^{\infty}|a_n|\) converges, then \(\sum_{n=1}^{\infty} a_n\) converges as well.
    </a></li>
    <li><a href="/jekyll/update/2024/02/07/analysis-series-alternating-series-test.html">
		  (2.7.7) The Alternating Series Test
    </a></li>
	<!-- don't get this one!
    <li><a href="/jekyll/update/2024/02/07/analysis-series-rearrangement.html">
		  (2.7.10) If a series converges absolutely, then any rearrangements of this series converges to the same limit.
    </a></li>
	-->
	<!-------------------------------------- Topology of R --------------------------------------->
	<div style="background-color: #F3EEEA; padding: 15px 5px 5px 5px; border:0px solid black;">
		<h4><i>Topology of R</i></h4>
	</div>
	<br>
    <p><a href="/jekyll/update/2024/04/24/analysis-sets-cantor.html">
		  Cantor Sets
    </a></p>
    <p><a href="/jekyll/update/2024/06/22/analysis-sets-open.html">
		  Open Sets
    </a></p>
    <li><a href="/jekyll/update/2024/06/23/analysis-sets-open-sets-union.html">
		  (3.2.3) The union of an arbitrary collection of open sets is open and the intersection of a finite collection of open sets is open.
    </a></li>
    <p><a href="/jekyll/update/2024/06/24/analysis-sets-limit-points.html">
		  Limit Points
    </a></p>
  </ol>
<br>
<!------------------------------------------------------------------->  
  <h3> Limits </h3>
  <ul style="list-style-type:none;">
    <li><a href="/jekyll/update/2024/04/16/limit-rational-functions.html">
            The Limit of Rational Functions As x Approaches Plus or Negative Infinity
    </a></li>
    <li><a href="/jekyll/update/2024/04/14/limit-sin-x.html">
          The Limit of sin(x) / x
    </a></li>
  </ul>
<br>

<!------------------------------------------------------------------->  
   <h3> Linear Algebra </h3>
   <ul style="list-style-type:none;">
       <li><a href="/jekyll/update/2023/09/11/vectors.html">
           Vectors
       </a></li>
       <li><a href="/jekyll/update/2023/09/12/linear-combinations.html">
           Linear Combinations
       </a></li>
       <li><a href="/jekyll/update/2023/09/22/linear-transformations.html">
           Linear Transformations
       </a></li>
       <li><a href="/jekyll/update/2023/09/25/matrix-multiplication-as-composition.html">
           Matrix Multiplication As Composition
       </a></li>
       <li><a href="/jekyll/update/2023/09/26/determinants.html">
           Determinants
       </a></li>
       <li><a href="/jekyll/update/2023/09/27/system-of-linear-equations.html">
           Inverse Matrices, Column Space and Null Space 
       </a></li>
	   <!--
       <li><a href="/jekyll/update/2023/09/29/dot-product.html">
           Dot Product
       </a></li>
       <li><a href="/jekyll/update/2023/10/02/cross-product.html">
           Cross Product
       </a></li>
	   -->
   </ul>
<br>

<!------------------------------------------------------------------->  
  <h3> Trigonometry </h3>
  <ul style="list-style-type:none;">
    <li><a href="/jekyll/update/2024/04/12/trigonometry-cheat-sheet.html">
           Trigonometry Cheat Sheet
      </a></li>
    <li><a href="/jekyll/update/2024/03/26/radians.html">
          Radians
    </a></li>
    <li><a href="/jekyll/update/2024/04/08/the-unit-circle.html">
          Sine, Cosine and The Unit Circle
    </a></li>
    <li><a href="/jekyll/update/2024/03/28/unit-circle-point.html">
          Finding a Point on the Unit Circle
    </a></li>
    <li><a href="/jekyll/update/2024/04/13/graphing-sine-cosine.html">
          Graphing the Sine and Cosine Functions
    </a></li>
  </ul>
<br>

<!------------------------------------------------------------------->  
  <h3> Graphing Functions </h3>
  <ul style="list-style-type:none;">
    <li><a href="/jekyll/update/2024/04/09/graph-vertical-asymptotes.html">
         Graphing Rational Functions: Vertical Asymptotes
    </a></li>
    <li><a href="/jekyll/update/2024/04/10/graph-horizontal-asymptotes.html">
         Graphing Rational Functions: Horizontal Asymptotes
    </a></li>
    <li><a href="/jekyll/update/2024/04/11/graph-slanted-asymptotes.html">
         Graphing Rational Functions: Slanted Asymptotes
    </a></li>
    <li><a href="/jekyll/update/2024/04/04/graph-function-linear-over-linear.html">
          Graphing Rational Functions (Example: Linear Over Linear)
    </a></li>
    <li><a href="/jekyll/update/2024/04/07/graph-function-quadratic-over-linear.html">
          Graphing Rational Functions (Example: Quadratic Over Linear)
    </a></li>
    <li><a href="/jekyll/update/2024/04/15/graph-function-exponential.html">
          Graphing the Exponential Function
    </a></li>
    <li><a href="/jekyll/update/2024/04/03/graph-function-logarithm.html">
          Graphing a Logarithmic Function
    </a></li>
    <li><a href="/jekyll/update/2024/04/05/graph-function-absolute-value.html">
          Graphing the Absolute Value Function
    </a></li>
  </ul>
<br>

<!------------------------------------------------------------------->  
  <h3> Elementary Stuff </h3>
  <ul style="list-style-type:none;">
    <li><a href="/jekyll/update/2024/04/01/rational-equations.html">
          Solving a Rational Equation
    </a></li>
    <li><a href="/jekyll/update/2024/04/02/partial-decomposition.html">
          Partial Decomposition
    </a></li>
    <li><a href="/jekyll/update/2024/04/06/inverse-rational-function.html">
          Inverse of a Rational Function
    </a></li>
  </ul>
<br>

<!------------------------------------------------------------------->  
 <h3> Other Topics </h3>
   <ul style="list-style-type:none;">
       <li><a href="/jekyll/update/2023/09/28/implicit-representation.html">
           Implicit Representation of an Equation
       </a></li>
       <li><a href="/jekyll/update/2023/09/30/parametric-representation.html">
           Parametric Representation an Equation
       </a></li>
   </ul>
<br>

<!------------------------------------------------------------------->  
 <h3> Elements of Euclid </h3>
   <ul style="list-style-type:none;">
       <li><a href="/jekyll/update/2024/04/28/elements-of-euclid-book1.html">
           Book 1
       </a></li>
   </ul>
<br>


<!------------------------------------------------------------------->  
<!--
   <h3> Abstract Algebra </h3>
   <ul style="list-style-type:none;">
       <li><a href="/jekyll/update/2019/09/07/groups.html">
           Groups
       </a></li>
   </ul>
--> 


<!------------------------------------------------------------------->  
<!--
   <h3> Number Theory </h3>
   <ul style="list-style-type:none;">
       <li><a href="/jekyll/update/2019/08/23/prime-numbers.html">
           Prime Numbers
       </a></li>
       <li><a href="/jekyll/update/2019/08/22/congruences.html">
           Congruences
       </a></li>
   </ul>
-->


<!--
<li><a href="/jekyll/update/2022/09/23/proof1.html">
   <b>09/23/2022:</b> If $n \in N,$ then $1 + (-1)^n(2n-1)$ is a multiple of $4$.
</a></li>
<li><a href="/jekyll/update/2022/09/24/proof2.html">
   <b>09/24/2022:</b> If two integers have opposite parity, then their sum is odd.
</a></li>
<li><a href="/jekyll/update/2022/09/25/proof3.html">
   <b>09/25/2022:</b> If $n \in N,$ then $1 + (-1)^n(2n-1)$ is a multiple of $4$.
</a></li>
-->
<br>