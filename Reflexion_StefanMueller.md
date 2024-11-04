# Reflexion - Pipeline Test Modul 324

## Workflow Auslöser
Im Workflow File unter on: push: branches: main wird definiert, dass die Pipeline ausgeführt wird, wenn auf den Branch 
"main" gepusht wird.

## Jobs
Bei den Jobs gibt es drei Jobs. Bei den Jobs "lint" und "test" werden als erste Schritte der Code ausgecheckt, 
Node installiert und die Dependencies installiert. 
1. lint
2. test
3. deploy

### Lint
Der Job Lint ist ein Job, der den Code auf Fehler überprüft. 
Es wird das Tool "eslint" verwendet. 
Es wird überprüft, ob der Code den Styleguides entspricht. 
Wenn der Code nicht den Styleguides entspricht, wird der Job fehlschlagen.

### Test
Dieser Job führt alle Jest Tests im Projekt aus. Job failed, falls mindestens ein Test fehlschlägt.

**Wichtig: Dieser Job wird nur ausgeführt, wenn der Job "lint" erfolgreich war.**

### Deploy
Dieser Job wird ausgeführt, um ein Deployment zu simulieren.

**Wichtig: Dieser Job wird nur ausgeführt, wenn der Job "test" erfolgreich war.**

## Debug Hilfe
Wenn ein Schritt in einem Job fehlschlägt habe ich an manchen Stellen ein "echo" eingefügt, damit der Fehler leichter 
gefunden und verstanden werden kann.

