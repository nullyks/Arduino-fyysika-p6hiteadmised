# Potentsiomeetri asendi näidiku näidislahendus

## Ühendused

| Komponent | Arduino ühendus |
|---|---|
| Potentsiomeetri keskmine jalg | A0 |
| Potentsiomeetri äärmised jalad | 5 V ja GND |
| Esimene LED koos 470 Ω takistiga | D2 ja GND |
| Teine LED koos 470 Ω takistiga | D3 ja GND |
| Kolmas LED koos 470 Ω takistiga | D4 ja GND |
| Neljas LED koos 470 Ω takistiga | D5 ja GND |
| Surunupp | D7 ja GND |

## Programm

```cpp
const byte LED_PINS[] = {2, 3, 4, 5};
const byte LED_COUNT = 4;
const byte BUTTON_PIN = 7;
const byte POTENTIOMETER_PIN = A0;

const unsigned long DEBOUNCE_TIME = 50;

bool deviceOn = false;
bool lastButtonReading = HIGH;
bool stableButtonState = HIGH;
unsigned long buttonChangedAt = 0;

void setup() {
  for (byte i = 0; i < LED_COUNT; i++) {
    pinMode(LED_PINS[i], OUTPUT);
    digitalWrite(LED_PINS[i], LOW);
  }

  pinMode(BUTTON_PIN, INPUT_PULLUP);
}

void loop() {
  updateDeviceState();

  if (!deviceOn) {
    showBar(0);
    return;
  }

  int potentiometerValue = analogRead(POTENTIOMETER_PIN);
  byte litLedCount = potentiometerValue / 256 + 1;

  showBar(litLedCount);
}

void updateDeviceState() {
  bool buttonReading = digitalRead(BUTTON_PIN);

  if (buttonReading != lastButtonReading) {
    buttonChangedAt = millis();
  }

  if (millis() - buttonChangedAt >= DEBOUNCE_TIME &&
      buttonReading != stableButtonState) {
    stableButtonState = buttonReading;

    if (stableButtonState == LOW) {
      deviceOn = !deviceOn;
    }
  }

  lastButtonReading = buttonReading;
}

void showBar(byte litLedCount) {
  for (byte i = 0; i < LED_COUNT; i++) {
    if (i < litLedCount) {
      digitalWrite(LED_PINS[i], HIGH);
    } else {
      digitalWrite(LED_PINS[i], LOW);
    }
  }
}
```

## Programmi selgitus

Nupp on ühendatud digitaalviigu D7 ja GND vahele. Režiim `INPUT_PULLUP` lülitab sisse Arduino sisemise tõmbetakisti. Seetõttu on vabastatud nupu olek `HIGH` ja vajutatud nupu olek `LOW`.

Muutuja `DEBOUNCE_TIME` määrab 50 ms pikkuse aja, mille jooksul peab nupu näit püsima muutumatuna. See vähendab nupu kontaktide võnkumisest põhjustatud valevajutusi.

Kui seade on sisse lülitatud, jagab tehe `potentiometerValue / 256 + 1` analoogsisendi väärtused neljaks vahemikuks:

| Analoogsisendi väärtus | Põlevate LED-ide arv |
|---:|---:|
| 0–255 | 1 |
| 256–511 | 2 |
| 512–767 | 3 |
| 768–1023 | 4 |

## Katsetamine

Kontrolli vähemalt järgmisi olukordi:

1. Arduino käivitamisel on kõik LED-id kustunud.
2. Üks nupuvajutus lülitab näidu sisse.
3. Järgmine nupuvajutus lülitab näidu välja.
4. Nupu all hoidmine ei vaheta seadme olekut korduvalt.
5. Potentsiomeetri pööramisel süttib igas määratud vahemikus õige arv LED-e.

## Edasijõudnute variant

Kahendarvu kuvamiseks lisa programmi järgmine funktsioon:

```cpp
void showBinary(byte value) {
  for (byte i = 0; i < LED_COUNT; i++) {
    digitalWrite(LED_PINS[i], (value >> i) & 1);
  }
}
```

Põhiprogrammis asenda tulpnäidu read:

```cpp
byte litLedCount = potentiometerValue / 256 + 1;
showBar(litLedCount);
```

järgmiste ridadega:

```cpp
byte binaryValue = potentiometerValue / 64;
showBinary(binaryValue);
```

Tehe jagab analoogsisendi väärtused 0–1023 kuueteistkümneks võrdseks vahemikuks ja kuvab vastava väärtuse 0–15 neljal LED-il kahendkujul.
