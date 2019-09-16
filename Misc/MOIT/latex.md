A(z_{f})=-lnT(z_{f})=\sum_{l=0,z_{l}<z_{f}}^{n-1}-ln(1-\alpha_{l})
\delta_{z_l}=\begin{cases} 1&z_l < z_f \\ 0 & otherwise \end{cases}
Z=\sum_{l=0}^{n-1}{-ln(1-\alpha_l)\cdot\delta_{z_l}}
\pmb{b}(z)=(1,z,z^2,...,z^m)^T
b=\varepsilon_z(\pmb{b})=\sum_{l=0}^{n-1}{-ln(1-\alpha_l) \cdot \pmb{b}(z_l)}
b_0=\sum_{l=0}^{n-1}{-ln(1-\alpha_l)}
T(z_f,b,\beta)=exp(-A(z_f,b,\beta))
\sum_{l=0}^{n-1}{L_l \cdot \alpha_l \cdot T(z_f,b,\beta)}
{-ln(1-\alpha_l) \cdot \pmb{b}(z_l)}
exp(-b_0) \cdot L_n+\frac{1-exp(-b_0)}{\sum_{l=0}^{n-1}{\alpha_l\cdot T(z_f,b,\beta)}}\cdot\sum_{l=0}^{n-1}{L_l\cdot \alpha_l \cdot T(z_f,b,\beta)}
\sum_{l=0}^{n-1}{\alpha_l\cdot T(z_f,b,\beta)}

\left(\begin{matrix}b_0 & b_1 & b_2 \\ b_1 & b_2 & b_3 \\ b2 & b3 & b4\end{matrix}\right) \cdot \left(\begin{matrix}q_0 \\ q_1 \\q_2\end{matrix}\right)=\left(\begin{matrix}1 \\ z_f^1 \\ z_f^2\end{matrix}\right)
A=LDL^T=\left(\begin{matrix}1&0&0\\ L_{10} & 1 &0 \\ L_{20} & L_{21} & 1\end{matrix}\right)\left(\begin{matrix}D_0&0&0\\0&D_1&0\\0&0&D_2\end{matrix}\right)\left(\begin{matrix}1&L_{10}&L_{20}\\0&1&L_{21}\\0&0&1\end{matrix}\right)
q_2\cdot z^2+q_1 \cdot z + q_0 = 0
\left(\begin{matrix}1 & z_f & z_f^2 \\ 1 & z_1 & z_1^2 \\ 1&z_2&z_2^2\end{matrix}\right)\cdot\left(\begin{matrix}u_0\\u_1\\u_2\end{matrix}\right)=\left(\begin{matrix}v_0\\v_1\\v_2\end{matrix}\right)
\sum_{j=0}^{\frac{m}{2}}{b_j\cdot u_j}