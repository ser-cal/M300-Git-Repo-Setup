[10]: https://github.com
[11]: https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh
[20]: https://git-scm.com/
[21]: https://git-scm.com/book/en/v2


# M300 Einführung GIT und Setup des M300 Repositorys

Ziel dieses Projektes (Tutorials) ist es, dass die Lernenden ins Thema GIT einsteigen können und beim Durcharbeiten gleichzeitig ein Repository mit einer Grundstruktur für das Modul 300 aufsetzen<br><br>

## Voraussetzungen:
- [Github](https://github.com/) Account
- Windows: [GitBash](https://git-scm.com/downloads) auf dem lokalen Host installiert
- Mac oder Linux: (Bash bereits vorhanden, sonst ebenfalls auf [GitBash](https://git-scm.com/downloads)) verfügbar
- Editor: z.B: [Visual Studio Code](https://code.visualstudio.com/) , [Atom](https://atom.io/) oder [Sublime Text](https://www.sublimetext.com/) etc...
<br><br>

Das folgende Dokument ist wie folgt strukturiert:

Im ersten Abschnitt **[Was ist GIT](#Was-ist-GIT)** wird grundsätzlich erklärt was GIT genau ist und welche Vorteile sich durch die Anwendung von GIT ergeben.

Im zweiten Abschnitt **[Git lokal einrichten und ein erstes Repository initialisieren](#Git-lokal-einrichten-und-ein-erstes-Repository-initialisieren)** werden die nötigen Schritte erläutert, welche zum Starten mit einem lokalen- und remote Git Repository nötig sind. 

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
Sobald die Daten zusätzlich für andere (Contributors) freigegeben werden, spricht man nicht mehr von **VCS**, sondern von  **DVCS** (**D**istributed **V**ersion **C**ontrol **S**ystem)
<br><br>

Hier nochmals die wichtigsten Merkmale eines **Distributed Version Control Systems**

![Was ist Git](images/01_Was-ist-GIT.jpg) <br><br>

---
<br>

## Git lokal einrichten und ein erstes Repository initialisieren ##
In diesem Kapitel werden wir zuerst GIT auf dem lokalen Rechner konfigurieren und anschliessend das Grundgerüst für das M300-Repository einrichten
<br>

### Git Standard-kommandos (good to know)

#### Git-Version
> `$ git --version ` _aktuelle Version_ <br>
#### Git-Hilfe

> `$ man git ` _Manual Pages_ <br>
> `$ git help  ` _Allgemeine Hilfe / Quick Reference Porcelaine Commands_ <br>
> `$ git help config  ` _Spezifische Hilfe (in diesem Fall zu "Configuration"_<br>

<br>

### Git Konfigurations Dateien

Git hat folgende Konfigurationsdateien. Jede Ebene überschreibt die obige

* **System** ( --system )
    * `/etc/gitconfig` oder `c:\Program Files\Git\etc`
* **Personal** ( --global )
    * `~/.gitconfig` oder `%HOMEPATH%/.gitconfig`
* **Repository** ( --local )
    * `o	[GIT-REPOSITORY/]/.git/config`

<br>

Separate Auflistung (System, Global und Local)

> `$ git config --list --system  ` _zeigt die aktuelle System-Konfiguration_<br>
> `$ git config --list --global  ` _zeigt die globalen Settings_ <br>
> `$ git config --list --local  ` _zeigt die lokalen Settings_ <br>

<br>

Beispiel für eine **globale** Konfiguration (in unserem Fall eine geeignetes Setup):

*Username* und *E-Mail* in der **globalen** Konfiguration speichern. Diese werden später bei den Commit Informationen zugefügt. 

```
$ git config --global user.name "Marco Brunner"
$ git config --global user.email marco.brunner@tbz.ch
```
<br>

Überprüfen der Settings

> `$ git config --list  ` _Ohne weitere Paramenter, zeigt die aktuelle Konfiguration_<br>
> `$ git config --list --show-origin  ` _zeigt die Location der Git Config files_ <br>


 <br>

---
<br>

### Starten mit einem neuen Git-Repository 

Jetzt geht es darum, ein *vorhandenes, lokales Verzeichnis* unter **Git Versionskontrolle** zu bringen und dieses anschliessend in das *remote Repository*  von [Github][10] zu pushen.

### Remote Git Repository erstellen

Vorbereitend erstellen wir auf [Github][10], ein neues, leeres Repository.

> Ein hinterlegter **SSH-PublicKey** des lokalen Benutzers/Rechner ist Voraussetzung <br>
> Das Erstellen und Einrichten ist in den [GitHub Docs][11] ausführlich dokumentiert 



Nachdem wir ein neues Repository in [Gitlab][10] oder [Github][11] erstellt haben, erhalten wir Informationen (passend zum eben erstellten Repository)  über den Import von existierenden lokalen Folder Strukturen in das eben erstellte remote Repsitory. Die Anweisungen sind fast identisch.
<br><br>

---

<br><br><br>
## Arbeiten mit GIT ##
