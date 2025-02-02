le programme en Go inspiré de GoBuster. Il permet d'identifier des fichiers et répertoires cachés sur un serveur web en testant différentes URLs.

## Fonctionnalités
- Scanner un serveur web en testant des chemins depuis un dictionnaire.
- Supporte la parallélisation avec plusieurs workers.
- Filtrage des résultats avec le mode `quiet`.
- Possibilité de scanner des cibles sur n'importe quel port.

## Usage
Exécuter le programme avec les options suivantes :
- `./mygb -d <fichier_dictionnaire> -t <cible> [-w <workers>] [-q]`

### Options disponibles
- `-d` : Chemin vers le fichier dictionnaire (obligatoire)
- `-t` : Cible à scanner (obligatoire)
- `-w` : Nombre de workers en parallèle (défaut : 1)
- `-q` : Mode quiet : n'affiche que les réponses HTTP 200

### Exemple d'utilisation
```bash
./mygb -w 10 -d /usr/share/dicts/sec.list -t localhost:8080
```

**Sortie attendue :**
```bash
Starting scan...
http://localhost:8080/admin 200
http://localhost:8080/login 404
http://localhost:8080/secret 200
Scan done in 3.21s
```
