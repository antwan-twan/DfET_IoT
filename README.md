# Stap 1 - Begin

Zorg er allereerst voor dat je de Arduino IDE hebt geïntstalleerd. De versie die ik gebruik is **v2.0.0**.
Ik maak gebruik van de NodeMCU 1.0 ESP-12E Module. 

Zorg er ook voor dat je de juiste poort selecteert, anders kun je geen bestanden uploaden naar je board. 

# Stap 2 - Library installeren

Open de Library Manager van Arduino IDE.  
<img src="images\libmanager.png" width="200px" alt="de library manager van Arduino IDE">

Zoek in de zoekbalk naar "Adafruit IO Arduino" en installeer "Adafruit IO Arduino".  
<img src="images\libmanager2.png" width="200px" alt="de library manager van Arduino IDE met zoekbalk">

**LET OP** De library die je als eerste ziet, is NIET de goede. Adafruit AW9523 is de eerste die je ziet, maar zeker niet de goede.

Klik daarna op 'install all'.  
<img src="images\install_all.png" width="375px" alt="install all">

De installatie is gelukt als je deze melding te zien krijgt.  
<img src="images\install_succes.png" width="375px" alt="install success">

# Stap 3 - Adafruit IO
Maak op https://io.adafruit.com/ een **gratis** account aan. 

Kopieer vanuit je account je username en je key.  

**LET OP!** 
Je vind je username en key **NIET** op de pagina waar je na het maken van je account op beland, maar ga terug naar io.adafruit.com en klik op de gele sleuter rechtsbovenin je scherm. 

# Stap 4 - Color Picker maken
Maak op https://io.adafruit.com/ een nieuw dashboard aan en ga vervolgens naar dit dashboard. 

In het dropdown-menu met het tandwiel druk je op "New Block" en kies de Color Picker.  
Tijdens het proces moet je een nieuwe feed aanmaken. Noem deze Color.

<!--- anthonie_meijers
aio_lpnk317H10vV84ZWvOJk2j1Z19t0 -->

# Stap 5 - Code
Volg de onderstaande stappen:
1. In Arduino: File > Examples > Adafruit IO Arduino > Adafruitio_14_neopixel
2. In tab ‘config.h’: plak je Adafruit IO username en Key in
3. In tab ‘config.h’: voer het wifi netwerk en wachtwoord in 
    1. (De NodeMCU werkt niet op 5Ghz WiFi)
    2. Gebruik liefst de hotspot van je telefoon, dit gebruikt < 0.1 Mb data per uur, dus niet bang zijn
    2. **LET OP!!** Bij een iPhone zet je de functie 'maximise compatability' aan, anders werkt de verbinding niet. Zelf ervaren :)
4. in de Tab adafruit_14_Neopixel.ino
    1. Pas: #define PIXEL_PIN 5 aan naar #define PIXEL_PIN D5

Extra stap, maar wel nodig, want anders werkt het niet:

5. Verander PIXEL_COUNT van 24 naar het juiste aantal LED's wat je hebt. In mijn geval moest ik het veranderen naar 10.
<img src="images\pixelcount.png" width="375px" alt="code with variables">

# Stap 6 - Kleuren aanpassen
Upload de code naar je board (je mag van te voren op 'verify' drukken, maar is niet perse nodig) en activeer daarna de serial monitor.
Zet je serial monitor op 115200 baud (whatever that means), zodat je de berichten goed door krijgt. 
<img src="images\baud.png" width="200px" alt="how to change serial monitor baud">

Normaal gesproken staat je serial monitor op 9600 baud, maar in dit geval wordt er dan niets uitgelezen. 
Hieronder staat wat je ziet als je wel met 9600 baud werkt.
<img src="images\baud_error.png" width="200px" alt="baud error">

Je kan nu in je dashboard wat je hebt aangemaakt, je kleuren kiezen die je de LEDstrip wil laten zijn. Vergeet vooral niet op save te drukken, alleen dan verandert de kleur. 

