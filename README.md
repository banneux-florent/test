# Github

`commit` =  agglomération de modifications
`repository` = répertoire en ligne sur Github qui stocke ton projet

Commencer par aller sur Github et créer un nouveau `repository`. Une fois créé, une page s'affichera avec dans le premier cadre cet enchainement de commandes:
```bash
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/banneux-florent/test.git
git push -u origin main
```
Tu peux ignorer certaines étapes et en rajouter d'autres pour donner ceci (commence par te rendre dans la racine de ton dossier via ton terminal):

```bash
git init
```
_Initialise la gestion des fichiers par Git localement, cela crée un dossier .git invisible dans ton répertoire_

```bash
git add .
```
_Ajoute tous les fichiers de ton répertoire en phase "staged". Cela veut dire que ces fichiers seront prêts à être ajouter à un commit qui pourra être envoyé vers ton repository. Ici, le point agit comme un regex et permet un ajout de la totalité des fichiers. Tu peux aussi le faire un a un avec le chemin complet, ou par dossier (via `git add ./dossier`, etc.), ou par type ( `git add *.php`), etc._

```bash
git commit -m "first commit"
```
_Permet de cristalliser l'ensemble des fichiers ajoutés à la phase "staged" dans un groupe auquel tu donnes une petite description. Cela permet de donner des étapes d'avancement à ton code, et de mieux t'y retrouver_

```bash
git remote add origin https://github.com/[user]/[repository].git
```
_A utiliser souvent une seule fois à la création du projet comme ici, afin d'informer Git vers quel repository tu veux envoyer tes commits/communiquer_

```bash
git push -u origin main
```
_Permet d'envoyer tes modifications locales (en attente dans tes commits réalisés) vers ton repository_

Une petite chose importante qui peut s'avérer utile: tu peux créer à la racine dans ton dossier un fichier `.gitignore`, dans lequel tu pourras indiquer tous les fichiers que tu ne veux pas que Git gère, comme par exemple des fichiers de log, personnels (notes, etc.), ou parfois encore des fichiers où se trouvent des clés privées/mot de passe si le repository est public. Dans ton cas, ca risque fort probablement d'être le dossier `/node_modules` que tu voudras écarter, car il est réinstallable à la demande et ne nécessite pas d'être sauvegardé.

Pour ajouter des exclusions, il suffit de les écrire pleinement ligne par ligne dans le fichier `.gitignore`.

Afin que cela soit prit en compte, vérifie bien que ce fichier est ajouté aux fichiers en phase "staged". Une fois complet, fait un coup de `git add ./.gitignore`.

Quoi que tu fasses (ou presque), normalement, il n'y a pas de quoi paniquer avec Git. Tu peux dans la grande majorité des cas revenir en arrière sauf si tu fais des dingueries!

---

Pour le futur, si tu es amené à travailler avec d'autres personnes, voici 2 commandes intéressantes:

```bash
git fetch
```
_Permet de mentionner à ton Git local toutes les modifications qui ont été apportées en ligne sur le repository SANS les appliquer_

```bash
git pull
```
_Une fois les dernières modifications récupérées, tu peux décider de les appliquer à ton code via cette commande. Cela mergera ton code avec les modifications automatiquement sauf conflits (là, c'est plus délicat, tu pourras toujours demander si besoin)_
