# Ohmi seadus

Ohmi seadus kirjeldab seost elektripinge, voolutugevuse ja takistuse vahel. Mida suurem on pinge, seda suurem on voolutugevus. Mida suurem on takistus, seda väiksem on voolutugevus.

## Valem

$$U = I \cdot R$$

kus:

* $U$ – pinge voltides (V);
* $I$ – voolutugevus amprites (A);
* $R$ – takistus oomides (Ω).

Ohmi seadust saab teisendada vastavalt sellele, millist suurust soovime arvutada.

### Pinge arvutamine

$$U = I \cdot R$$

### Voolutugevuse arvutamine

$$I = \frac{U}{R}$$

### Takistuse arvutamine

$$R = \frac{U}{I}$$

Ohmi seaduse kasutamiseks peavad kõik suurused olema omavahel sobivates ühikutes. Näiteks tuleb milliamprid enne valemisse asetamist teisendada ampriteks:

$$20\ \mathrm{mA} = 0{,}020\ \mathrm{A}$$

## Arvutusnäide

Vooluahelas on 100 Ω takisti, mis on ühendatud 5 V toiteallikaga. Leiame takistit läbiva voolutugevuse.

**Antud:**

* $U = 5\ \mathrm{V}$
* $R = 100\ \Omega$

**Valem:**

$$I = \frac{U}{R}$$

**Arvutus:**

$$I = \frac{5\ \mathrm{V}}{100\ \Omega} = 0{,}05\ \mathrm{A} = 50\ \mathrm{mA}$$

**Vastus:** takistit läbib vool tugevusega 50 mA.

Takistitest räägitakse täpsemalt [Arduino baaselementide õppematerjalis](https://github.com/nullyks/Arduino-baaselemendid/blob/main/materjalid/1_takistid.md).

## Miks seda vaja teada on?

Ohmi seadus aitab valida vooluahelasse sobiva takisti ning kontrollida, et komponentide ja Arduino viikude kaudu ei liiguks liiga tugev vool.

### LED-i takisti valimine

LED-iga tuleb jadamisi ühendada voolu piirav takisti. Takisti arvutamisel lahutatakse toitepingest LED-i päripinge.

Oletame, et:

* Arduino väljundpinge on 5 V;
* punase LED-i päripinge on ligikaudu 2 V;
* takisti väärtus on 470 Ω.

LED-i ja takistit läbiv voolutugevus on:

$$I = \frac{5\ \mathrm{V} - 2\ \mathrm{V}}{470\ \Omega} \approx 0{,}0064\ \mathrm{A} = 6{,}4\ \mathrm{mA}$$

[Arduino UNO R3 tehniliste andmete](https://docs.arduino.cc/hardware/uno-rev3) järgi on ühe I/O-viigu suurim lubatud vool 20 mA. [Arduino UNO R4 WiFi andmelehe](https://docs.arduino.cc/resources/datasheets/ABX00087-datasheet.pdf) järgi võib selle GPIO-viik ohutult taluda kuni 8 mA voolu. Arvutatud 6,4 mA jääb mõlema plaadi piiridesse, mistõttu kasutatakse selle kursuse füüsilistes LED-ahelates 470 Ω takisteid.

LED-i tegelik päripinge sõltub selle tüübist ja värvist. Vajaduse korral leiab täpse väärtuse LED-i andmelehelt või mõõdab multimeetriga.

### Suurema voolutarbega seadmed

Mootorit, relee mähist või muud suurema voolutarbega seadet ei tohi ühendada otse Arduino I/O-viiguga. Sellise seadme juhtimiseks kasutatakse sobivat transistorit või muud draiverit ning vajaduse korral eraldi toiteallikat. Mootori ja relee mähise puhul tuleb arvestada ka induktiivkoormuse kaitsedioodiga.

Ohmi seadust kasutatakse:

* vooluahelate analüüsimisel ja kavandamisel;
* takisti väärtuse valimisel;
* komponentide ja ühenduste ohutuse kontrollimisel.

---

[Sisukord](README.md) · [Järgmine: elektrivõimsus](2_võimsus.md)
