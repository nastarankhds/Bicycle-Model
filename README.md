# Bicycle-Model
Bicycle Model Derivation


<img width="700" height="586" alt="image" src="https://github.com/user-attachments/assets/da1080be-4dd1-47db-a5ff-d5a11766b81f" />



The figure above shows diagram of a bicycle model or a single track model.

Base on this figure and its shown vectors such as velocity, sideslip angle, slip angles in the front and rear, lateral forces, and steering angle, the model formulation will be derived.

First of all, let's derive the **slip angle formulations in the front and rear**:


## Slip Angle Calculation (Bicycle Model)

First, we derive the **front** and **rear** slip angles from the geometry in the figure.

### Frames and Unit Vectors

- **Body frame at CoG** 

- **Wheel-plane unit vectors (front steered by  $\delta$ )**

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

- **Wheel-plane unit vectors (rear, no steer)**

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

Let $u$ be longitudinal speed at CoG, $v$ lateral speed at CoG, $r$ yaw rate, $l_f$ front axle distance, $l_r$ rear axle distance.

$$
\mathbf v_F^{\text{body}}=
\begin{bmatrix}
u\\
v+l_f r
\end{bmatrix},
\qquad
\mathbf v_R^{\text{body}}=
\begin{bmatrix}
u\\
v-l_r r
\end{bmatrix}.
$$

### Projections onto Wheel Axes

Front wheel:

$$
V_{xF}=u\cos\delta+(v+l_r r)\sin\delta,
\qquad
V_{yF}=-u\sin\delta+(v+l_f r)\cos\delta.
$$

Rear wheel:

$$
V_{xR}=u,
\qquad
V_{yR}=v-l_r r.
$$

### Slip Angles (wheel-frame definition)

$$
\alpha_f=\mathrm{atan2}(V_{yF},\,V_{xF}),\qquad
\alpha_r=\mathrm{atan2}(V_{yR},\,V_{xR}).
$$

*Linearized (small angles):* 

$$ \alpha_f \approx \dfrac{v+l_f r}{u}-{\delta} $$

$$ \alpha_r \approx \dfrac{v-l_r r}{u} $$

in other words:

$$ \alpha_f \approx {\beta} + \dfrac{l_f r}{u}-{\delta} $$

$$ \alpha_r \approx {\beta} - \dfrac{l_r r}{u} $$


## Single-Track model Derivation

we start with the most basic rule in physics:


#### $\beta$:

$$
\{\sum{F_y}} = \{m}*{a_y}
$$

$$
\{\{fy_f}*cos({\delta}) + \{fyr_r} } = \{m * ({\dot{v_y}} + \{v_x}*r)}
$$

after substitution:

$$
\dot{v_y} = \frac{c_r + c_f}{mv_x}
$$
