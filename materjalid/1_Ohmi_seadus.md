# Ohmi seadus

Ohmi seadus on üks elektrotehnika põhilisi seadusi, mis kirjeldab seost elektrivoolu, pinge ja takistuse vahel.

## Valem ja selgitus
Ohmi seadus väljendub järgmiselt:

### $U = I \cdot R$

**kus**:
* **U** – pinge (voltides, V)
* **I** – voolutugevus (amprites, A)
* **R** – takistus (oomides, Ω)

Seaduse järgi on voolutugevus juhis otseselt proportsionaalne pingega ja pöördvõrdeline takistusega.

## Ohmi seaduse teisendused

Ohmi seadust saab kasutada ka teistes vormides sõltuvalt otsitavast suurusest:

**Voolutugevuse arvutamine:** 

$$I = \frac{U}{R}$$
   

**Takistuse arvutamine:** 

$$R = \frac{U}{I}$$


## Näide arvutamisest

Kui vooluringis on takistus **100 Ω** ja sellele rakendatakse pinge **5 V**, siis voolutugevus on:

$$I=\frac{5V}{100\Omega}=0.05 A$$


## Miks seda vaja teada on?
* **Seadmed ja sensorid vajavad tööks kindla pingega voolu** - Arduino töötab tavaliselt 5V või 3.3V pingega, kuid erinevad komponendid, nagu LEDid, mootorid ja andurid, vajavad kindlat voolutugevust. Ilma Ohmi seadust rakendamata võib liiga suur vool neid komponente kahjustada.
* **Kontrollerite poolt pakutava toite voolutugevus on piiratud** - kui kasutatakse mootoreid või releesid, tuleb arvestada voolutugevusega, mida Arduino suudab pakkuda. Sageli kasutatakse transistore või releesid, et suuremad voolud suunata läbi eraldi toiteallika.
* **Liiga suur voolutugevus kahjustab elektroonikakomponente** - Näiteks LEDide kasutamisel tuleb arvutada õige piirav takisti, et vältida liigset voolutugevust, mis võiks LEDi läbi põletada. Kui LED töötab 20mA (0.02A) vooluga ja pinge on 5V, aga LEDi pinge langus on 2V, siis vajalik takisti arvutatakse: 

$$R=\frac{5V - 2V}{0.02 A}=150 \Omega$$

**Ohmi seadust kasutatakse:**
* **Elektriahelate** analüüsimisel ja kavandamisel
* **Takistuse** määramisel elektriahelas
* **Elektriliste komponentide** (nt takistid, juhtmed) omaduste hindamisel