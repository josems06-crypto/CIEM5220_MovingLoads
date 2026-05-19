2. Consider an infinite beam with continuous visco-elastic foundation, subject to a constant moving load. The equation of motion reads as follows
$$\rho A \frac{\partial^2 w}{\partial t^2} + EI \frac{\partial^4 w}{\partial x^4} + \chi w + \eta \frac{\partial w}{\partial t} = Q_0 \delta(x - Vt)$$
Derive and compute the steady-state response in the moving reference system for a sub-critical velocity (note that the critical velocity is approximately the same as that of the undamped system) and plot the result. 


We introduce the moving reference system $\xi = x - Vt$, which makes the deflection profile constant over time in this reference system $w(x,t) \to w(\xi)$.

Applying chain rule to convert the partial derivatives x and t to $xi$ yields and ODE in the moving coordinate. 

$$\rho A V^2 \frac{d^2 w}{d\xi^2} + EI \frac{d^4 w}{d\xi^4} + \chi w - \eta V \frac{dw}{d\xi} = Q_0 \delta(\xi)$$

We transform the equation from the spatial domain to the wavenumber domain k using spatial Fourier transform, defined as: 

$$\hat{w}(k) = \int_{-\infty}^{\infty} w(\xi) e^{-ik\xi} d\xi \quad \text{and} \quad w(\xi) = \frac{1}{2\pi} \int_{-\infty}^{\infty} \hat{w}(k) e^{ik\xi} dk$$

We plug in the inverse Fourier transform into the equation of motion. $$\left[ -\rho A V^2 k^2 + EI k^4 + \chi - i\eta V k \right] \tilde{w}(k) = Q_0$$

Isolating $\tilde{w}(k)$, we obtain the steady-state response in the frequency/wavenumber domain:$$\tilde{w}(k) = \frac{Q_0}{EI k^4 - \rho A V^2 k^2 + \chi - i\eta V k}$$

The physical deflection profile $w(\xi)$ is found by applying the inverse Fourier transform:$$w(\xi) = \frac{1}{2\pi} \int_{-\infty}^{\infty} \frac{Q_0}{EI k^4 - \rho A V^2 k^2 + \chi - i\eta V k} e^{ik\xi} dk$$

Assuming that the critical velocity is approximately the same as that of the undamped system, it occurs when the moving load travels at the same speed as the lowest phase velocity of bending waves in the foundation. This is when the real part of the denominator = 0. 
$$EI k^4 - \rho A V^2 k^2 + \chi = 0 \implies V^2 = \frac{EI k^4 + \chi}{\rho A k^2} = \frac{EI}{\rho A}k^2 + \frac{\chi}{\rho A k^2}$$

To find the minimum velocity that satisfies this, we take the derivative with respect to $k^2$ and set it to zero, which yields $k^2 = \sqrt{\chi / EI}$. Substituting this back into the velocity equation gives the critical velocity:$$V_{cr} = \sqrt{\frac{2\sqrt{EI \chi}}{\rho A}}$$Using the provided parameters, $V_{cr} \approx 447.7$ m/s. For our sub-critical calculation, we will choose $V = 100$ m/s.

3. For the same problem considered in the previous question, derive and compute the equivalent stiffness at the loading/contact point and plot it versus velocity. Consider in the plot only the sub-critical velocity range (up to the 99% of the critical velocity) and explain what you observe.

The equivalent stiffness $K_{eq}$ at the loading point is defined as the ratio of the applied external load $Q_0$ to the actual deflection $w(0)$ occurring directly underneath that load (at $\xi = 0$).$$K_{eq} = \frac{Q_0}{w(0)}$$

To find the deflection exactly at the contact point, we set $\xi = 0$. The exponential term $e^0$ becomes exactly 1:$$w(0) = \frac{Q_0}{2\pi} \int_{-\infty}^{\infty} \frac{1}{(EI k^4 - \rho A V^2 k^2 + \chi) - i(\eta V k)} dk$$

For which the $K_{eq}$ can be defined as $$2\pi \int_{-\infty}^{\infty} {(EI k^4 - \rho A V^2 k^2 + \chi) - i(\eta V k)} dk$$


