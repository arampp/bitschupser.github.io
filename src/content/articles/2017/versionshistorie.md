---
title: "Tipps für eine aussagekräftige Versionshistorie"
date: 2017-02-23T19:22:56+01:00
draft: false
tags:
  - dokumentation
  - git
  - qualität
  - tool
---

Wenn ich (z. B. in einem neuen Projekt) auf einer bestehenden Code Basis aufbauen soll, wandert mein Blick meist sehr schnell in die Commit-Historie des Versionskontrollsystems. Ich möchte mir damit einen Überblick verschaffen wann welche Features eingebaut wurden, wer an der Code Basis gearbeitet hat und warum gewisse Änderungen vorgenommen wurden.

Leider findet man immer wieder Historien, die so oder so ähnlich aussehen:

```
bff324d fix bug
a2fd532 first try
765a88f next try
dd876b2 add feature
```

Mit solchen Commit Messages lässt sich wenig anfangen. Dieser Artikel gibt einige einfache Tipps, die helfen zu einer aussagekräftigen Historie, die einen echten Mehrwert liefert, zu kommen.

## Erwartungen an eine gute Historie

Eine gute Historie erzählt eine Geschichte. Nämlich die Geschichte, wie die Software entstanden ist. Sie gibt einen Überblick wann welche Features eingebaut und wann welche Bugs gefixt wurden. Hat man einen Fehler, so lässt sich mit einer guten Historie nachvollziehen, wann und unter welchen Umständen dieser Fehler entstanden. Dadurch kann man lernen, solche Fehler künftig zu vermeiden. Eine gute Historie enthält zudem Informationen warum gewisse Änderungen vorgenommen wurden. Hier kann man auch auf Tickets in Issue Trackern oder Anforderungen verweisen.

## Wie man zu einer aussagekräftigen Historie kommt

