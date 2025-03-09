---
# TMUX Cheat Sheet

Eine übersichtliche Zusammenfassung der wichtigsten TMUX-Befehle.

---

## Sessions

- **TMUX starten**  
  ```
  tmux
  ```

- **Neue Session erstellen**  
  ```
  tmux new-session[^0] [-s session_name] [-n window_name]
  : new [-s session_name]
  ```  
  *Erstellt eine neue Session (optional mit Session- und Fensternamen).*

- **Aktuelle Session beenden**  
  ```
  : kill-session
  ```  

- **Bestimmte Session beenden**  
  ```
  tmux kill-session -t <session_name>
  ```  
  *Alias*: `kill-ses`  

- **Alle Sessions außer eine löschen**  
  ```
  tmux kill-session -a [-t session_name]
  ```  
  *Alias*: `kill-ses`  
  Löscht alle Sessions außer der angegebenen oder der aktuellen

- **Session umbenennen**  
  ```
  ^b $
  ```  

- **Session detachten**  
  ```
  ^b d
  ```  

- **Attatchen und andere detatchen**  
  ```
  : attatch -d
  ```  

- **Sessions auflisten**  
  ```
  tmux list-sessions
  ```  
  *Alias*: `ls`  

- **Session wechseln**  
  ```
  tmux attatch-session [-t session_name]
  ```  
  Aliases: `attatch`, `at`, `a`
  *Öffnet die letzte oder eine bestimmten Session.*

- **Session- und Fenster-Vorschau anzeigen**  
  ```
  ^b w
  ```

- **Sessions wechseln**  
  - Vorherige Session:  
    ```
    ^b (
    ```  
  - Nächste Session:  
    ```
    ^b )
    ```

---

## Windows

- **Neues Fenster erstellen**  
  ```
  ^b c
  ```

- **Fenster umbenennen**  
  ```
  ^b ,
  ```

- **Aktuelles Fenster schließen**  
  ```
  ^b &
  ```

- **Fenster auflisten**  
  ```
  ^b w
  ```

- **Zwischen Fenstern wechseln**  
  - Zum vorherigen Fenster:  
    ```
    ^b p
    ```  
  - Zum nächsten Fenster:  
    ```
    ^b n
    ```

- **Direkt zu einem Fenster wechseln**  
  ```
  ^b <0-9>
  ```

- **Zum zuletzt aktiven Fenster wechseln**  
  ```
  ^b |
  ```

- **Fenster tauschen**  
  ```
  : swap-window -s <src> -t <dst>
  ```  

- **Fenster neu nummerieren**  
  ```
  : move-window -r
  ```
  *Alias*: `movew`  

---

## Panes

- **Pane horizontal teilen**  
  ```
  ^b %
  : split-window -h
  ```

- **Pane vertikal teilen**  
  ```
  ^b "
  : split-window -v
  ```  

- **Pane nach links verschieben**  
  ```
  ^b {
  ```

- **Pane nach rechts verschieben**  
  ```
  ^b }
  ```

- **Zwischen Panes wechseln**  
  ```
  ^b <arrow>
  ```  

- **Layout zwischen Panes wechseln**  
  ```
  ^b space
  ```

- **Pane-Nummern anzeigen (und wechseln)**  
  ```
  ^b q [0-9]
  ```

- **Pane-Zoom umschalten**  
  ```
  ^b z
  ```

- **Pane-Größe anpassen**  
  ```
  hold ^, press b, press <arrow>
  ```  

- **Aktuelle Pane schließen**  
  ```
  ^b x
  ```

- **Befehlsmodus aktivieren**  
  ```
  ^b :
  ```

---

[^0]: Alias: new