4. Consider a beam with continuous visco-elastic foundation having finite length and being simply supported at the edges, and excited by a constant moving load. Derive and compute the response of the structure
and plot the response for a number of time moments (include one with
t > L/V). Explain the observed behaviour (in terms of steady state and transient effects). Use the same parameter values as in Problem 2, take the velocity of the load 0.75 times the critical speed of the infinite beam with distributed elastic foundation and assume the length sufficiently long so that the steady-state profile of the infinite beam under the same load can develop (e.g., 100 m); include as many modes as needed for convergence (if needed, increase the value of η to make sure that the number of modes is not too large; damping decreases the importance of higher modes).

The equation of motion of an Euler Bernoulli beam on a continuous visco-elastic foundation with finite length, simply supported at the edges, and excited by a constant moving load can be described as following: 
 $$EI \frac{\partial^4 w(x,t)}{\partial x^4} + \chi w(x,t) + {\eta \frac{\partial w(x,t)}{\partial t}} + \rho A \frac{\partial^2 w(x,t)}{\partial t^2} = F(x,t) = Q_0 \delta(x - Vt) [H(t) - H(t - L/V)]$$

 Where $\chi$ is the elastic foundation coefficient, $\eta$ the viscous foundation coefficient, and a double heaviside function is used in the excitation to capture the "turn-off" effect after the load leaves the finite beam. 

 We use modal expansion, assuming that deflection can be separated into a sum of spatial sinusodial mode shapes and time-dependent modal coordinates. 
 $$w(x,t) = \sum_{n=1}^{\infty} \sin\left(\frac{n\pi x}{L}\right) q_n(t)$$

 Substituting the assumed solution in the PDE gives: 
 $$\sum_{n=1}^{\infty} \left[ EI \left(\frac{n\pi}{L}\right)^4 + \chi \right] \sin\left(\frac{n\pi x}{L}\right) q_n(t) + \sum_{n=1}^{\infty} \eta \sin\left(\frac{n\pi x}{L}\right) \dot{q}_n(t) + \sum_{n=1}^{\infty} \rho A \sin\left(\frac{n\pi x}{L}\right) \ddot{q}_n(t) = Q_0 \delta(x - Vt) [H(t) - H(t - L/V)]$$

Looking at the free vibration case, we can derive the following relation (also given in the assignment description): 
$$EI \left(\frac{n\pi}{L}\right)^4 = \rho A \omega_n^2 - \chi$$

Substituting this in the first bracket cancels out $\chi$. Foundation stiffness is now completely expressed in the $\omega_{n}$ term. 

$$\sum_{n=1}^{\infty} \left[ \rho A \ddot{q}_n + \eta \dot{q}_n + \rho A \omega_n^2 q_n \right] \sin\left(\frac{n\pi x}{L}\right) = Q_0 \delta(x - Vt) \left[ H(t) - H(t - L/V) \right]$$

 We eliminate the summation by using the orthogonality property, multiplying the PDE by  $\sin(\frac{m\pi x}{L})$ and integrating over the length of the beam. 

 $$\frac{L}{2} \left( \rho A \ddot{q}_m + \eta \dot{q}_m + \rho A \omega_m^2 q_m \right) = \int_0^L Q_0 \delta(x - Vt) \sin\left(\frac{m\pi x}{L}\right) [H(t) - H(t - L/V)] dx$$


 The right hand side integrates a dirac delta function at x = Vt, hence we used the sifting property to evalute the right hand side to be : 
 $$\text{Right Hand Side} = Q_0 \sin\left(\frac{m\pi V t}{L}\right) [H(t) - H(t - L/V)]$$
 
 Dividing the whole equation by the modal mass $\left(M_n = \rho A \frac{L}{2}\right)$, the equation of motion is simplified into: 
 $$\ddot{q}_m(t) + 2\zeta_m \omega_m \dot{q}_m(t) + \omega_m^2 q_m(t) = \frac{2Q_0}{\rho A L} \sin(\Omega_m t) [H(t) - H(t - L/V)]$$

 For which we have defined: 

 - Natural frequency squared: $\omega_m^2 = \frac{EI (m\pi/L)^4 + \chi}{\rho A}$
 - Modal forcing frequency: $\Omega_m = \frac{m\pi V}{L}$
 - Modal damping ratio: $\zeta_m = \frac{\eta}{2\rho A \omega_m}$

