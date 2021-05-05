[10]: https://github.com
[20]: https://git-scm.com/
[21]: https://git-scm.com/book/en/v2


# M300 Einführung GIT und Setup des M300 Repositorys

Ziel dieses Projektes (Tutorials) ist es, dass die Lernenden ins Thema GIT einsteigen können und beim Durcharbeiten gleichzeitig ein Repository mit einer Grundstruktur für das Modul 300 aufsetzen<br><br>

Das folgende Dokument ist wie folgt strukturiert:

Im ersten Abschnitt **[Was ist GIT](#Was-ist-GIT)** wird grundsätzlich erklärt was GIT genau ist und welche Vorteile sich durch die Anwendung von GIT ergeben.

Im zweiten Abschnitt **[Git Repository einrichten](#git-repository-einrichten)** werden die nötigen Schritte erläutert, welche zum Starten mit einem lokalen- und remote Git Repository nötig sind. 

Im dritten Abschnitt **[Arbeiten mit Git](#arbeiten-mit-git)** geht es darum, die wichtigsten *Handgriffe* im Umgang mit Git zu lernen.

Git ist sehr umfangreich. Für den täglichen Gebrauch reichen aber wenige Kommandos und ein **generelles Verständnis über die Funktionsweise von Git**. Diese sind im **[Pro Git book][21]** (Kapitel 1 und 2) sehr gut beschrieben.  Alle in diesem Dokument verwendeten Kommandos finden sie ebefalls in diesen beiden Kapiteln wieder <br><br>

---
<br>

## Was ist GIT ##

GIT ist ein sogenanntes **Versionskontrollsystem** (VCS) und wurde Anfang 2005 von Linus Torvalds, dem Initiator des Linux-Kernels, entwickelt. Es erstaunt deshalb nicht, dass GIT konzeptionell ähnlich aufgebaut ist wie ein Linux-Filesystem. <br>
Torvalds wünschte sich ein verteiltes System, welches folgenden Anforderungen erfüllt:

- Unterstützung verteilter Arbeitsabläufe (Mehrere können an einem Projekt arbeiten)
- Hohe Sicherheit gegen sowohl unbeabsichtigte als auch böswillige Verfälschung
- Effizienz (Einfach und zweckmässige Handhabung)

![Was ist Git](images/04_DVCS.jpg)

Ein Versionskontrollsystem  wie **GIT** ist grundsätzlich ein Softwaretool, mit dessen Hilfe Entwickler Quellcode kooperativ verwalten können. Die Versionskontrollsoftware verfolgt jede Änderung am Code und speichert sie in einer speziell hierfür angelegten Datenbank (im Verzeichnis **.git**). Unterläuft einem Entwickler ein Fehler, kann er zu jeder Zeit einen (oder mehrere) Schritt(e) zurück machen, seinen Code mit früheren Codeversionen abgleichen und Korrekturen implementieren.
<br>

### **VCS** vs **DVCS** ###
- **VCS** (Version Control System) <br>
Solange die Daten nur lokal mit GIT getracked werden, spricht man von **VCS**

- **DVCS** (Distributed Version Control System)<br>
Sobald die Daten allerdings für andere (Contributors) freigegeben werden, spricht man nicht mehr von **VCS**, sondern von  **DVCS** (**D**istributed **V**ersion **C**ontrol **S**ystem)
<br><br>
Hier nochmals die wichtigsten Merkmale eines **Distributed Version Control Systems**

![Was ist Git](images/01_Was-ist-GIT.jpg)

<img style="float: none;width:512px;height:223px;" src="images/Git_StorageDataFlow1.png"> 

<br><br><br>
## Git Repository einrichten ##



<br><br><br>
## Arbeiten mit GIT ##
