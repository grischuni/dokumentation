## Wifi Sticks
Dies ist eine Kompatibilitätsliste von Wifi-Sticks die am WiFree getestet wurden. Prinzipiell sollten alle Sticks funktionieren deren Chipsatz von hostapd unterstützt wird.  Infos zu einigen Adaptern bezüglich (nicht-)Unterstützung finden sich z.B. auf [elinux.org](http://elinux.org/RPi_USB_Wi-Fi_Adapters).

Hier möchten wir mit euch und euren Sticks eine Liste der funktionierenden Sticks erstellen. Wichtig ist hierbei das die WLAN-Sticks die Signalstärke übertragen können da sonst das Fale-Safe nicht funktioniert.

### Kompatibilität Prüfen
Grundsätzlich empfiehlt es sich dringend vor dem Kauf des WLAN-Sticks nach dem konkret verbauten Chipsatz für genau diesen Stick zu suchen. Dieser konkrete Chipsatz wiederum muss durch einen Standard-Linuxtreiber unterstützt sein, welcher laut [Wireless Kernel Wiki](https://wireless.wiki.kernel.org/en/users/drivers) cfg80211 und AP unterstützt (Spalten 3 und 4 = Yes). cfg80211 ist relevant, damit das Kommando ''iw'' überhaupt funktioniert, AP damit der Raspberry Pi mit dem Stick einen Funknetz im Access Point Modus aufbauen kann.

Den konkreten Linuxkerneltreiber kann man auch über die sog. [Hardware ID](https://wikidevi.com/wiki/List_of_Wi-Fi_Device_IDs_in_Linux) des Sticks herausfinden.

#### Signalstärke ermitteln
Ob dein Stick die Signalstärke überträgt kannst du herausfinden indem du dich mit dem Raspberry Pi per SSH verbindest. Hierzu nutzt du am besten das passende Tool für dein Betriebssystem:

Windows: Putty  
Linux: ssh root@192.168.12.1  
Android: z.B. JuiceSSH  

Mit den Anmeldedaten kannst du dich im WiFree Image einloggen: 

```
User: root
Passwort: wifree
Host: 192.168.12.1
```

Mithilfe von ''iw dev wlan0 station dump'' eingeben und die Ausgabe HIER posten!

## Getestete Sticks
In der folgenden Liste findest du alle von der Community ausprobierten Sticks. Teilweise kompatible Sticks unterstützen meist keine Signalübertragung und sind daher ungeeignet für den Einsatz im WiFree. 

* [CSL](wifi-kompatibilitaet.md#csl)
* [Edimax](wifi-kompatibilitaet.md#edimax)
* [Logilink](wifi-kompatibilitaet.md#logilink)
* [TP-Link](wifi-kompatibilitaet.md#tp-link)
* [Raspberry Pi](wifi-kompatibilitaet.md#raspberry-pi)

### CSL
| Name        | Hardware      | Kompatibel                                                                        |
| --------    | --------      | --------                                                                          |
| CSL 300Mbit | Ralink RT5572 | [ja](http://open-diy-projects.com/topic/troubleshooting-wifree/page/4/#post-3379) |

### Edimax
| Name          | Hardware           | Kompatibel                                                                               |
| --------      | --------           | --------                                                                                 |
| EW-7811Un     | Realtek RTL8188CUS | [teilweise](http://open-diy-projects.com/topic/troubleshooting-wifree/page/3/#post-3339) |
| EW-7811UAC    | Realtek RTL8812AU  | [teilweise](http://open-diy-projects.com/topic/troubleshooting-wifree/page/3/#post-3333) |
| EW-7612UAn V2 | kA.                | [teilweise](http://open-diy-projects.com/topic/troubleshooting-wifree/page/3/#post-3365) |

### Logilink
| Name     | Hardware           | Kompatibel                                                                        |
| -------- | --------           | --------                                                                          |
| WL0084E  | kA.                | nein                                                                              |
| WL0084B  | Ralink RT5370      | ja                                                                                |
| WL0151   | Ralink RT5370      | [ja](http://open-diy-projects.com/topic/troubleshooting-wifree/page/4/#post-3377) |
| WL0151A  | Realtek RTL8188EUS | teilweise                                                                         |

### TP-Link
| Name           | Hardware          | Kompatibel                                                                        |
| --------       | --------          | --------                                                                          |
| TL-WN725N V2.1 | Realtek RTL8188EU | [ja](http://open-diy-projects.com/topic/troubleshooting-wifree/page/3/#post-3354) |
| TL-WN821N V4.1 | Realtek RTL8192CU | ja                                                                                |

### Raspberry Pi
| Name                     | Hardware | Kompatibel                                                                               |
| --------                 | -------- | --------                                                                                 |
| Raspberry Pi WiFi dongle | BCM43143 | [teilweise](http://open-diy-projects.com/topic/troubleshooting-wifree/page/5/#post-3546) |

-----
**Legende:**  
ja = Stick wurde getestet und wird voll unterstützt.  
teilweise = Stick wird eingesetzt, jedoch scheinen Änderunge notwendig oder nicht alle Features (z.B. Signalstärkenanzeige) werden unterstützt.  
nein = Stick wird aktuell nicht unterstützt.  
kA. = keine Angabe

**Hinweis:** Für einige der hier genannten Sticks sind Anpassungen notwendig.
# Flightcontroller
Der WiFree Copter bietet dir eine freie Wahl an Flightcontroller. Einzig das MSP-Protocoll muss der Flightcontroller verstehen. Im folgenden findest du eine Liste von Flightcontroller die im WiFree Projekt eingesetzt werden oder verwendet werden können. 

* [Arduino](flightcontroller.md#arduino)
* [CC3D](flightcontroller.md#cc3d)
* [Flip32](flightcontroller.md#Flip32)
* [NAZ32](flightcontroller.md#naz32)

## Arduino
Es ist noch zu klären ob sich auch ein Arduino mit den passenden Erweiterungen zu einem brauchbaren Flightcontroller umfunktionieren lässt. 

### Recherche
* http://mydronelab.com/blog/arduino-quadcopter.html
* https://github.com/ArduPilot/ardupilot
* http://www.instructables.com/id/DIY-ARDUINO-FLIGHT-CONTROLLER/
* http://drohnenbau.de/ardupilot-mega/

## CC3D
Der CC3D ist ein gängiger Flightcontroller mit dem im WiFree Projekt gute erfahrungen gemacht wurden. Er bietet alle nötigen Funktionen um den Copter abheben zu lassen. Leider ist kein Barometer oder Compass mit an Bord und auch der Anschluss von GPS ist nicht auf allen Versionen möglich. 

## Flip32
## NAZ32
