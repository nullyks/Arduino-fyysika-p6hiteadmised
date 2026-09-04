# Takisti võimsuse ülesande lahendus

**Antud:**

* $U = 9\ \mathrm{V}$
* $R = 100\ \Omega$

## 1. Voolutugevuse arvutamine

Ohmi seaduse järgi:

$$I = \frac{U}{R}$$

$$I = \frac{9\ \mathrm{V}}{100\ \Omega} = 0{,}09\ \mathrm{A} = 90\ \mathrm{mA}$$

Takistit läbib vool tugevusega 90 mA.

## 2. Võimsuse arvutamine

Arvutame võimsuse pinge ja voolutugevuse järgi:

$$P = U \cdot I$$

$$P = 9\ \mathrm{V} \cdot 0{,}09\ \mathrm{A} = 0{,}81\ \mathrm{W}$$

Kontrollime tulemust teise valemiga:

$$P = \frac{U^2}{R}$$

$$P = \frac{(9\ \mathrm{V})^2}{100\ \Omega} = \frac{81}{100}\ \mathrm{W} = 0{,}81\ \mathrm{W}$$

Mõlemad valemid annavad sama tulemuse: takistis hajub 0,81 W võimsust.

## 3. Sobiva takisti valimine

0,25 W takistit ei tohi selles ahelas kasutada, sest arvutatud 0,81 W ületab selle nimivõimsust rohkem kui kolm korda. Takisti kuumeneks tugevalt ja võiks kahjustuda.

1 W takisti nimivõimsust arvutus otseselt ei ületa, kuid 0,81 W oleks selle jaoks pikaajalisel kasutamisel väga suur koormus. Mõistliku võimsusvaru jätmiseks valime vähemalt 2 W nimivõimsusega takisti.

## Vastus

Ahelat läbib vool tugevusega 90 mA ja takistis hajub 0,81 W võimsust. 0,25 W takisti ei sobi. Pikemaajaliseks kasutamiseks valime vähemalt 2 W takisti.

**Ohutusmärkus:** see on arvutusülesanne. Sellist 90 mA koormust ei tohi ühendada Arduino I/O-viiguga.
