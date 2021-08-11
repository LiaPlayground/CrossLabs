<!--
author:   André Dietrich

email:    Andre.Dietrich@informatik.tu-freiberg.de

version:  0.0.1

language: de

date:     12.08. 2021

narrator: Deutsch Female

comment:  Präsentation zum inoffizellen und internem CrossLabs-Meeting in Freiberg.

logo:     https://technofaq.org/wp-content/uploads/2020/05/kick-off-meetings.png

icon:     pic/Logo_TU_Bergakademie_Freiberg.svg

import:   https://github.com/LiaTemplates/AVR8js/blob/main/README.md

-->

# 01 KickOff-Light



## Vergangenheit (Hardware)

                         {{0-1}}
!?[YouTube: eLab in Magdeburg](https://www.youtube.com/watch?v=bICfKRyKTwE)


                          {{1}}
*******************************************************************************

**Probleme & Lessons Learned:**

* Login & Rechtemanagement
* Persistente Datenhaltung
* Wartung der Infrastruktur
* __Konsistentes didaktisches Konzept__
* Geringfügig Abstraktionsfähig

*******************************************************************************

## Gegenwart (Simulation & Emulation)

**[LiaScript](https://LiaScript.github.io)**

* Auf Markdown basierende Markup-Sprache für freie Lehrinhalte
* JAMStack (https://en.wikipedia.org/wiki/Jamstack)
* Dezentrale Erstellung von Lehrinhalten
* Clientseitig, _"kein Backend"_
* Beliebig erweiterbar
* Offline-First -> [PWA](https://en.wikipedia.org/wiki/Progressive_web_application)

### Schaltungen

??[Simulation: Noninverting Amplifier](https://www.falstad.com/circuit/circuitjs.html?startCircuit=amp-noninvert.txt)

### Programmierung

<div id="example">
<wokwi-led color="red"   pin="13" label="13"></wokwi-led>
<wokwi-led color="green" pin="12" label="12"></wokwi-led>
<wokwi-led color="blue"  pin="11" label="11"></wokwi-led>
<wokwi-led color="blue"  pin="10" label="10"></wokwi-led>
<span id="simulation-time"></span>
</div>

``` cpp
byte leds[] = {13, 12, 11, 10};
void setup() {
  Serial.begin(115200);
  for (byte i = 0; i < sizeof(leds); i++) {
    pinMode(leds[i], OUTPUT);
  }
}

int i = 0;
void loop() {
  Serial.print("LED: ");
  Serial.println(i);
  digitalWrite(leds[i], HIGH);
  delay(250);
  digitalWrite(leds[i], LOW);
  i = (i + 1) % sizeof(leds);
}
```
@AVR8js.sketch(example)

### Sonstiges

    {{0}}
??[ear model](https://sketchfab.com/3d-models/ear-anatomy-468e2039bde34a3fabb9e90bff9cd56b)

    {{1}}
<iframe src="https://phet.colorado.edu/sims/html/gas-properties/latest/gas-properties_en.html" width="100%" height="600" scrolling="no" allowfullscreen></iframe>

## Zukunft (...)

__RemoteLabs as a service__

* RTCP -> [RealTime Control Protocol](https://en.wikipedia.org/wiki/RTP_Control_Protocol)
* Abstraktion von Login & Nutzer und Rechtemanagement
* [Responsive Design](https://en.wikipedia.org/wiki/Responsive_web_design)
* Integration ala [oEmbed](https://en.wikipedia.org/wiki/OEmbed)
