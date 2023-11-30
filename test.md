I apologize in advance for the long question, but it involves some work I been thinking about and would like help with. The Navier-Stokes equation in $\mathbb{R}^3$ subjected to no gravitational forces are provided as:

$$
 \dfrac{\partial }{\partial t} \textbf{u} + \left(\textbf{u}\cdot \nabla \right)\textbf{u} -    \nu \bigtriangleup \textbf{u} = -\dfrac{1}{\rho}  \textbf{Grad}(p) ~~~~~(1)
$$

$$
\textbf{Div}(\textbf{u}) = 0 ~~~~~(2)
$$


$$
\textbf{u}(x,0) = \textbf{u}^0(x). ~~~~~(3)
$$

Here $\rho>0$ is a scalar which represents the fluids density and $\nu>0$ is a scalar which denoted the fluids kinetic viscosity. These equations are to be solved for the velocity field $\textbf{u}(x,t)$ and scalar pressure function $p(x,t)$ as time progresses. For physical reasonable solutions the initial condition is restricted to be smooth (infinitely differentiable) and decay $$|\textbf{u}^0|_{L^2_{x}(\mathbb{R})}\le \infty$$ so that $\textbf{u}(x,t)$ does not grow large as $|x|\rightarrow \infty$. According to Fefferman's official problem description we say a solution $\textbf{u}$ and $p$ is reasonable if

$$
p, \textbf{u}\in C^{\infty}(\mathbb{R}^3\times [0,\infty))~~~~~ \text{and}~~~~~ \int_{\mathbb{R}^3}^{}{|\textbf{u}|} < \epsilon, ~~~~~\forall t >0.  ~~~~~(4)
$$

That is $\text{u}$ and $p$ are infinitely differentiable and $\textbf{u}$ has finite energy. Assume for simplicity that there is a smooth solution to Eq.(1)-Eq.(3) that satisfy the conditions of Eq.(4). If the vector field $\left(\textbf{u}\cdot \nabla \right)\textbf{u} -    \nu \bigtriangleup \textbf{u}$ vanishes as fast as $\dfrac{1}{x}$ as $x\rightarrow \infty$, is twice differentiable, and is of bounded support then according to Helmholtz decomposition the vector field $\left(\textbf{u}\cdot \nabla \right)\textbf{u} -    \nu \bigtriangleup \textbf{u}$ can be written as 

$$
\left(\textbf{u}\cdot \nabla \right)\textbf{u} -    \nu \bigtriangleup \textbf{u}= \textbf{Grad}(\phi) + \textbf{Curl}(\Phi)~~~~~(5)
$$


where $\phi$ and $\Phi$ are provided explicitly by the formula 

$$
\phi(x) = \dfrac{1}{4\pi}\int_{\mathbb{R}^3}^{}{\dfrac{\textbf{Div}(\bigg(\left(\textbf{u}\cdot \nabla \right)\textbf{u} -    \nu \bigtriangleup \textbf{u}\biggr)(x^\prime))}{|x-x^\prime|}}dV^\prime$$ and $$ \Phi(x) = \dfrac{1}{4\pi}\int_{\mathbb{R}^3}^{}{\dfrac{\textbf{curl}(\bigg(\left(\textbf{u}\cdot \nabla \right)\textbf{u} -    \nu \bigtriangleup \textbf{u}\biggr)(x^\prime))}{|x-x^\prime|}}dV^\prime$$ respectfully. Substituting Eq.(5) into Eq.(1) one finds 


$$
\dfrac{\partial }{\partial t} \textbf{u}+\textbf{Curl}(\Phi) = -\dfrac{1}{\rho}  \textbf{Grad}(p - \rho \phi).~~~~~(6)
$$

Next if one computes the divergence of Eq.(6) one finds


$$
\dfrac{\partial }{\partial t} \textbf{Div}(\textbf{u})+\textbf{Div}(\textbf{Curl}(\Phi)) = -\dfrac{1}{\rho}  \textbf{Div}(\textbf{Grad}(p - \rho \phi)).~~~~~~(7)
$$

According to Eq.(2) and the fact that $\textbf{Div}(\textbf{Curl}(\textbf{f})) = 0$ for any vector field $f$ Eq.(7) then reduces to 