The form of the equation of motion is derived such that the Green's function can be applied, as suggested by the assignment description. Which is defined as the following: 

$$\ddot{g}_n + 2\zeta_n \omega_n \dot{g}_n + \omega_n^2 g_n = \delta(t)$$
$$g_n(t) = \frac{1}{\omega_{dn}} e^{-\zeta_n \omega_n t} \sin(\omega_{dn} t) H(t), \omega_{dn} = \omega_n \sqrt{1 - \zeta^2}$$

The Green's function gives the response of the beam of a single infinesimally short excitation at t=0. To get the total response for a moving load $q_n(t)$ we use the Duhamel's integral to get the excitation at current time t as a sum of the past tiny impulses (Green's function). 

$$q_m(t) = \int_0^t f_m(\tau) g_m(t - \tau) d\tau$$

Substituting the forcing term and the Green's function gives the total reaction as : $$q_m(t) = \frac{2Q_0}{\rho A L \omega_{dm}} \int_0^t \sin(\Omega_m \tau) e^{-\zeta_m \omega_m (t-\tau)} \sin(\omega_{dm} (t-\tau)) d\tau, for (t < L/V)$$
and 
$$q_m(t) = \frac{2Q_0}{\rho A L \omega_{dm}} \int_0^{L/V} \sin(\Omega_m \tau) e^{-\zeta_m \omega_m (t-\tau)} \sin(\omega_{dm} (t-\tau)) d\tau, for (t > L/V)$$

5. Consider an overhead powerline structure of a railway track, which is modelled as an infinite tensioned string that is periodically supported by discrete springs and dashpots. 


a) Proof that the dispersion equation of the system (without damping) reads as follows:

$$\xi^2 - \left( \frac{K_s}{\kappa} \sin(\kappa L) + 2\cos(\kappa L) \right)\xi + 1 = 0$$

We look for the free harmonic waves of the system to find the dispersion equation (no external load and damping). Consequently, the governing equation of motion simplifies to: 

$$\rho A \frac{\partial^2 w}{\partial t^2} - T \frac{\partial^2 w}{\partial x^2} + \sum_{n=-\infty}^{\infty} k_s w \delta(x - nL) = 0$$

Again, we assume a steady-state harmonic wave solution in the form $w(x,t) = W(x)e^{i\omega t}$, upon substitution we get the following ODE: 

$$-\rho A \omega^2 W(x) - T \frac{d^2 W(x)}{dx^2} + \sum_{n=-\infty}^{\infty} k_s W(x) \delta(x - nL) = 0$$

Dividing by T; we can define wavenumber $\kappa$ for the string without supports: 
$$\kappa^2 = \frac{\rho A \omega^2}{T} \implies \kappa = \frac{\omega}{\sqrt{T/\rho A}} = \frac{\omega}{c}$$

We divide the string into periodic cells. The dirac functions vanish for the inner part of an arbitrary cell m (between x = mL and x = (m+1)L) (not for the interface conditions).
Defining a local coordinate $x_m = x - mL$ such that $0 \leq x_m \leq L$, we get $$\frac{d^2 W_m}{dx_m^2} + \kappa^2 W_m = 0$$ for which the general steady-state solution is $$W_m(x_m) = A_m \cos(\kappa x_m) + B_m \sin(\kappa x_m)$$

Between adjacent cells m and m+1, 2 interface conditions are imposed (ODE 2nd order): 
$$W_m(L) = W_{m+1}(0)$$ and $$W'_{m+1}(0) - W'_m(L) = K_s W_{m+1}(0),  K_s = \frac{k_s}{T} $$

Additionally, we use the Floquet's theorem which states that for a period structure, the wave solution translates from one cell to the next by a wavenumber dependent complex phase factor 
$$W(x+L) = W(x) e^{-ikL}$$
Defining this complex phase factor as $\xi = \exp(-ikL)$ which results in 
$A_{m+1} = \xi A_m$ and $B_{m+1} = \xi B_m $

Using the Floquet's theorem into the two equations imposed by the 2 interface conditions create a system of equations purely in terms of m. 
$$\begin{bmatrix} \cos(\kappa L) - \xi & \sin(\kappa L) \\ \sin(\kappa L) - \frac{K_s}{\kappa}\xi & \xi - \cos(\kappa L) \end{bmatrix} \begin{bmatrix} A_m \\ B_m \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$$

