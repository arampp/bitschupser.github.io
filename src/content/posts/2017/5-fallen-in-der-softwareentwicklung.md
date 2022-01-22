---
title: "5 Fallen in Der Softwareentwicklung"
date: 2017-09-20T08:00:00+01:00
draft: true
---



Mit einer sehr eindrucksvollen Keynote hat [Dr. Carola Lilienthal](https://www.wps.de/carola-lilienthal/) das derzeitige [Software Architecture Summit](https://software-architecture-summit.de/) in Berlin eröffnet. In ihrem Vortrag nannte sie einige Fallen, in die die Softwareentwicklung immer wieder gerät. Dieser Artikel beschreibt meine Top 5 Fallen sowie meine persönlichen Erfahrungen dazu.

## 1. Das Modell-Monopol

Die Entwicklung benutzt Modelle, die der Kunde bzw. der Anwender nicht versteht. Problem dabei ist, dass damit Feedback vom Kunden über das Modell praktisch unmöglich ist. Als Lösungsmöglichkeit wurde [Domainstorytelling](http://www.domainstorytelling.org/) genannt.

Obwohl ich Lösungen sehr oft zusammen mit Kunden und Anwendern entwickle, kann ich hier vermutlich noch viel lernen. Gerade das Thema
[Ubiquitous Language](https://martinfowler.com/bliki/UbiquitousLanguage.html) und [Domainstorytelling](http://www.domainstorytelling.org/) sind mir zwar bekannt, ich wende sie aber noch zu wenig in Kundenprojekten an. Meist werden Modelle relativ informell entwickelt – dieses Wissen z. B. in ein Glossar zu überführen würde wahrscheinlich nochmal ordentlich Klarheit schaffen.

## 2. Die Soll Falle

Man fokussiert sich viel zu schnell darauf, was der SOLL-Zustand sein soll, nachdem die neue Anwendung eingeführt ist. Dabei vergisst man, erst einmal genau zu analysieren, was der IST-Zustand ist.

Dies ist meiner Erfahrung nach eine Falle, in die sowohl Kunden, als auch Entwickler sehr oft geraten. Wenn ich an ein neues Projekt herangehe, versuche ich deshalb immer zuerst zu verstehen, wie der Kunde derzeit arbeitet und wo der wirkliche Bedarf liegt. In den seltensten Fällen möchte der Kunde eine Software, nein er möchte vielmehr eine Lösung für ein Problem (siehe auch [„Nobody wants to use software"](https://medium.freecodecamp.org/nobody-wants-to-use-software-a75643bee654)).

## 3. Zu starker Fokus auf Wiederverwendung

Man fokussiert sich beim Design von Komponenten darauf, dass diese Komponente auf jeden Fall wiederverwendet werden kann. Das führt zu generischen Lösungen, die für die eigentliche Problemstellung zu kompliziert sind. Besser ist es, einfache Lösungen, die konkret auf das eine Problem zugeschnitten sind, zu bauen.

Oft hat man im Unternehmen bestimmte Bibliotheken oder sogar ganze Plattformen, die oft benötigten Code bündeln. Problem dabei ist, dass diese meist erweitert/geändert werden müssen um ins aktuelle Projekt zu „passen“. Oft werden diese Bibliotheken von externen Teams betreut, die z. B. andere Releasezyklen haben als das eigene Team. Somit hat man sich durch den Fokus auf Wiederverwendung eine zusätzliche externe Abhängigkeit geschaffen.

## 4. Fokus auf einzelne Komponenten

Einzelne Komponenten werden Komplett „fertig“ gebaut, während das Gesamtsystem aus dem Blick gerät. Werden die Komponenten dann (relativ spät im Projekt) zusammengefügt ergeben sich oft Probleme durch unterschiedliche Schnittstellen oder inkompatible Konzepte.

Ich sehe hier sogar noch ein weiteres Problem: sehr spätes Anwenderfeedback. Fertigt man eine Komponente nach der anderen, so hat man sehr spät eine erste lauffähige Version und kann sich somit sehr spät Feedback einholen. Die Lösung sind hier Durchstiche oder sog. „Minimum Viable Products“. D. h. man beschränkt sich auf das absolute Minimum an Features die dem Anwender einen Mehrwert bringen, entwickelt die als Durchstich und liefert diese aus. Ich kann aus eigener Erfahrung bestätigen, dass Kunden begeistert sind wenn sie bereits nach 2 Wochen eine erste funktionierende Version mit minimalem Featureset bekommen.

## 5. Die Expertenfalle

Die Entwickler sehen sich als die wahren Domänenexperten und reden nicht mit dem Anwender. Dies führt dazu dass die Entwickler nicht wissen, wie der Anwender mit ihrer Software arbeitet und die Anwendung am Bedarf vorbei entwickelt wird.

Hier stimme ich voll zu. Anwender benutzen die Software oft ganz anders, als man es sich als Entwickler vorstellt. Deshalb ist es essentiell, von Anfang an Kontakt zum Anwender zu haben. In einem Beratungsprojekt lieferte ich einmal eine Version meiner Software aus und begleitete anschließend einen Anwender durch seinen Arbeitstag. Die meiste Zeit schaute ich ihm einfach über die Schulter um herauszufinden, wie unsere neue Lösung seine Arbeitsprozesse beeinflusst. Dabei stellte sich heraus, dass durch die suboptimale Sortierung der Felder eines Eingeabeformulars immer wieder Fehler passieren – solche Details stehen in keinem Anforderungsdokument.

## Fazit

In einem komplexen Projekt lauern Fallen an jeder Ecke. Wichtig ist dabei, regelmäßig zu reflektieren um diese Fallen zu erkennen. Ich denke nicht, dass es sich verhindern lässt in die eine oder andere (unbekannte) Falle zu tappen. Wichtig ist aber, diese Falle im Nachhinein zu erkennen und daraus zu lernen sowie seine Erfahrung zu teilen, damit andere nicht auch in diese Falle geraten.