Die folgenden Beispiele basieren auf dem Versionskontrollsystem [git](https://git-scm.com/). Sie lassen sich aber auch auf andere Systeme übertragen.

### Verständliche Commit Messages

Eine verständliche [Commit Message](https://robots.thoughtbot.com/5-useful-tips-for-a-better-commit-message) beantwortet folgende Fragen:

- Warum ist die Änderung nötig?
- Was trägt diese Änderung zur zu implementierenden Anforderung aus?
- Welche Seiteneffekte hat diese Änderung?

Zudem sollte man gewisse [Formatierungsregeln](https://chris.beams.io/posts/git-commit/) einhalten. Die wichtigsten Regeln sind:

- Separiere die Überschrift vom Textkörper mit einer Leerzeile
- Limitiere die Überschrift auf 50 Zeichen
- Zeilenlänge des Textkörpers sollte nicht länger als 72 Zeichen sein

Diese Regeln sind im Git Umfeld etabliert und viele Tools bauen darauf auf. Hält man sich daran, kann jeder die Historie einwandfrei lesen und durchsuchen.

Hier ein Beispiel für eine aussagekräftige und dennoch kurze Commit-Message

```
tcp: tcp_probe: use spin_lock_bh()

tcp_rcv_established() can now run in process context.

We need to disable BH while acquiring tcp probe spinlock,
or risk a deadlock.

Fixes: 5413d1b ("net: do not block BH while processing socket backlog")
Signed-off-by: Eric Dumazet 
Reported-by: Ricardo Nabinger Sanchez 
Signed-off-by: David S. Miller 
```

Quelle: [Linux Kernel, Commit e70ac17](https://github.com/torvalds/linux/commit/e70ac171658679ecf6bea4bbd9e9325cd6079d2b)

### Atomare Commits

Es gibt Entwickler, die comitten erst wenn ein Feature komplett „fertig“ ist. Dadurch entstehen meist sehr große Commits. Diese Commits haben verschiedene Probleme:

- Sie sind schwer zu lesen, weil sie meist viele verschiedene Änderungen enthalten.
- Einzelne Änderungen können nicht einzeln referenziert werden (z. B. beim [Cherry Picking](https://git-scm.com/docs/git-cherry-pick))
- Da große Commits viele Änderungen enthalten, müssten auch die Commit Messages entsprechend lang sein. Meist wird aber darauf aus Bequemlichkeit verzichtet, hier alle Änderungen aufzuführen.

Ein atomarer Commit dagegen ist in sich abgeschlossen und liefert einen Mehrwert für die zu lösende Aufgabe. Wird ein Feature in mehreren atomaren Commits entwickelt so ist viel besser nachvollziehbar, wie ein Feature (oder auch ein Bug) entstanden ist. Code Reviews gestalten sich einfache und Techniken wie [Cherry Picking](https://git-scm.com/docs/git-cherry-pick) oder [Bisecting](https://git-scm.com/book/de/v1/Git-Tools-Mit-Hilfe-von-Git-debuggen#Das-Bisect-Werkzeug-%E2%80%93-Bin%C3%A4re-Suche) können sinnvoll angewendet werden.

### Single Purpose Branches

Fängt man ein neues Feature, Bugfix, Refactoring o.ä. an, so ist es sinnvoll zunächst einen neuen Branch zu erstellen. Das hat den Vorteil, dass man auf einer stabilen Basis arbeitet. Würden alle Entwickler auf dem master-Branch arbeiten, wäre die Wahrscheinlichkeit sich in die „Quere“ zu kommen recht hoch.

Diese Entwicklungsbranches sollten kurzlebig und auf ein Thema beschränkt sein. Dadurch ist die Wahrscheinlichkeit von Merge-Konflikten gering und die neuen Funktionen stehen schnell allen Entwicklern zur Verfügung. Diverse Git Tools zeigen Branches grafisch an, wodurch schön nachvollziehbar ist, was wann entwickelt und gemerged wurde.

### History neu schreiben

Gerade bei schwierigen Refactorings arbeite ich oft mit sehr kleinen („sub-atomaren“) Commits. Dabei kann es durchaus vorkommen, dass der Code bei bestimmten Versionsständen nicht einmal kompiliert. Solche Versionen möchte man natürlich nicht veröffentlichen. Sie helfen aber, eine große Aufgabe (z. B. Refactoring einer zentralen Komponente) handhabbar zu machen.

Möchte man die Änderung nun anderen Entwicklern zur Verfügung stellen, ist es ratsam, die Historie „glatt zuziehen“ sodass keine nicht-funktionierenden Versionsstände existieren und oben genannte Punkte eingehalten sind.

Dazu bietet Git mehrere Möglichkeiten:

- Mit `git commit --amend` kann man den letzten Commit schnell und einfach ändern
- Mit `git merge --squash <feature branch>` fasst man alle commits von `<feature branch>` zu einem einzigen zusammen.
- Mit `git cherry-pick <commit>` kann man einzelne Commits auf einen Branch anwenden.
- Mit `git rebase -i HEAD~3` lassen sich die letzten drei Commits nachbearbeiten. Durch den Parameter `-i` wird interaktives Rebasing gestartet. Mit Hilfe der folgenden Dialoge lassen sich Commits ändern, zusammenfassen, splitten, neu sortieren oder löschen.

Einen detaillierteren Überblick über die Möglichkeiten, die Historie zu bearbeiten findet man [hier](https://xitaso.com/xitaso-tech-talk-history-rewriting-in-git/).

### Fazit

Es ist durchaus sinnvoll der Historie eine gewisse Beachtung zu schenken. Auch wenn zu Projektbeginn meist alles klein und übersichtlich ist, ist es auf lange Sicht sinnvoll sich von Anfang an um eine aussagekräftige Historie zu kümmern. Wie in diesem Artikel gezeigt, reichen dazu ein paar einfache Regeln. Der Software-Archäologe, der sich die Code Basis in zehn Jahren anschaut wird es einem sicher danken.