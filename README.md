# ViKey : claviers virtuels personnalisables
Virtual keyboards that can be linked to HTML forms.

ViKey est un module javascript permettant d'attacher un clavier virtuel à un champ de formulaire. Il embarque, dans sa distribution originelle, un support IPA (*International Phonetic Alphabet*).

## Distribution
ViKey est distribué sous licence CECILL 2.1.

L'archive la plus récente, disponible en téléchargement, est constituée de sept fichiers :
- *jquery-2.2.0.min.js* : la bibliothèque jQuery v2.2.0 ;
- *vikey.html* : un exemple d'implémentation du clavier virtuel ;
- *vikey.css* : les styles CSS qui habillent le clavier virtuel ;
- *vikey.js* : le script gérant l'apparition du clavier virtuel et la saisie des caractères ;
- *vk-ipa.json* : le support IPA, écrit au format JSON ;
- *vk-alpha.json* : un clavier alphabétique, au format JSON ;
- *README.txt* : le fichier avec les instructions de mise en place et de personnalisation.

## Installation
1. Téléchargez la dernière archive :  
ViKey v0.7b (5 avril 2016)
2. Décompressez l'archive dans un répertoire de l'arborescence de votre site Web.  
/!\ Attention /!\ Si vous séparez les fichiers ".js" et ".json", vous devrez mettre à jour les liens dans le script vikey.js
3. Sur la page HTML où vous souhaitez activer le clavier virtuel :
- Lier le fichier CSS vikey.css :
```html
<link rel="stylesheet" type="text/css" href="{VOTRE_DOSSIER_CSS}/vikey.css" />
```
- Lier les fichiers JS jquery-2.2.0.min.js et vikey.js, à l'intérieur des balises d'en-tête ("head") :
```html
<script src="{VOTRE_DOSSIER_JS}/jquery-2.2.0.min.js"></script>
<script src="{VOTRE_DOSSIER_JS}/vikey.js"></script>
```
- Sur l'élément de formulaire cible, ajouter les classes "vikey" et, si vous souhaitez utiliser le clavier IPA, "vk-ipa" :
```html
<input type="text" name="champ" id="champ" class="vikey vk-ipa" />
```
## Personnalisation
ViKey supporte autant de claviers virtuels personnalisés que vous le souhaitez. Il est ainsi possible d'en utiliser plusieurs sur une même page HTML.

Chaque clavier virtuel doit disposer d'un identifiant propre avec, comme préfixe obligatoire *vk-*, et, comme extension, *.json*. Vous devez par conséquent veiller à la dénomination de vos fichiers. Exemples de noms corrects : *vk-anglais.json*, *vk-formules.json*, *vk-145055.json*…

La structure des claviers est composée d'une liste de lignes, elles-mêmes constituées d'un tableau listant les différents symboles. Une "cellule vide" générera un espace entre le caractère précédent et le suivant afin d'aligner les symboles.

Exemple de code au format JSON pour un clavier minimal :
```js
{
  "0": ["a", "", "b"],
  "1": ["c", "d", "e"]
}
```
Pour appeler ce clavier que l'on aura nommé vk-minimal.json, il faudra ajouter les classes CSS *vikey* et *vk-minimal* à l'élément de formulaire cible :
```html
<input type="text" name="champ" id="champ" class="vikey vk-minimal" />
```
