# ARPANET

## Design
![[Pasted image 20241014112805.png]]

| genutzer Recher                      | use-case                                                                |
| ------------------------------------ | ----------------------------------------------------------------------- |
| Host                                 | Benutzerrechner                                                         |
| IMP<br(Interface Message Processor) | dedizierte Netzrechner zur  Nachrichtenzerlegung und Paketweiterleitung |
| TIP                                  | spezielle IMPs, die einen direkten Terminalzugang zum Netz erlauben     |
###### Protokolle
- Host-to-Host-Protokoll
- Host-to-IMP-Protokoll
- IMP-to-IMP-Protokoll

# Internet
- dient der Kommunikation von Rechnern 

| **Logische Sicht**                                                                                                                     | **Physische Sicht**                                                                                                          |
| -------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Netzwerk ist Black Box                                                                                                                 | „Interconnected Networks“                                                                                                    |
| Interne Struktur und Funktionsweise für Nutzer nicht relevant                                                                          | Internet besteht aus vielen Teilnetzen (Subnetze), die durch Router miteinander verbunden werden                             |
| Nutzer benötigen nur Kenntnisse über die Interaktion mit dem Netz                                                                      | Hierarchische Anordnung der Subnetze, wobei Backbone-Netze nationale, kontinentale und transkontinentale Verbindungen bieten |
| => Notwendig sind Schnittstellen und Protokollen, die auch ohne Kenntnis von Implementierungsdetails zu funktionsfähigen Netzen führen | => Größe und Komplexität erzwingen dezentrale Administration                                                                 |

# WWW
- ist eine Anwendung des Internets
- ist das umgangssprachliche "Internet"

| **Statische Webseiten**                                                                               | **Dynamische Webseiten**                                                 |
| ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Bieten Zugang zu sich nicht bzw. nur selten ändernden Informationen                                   | Ermöglichen den Zugang zu ausgewählten oder sich ändernden Informationen |
| Realisierung durch Zugriff auf statische, miteinander verlinkte HTML-Dokumente mittels URL und HTTP   | Gehen über den reinen Abruf von Informationen weit hinaus                |
| Übertragung des angeforderten Dokuments vom Webserver zum Webclient (z.B. Webbrowser)                 |                                                                          |
| Die Webseite wird so übertragen, wie sie zum Zeitpunkt des Zugriffs auf dem Server als Datei vorliegt |                                                                          |
