---
name: Vorbereitung
index: 0
lang: de
---

# Vorbereitung

Nun werden wir mit der Implementierung des Spiels beginnen. Dazu laden wir uns zuerst die Bibliothek [**Scratch for Java**](https://scratch4j.openpatch.org) herunter. Diese wird uns die Spieleentwicklung vereinfachen.

::download[Scratch for Java]{src="https://github.com/openpatch/scratch-for-java/releases/tag/v3.7.0"}

Anschließend laden wir uns die Grafiken für unser Spiel herunter.

::download[Grafiken]{src="https://www.kenney.nl/assets/jumper-pack#inline-download"}

## Einrichtung BlueJ

Wir öffnen BlueJ und legen ein neues Projekt an.

![](/assets/vorbereitung/neues-projekt.png)

Dieses Projekt nennen wir **Bunny Hop**.

Jetzt müssen wir die Bibliothek **Scratch for Java** registrieren. Das machen wir durch die folgenden Schritte:

1. Den Projekt-Ordner von **Bunny Hop** im Dateimanager öffnen.
2. Einen Ordner **+libs** im Hauptverzeichnis des Projekt-Ordners anlegen.
3. Die Jar-Datei von Scratch for Java in den Ordner **+libs** verschieben.
4. BlueJ neustarten. Erst danach wir die neue Bibliothek registriert.

Als nächstes wollen wir die Grafiken verfügbar machen. Dazu führen wir folgende Schritte durch:

1. Den Projekt-Ordner von **Bunny Hop** im Dateimanager öffnen.
2. Einen Ordner Grafiken anlegen.
3. Die Zip-Datei jumperpack_kenny.zip entpacken.
4. Den Inhalt des Ordners PNG in den Ordner Grafiken verschieben.

Deine Ordnerstruktur sollte jetzt wie folgt aussehen:

```bash
├── Grafiken
│   ├── Background
│   ├── Enemies
│   ├── Environment
│   ├── HUD
│   ├── Items
│   ├── Particles
│   └── Players
├── +libs
│   └── scratch-standalone-windows-amd64.jar
├── package.bluej
└── README.TXT
```

## Das erste Programm

Um zu überprüfen, ob alles funktioniert hat, werden wir jetzt ein kleines erstes Programm erstellen.

Erstelle dazu eine Klasse **BunnyHop** und eine Klasse **Spieler**. Anschließend kopiere die folgenden Quelltexte in die Klassen.

::::tabs{id="845876"}

:::tab{title="BunnyHopp" id="605171"}

```java
import org.openpatch.scratch.*;

public class BunnyHop extends Stage
{
    Spieler bugs;

    public BunnyHop()
    {
       super(800, 400);
       bugs = new Spieler();
       this.add(bugs);
    }
}

```

:::

:::tab{title="Spieler" id="605170"}

```java
import org.openpatch.scratch.*;

public class Spieler extends Sprite
{

    public Spieler()
    {
      this.addCostume("stehen", "Grafiken/Players/bunny1_stand.png");
    }

}

```

:::

::::

Um Bugs auf der Bühne zu sehen, musst du das Programm nur noch ausführen. Erzeuge dazu ein neues Objekt von der Klasse **BunnyHop**.

![](/assets/vorbereitung/ausführen.png)

Anschließend solltest du die folgende Ausgabe sehen.

![](/assets/vorbereitung/bunny.png)

:::alert{warn}
Es kann immer nur ein Objekt der Klasse Stage erzeugt werden. Sei also sicher, dass du das Fenster immer schließt, sonst kommt es zu einer Fehlermeldung.

![](/assets/vorbereitung/nur-eine-stage-fehler.png)
:::