For non trivial solutions, the determinant of the matrix must be zero which gives the target dispersion equation: $$\xi^2 - \left( \frac{K_s}{\kappa} \sin(\kappa L) + 2\cos(\kappa L) \right)\xi + 1 = 0$$

b) Derive expressions for the wavenumbers, plot the dispersion lines and interpret the result.

The derived dispersion equation with the Floquet parameter is recalled as $$e^{-2ikL} - \left( \frac{K_s}{\kappa} \sin(\kappa L) + 2\cos(\kappa L) \right)e^{-ikL} + 1 = 0$$

Dividing the entire solution by $e^{-ikL}$ gives $$e^{-ikL} + e^{ikL} = \frac{K_s}{\kappa} \sin(\kappa L) + 2\cos(\kappa L)$$

Using Euler's identity $e^{ikL} + e^{-ikL} = 2\cos(kL)$ and recalling that  $K_s = k_s/T$ allows the characteristic equation to be simplified to $$\cos(kL) = \cos(\kappa L) + \frac{k_s}{2T\kappa} \sin(\kappa L)$$

The RHS is evidentally frequency depenedent; $\kappa$ frequency dependent, for which we can plot. 

c) Derive an expression for the steady-state response in the frequency-space domain (at x=0) and plot the corresponding amplitude spectrum (for the system with damping). Interpret the result.

Now we consider the system with damping, for which the equation of motion is $$\rho A \frac{\partial^2 w}{\partial t^2} - T \frac{\partial^2 w}{\partial x^2} + \sum_{n=-\infty}^{\infty} R_n(t)\delta(x - nL) = Q_0\delta(x - Vt)$$
with $R_n(t) = \left( k_s + \eta_s \frac{\partial}{\partial t} \right) w(nL, t)$

In the steady-state, the response of the string subject to a constant load moving at velocity V is periodic. The reaction force at any support n is a time-shifted version of the reaction force at the origin: 
$$R_n(t) = R_0\left(t - n\frac{L}{V}\right) \implies \hat{R}_n(\omega) = \hat{R}(\omega)e^{-i\omega\frac{nL}{V}}$$

Applying the 2D Fourier transform in space and time with the following Fourier pair: 
$$\tilde{w}(k, \omega) = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} w(x, t) e^{-i(\omega t - k x)} \, dt \, dx ; w(x, t) = \frac{1}{2\pi} \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} \tilde{w}(k, \omega) e^{i(\omega t - k x)} \, d\omega \, dk$$

For which the 2D Fourier in the R term is 
$$ \sum_{n=-\infty}^{\infty} { \left[ \int_{-\infty}^{\infty} R\left(t - \frac{nL}{V}\right) e^{-i\omega t} \, dt \right] } { \left[ \int_{-\infty}^{\infty} \delta(x - nL) e^{ikx} \, dx \right] } = \sum_{n=-\infty}^{\infty} \hat{R}(\omega) e^{-i\omega\frac{nL}{V}} e^{iknL}$$


For which the equation of motion in the frequency, wavenumber domain becomes: 
$$(T k^2 - \rho A \omega^2)\tilde{w}(k, \omega) = 2\pi\frac{Q_0}{V}\delta\left(\omega - kV\right) - \hat{R}(\omega)\sum_{n=-\infty}^{\infty}e^{-i(\frac{\omega}{V} -k)nL}$$

We use the Poisson Summation identitiy: 
$$\sum_{n=-\infty}^{\infty} e^{-\alpha nL} = 2\frac{\pi}{L} \sum_{n=-\infty}^{\infty} \delta(\alpha - \frac{2\pi n}{L})$$

$$\hat{R}(\omega)\sum_{n=-\infty}^{\infty} e^{-i\left(\frac{\omega}{V} - k\right)L n} = \hat{R}(\omega) 2 \frac{\pi}{L} \sum_{n=-\infty}^{\infty} \delta( \frac{\omega}{V} - k - \frac{2\pi n}{L} )$$

