# metacomposition-rule.github.io

Metacomposition ist eine fundamentale semantische Regel, die von John Backus in seinem wegweisenden Turing-Award-Vortrag von 1977 ("Can programming be liberated from the von Neumann style?") eingeführt wurde. Sie bildet das Herzstück von FFP (Formal Functional Programming), dem formalen System, das Backus als theoretische Erweiterung seiner reinen Programmiersprache FP konzipierte. [1] (https://github.com/kseo/fp), [2] (https://www.hinkali.com/Education/BackusTuringLecture1977.pdf), [3] (https://www.sciencedirect.com/science/article/pii/S1018363918306068)
Während FP auf einer festen Menge von Kombinationen (höheren Funktionen wie Komposition oder apply-to-all) basiert, erlaubt es die Metacomposition in FFP, neue funktionale Formen (Kombinatoren) dynamisch innerhalb des Systems selbst zu definieren. [1] (http://www.cs.unc.edu/techreports/87-014.pdf), [2] (https://www.sciencedirect.com/science/article/pii/S1018363918306068)

Die Funktionsweise

In FFP wird kein Unterschied zwischen Programmen und Daten gemacht; alles ist ein Objekt (z. B. atomare Werte oder Sequenzen). Ein Funktionsaufruf wird als Applikation der Form (Operator : Operand) dargestellt. [1] (https://worrydream.com/refs/Backus_1978_-_Can_Programming_Be_Liberated_from_the_von_Neumann_Style.pdf), [2] (http://www.cs.unc.edu/techreports/87-014.pdf)
Wenn der Operator selbst eine Sequenz ist – also eine zusammengesetzte Struktur – greift die Metacomposition-Regel: [1] (http://www.cs.unc.edu/techreports/87-014.pdf)
\(\langle x_{1},x_{2},\dots ,x_{n}\rangle :y\implies x_{1}:\langle \langle x_{1},x_{2},\dots ,x_{n}\rangle ,y\rangle \)

Die Kernmechanik im Detail

Wenn ein System versucht, eine Sequenz als Operator auf einen Operanden y anzuwenden, wird der Ausdruck wie folgt umgeschrieben: [1] (http://www.cs.unc.edu/techreports/87-014.pdf)
1. Das erste Element der Sequenz (x₁, üblicherweise ein Bezeichner oder eine primitive Funktion) wird als der neue Operator herangezogen.
2. Dieses x₁ wird auf ein Paar (eine zweielementige Sequenz) angewendet.
3. Dieses Paar besteht aus der gesamten ursprünglichen Operator-Sequenz selbst und dem ursprünglichen Operanden y. [1] (http://www.cs.unc.edu/techreports/87-014.pdf)

Warum das wichtig ist

• Erweiterbarkeit ohne Metasprache: Herkömmliche funktionale Sprachen benötigen oft eine Definitionsebene außerhalb des normalen Datenflusses, um neue Kontrollstrukturen oder Kombinatoren einzuführen. Metacomposition erlaubt es der Sprache, sich "von innen heraus" zu erweitern. [1] (http://www.cs.unc.edu/techreports/87-014.pdf)
• Mächtige Rekursionen: Durch die Metacomposition erhält die aufgerufene Funktion x₁ Zugriff auf die vollständige Definition ihrer eigenen Struktur. Dadurch lassen sich komplexe, rekursive Funktionen komplett ohne Variablen oder explizite Namensbindung (wie z. B. den Y-Kombinator in der Lambda-Kalkül) ausdrücken. [1] (https://softwarepreservation.computerhistory.org/FP/doc/Williams-Formal_Representations-LNCS107_1981.pdf), [2] (https://www.hinkali.com/Education/BackusTuringLecture1977.pdf), [3] (https://github.com/kseo/fp)
• Reflektion: Da Programme als einfache Sequenz-Objekte dargestellt werden, können sie sich zur Laufzeit selbst inspizieren, transformieren und interpretieren. [1] (https://worrydream.com/refs/Backus_1978_-_Can_Programming_Be_Liberated_from_the_von_Neumann_Style.pdf), [2] (http://www.cs.unc.edu/techreports/87-014.pdf)
Möchten Sie ein konkretes Beispiel sehen, wie Backus mithilfe der Metacomposition eine neue Kontrollstruktur (wie eine bedingte Verzweigung) in FFP formal hergeleitet hat, oder interessiert Sie die Abgrenzung zum Lambda-Kalkül?
