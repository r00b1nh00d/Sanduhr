# Sanduhr
## ~avatar avatar @unplugged
![Sanduhr](https://github.com/r00b1nh00d/Sanduhr/blob/master/Sanduhr.gif?raw=true) <br>
Lerne in diesem Tutorial einen Countdown oder eine Sanduhr mit dem Calliope zu programmieren.


## ~ @unplugged
Zum Plätzchenbacken ist es wichtig, die Zeit im Auge zu behalten. Damit hier nichts schief geht, kannst du den Calliope nutzen und ihn so programmieren, dass er einen Signalton abgibt, sobald die Zeit um ist. <br>
![Kekse](https://github.com/r00b1nh00d/Sanduhr/blob/master/Kekse4.jpg?raw=true)

## Schritt 1: Die LED Matrix ansteuern
Beginnen wir mit dem Block ``||input: wenn Knopf A gedrückt||``, welcher den Countdown starten soll. Bevor der Countdown wirklich startet, ist es gut, erstmal den  ``||basic: Bildschirminhalt zu löschen||``. Diesen Block gibt es auch unter ``||basic: Grundlagen||``.
Als nächstes nehmen wir aus dem Bereich ``||loops:Schleifen||`` den Block ``||loops: für Index von 0 bis 4 ||``. Dieser kommt unter den Block ``|basic: Bildschirminhalt löschen|``. In die For-Schleife können wir aus dem Bereich ``||led: LED||`` den Block ``||led: zeichne x 0 y 0||`` schieben.
Schiebe jetzt noch die Variable ``||variables:Index||`` an die Stelle für den x-Wert. <br>
**Hinweis:** Eine ``||basic:Pause||`` am Ende der Schleife lässt diese langsamer durchlaufen, damit unser Auge dem folgen kann.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.clearScreen()
    for (let Index = 0; Index <= 4; Index++) {
        
            led.plot(Index, 0)
            basic.pause(1000)
        
    }
  
})
```

## Schritt 2: Die LED Matrix auch in y-Richtung ansteuern
Versuche nun in die bisherige Schleife eine weitere Schleife zu schieben. Nehme ab jetzt die ``||variables:Variablen||`` ``||variables:x-Index||`` und ``||variables:y-Index||``. 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.clearScreen()
    for (let xIndex = 0; xIndex <= 4; xIndex++) {
        for (let yIndex = 0; yIndex <= 4; yIndex++) {
            led.plot(xIndex, yIndex)
            basic.pause(1000)
        }
    }

})
```

## Schritt 3: Einen Signalton zum Schluss
Zum Abschluss kannst du noch aus dem Bereich ``||music:Musik||`` einen Ton abspielen lassen. Wenn du diesen Block unter die Schleifen schiebst, sollte der Ton abgespielt werden, wenn der Countdown komplett abgelaufen ist.

```blocks

input.onButtonPressed(Button.A, function () {
    basic.clearScreen()
    for (let xIndex = 0; xIndex <= 4; xIndex++) {
        for (let yIndex = 0; yIndex <= 4; yIndex++) {
            led.plot(xIndex, yIndex)
            basic.pause(1000)
        }
    }
    music.playTone(262, music.beat(BeatFraction.Whole))
})

```

## ~ @unplugged 

Es ist geschafft, dein Countdown sollte nun jede Sekunde eine weitere LED auf der Anzeige am Calliope anschalten und am Ende einen Ton abspielen, der signalisiert, dass der Countdown abgelaufen ist.

## ~ @unplugged 
Damit viel Spaß beim Backen und dass dir keine Plätzchen mehr im Ofen verbrennen.

