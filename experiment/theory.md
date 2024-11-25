<p>These formulae are developed the basis of finite difference operators. The differencs table is prepared for all the values in the available function. In general, each element in th difference table which is in the i<sup>th</sup> row and j<sup>th</sup> column is estimated as</p>

<p>element [i, j] = element [i + 1, j - 1] - element [i, j - 1]</p>

<ol type="1">
   To serve the various objectives, hese elements are known by different names as
   <li>Forward difference (&Delta;)</li>
   <li>Backward difference (&nabla;)</li>
</ol>

<p>Also, the tables showing these differences are presented in different ways</p>

<h3>1. Forward difference table (&Delta;):</h3>

$$
\begin{array}{|c|c|c|c|c|}
\hline \\
X & Y & \Delta^1 & \Delta^2 & \Delta^3 \\[4px]
\hline
\\
x_1 & y_1 & \Delta^1_1 = y_2 - y_1 & \Delta_1^2 = \Delta_2 - \Delta_1 & \Delta_1^3 = \Delta_2^2 - \Delta_1^2 \\[4px]
\hline
\\
x_2 & y_2 & \Delta^1_2 = y_3 - y_2 & \Delta_2^2 = Δ_3 - \Delta_2 & \\[4px]
\hline
\\
x_3 & y_3 & \Delta^1_3 = y_4 - y_3 & & \\[4px]
\hline
\\
x_4 & y_4 &  &  &  \\[4px]
\hline \\
\vdots & \vdots & & & \\
\hline
\end{array}
$$

<h3>2. Backward difference table (&nabla;):</h3>

$$
\begin{array}{|c|c|c|c|c|}
\hline
\\ 
X & Y & \nabla^1 & \nabla^2 & \nabla^3 \\[4px]
\hline
\\ 
x_1 & y_1 &  &  &  \\[4px]
\hline
\\ 
x_2 & y_2 & \nabla^1_2 = y_2 - y_1 &  & \\[4px]
\hline
\\ 
x_3 & y_3 &  \nabla^1_3 = y_3 - y_2  & \nabla_3^2 = \nabla_3 - \nabla_2 & \\[4px]
\hline
\\ 
 x_4 & y_4 & \nabla^1_4 = y_4 - y_3 & \nabla_4^2 = \nabla_4 - \nabla_3 & \nabla_4^3 = \nabla_4^2 - \nabla_3^2 \\[4px]

\hline
\end{array}
$$

<h3>1. Forward Difference Interpolation :</h3>

<p>This method is used for interpolation near the BEGINNING of the tabular data.</p>

<p><strong style="font-size:18px">Necessary Conditions :</strong> Available data must be at equal intervals of x.</p>

<p>Let the 'x interval be 'h'</p>

$$ h = x_2 - x_1 = x_3 - x_2 \ \ etc. $$

<p>Then the interpolating formula is,</p>

$$ y = y_1 + \frac{\Delta_1 (x - x_1)}{h} + \frac{\Delta_1^2(x - x_1)(x - x_2)}{2!h^2} + \frac{\Delta_1^3(x - x_1)(x - x_2)(x - x_3)}{3!h^3} + ... \qquad \qquad ...equ(1) $$

<br>

<strong style="font-size:18px">Direct interpolating Formula :</strong>

<p>&emsp;When we want to carry out the interpolation directly without obtaining the polynomial then the use of above formula becomes very laborious. In order to simplify the procedure and calculations, the above formula is expressed in other form as follows,</p>

<p>Let</p>

$$ x = x_1 + uh $$

<p>Then</p>

$$ u = \frac{x - x_1}{h} $$

<p>The forward difference formula is</p>

$$ y = y_1 + \frac{\Delta_1(x-x_1)}{h} + \frac{\Delta_1^2(x-x_1)(x-x_2)}{2!h^2} + \frac{\Delta_1^3(x-x_1)(x-x_2)(x-x_3)}{3!h^3} + ... $$

<p>In terms of 'u', we get</p>

<strong>Term &#8544; :</strong>

$$ \frac{\Delta_1(x-x_1)}{h} = \Delta_1u $$

<strong>Term &#8544;&#8544; :</strong>

$$
\frac{\Delta_1^2(x-x_1)(x-x_2)}{2!h^2} = \frac{\Delta_1^2}{2!}× \frac{(x-x_1)(x-x_1 + x_1 - x_2)}{h^2}
$$

<br>

$$
= \frac{\Delta_1^2}{2!} × \frac{(x-x_1)}{h} × \left(\frac{(x-x_1)}{h} - \frac{(x_2-x_1)}{h} \right)
$$

<br>

$$
= \frac{\Delta_1^2}{2!} × u(u-1)
$$

<p>Similarly, we can get all the terms in 'u'. Now the formula reduces to</p>

$$
y = y_1 + u\Delta_1 + \frac{u(u-1)\Delta_1^2}{2!} + \frac{u(u-1)(u-2)\Delta_1^3}{3!} + ....... \qquad \qquad ...equ(2)
$$

<br>

<h3>2. backward Difference Interpolation :</h3>

<p>This method is used for interpolation near the END of the tabular data.</p>

<p><strong style="font-size:18px">Necessary Condition :</strong> Available data must be at equal intervals of x.</p>

<p><strong style="font-size:18px">Formula :</strong></p>

$$
y = y_4 + \frac{\nabla_4^1(x - x_4)}{h} + \frac{\nabla_4^2(x-x_4)(x-x_3)}{2!h^2} + \frac{\nabla_4^3(x-x_4)(x-x_3)(x-x_2)}{3!h^3} \qquad \qquad ...equ(3)
$$

<p>&emsp; Similar to that in Forward difference method, the above formula is useful to obtain the polynomial between x and y. While in order to perform the interpolation directly, the expression in terms of 'u' makes the work simple.</p>

<p>Let</p>

$$ u = \frac{x-x_4}{h} $$

<p>then the formula in terms of 'u' becomes</p>

$$
y = y_4 + u\nabla_4^1 + \frac{u(u+1)\nabla_4^2}{2!} + \frac{u(u+1)(u+2)\nabla_4^3}{3!} \qquad \qquad ...equ(4)
$$