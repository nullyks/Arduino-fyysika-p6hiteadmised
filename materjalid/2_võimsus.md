# Elektrivõimsus

Elektrivõimsus näitab, kui palju elektrienergiat ajaühikus muundatakse või edastatakse. Võimsuse tähis on $P$ ja mõõtühik vatt (W).

Üks vatt tähendab, et ühe sekundi jooksul muundatakse või edastatakse üks džaul energiat:

$$1\ \mathrm{W} = 1\ \mathrm{J/s}$$

Alalisvooluahelas arvutatakse elektrivõimsus pinge ja voolutugevuse korrutisena:

$$P = U \cdot I$$

kus:

* $P$ – võimsus vattides (W);
* $U$ – pinge voltides (V);
* $I$ – voolutugevus amprites (A).

## Arduino arendusplaat ja toide

Arduino arendusplaat ja sellega ühendatud komponendid vajavad sobiva pingega toiteallikat. Toiteallikas peab suutma varustada kogu vooluahelat vajaliku vooluga, kuid komponendid võtavad sellest ainult nii palju voolu, kui nende tööks vaja läheb.

Arduino arendusplaadi toiteallika valimisel tuleb lähtuda konkreetse plaadi dokumentatsioonist ja [Arduino ametlikust toitejuhendist](https://support.arduino.cc/hc/en-us/articles/360018922259-What-power-supply-can-I-use-with-my-Arduino-board).

Arduino UNO arendusplaati saab toita järgmistel viisidel:

* **USB-kaabli kaudu** – USB-ühendus võimaldab arendusplaati programmeerida ja annab sellele ligikaudu 5 V toitepinge.
* **Barrel-jack-tüüpi toitepistiku kaudu** – pistikusse ühendatakse sobiv alalisvooluadapter. UNO R3 soovituslik sisendpinge on 7–12 V. UNO R4 WiFi sisendpinge võib olla 6–24 V. Pistiku keskmine kontakt peab olema positiivne.
* **VIN- ja GND-viigu kaudu** – välise alalisvooluallika positiivne juhe ühendatakse VIN-viiguga ja negatiivne juhe GND-viiguga. VIN on sisendviik. VIN-viiku ja barrel-jack-tüüpi toitepistikut ei kasutata samal ajal, sest need on ühendatud sama toiteahelaga.

Arduino **5 V toiteviiku** kasutatakse selles õppematerjalis ainult väikese voolutarbega andurite ja muude komponentide toitmiseks. Arduino arendusplaati ennast me 5 V viigu kaudu ei toida.

5 V viigust saadaolev vool sõltub arendusplaadi toiteviisist, pingeregulaatorist ja teiste komponentide voolutarbest. Mootoreid, servomootoreid ja muid suure voolutarbega seadmeid tuleb toita eraldi sobivast toiteallikast.

Arduino I/O-viik ei ole toiteviik. [UNO R3 tehniliste andmete](https://docs.arduino.cc/hardware/uno-rev3) järgi on ühe I/O-viigu suurim lubatud vool 20 mA ja [UNO R4 WiFi andmelehe](https://docs.arduino.cc/resources/datasheets/ABX00087-datasheet.pdf) järgi 8 mA.

### Võimsuse arvutamise näide

Oletame, et Arduino koos ühendatud komponentidega kasutab 5 V pingel voolu 200 mA. Esmalt teisendame milliamprid ampriteks:

$$200\ \mathrm{mA} = 0{,}2\ \mathrm{A}$$

Seejärel arvutame võimsuse:

$$P = 5\ \mathrm{V} \cdot 0{,}2\ \mathrm{A} = 1\ \mathrm{W}$$

Arduino ja sellega ühendatud komponendid kasutavad selles näites elektrivõimsust 1 W.

Arduino kasutamisest koos mootoritega räägitakse täpsemalt [mootorite ja toite õppematerjalis](https://github.com/nullyks/Arduino-mootorid-ja-toide).

## Üksikud komponendid ja võimsus

### Takisti

Takisti muundab selles hajuva elektrienergia peamiselt soojuseks. Takistis hajuvat võimsust saab arvutada järgmiste valemitega:

$$P = I^2 \cdot R$$

või

$$P = \frac{U^2}{R}$$

kus:

* $P$ – takistis hajuv võimsus vattides (W);
* $I$ – takistit läbiv voolutugevus amprites (A);
* $U$ – takistile rakendatud pinge voltides (V);
* $R$ – takistus oomides (Ω).

#### Näide

100 Ω takisti ühendatakse otse 5 V toiteallikaga. Selles näites ei ühendata takistit Arduino I/O-viiguga.

Takistit läbiv voolutugevus on:

$$I = \frac{5\ \mathrm{V}}{100\ \Omega} = 0{,}05\ \mathrm{A} = 50\ \mathrm{mA}$$

Takistis hajuv võimsus on:

$$P = \frac{(5\ \mathrm{V})^2}{100\ \Omega} = 0{,}25\ \mathrm{W}$$

Arvutatud 0,25 W on takisti tegelik koormus, mitte sobiva takisti soovituslik nimivõimsus. Takistit ei ole hea kasutada pidevalt selle suurima lubatud võimsuse piiril. Seetõttu valime sellele ahelale vähemalt 0,5 W nimivõimsusega takisti.

### LED

LED muundab elektrienergiat valguseks ja soojuseks. LED-is hajuv võimsus arvutatakse LED-i päripinge ja seda läbiva voolutugevuse järgi:

$$P_{\mathrm{LED}} = U_{\mathrm{LED}} \cdot I$$

Kasutame sama näidet nagu Ohmi seaduse peatükis:

* toitepinge on 5 V;
* punase LED-i päripinge on ligikaudu 2 V;
* takisti väärtus on 470 Ω;
* ahela voolutugevus on ligikaudu 6,4 mA ehk 0,0064 A.

LED-is hajuv võimsus on:

$$P_{\mathrm{LED}} = 2\ \mathrm{V} \cdot 0{,}0064\ \mathrm{A} = 0{,}0128\ \mathrm{W} \approx 13\ \mathrm{mW}$$

Takistile jääb pinge:

$$U_R = 5\ \mathrm{V} - 2\ \mathrm{V} = 3\ \mathrm{V}$$

Takistis hajuv võimsus on:

$$P_R = 3\ \mathrm{V} \cdot 0{,}0064\ \mathrm{A} = 0{,}0192\ \mathrm{W} \approx 19\ \mathrm{mW}$$

Kogu LED-i ja takisti haru kasutab ligikaudu:

$$P_{\mathrm{kokku}} = 13\ \mathrm{mW} + 19\ \mathrm{mW} = 32\ \mathrm{mW}$$

Sama tulemuse saame toitepinge ja koguvoolu järgi:

$$P_{\mathrm{kokku}} = 5\ \mathrm{V} \cdot 0{,}0064\ \mathrm{A} = 0{,}032\ \mathrm{W}$$

### Mootor

Mootori voolutarve sõltub selle koormusest. Mootori andmelehel võivad olla eraldi näidatud koormuseta vool, nimivool ja seiskumisvool. Kõige suurem vool tekib tavaliselt mootori käivitamisel või siis, kui mootori võll ei saa pöörelda.

Oletame, et 5 V alalisvoolumootor kasutab tavapärasel töötamisel voolu 200 mA ehk 0,2 A. Mootori kasutatav elektrivõimsus on:

$$P = 5\ \mathrm{V} \cdot 0{,}2\ \mathrm{A} = 1\ \mathrm{W}$$

Toiteallika ja mootoridraiveri valimisel ei piisa ainult tavapärase töövoolu arvestamisest. Need peavad taluma ka mootori suuremat käivitus- ja seiskumisvoolu.

Mootorit ei tohi ühendada otse Arduino I/O-viigu ega selles õppematerjalis ka Arduino 5 V toiteviiguga. Mootori juhtimiseks kasutatakse transistorit, MOSFET-i või spetsiaalset mootoridraiverit ning mootorit toidetakse sobivast eraldi toiteallikast.

Arduino ja mootori toiteallika GND-ühendused peavad olema omavahel ühendatud. Harjadega alalisvoolumootori puhul kasutatakse pingeimpulsside eest kaitsmiseks ka kaitsedioodi.

---

[Eelmine: Ohmi seadus](1_Ohmi_seadus.md) · [Sisukord](README.md) · [Järgmine: vooluahelad](3_vooluahelad.md)
