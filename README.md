# Monitorizarea-calitatii-aerului

**Introducere**

 Lipsa aerului curat este o problema des intalnita, in special in orasele mari. Avand in vedere acest fapt am decis ca proiectul meu sa incerce sa faca oamenii constienti de acest lucru si fiecare sa-si ia masurile necesare pentru a rezolva aceasta problema.

 Am reusit sa creez un circuit care sa verifice calitatea aerului. La baza proiectului este o placa Arduino care, impreuna cu senzorul MQ-135, poate sa citeasca valorile calitatii aerului, iar aceste informatii sunt afisate pe un LCD. Daca valoarea trece peste limita normala, un led si un buzzer vor atentiona utilizatorul.

**Descriere generala**

 Un senzor MQ-135 va fi conectat la breadboard, unde va fi alimentat. Valoarea citita de senzor va fi convertita si afiasata pe un LCD folosind interfata arduino. Utilizatorul va citi valorile si va observa daca ceva nu este in regula. Cand valorile limita vor fi depasite, acesta va fi atentionat vizual de un led, iar auditiv de un buzzer. In permanenta valorile exacte vor fi afisate pe ecranul LCD.

 Atunci cand senzorul este alimentat, acesta incepe sa citeasca valorile aerului si afiseaza pe LCD mesajul “AQ Level Good”, daca valorile citite de senzor sunt maxim 400. Dar daca aceste valori sunt mai mari este afisat mesajul “AQ Level HIGH”, iar ledul si buzzerul sunt activate pentru a atentiona ca aerul nu este calitativ si trebuiesc luate masuri.

 Acest detector este util pentru ca poate sa ajute oamenii sa-si imbunatateasca calitatea vietii. Acestia incep sa fie mai productivi la treburile de zi cu zi, iar societatea se dezvolta.

**Schema bloc**
  
  ![DiagramaBloc](https://user-images.githubusercontent.com/33146527/200193250-d9f03a65-2463-426f-bb21-c3a871d39942.png)

**Hardware Design**

Lista de piese:

1. Placa de Dezvoltare Compatibila cu Arduino UNO R3 (ATmega328p + ATmega16u2
2. Modul cu Buzzer activ
3. Modul Senzor de Gaz MQ-135
4. Rezistor Variabil 10k WH148 (Potențiometru)
5. Rezistor 0.5W 220KΩ
6. LED Roșu de 3 mm cu Lentile Difuze
7. Placa test breadboard 400
8. LCD 1602 albastru
9. Bareta 40 x pini tata 2.54mm
10. Fire Colorate Tată-Tată (10p, 30 cm)
11. Fire Colorate Mamă-Tată (10p) 20 cm


**Schema Electrica:**

![SchemaH](https://user-images.githubusercontent.com/33146527/200194038-059b7ef3-83ef-40d5-83dc-d940129c2cb6.png)

  

**Software Design**

Programul de fata a fost implementat in IDE-ul Arduino.

Am utilizat bibliotecile:

- hd44780.h
- LiquidCrystal.h - biblioteca folosita pentru functiile LCD ului


Avem functiile:

        -- setup()

Vom conecta buzzerul si led ul ca outputuri pentru placuta Arduino, iar senzorul ca input pentru aceasta. Setam baud rate ul de start si resetam LCD ul.

        -- loop()

Se citesc outputurile de tip analog, se afiseaza mesajele corespunzatoare tipului nivelelor poluarii aerului. Se verifica daca nivelul acestuia depaseste limita stabilita in program ca fiind maxima dupa care aerului detectat este unul poluat si se afiseaza mesajele pe ecranul LCD-ului. De asemenea, ledul si buzzerul vor fi utilizate pentru a atentiona acest lucru.


**Rezultate Obtinute**

  In momentul in care conectam cablul placutei Arduino la calculator, iar aerul va fi la un nivel normal din punct de vedere al poluarii (pana in 400), atunci LCD ul va afisa mesajul corespunzator din imaginea de mai jos, urmat de valoarea masurata de catre senzor.

![lvl_good](https://user-images.githubusercontent.com/33146527/200194007-fd4872bc-3ecc-4d46-bc54-bb9e24561386.jpg)


  Vom aprinde gaz in prezenta senzorului de aer, iar aceasta va detecta un nivel ridicat, astfel ca va afisa mesajul din imagine urmat de valoarea aerului, Buzzer-ul va scoate sunete diferite, iar ledul se va aprinde.

![high](https://user-images.githubusercontent.com/33146527/200193989-5910946a-d9e1-425f-b62c-a09d217c06c1.jpg)


  Dupa aceea vom departa bricheta cu gaz si vom astepta cateva secunde pentru ca aerul sa fie din nou la un nivel normal. In acest moment senzorul va detecta aerul nepoluat si, in consecinta, se va afisa din nou mesajul corespunzator nivelului de aer normal, ledul se va opri, iar Buzzerul isi va reveni la starea initiala.

![0 hard](https://user-images.githubusercontent.com/33146527/200193972-e1871188-55d5-41ea-a418-29fb48aa886d.jpg)


**DEMO Proiect:**

    https://www.youtube.com/watch?v=lSXaa1Sl8ds&ab_channel=CristinaRosu
          
**OCW proiect**

    https://ocw.cs.pub.ro/courses/pm/prj2021/avaduva/monitorizareacalitatiiaerului
