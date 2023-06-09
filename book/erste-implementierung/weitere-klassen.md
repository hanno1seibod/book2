---
name: Weitere Klassen
lang: de
index: 1
---

# Weitere Klassen

Unser Spiel besteht im Moment aus zwei Klassen. Im Laufe dieser Seite wollen wir weitere Klassen implementieren und die folgende Ausgabe erreichen.

![](/assets/weitere-klassen/ausgabe.png)

## Aufgaben

### Klassen implementieren

Setze das folgende :t[UML-Klassendiagramm]{#klassendiagramm} im BlueJ-Projekt um. Die Klassen **Sprite** und **Stage** stammen aus der **Scratch for Java** Bibliothek. Deshalb brauchst du sie **nicht** selbst anzulegen. Die Klassen **Sprite** und **Stage** haben eine Vielzahl von Methoden, die den Blöcken in Scratch ähneln. Wir werden diese nach und nach kennenlernen. Im Klassendiagramm werden nur im Moment relevante dargestellt, damit es übersichtlich bleibt.

```mermaid
classDiagram
    Stage <|-- BunnyHop
    Sprite <|-- Spieler
    Sprite <|-- Feind
    Sprite <|-- Plattform
    Feind <|-- StachelFeind

    class Stage {
        add(sprite: Sprite)
        remove(sprite: Sprite)
        setColor(r: int, g: int, b: int)
        addBackdrop(name: String, filePath: String)
        switchBackdrop(name: String)
        nextBackdrop()
    }

    class BunnyHop {
        Spieler bugs
        StachelFeind ingo
        Plattform p1
        Plattform p2
        Plattform p3
        Plattform p4
    }

    class Sprite {
        getX(): float
        getY(): float
        setX(x: float)
        setY(y: float)
        setPosition(x: float, y: float)
        changeX(x: float)
        changeY(y: float)
        setSize(percentage: float)
        move(steps: float)
        setDirection(direction: float)
        turnLeft(amount: float)
        turnRight(amount: float)
        addCostume(name: String, filePath: String)
        switchCostume(name: String)
        nextCostume()
    }

    class Spieler {
    }

    class Plattform {
        istKaputt: boolean
    }

    class Feind {
    }

    class StachelFeind {
    }
```

:::alert{info}
Wenn du dir nicht sicher bist wie man das Klassendiagramm in Java umsetzen kann, dann orientiere dich an der Klasse Spieler oder schaue hier: :t[Vererbung in Java]{#vererbung-java}
:::

### Ausgabe nachstellen

Da wir nun alle notwendigen Klassen zur Verfügung haben, können wir jetzt die Klasse **BunnyHop** so verändern, dass sie der obigen Ausgabe entspricht.

Modifiziere die Klasse **BunnyHop** so, dass sie der obigen Ausgabe entspricht.

Nutze die folgenden Objektdiagramme:

::excalidraw{src="/assets/weitere-klassen/object-diagram.excalidraw" aspectRatio="4/3" autoZoom=true center=true}



:::collapsible{title="Tipp: Position" id="tipp-1"}
Mit den Methoden [**setX**](https://scratch4j.openpatch.org/reference/sprite/motion/setX), [**setY**](https://scratch4j.openpatch.org/reference/sprite/motion/setY), [**setPosition**](https://scratch4j.openpatch.org/reference/sprite/motion/setPosition) kannst du die Position von Objekten der Klasse Sprite verändern.
:::

:::collapsible{title="Tipp: Koordinaten" id="tipp-2"}
Falls du Hilfe bzgl. der Koordinaten brauchst, kannst du im Konstruktor der **BunnyHop**-Klasse die Methode `this.setDebug(true)` aufrufen.
:::

### Lösung

::archive[Projekt Weitere Klassen.zip]{name="bugs-weitere-klassen"}
