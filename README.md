---
# TMUX Cheat Sheet

Eine übersichtliche Zusammenfassung der wichtigsten TMUX-Befehle.

---

## Sessions

- **Session erstellen**  
  Erstellt eine neue Session (optional mit Session- und Fensternamen).  
  ```
  tmux new-session [-s session_name] [-n window_name]
  : new [-s session_name]
  ```
  *Alias*: `new`  

- **Session beenden**  
  Löscht alle Sessions außer der angegebenen oder der aktuellen  
  ```
  tmux kill-session [-t session_name]
  ```
  *Alias*: `kill-ses`  
  *Option* `-a`: Beendet alle Sessions **außer** die angegebene  
  
- **Session attachen**  
  Öffnet die letzte oder eine bestimmten Session.  
  ```
  tmux attach-session [-t session_name]
  ```  
  *Aliases*: `attach`, `at`, `a`  
  *Option* `-d`: Detacht andere  


- **Session detachen**  
  ```
  ^b d
  ```  

- **Session umbenennen**  
  ```
  ^b $
  ```  

- **Sessions auflisten**  
  ```
  tmux list-sessions
  ```  
  *Alias*: `ls`  

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

- **Fenster erstellen**  
  ```
  ^b c
  ```

- **Fenster umbenennen**  
  ```
  ^b ,
  ```

- **Fenster schließen**  
  ```
  ^b &
  ```

- **Fenster auflisten**  
  ```
  ^b w
  ```

- **Fenster wechseln**  
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

- **Pane verschieben**  
  - Links:
    ```
    ^b {
    ```
  - Rechts:
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

