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





## Slip Angle Calculation (Bicycle Model)

First, we derive the **front** and **rear** slip angles from the geometry in the figure.

![Bicycle model free-body diagram](assets/bicycle_fbd.png)
*Figure — Geometry and vectors used for slip angles*

### Frames and Unit Vectors
- **Body frame at CoG:** \( \mathbf i_x \) along \( x_{\text{CoG}} \), \( \mathbf i_y \) along \( y_{\text{CoG}} \).
- **Wheel-plane unit vectors**
  
  Front wheel steered by \( \delta \):
  $$
  \mathbf e_{xF}=
  \begin{bmatrix}
  \cos\delta\\
  \sin\delta
  \end{bmatrix},
  \qquad
  \mathbf e_{yF}=
  \begin{bmatrix}
  -\sin\delta\\
  \cos\delta
  \end{bmatrix}.
  $$

  Rear wheel (no steer):
  $$
  \mathbf e_{xR}=
  \begin{bmatrix}
  1\\
  0
  \end{bmatrix},
  \qquad
  \mathbf e_{yR}=
  \begin{bmatrix}
  0\\
  1
  \end{bmatrix}.
  $$

### Wheel-Center Velocities (rigid-body kinematics)
Let \(u\) be longitudinal speed at CoG, \(v\) lateral speed at CoG, \(r\) yaw rate, \(a\) front axle distance from CoG, \(b\) rear axle distance from CoG.

$$
\mathbf v_F^{\text{body}}=
\begin{bmatrix}
u\\
v+a r
\end{bmatrix},
\qquad
\mathbf v_R^{\text{body}}=
\begin{bmatrix}
u\\
v-b r
\end{bmatrix}.
$$
