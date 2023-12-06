# Site Markdown plat
Site simple à fichier unique généré à partir d'un contenu markdown. 

## Prerequisites
Installer pandoc en utilisant le gestionnaire de paquets approprié pour le OS. Par exemple ubuntu :
```
sudo apt update -y
sudo apt install -y pandoc
```

## Générateur de site
```
pandoc -s index.md --template _template_.html -o index.html
```

Le fichier docx téléchargeable peut être généré à l'aide de :
```
pandoc -s index.md index.docx
```

## Auteurs
Boris K

Adrien M

Victorien SM
