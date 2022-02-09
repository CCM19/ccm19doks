# Eine Funktion auf meiner Webseite arbeitet nicht mehr korrekt, seit ich CCM19 einsetze

Das Problem ist, dass CCM19 ein Skript blockiert, das nicht blockiert werden soll. Das kann mehrere Ursachen haben.

1. Sie haben unter dem Menüpunkt „Developer-Einstellungen“ für die Blockierung von Skripten zu restriktive Einstellungen getroffen. Vor allem die Optionen, alle unbekannten Cookies zu löschen, neue Skripte oder Inline-Skripte zu blockieren, kann zu unerwünschtem Verhalten führen. Deaktivieren Sie die genannten Funktionen einmal und testen, ob der Fehler weiterhin auftritt.

   Sie haben auch die Möglichkeit eine Ausnahme für Inline-Skripte zu definieren, um ein bestimmtes Skript nicht zu blockieren. Es kann also auch helfen, wenn Sie im entsprechenden Feld einen Textbaustein aus dem Skript, das fälschlicherweise geblockt wird, eintragen.

2. Sie haben bei einer Einbindung einen zu allgemeinen Text im Feld „Skripte blockieren, die folgenden Text enthalten“, hinterlegt. Wenn Sie hier beispielsweise einen generische Skript-Bestandteil wie „var“ eingetragen haben, kann es vorkommen, dass dieser noch in einem anderen Skript in Ihrer Seite vorkommt, das nicht blockiert werden soll. Überprüfen Sie also unter dem Punkt „Einbindungen & Cookies“, ob Ihre Einbindungen generische Blockier-Befehle enthalten und spezifizieren Sie diese.

3. Bei der Funktion handelt es sich um einen Iframe und dieser wird von unserem Iframe-Blocker blockiert. In diesem Fall können Sie für den entsprechenden Iframe im CCM19-Menüpunkt „Iframes“ eine Ausnahme hinzufügen oder auf die Blockiermethode „Blocklist“ umstellen, bei der nur ausgewählte Iframes blockiert werden.