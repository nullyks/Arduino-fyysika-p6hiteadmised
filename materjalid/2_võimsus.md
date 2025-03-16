# Võimsus

Võimsus (ingl *power*) on füüsikaline suurus, mis iseloomustab töö tegemise kiirust. 
Elektroonikaseadmete juures on võimsus oluline parameeter, mis määrab ära, kui palju energiat seade tarbib või kui palju energiat on võimalik vooluahelas kasutada. 
Arduino rakendustes on oluline mõista, kuidas arvutada ja hallata alalisvoolu (ingl *direct current, DC*) võimsust, et vältida komponentide ülekuumenemist ja kahjustumist.

Elektriahelates on võimsuse arvutamiseks üldine valem:
### $P = U  I$

**kus:**
* **P** – võimsus (vattides, W)
* **U** – pinge (voltides, V)
* **I** – voolutugevus (amprites, A)

## Arduino arendusplaat ja võimsus
Arduino arendusplaadid saavad toidet erinevatest allikatest. On oluline, et Arduino enda ja sellega ühendatud komponendtide koguvõimsus ei ületaks toiteallika poolt pakutavat võimsust.
* **USB (5V, 500mA max)** – standardne USB-toide võib anda kuni 2.5W (5V × 0.5A).
* **VCC-viik (5V)** – otsetoide Arduino 5V väljundist (pole soovitatav kasutada suurte koormuste korral).
* **Toitepistik (*ingl Barrel jack*) (7-12V)** – kasutatakse koos sisemise regulaatoriga, kuid kõrgem pinge tekitab rohkem soojuskadu.


Kui Arduino toidab LED-e, mootoreid või andureid, tuleb arvestada nende voolutarbimisega. Kui Arduino töötab 5V ja tarbib 200 mA voolu, siis:

$P = 5V \times 0.2A = 1W$

See tähendab, et Arduino ja selle komponendid tarbivad 1 vati energiat.

Arduino kasutamisest koos mootoritega räägitakse täpsemalt [selles õppematerjalis](https://github.com/nullyks/Arduino-mootorid-ja-toide)

## Üksikud komponendid ja võimsus
### Takisti
Takisti tarbib vooluahelas energiat ja muundab selle soojuseks. Takisti poolt hajutatud soojusenergia võimsus arvutatakse:

$P = I^2 \times R$ või 
$P = \frac{U^2}{R}$

*kus:*
* **R** – takistus (oomides, Ω)
* **U** – pinge (voltides, V)
* **I** – voolutugevus (amprites, A)

**Näide takisti võimsuse arvutusest**

Kui ühendame 100Ω takisti 5V toiteallikaga:

$P = \frac{5V^2}{100\Omega} = 0.25W$

Takisti peab olema vähemalt 0.25W lubatud võimsusega, et mitte üle kuumeneda.

### LED
Kui LEDi läbib vooluahelas vool, siis tarbib LED energiat ja muundab selle peamiselt valguskiirguseks. Kui LED töötab 20mA ja 5V pingel, siis tema tema poolt tarbitav võimsus on:

$P = 5V \times 0.02A = 0.1W$

### Mootor
Isegi väga väike alalisvoolu mootor võib tarbida 200mA voolu. Eeldame taaskord, et see toimub toitepinvel 5V. Selle mootori võimsuseks on:

$P = 5V \times 0.2A = 1W$

Kui mootor on ühendatud otse näiteks Arduino digitaalse viiguga, põhjustab see ülekoormust. Seetõttu tuleks selle mootori juhtimiseks kasutada transistorit või releed.