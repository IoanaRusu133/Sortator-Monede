# Sistem Automat de Sortare a Monedelor 🪙

Proiect realizat pentru disciplina **Arhitectura Microprocesoarelor 2 (AMP2)** din cadrul facultății de **Electronică, Telecomunicații și Tehnologia Informației (ETTI), UPB**.

## 🎯 Obiectivul Proiectului
Implementarea unui sistem automatizat capabil să identifice și să sorteze monedele românești (5 bani, 10 bani și 50 bani) pe baza caracteristicilor fizice: **greutatea** și **diametrul**. Sistemul utilizează circuite logice combinaționale și secvențiale pentru a asigura detectarea și sortarea precisă.

## 📋 Structura Sistemului
Sistemul este alcătuit din următoarele componente hardware gestionate de microcontroler:
* **Microcontroler ATMega164P:** Elementul central care gestionează citirea senzorilor, analiza datelor și comanda clapetelor.
* **Senzor optic:** Utilizat pentru determinarea diametrului monedei.
* **Senzor de greutate:** Utilizat pentru măsurarea masei monedei pentru validare.
* **Afișaj cu 7 segmente:** Indică valoarea monedei detectate sau mesaje de eroare.
* **Mecanisme de execuție:** Patru clapete acționate electronic, buzzer pentru erori și LED-uri de stare (verde/roșu).

[Image of block diagram of an automated coin sorting system with ATmega164P]

## ⚙️ Parametri de Identificare
Sistemul validează monedele conform specificațiilor oficiale:

| Moneda | Greutate (g) | Diametru (mm) |
| :--- | :--- | :--- |
| **5 bani** | 2.81 | 18.2 |
| **10 bani** | 4.0 | 22.5 |
| **50 bani** | 6.1 | 23.74 |

## 🕹️ Mod de Funcționare (FSM)
Logica software este bazată pe un **Automat Finit de Stare (FSM)** cu următoarea succesiune:

1. **Starea 0 (Așteptare):** Sistemul este în repaus; LED-ul verde este aprins.
2. **Starea 1 (Măsurare):** Senzorii măsoară diametrul și greutatea monedei introduse.
3. **Starea 2 (Comparare):** Datele sunt analizate față de valorile standard.
4. **Starea 3 (Direcționare):** Se acționează clapeta corespunzătoare și se afișează valoarea. În caz de eroare, se activează LED-ul roșu și buzzer-ul.
5. **Starea 4 (Reset):** Sistemul revine la starea inițială.

[Image of state machine diagram for a coin sorting machine]

## 🛠️ Detalii Tehnice Software
* **Limbaj de programare:** C.
* **Mediu de dezvoltare:** CodeVision AVR v4.03.
* **Simulare:** AVR Studio v4.13.
* **Configurație Timer:** Timer
