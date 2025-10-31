# Bicycle-Model
Bicycle Model Derivation


<img width="700" height="586" alt="image" src="https://github.com/user-attachments/assets/da1080be-4dd1-47db-a5ff-d5a11766b81f" />



The figure above shows diagram of a bicycle model or a single track model.

Base on this figure and its shown vectors such as velocity, sideslip angle, slip angles in the front and rear, lateral forces, and steering angle, the model formulation will be derived.

First of all, let's derive the **slip angle formulations in the front and rear**:

if we consider the body frame at COG, for front and rear we have:

$$ \{e_\{xf}} = \beginmetrix{bmatrix}
\{cos[\{delta})} \\
\{sin(\{delta})}
$$





# Slip Angle Calculation (Bicycle Model)

<!-- Optional figure (edit path/URL as needed) -->
<p align="center">
  <img src="assets/bicycle_fbd.png" alt="Bicycle model free-body diagram" width="520">
  <br><em>Figure — Geometry and vectors used for slip angles</em>
</p>

## Frames and Vectors
- **Body frame at CoG:** \( \mathbf{i}_x \) along \(x_{\text{CoG}}\), \( \mathbf{i}_y \) along \(y_{\text{CoG}} \).
- **Wheel-plane frames**
  - **Front (steered by \(\delta\))**
    \[
    \mathbf{e}_{xF}=\begin{bmatrix}\cos\delta\\ \sin\delta\end{bmatrix},\quad
    \mathbf{e}_{yF}=\begin{bmatrix}-\sin\delta\\ \cos\delta\end{bmatrix}.
    \]
  - **Rear (no steer)**
    \[
    \mathbf{e}_{xR}=\begin{bmatrix}1\\0\end{bmatrix},\quad
    \mathbf{e}_{yR}=\begin{bmatrix}0\\1\end{bmatrix}.
    \]

## Wheel-Center Velocities (Rigid-Body Kinematics)
Let \(u\) be longitudinal speed at CoG, \(v\) lateral speed at CoG, \(r\) yaw rate, \(a\) front axle offset, \(b\) rear axle offset.
\[
\mathbf{v}_F^{\text{body}}=\begin{bmatrix}u\\ v+a r\end{bmatrix},\qquad
\mathbf{v}_R^{\text{body}}=\begin{bmatrix}u\\ v-b r\end{bmatrix}.
\]

## Projections onto Wheel Axes
Front wheel (project \(\mathbf{v}_F\) onto wheel axes):
\[
V_{xF}= \mathbf{v}_F\!\cdot\!\mathbf{e}_{xF}
= u\cos\delta+(v+a r)\sin\delta,
\]
\[
V_{yF}= \mathbf{v}_F\!\cdot\!\mathbf{e}_{yF}
= -u\sin\delta+(v+a r)\cos\delta.
\]

Rear wheel:
\[
V_{xR}=u,\qquad V_{yR}=v-b r.
\]

## Slip Angles (Definition in Wheel Frames)
Angle between wheel plane and wheel-center velocity:
\[
\boxed{\alpha_f=\operatorname{atan2}(V_{yF},\,V_{xF})},\qquad
\boxed{\alpha_r=\operatorname{atan2}(V_{yR},\,V_{xR})}.
\]

### Linearized Form (small \(\beta,\ ar/u,\ br/u,\ \delta\))
Using \(\beta=\arctan(v/u)\approx v/u\):
\[
\alpha_f \approx \beta+\frac{a r}{u}-\delta,\qquad
\alpha_r \approx \beta-\frac{b r}{u}.
\]

## Notes
- Angles in radians. Keep a small floor on \(u\) in code to avoid division spikes.
- Sign convention: left turn \(r>0\), \(\delta>0\), \(v>0\) gives positive \(\alpha_f,\alpha_r\).