$$
\dfrac{1}{\rho}  \textbf{Div}(\textbf{Grad}((p - \rho \phi))= \dfrac{1}{\rho}\sum_{i=1}^{3}{\dfrac{\partial^2}{\partial x_i^2} (p - \rho \phi)} = 0  .~~~~~~~~(8)
$$

Conveniently, Eq.(8) is simply the non-homogeneous heat equation in terms of the variable $(p - \rho \phi)$ which then gives one the analytic result

$$
(p - \rho \phi) = \int_{\mathbb{R}^3}^{}{\alpha(x-y,t)(p - \rho \phi)\circ(x,0)}dy:= \Gamma(x,t)~~~~~~~(9)
$$

with $\alpha(x,t)$ the kernel defined as $$\alpha(x,t):= \dfrac{1}{(4\pi t)^{3/2}}~ \exp\biggl(\dfrac{x^2}{4t}\biggr), ~~~~~ x\in \mathbb{R}^3, t>0$$ according to Evans book on PDEs as the heat equations solution is unique. Next using Eq.(9) we may rewrite Eq.(6) in terms of $\Gamma$ which yields 

$$
\dfrac{\partial }{\partial t} \textbf{u}+\textbf{Curl}(\Phi) = -\dfrac{1}{\rho}  \textbf{Grad}(\Gamma(x,t))~~~~~~~(10)
$$

Here recall $\Gamma(x,t)$ is known and the vector field $\Phi$ is not because it is a function of $\textbf{u}$. Substituting the definition of $\Phi$ into Eq.(10) reveals 


$$
\dfrac{\partial }{\partial t} \textbf{u}+ \dfrac{1}{4\pi}\textbf{curl}\biggl(\int_{\mathbb{R}^3}^{}{\dfrac{\bigg( \textbf{Curl}(\left(\textbf{u}\cdot \nabla \right)\textbf{u} -    \nu \bigtriangleup \textbf{u}\biggr)(x^\prime,t)}{|x-x^\prime|}}dV^\prime \biggr) = -\dfrac{1}{\rho}  \textbf{Grad}(\Gamma(x,t)).~~(11)
$$

The exceptional part in this formula is that it does not involve any pressure term even as difficult as it may seem.  A simple reduction can be done by comparing to the curl of Eq.(1) and noticing the curl of the vector field $\textbf{u}$ is equivalent to the curl of its non-linear part minus the Laplacian term

$$
- \dfrac{d}{dt}\textbf{curl}(\textbf{u}) = \textbf{Curl}\biggl(\left(\textbf{u}\cdot \nabla \right)\textbf{u} -    \nu \bigtriangleup \textbf{u}\biggr). ~~~~~~~(12)
$$

Hence, Eq.(11) reads 

$$
\dfrac{\partial }{\partial t} \textbf{u}- \dfrac{1}{4\pi}\textbf{curl}( \textbf{curl} \biggl(\int_{\mathbb{R}^3}^{}{\dfrac{  \dfrac{d}{dt}\textbf{u} (x^\prime,t)}{|x-x^\prime|}}dV^\prime \biggr)) = -\dfrac{1}{\rho}  \textbf{Grad}(\Gamma(x,t)).~~~~~~~(13)
$$

If I am not mistaken, we can pull out the time derivative and we should actually get the following

$$
 \textbf{u}- \dfrac{1}{4\pi}\textbf{curl}( \textbf{curl} \biggl(\int_{\mathbb{R}^3}^{}{\dfrac{\textbf{u} (x^\prime,t)}{|x-x^\prime|}}dV^\prime \biggr)) = -\int_{0}^{t}{\dfrac{1}{\rho}  \textbf{Grad}(\Gamma(x,s))}ds.~~~~~~(14)
$$

any ideas on how to solve this last equation? Does it give an implicit formula in terms of $\textbf{u}$ or did I make a mistake somewhere? If this equation doesn't make since then maybe there is not a solution that vanishes as fast as Helmholtz theorem constraints. However, it seems it cant blow up because the time component does not depend on the curl of the unkown vector field and indeed it does make since when $\textbf{u}$ is curl free. An immediate consequence is that if $\textbf{u}$ is curl free then we must have $$\textbf{u}(x,t) = -\dfrac{1}{\rho} \textbf{Grad}\biggl(\int_{0}^{t}{\Gamma(x,s) ds}\biggr)$$ because the left term vanishes as we move the curl inside the integral as it is a linear operator and commutes with the integral. We can check if our solution decays and satisfies Fefferman's conditions mentioned prior. In full generality if we can solve the PDE 

$$
\textbf{u}- \dfrac{1}{4\pi}\textbf{curl}( \textbf{curl} f(\textbf{u})) = -\dfrac{1}{\rho}  \textbf{Grad}(\int_{0}^{t}{\Gamma(x,s)}ds).~~~~~~~(15)
$$

for special functions f we may be able to solve this PDE. We can even go a bit farther then just the curl vanishing and say if the double curl of the vector field is zero ($\textbf{curl}(\textbf{curl}(\textbf{u}(x,t))=0$)) then it seems this would still yield the same solution. We don't even need the first curl operation to be zero only the second. We see the formula is actually a solution to Eq.(1) it just so happens to be curl free but there could be more solutions or if there is not a curl free solution then this is the only solution, and it would be unique based off the uniqueness of the heat equation. To find $p(x,0)$ and $\phi(x,0)$ we can use the initial condition $\textbf{u}(x,0)$ this would give us $\Gamma(x,s)$ explicitly. Any ideas much appreciated. 