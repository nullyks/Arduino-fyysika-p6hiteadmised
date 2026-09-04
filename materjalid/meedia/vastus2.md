# Segavooluahela ülesande lahendus

**Antud:**

* $R_1 = 330\ \Omega$
* $R_2 = 220\ \Omega$
* $R_3 = 100\ \Omega$
* $U = 5\ \mathrm{V}$

## 1. Rööpühenduse kogutakistus

Takistid $R_2$ ja $R_3$ on ühendatud rööbiti:

$$R_{23} = \frac{R_2 \cdot R_3}{R_2 + R_3}$$

$$R_{23} = \frac{220\ \Omega \cdot 100\ \Omega}{220\ \Omega + 100\ \Omega} = 68{,}75\ \Omega$$

## 2. Kogu vooluahela kogutakistus

Takisti $R_1$ on rööpühendusega jadamisi:

$$R_{\mathrm{kokku}} = R_1 + R_{23}$$

$$R_{\mathrm{kokku}} = 330\ \Omega + 68{,}75\ \Omega = 398{,}75\ \Omega$$

## 3. Takistit R₁ läbiv voolutugevus

Takistit $R_1$ läbib kogu vooluahela vool:

$$I_1 = \frac{U}{R_{\mathrm{kokku}}}$$

$$I_1 = \frac{5\ \mathrm{V}}{398{,}75\ \Omega} \approx 0{,}01254\ \mathrm{A} = 12{,}54\ \mathrm{mA}$$

## 4. Takistile R₁ langev pinge

$$U_1 = I_1 \cdot R_1$$

$$U_1 = 0{,}01254\ \mathrm{A} \cdot 330\ \Omega \approx 4{,}14\ \mathrm{V}$$

## 5. Rööpühendusele langev pinge

$$U_{23} = U - U_1$$

$$U_{23} = 5\ \mathrm{V} - 4{,}14\ \mathrm{V} \approx 0{,}86\ \mathrm{V}$$

Sama pinge rakendub nii takistile $R_2$ kui ka takistile $R_3$.

## 6. Takistit R₂ läbiv voolutugevus

$$I_2 = \frac{U_{23}}{R_2}$$

$$I_2 = \frac{0{,}862\ \mathrm{V}}{220\ \Omega} \approx 0{,}00392\ \mathrm{A} = 3{,}92\ \mathrm{mA}$$

## 7. Takistit R₃ läbiv voolutugevus

$$I_3 = \frac{U_{23}}{R_3}$$

$$I_3 = \frac{0{,}862\ \mathrm{V}}{100\ \Omega} \approx 0{,}00862\ \mathrm{A} = 8{,}62\ \mathrm{mA}$$

## Kontroll

$$I_2 + I_3 = 3{,}92\ \mathrm{mA} + 8{,}62\ \mathrm{mA} = 12{,}54\ \mathrm{mA}$$

Rööpharude voolude summa võrdub takistit $R_1$ läbiva vooluga.

## Vastused

* $R_{23} = 68{,}75\ \Omega$
* $R_{\mathrm{kokku}} = 398{,}75\ \Omega$
* $I_1 \approx 12{,}54\ \mathrm{mA}$
* $U_1 \approx 4{,}14\ \mathrm{V}$
* $U_{23} \approx 0{,}86\ \mathrm{V}$
* $I_2 \approx 3{,}92\ \mathrm{mA}$
* $I_3 \approx 8{,}62\ \mathrm{mA}$