Consequently, the transformed equation motion is $$(T k^2 - \rho A \omega^2)\tilde{w}(k, \omega) = 2\pi\frac{Q_0}{V}\delta\left(\frac{\omega}{V} - k\right) - \hat{R}(\omega)\frac{2\pi}{L}\sum_{n=-\infty}^{\infty}\delta\left(\frac{\omega}{V} - k - \frac{2\pi n}{L}\right)$$

Diving by T and setting $\kappa^2 = \frac{\rho A \omega^2}{T}$ we get :
$$\tilde{w}(k, \omega) = \frac{2\pi}{T(k^2 - \kappa^2)}\left[ \frac{Q_0}{V}\delta\left(\frac{\omega}{V} - k\right) - \frac{\hat{R}(\omega)}{L}\sum_{n=-\infty}^{\infty}\delta\left(\frac{\omega - \omega_n}{V} - k\right) \right]$$

With $\omega_n = n\frac{2\pi V}{L}$ the passing frequency of the n-th harmonic

To return to the frequency-space domain  $\hat{w}(x, \omega)$, we apply the inverse spatial Fourier transform $\frac{1}{2\pi}\int_{-\infty}^{\infty} \tilde{w}(k,\omega)e^{-ikx} dk$. Evaluating this explicitly at the origin (x = 0, so $e^{-ik(0)} = 1$) yields: 
$$\hat{w}(0, \omega) = \frac{1}{TV}\left[ \frac{Q_0}{\left(\frac{\omega}{V}\right)^2 - \kappa^2} - \frac{\hat{R}(\omega)}{L}\sum_{n=-\infty}^{\infty}\frac{1}{\left(\frac{\omega}{V} - \frac{2\pi n}{L}\right)^2 - \kappa^2} \right]$$

We factor out $\frac{1}{L^2}$ and use the mathematical identity provided in the assignment description 
$$\sum_{n=-\infty}^{\infty}\frac{1}{\left(\frac{\omega}{V} - \frac{2\pi n}{L}\right)^2 - \kappa^2} = \frac{L}{2\kappa} \frac{\sin(\kappa L)}{\cos(\kappa L) - \cos\left(\frac{\omega L}{V}\right)}$$

Substituting this back into the displacement equation gives:
  $$\hat{w}(0, \omega) = \frac{1}{TV}\frac{Q_0}{\left(\frac{\omega}{V}\right)^2 - \kappa^2} - \hat{R}(\omega)\frac{1}{2T\kappa}\frac{\sin(\kappa L)}{\cos(\kappa L) - \cos\left(\frac{\omega L}{V}\right)}$$

Recall the definition of the reaction force $\hat{R}(\omega) = (k_s + i\omega\eta_s)\hat{w}(0, \omega)$ which allows simplification in the following form: 

$$\hat{w}(0, \omega) \left[ 1 + (k_s + i\omega\eta_s) \frac{\sin(\kappa L)}{2T\kappa \left( \cos(\kappa L) - \cos\left(\frac{\omega L}{V}\right) \right)} \right] = \frac{Q_0}{TV\left( \left(\frac{\omega}{V}\right)^2 - \kappa^2 \right)}$$

By defining the dynamic stiffnesses as the following: 
- Moving load stiffness: $\hat{K}_{s,ml} = TV\left( \left(\frac{\omega}{V}\right)^2 - \kappa^2 \right)$
- String-support stiffness: $\hat{K}_{s,s} = 2T\kappa \frac{\cos(\kappa L) - \cos\left(\frac{\omega L}{V}\right)}{\sin(\kappa L)}$

We derive the final steady-state response expression: 
$$\hat{w}(0, \omega) = \frac{Q_0}{\hat{K}_{s,ml}} \left( \frac{\hat{K}_{s,s}}{\hat{K}_{s,s} + k_s + i\omega\eta_s} \right)$$

d) Compute numerically the response (at x=0) versus time (make sure you respect the sampling theorem related to the discrete Fourier transform). Interpret the result.

Using discrete Fourier transform to compute a continuous integral requires the Nyquist theorem to be respected to prevent aliasing. 
- The sampling frequency $f_s$ must be large enough to capture the highest frequencies in the response 
- $T_window$ also must be large enough to guarantee that the signal decays to zero to prevent leakage 

The IFFT output is multiplied with the sampling frequency $f_s$ to scale the dimensionless array of np.fft.ifft back into physical meters. 