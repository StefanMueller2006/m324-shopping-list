# Reflexion - Pipeline Test Modul 324

## Workflow Auslöser
Im Workflow File unter on: push: branches: main wird definiert, dass die Pipeline ausgeführt wird, wenn auf den Branch 
"main" gepusht wird.

## Jobs
Es gibt insgesamt 5 Jobs. Checkout und Build laufen nacheinander. Sobald build fertig ist laufen lint und test parallel.
Das habe ich so gemacht da die beiden jobs nicht voneinander abhängig sind. Sobald lint und test fertig sind wird deploy 
ausgeführt.
1. checkout
2. build
3. lint
4. test
5. deploy

### checkout
Hier wird das Repository gecloned.

### build
Hier wird das Projekt gebaut. Dieser Job failed, falls das Projekt nicht gebaut werden kann.

### Test
Dieser Job führt alle Jest Tests im Projekt aus. Job failed, falls mindestens ein Test fehlschlägt.


### Deploy
Dieser Job wird ausgeführt, um ein Deployment zu simulieren.


## Debug Hilfe
Wenn ein Schritt in einem Job fehlschlägt habe ich  ein "echo" eingefügt, damit der Fehler leichter 
gefunden und verstanden werden kann.

## Was hätte ich besser machen können
Das mehrfache Ausführen von actions/checkout@v3 und actions/setup-node@v3 in jedem Job 
hätte ich optimieren können, indem ich ein Caching implementiert hätte. Dies spart Laufzeit und Ressourcen.

