---
title: "Resümee zur Clean Code Days Konferenz"
date: 2017-06-23T19:02:07+01:00
draft: false
aliases: 
  - /2017/06/23/resuemee-zur-clean-code-days-konferenz/
tags:
  - konferenz
  - clean-code
  - community
---


In der vergangenen Woche war ich zum ersten mal auf den [Clean Code Days](http://www.cleancode-days.de/) in München.

## Workshoptag

Los ging es am ersten Tag mit einem Workshop zum Thema „Testgetriebene Analyse von Legacy Code“, den ich zusammen mit einem Kollegen hielt. Die Teilnehmer bekamen dabei eine C# Code Basis mit diversen Problemen „vorgesetzt“. Gemeinsam analysierten wir den Code mit Hilfe von Experimenten, die wir als Unit Tests implementierten. Dabei waren natürlich diverse Hürden z. B. durch Abhängigkeiten zu überwinden. Hier zeigten wir den Teilnehmern, wie man sich im sogenannten „Brown Field“ nach und nach ein Sicherheitsnetz schafft, das komplexere Refactorings möglich macht. In einer abschließenden Diskussionsrunde tauschten wir Erfahrungen Tipps & Tricks aus.

Das Feedback der Teilnehmer war durchweg positiv und auch uns machte der Workshop viel Spaß.

## Tag 1: Clean Code mit dreihändigen Affen

In seiner Keynote „Von Clean Code zu Clean Software“ stellte Dr. Elmar Jürgens klar, dass sich Qualität nicht nur auf Code beschränkt. Insbesondere die Organisation und Umgebung in der Entwickler arbeiten hat massive Auswirkungen auf die Qualität einer Software. Interessanterweise lassen sich diese Auswirkungen im Code finden, was Jürgens eindrucksvoll an realen Beispielen demonstrierte. Netterweise stehen die durchaus sehenswerten [Slides](https://www.cqse.eu/en/blog/vortrag-clean-software-keynote-clean-code-days-2017/) online zu Verfügung.

Remy Loy zeigte anschließend, wie man Clean Code im Bereich funktionale Programmierung erweitern kann. In seinem Vortrag gab er viele Tipps, wie sich die Code Qualität mit funktionalen Erweiterungen verbessern lässt.

Nach einem leckeren Mittagessen kam mein persönlicher Höhepunkt des Tages. Lutz Marquardt und Frank Blendinger präsentierten Clean Code Konzepte in einer ganz neuen Form – als Rollenspiel. Das Publikum schlüpfte dabei in die Rolle eines Programmierers und konnte an entscheidenden Stellen durch Handzeichen den Verlauf der Geschichte beeinflussen. Hierbei begegnete uns ein Ork als unser Chef, ein dreihändiger Affe der sich für Testautomatisierung aussprach sowie ein Staubsauger, der durch einen Bug plötzlich Menschen tötet („Code Reviews können Leben retten!“). Glücklicherweise erschien uns ein Geist namens „Bob“, der uns einen alten Folianten namens „Clean Code“ schenkte. Auch wenn ich dabei wenig neues gelernt habe war dieses Event purer Spaß und macht Lust auf mehr.

In seinem Vortrag „Clean Code for the Front End“ zeigte Mathias Arens, wie moderne Web Frontend Entwicklung funktioniert. Hier konnte ich am Meisten mitnehmen, da ich nicht primär Frontend Entwicklung betreibe, trotzdem aber immer mal wieder damit konfrontiert werde. Mathias zeigte hier viel Erfahrungswissen sowie verbreitete Patterns. Insbesondere die CSS Namenskonvention [Block Element Modifier (BEM)](http://getbem.com/) erscheint simpel, ist aber sehr mächtig – diese Methodik kommt auf jeden Fall in meinen Werkzeugkasten.

Mike Kaufmann zeigte wie man mit [Sonar Cube](https://www.sonarqube.org/) Kennzahlen zur [technischen Schuld](https://de.wikipedia.org/wiki/Technische_Schulden) berechnen kann. Trotz der durchaus beeindruckenden Präsentation bezweifle ich allerdings, dass man so ein komplexes Thema in ein paar wenigen
Zahlen erfassen kann. Seiner Aussage „Clean Code ist Team Sport“ stimme ich allerdings voll zu.

In einer sehr unterhaltsamen Live Coding Session zeigte uns Roland Golla, wie man mit dem PHP Framework [Codeception](http://codeception.com/) komplette End-to-End Tests für Webanwendungen implementiert.

Beim anschließenden Feierabendbier erzählte mir Roland über seine Initiative [Never Code Alone](https://nevercodealone.de) in der er soziale Einrichtungen mit Software-Entwicklungsprojekten unterstützt und gleichzeitig den Austausch in der Entwicklercommunity fördert.

## Tag 2: Clean Code ist mehr als nur Code

Frisch ausgeruht legte ich an diesem Vormittag den Fokus auf Themen, die über das codieren hinausgehen.

Stark war hier die Aussage von Steven Kolbenschlag, dass die Einführung von agilen Vorgehensweisen oft scheitert, wenn die Code Qualität nicht stimmt. Er schloss seinen Vortrag „Wie agil ist ihr Code?“ mit der Aussage, dass die Vorteile des agilen Vorgehens ohne Clean Code Development nicht voll ausgeschöpft werden können.

Francois Lorioux teilte Erfahrungen aus seinem 30-jährigen Berufsleben und zeigte worauf es ankommt, wenn Software über viele Jahr(zehnte) wartbar und erweiterbar sein soll. Neben vielen Tipps und Anekdoten gefiel mir hier der Satz „If you want to kill software, use inheritance“ besonders gut.

Im Vortrag „Erfolgsfaktor Mensch“ zeigten Claudia Simsek-Graf und Christoph Meyer, dass Software letztlich von Menschen gemacht wird und dass Projekte meist an menschlichen Konflikten scheitern statt an technischen Problemen. Die sehr interaktive Session bot viel Raum zum Erfahrungsaustausch und Diskussion. Gerade die Aussage „Clean Code funktioniert nicht im Alleingang“ kann ich aus eigener Erfahrung voll unterschreiben.

Da es ganz ohne Code doch nicht geht hörte ich mir zum Abschluss Gregor Trefs Vortrag „Combinator als funktionales Entwurfsmuster in Java 8“ an. Positiv überraschte mich, dass der Vortrag von Anfang an sehr praxisorientiert war und die oft etwas trockene Theorie der funktionalen Programmierung weggelassen wurde. Am Beispiel Eingabevalidierung zeigte Gregor, wie man mit Hilfe von primitiven Funktionen und Kombinatoren immer komplexere Regeln realisieren kann ohne die Lesbarkeit zu verschlechtern. Neben der Präsentation hat er die Methode auch in einem [Blogartikel](https://gtrefs.github.io/code/combinator-pattern/) beschrieben.

## Fazit: Gerne wieder

Insgesamt ziehe ich von den Clean Code Days ein sehr positives Fazit. Insbesondere die familiäre Atmosphäre war super – da geht es bei größeren Konferenzen oftmals anonymer zu. Ich hatte viele spannende Gespräche während und lernte viele neue Leute kennen.

Die Räumlichkeiten sowie die Organisation waren toll. Das Essen schmeckte allerdings mal wieder zu gut – was der schlanken Linie nicht gerade förderlich ist ;-).

Ein kleiner Wermutstropfen war lediglich, dass sich relativ viele Vorträge eher am Einsteigerniveau und der bekannten Literatur orientierten. Hier wäre es schön, in Zukunft mehr fortgeschrittene Themen sowie Spezialthemen (z. B. Anwenderberichte über Refactoring in regulierten Bereichen wie Medizintechnik) zu sehen.

Insgesamt waren es drei super Tage in München, die Lust darauf machten sich noch mehr mit dem Thema auseinanderzusetzen. Ich freue mich schon auf eine Wiederholung im nächsten Jahr.
