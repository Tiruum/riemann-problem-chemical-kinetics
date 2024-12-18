# Numerical solution of Riemann problem
>[!TLDR]
>Numerical solution of Riemann problem with chemical reaction of $C_2H_6 + 3.5O_2  = 2CO_2 + 3H_2O$ using `Python`.

Система уравнений для данной задачи представляет собой систему уравнений Эйлера с добавлением химической реакции.

### 1. Уравнение сохранения массы
$$
\frac{\partial \rho}{\partial t} + \frac{\partial (\rho u)}{\partial x} = 0
$$
где $\rho$ — плотность, $u$ — скорость потока.

### 2. Уравнение сохранения импульса
$$
\frac{\partial (\rho u)}{\partial t} + \frac{\partial \left(\rho u^2 + p\right)}{\partial x} = 0
$$
где $p$ — давление, связанное с плотностью и энергией через уравнение состояния для идеального газа.

### 3. Уравнение сохранения энергии
$$
\frac{\partial E}{\partial t} + \frac{\partial \left((E + p) u\right)}{\partial x} = -\omega Q_{\text{reaction}}
$$
где $E$ — полная энергия, $\omega$ — скорость химической реакции, и $Q_{\text{reaction}}$ — теплота реакции.

### 4. Уравнения для массовых долей компонентов (A и B)
$$
\frac{\partial (\rho Y_A)}{\partial t} + \frac{\partial (\rho Y_A u)}{\partial x} = -\omega
$$
$$
\frac{\partial (\rho Y_B)}{\partial t} + \frac{\partial (\rho Y_B u)}{\partial x} = \omega
$$
где $Y_A$ и $Y_B$ — массовые доли видов A и B соответственно.

### Химическая кинетика (источниковые члены)
Скорость реакции определяется уравнением Аррениуса:
$$
\omega = A_{\text{preexp}} \exp\left(-\frac{E_a}{R_{\text{universal}} T}\right) \frac{\rho Y_A}{\rho}
$$
где:
- $A_{\text{preexp}}$ — предэкспоненциальный множитель,
- $E_a$ — энергия активации,
- $T$ — температура.

### Полная система
С учетом вышеописанных уравнений и уравнения состояния для давления $p$, система уравнений может быть решена численно.
