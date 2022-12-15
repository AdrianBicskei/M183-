# Lern-Bericht
Adrian Bicskei

## Einleitung

Bei der Cross-Site-Scripting geht es darum, (JavaScript)-Code auf eine Website durch Benutzereingaben einzuschleichen, damit der Browser diese Benutzereingaben darstellt, diese jedoch nicht als Seiteninhalte, sondern als Code interpretiert. 

## Was habe ich gelernt?

Im Modul 183 habe einerseits gelernt, wie man Cross-Site-Scripting bei einer Webapplikation, welche vor dieser Art von Angriffen nicht geschützt ist, anwendet. Anderseits habe ich gelernt, was man als Entwickler einer Webapplikation unternehmen kann, um sich vor XSS zu wehren. 

## Beschreibung

Um ein Stück von (JavaScript)-Code in die ungeschützte Webapplikation einzuschleichen, muss man in ein Formular-/Eingabeelement, dessen eingegebener Inhalt nach der Validierung auf der Website dargestellt wird, das folgende Beispiel eingeben, mit dem man ein Alert erzeugen kann: 

```
<script>alert('XSS')</script>

```
Der Alert, welche dadurch erzeugt wurde:



![alert](https://user-images.githubusercontent.com/112397931/207857233-5102c2d7-f1d3-43f5-b84f-6229e6121cc4.png)


Schützen kann man sich gegen Cross-Site-Scripting durch "escaping". Um sich bei einer JSF Webapplikation gegen XSS zu schützen, kann man das "escaping "bei den Ausgaben explizit auf "true" setzen, wie im folgenden Beispiel: 

```
<h:outputText value="#{newsitem.detail}" escape="true"/>
```

## Verifikation

In der JavaScript-Code ist zu sehen, mit was für einer Eingabe ein Alert auf einer vor XSS ungeschützter Webapplikation erzeugen kann. 

In der XHTML-Code ist zu sehen, wie man das Escaping explizit auf True stellen kann, um sich vor XSS Angriffen zu wehren.

# Reflektion zum Arbeitsprozess

Gut gelaufen während dem Lernprozess ist es die Ausgaben bei einer JSF-Webapplikation mit escape="true" abzusichern.

Was während dem Lernprozess nicht gut gelaufen ist, war es beim Darstellen von Seiteninhalten, welche JavaScript-Code enthalten, auf einer Website manuell mit dem Sonderzeichen zu Escapen.

**VBV**: Damit ich in der Zukunft keine Schwierigkeiten bei der Escaping von Seiteninhalten, welche Code enthalten, werde ich auf die Sonderzeichen, die es dazu braucht, besser achten.
