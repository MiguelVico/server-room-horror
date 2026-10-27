El problema és la ruta absoluta que estàs utilitzant. A l'arrel del teu repositori (on tens el `guia.md`), la carpeta `screenshots` ja hi és directament. Per tant, has d'utilitzar rutes relatives perquè GitHub (o qualsevol visor de Markdown) les pugui trobar.

La ruta correcta ha de ser simplement `screenshots/cX.png` (sense la barra inicial `/` ni el nom del repositori `server-room-horror/` al davant).

A més, he vist a la teva captura de la carpeta que tens un fitxer anomenat `13.png` (sense la "c"). L'he corregit a la guia perquè no et doni error.

Aquí tens la guia corregida amb les rutes adequades:

```markdown
# 🎃 The Halloween Commit: Horror at the Server Room - Guia de Resolució

Aquesta guia documenta el procés d'anàlisi forense, reconstrucció i exorcisme del repositori infectat `server-room-horror`, seguint la seqüència d'accions de la tasca. L'entorn utilitzat és Windows 11 amb PowerShell i Git.

---

## Bloc 1: Invocació del Repositori i Línia Base

### Acció 3.1: Creació del directori i inicialització de Git
Es crea el directori del cas d'estudi `server-room-horror` i s'inicialitza el repositori local de Git per començar a rastrejar els esdeveniments.

```bash
mkdir server-room-horror
cd server-room-horror
git init
```
![Captura inicialització Git](screenshots/c1.png)

### Acció 3.3: Creació del codi base (1r Commit)
Generem el fitxer principal `main.js` amb l'arquitectura base del sistema i l'emmagatzemem formalment a l'historial.

```bash
echo "// Base System Architecture - Halloween Protocol" > main.js
git add main.js
git commit -m "docs: init base system architecture"
```
![Captura 1r Commit](screenshots/c2.png)

### Acció 3.4: Sistema de seguretat de l'edifici (2n i 3r Commit)
S'apliquen dues modificacions successives al fitxer de codi per establir el sistema de seguretat de l'edifici, enregistrant cadascuna per separat.

**2n Commit:**
```bash
echo "const securityLevel = 'LOW';" >> main.js
git add main.js
git commit -m "feat: initialize building security protocol level"
```

**3r Commit:**
```bash
echo "function verifyDoorAccess() { return true; }" >> main.js
git add main.js
git commit -m "feat: add door access verification logic"
```
![Captura 2n i 3r Commit](screenshots/c3.png)

### Acció 3.5: Consulta de l'historial simplificat
Verifiquem que la línia temporal inicial és estable consultant l'historial en una sola línia.

```bash
git log --oneline
```
![Captura git log --oneline](screenshots/c4.png)

---

## Bloc 2: Les Branques del Més Enllà i Resolució del Conflicte

### Acció 3.6: Creació de branques paral·leles i justificació de la topologia
Es creen dues branques aïllades directament des del commit estable de `main`:
- `feature-nightmare`: representació de la visió fosca/infectada.
- `feature-sanctuary`: línia temporal de protecció.

**Justificació de la topologia:** Es decideix bifurcar ambdues branques des del mateix punt d'origen (`main`) per simular un desdoblament de la realitat a partir de l'últim estat segur conegut del servidor.

```bash
git branch feature-nightmare
git branch feature-sanctuary
git checkout feature-nightmare
```
![Captura creació de branques i checkout](screenshots/c5.png)

### Acció 3.7: Injecció de la visió fosca (Commit a feature-nightmare)
Modifiquem la línia de codi del fitxer principal per injectar la lògica corrupta i ho enregistrem.

```bash
sed -i 's/const securityLevel = '\''LOW'\'';/const securityLevel = '\''CORRUPTED_NIGHTMARE'\'';/' main.js
git add main.js
git commit -m "feat: inject nightmare protocol security logic"
```
![Captura commit nightmare](screenshots/c6.png)

### Acció 3.8: Lògica de protecció (Commit a feature-sanctuary)
Ens desplacem a la branca de protecció i modifiquem exactament la mateixa línia per establir el santuari.

```bash
git checkout feature-sanctuary
sed -i 's/const securityLevel = '\''LOW'\'';/const securityLevel = '\''SANCTUARY_SHIELD_MAX'\'';/' main.js
git add main.js
git commit -m "feat: apply sanctuary shield defense logic"
```
![Captura commit sanctuary](screenshots/c7.png)

### Acció 3.9: Integració de les branques
Tornem a `main` i intentem integrar les dues branques. (Nota: El sistema mostra un error de `pathspec 'main'` perquè en aquest entorn la branca principal es diu `master`).

```bash
git checkout main
git merge feature-nightmare
git merge feature-sanctuary
```
![Captura inici de fusió i error de path](screenshots/c8.png)

### Acció 3.10: El ritual de fusió i resolució del conflicte
*(Nota: Tot i que la fusió anterior es va aturar per l'error de la branca, el procés de conflicte es va resoldre manualment netejant les marques `<<<<<<<`, `=======`, `>>>>>>>` i escollint el codi del santuari, finalitzant amb el commit de fusió).*

Un cop resolt el conflicte al fitxer `main.js`, finalitzem la integració:
```bash
git add main.js
git commit -m "merge: resolve conflict and secure the server"
```

---

## Bloc 3: Viatge Temporal, Exorcisme del Codi i Publicació Remota

### Acció 3.11: Injecció del commit infectat
L'esperit maligne aconsegueix executar un commit corruptor que fa caure el sistema.

```bash
echo "throw new Error('FANTASMES_IN_PRODUCTION: SYSTEM DESTROYED');" >> main.js
git add main.js
git commit -m "feat: unhandled spectral exception"
```
![Captura commit infectat i git diff](screenshots/c9.png)

### Acció 3.12: Inspecció de la diferència textual
Executem l'ordre per veure exactament què ha canviat el codi infectat respecte a l'estat segur anterior.

```bash
git diff HEAD~1 HEAD
```
*(Veure captura anterior `c9.png`)*

### Acció 3.13: Reversió temporal i purificació
Per purificar l'historial i destruir completament el codi infectat de l'espai de treball, executem una reversió forçada que esborra el registre del commit defectuós.

```bash
git reset --hard HEAD~1
```
*(Veure captura anterior `c9.png`)*

### Acció 3.14: Visualització gràfica de la topologia
Comprovem l'arbre de branques, fusions i la línia temporal ja purificada. Veiem que `HEAD` apunta a `master` i que les branques `feature-nightmare` i `feature-sanctuary` hi són presents.

```bash
git log --graph --oneline --all
```

A continuació, preparem la documentació (creant els fitxers Markdown i la carpeta de captures) i l'afegim a Git per a l'auditoria:

```bash
git add README.md bloc1.md bloc2.md bloc3.md screenshots/
```
![Captura git log graph i add](screenshots/c10.png)

*(Nota: A la captura `c10` es pot veure com el primer `git add README.md ...` falla perquè els fitxers encara no existien, i el segon intent d'afegir els fitxers Markdown es mostra a la part inferior).*

### Acció 3.15: Publicació remota a GitHub
Vinculem el repositori local amb el repositori públic de GitHub i pugem tota la informació (branques, historial i fitxers Markdown).

```bash
git remote set-url origin https://github.com/MiguelVico/halloween-git-rescue.git
git push -u origin --all
```
![Captura git remote i push](screenshots/c11.png)

---

## Annex: Documentació Markdown (Captures de text)
A continuació es mostren les captures dels fitxers Markdown creats per a l'auditoria, on es justifica la topologia i es documenten les accions.

**Bloc 1: Invocació del Repositori i Línia Base**
![Captura Markdown Bloc 1](screenshots/c12.png)

**Bloc 2: Les Branques del Més Enllà i Resolució del Conflicte**
![Captura Markdown Bloc 2](screenshots/13.png)
```

### Què has de fer ara:
1. Copia aquest text i enganxa'l al teu fitxer `guia.md`.
2. Guarda els canvis.
3. Fes un `git add guia.md` i un `git commit -m "docs: fix image paths in guide"`.
4. Torna a fer el `git push` perquè els canvis es pugin a GitHub. 

D'aquesta manera, quan obris el `guia.md` des de la pàgina web de GitHub, les imatges es carregaran correctament.