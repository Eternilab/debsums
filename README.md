---
title: debsums ansible role
---
# Debsums

## Licence

Ce rôle est sous licence MIT

## Description

Ce rôle installe et configure _debsums_
_Debsums_ est un outil qui permet de vérifier l'intégrité des fichiers des paquets intallés avec les sommes de contrôle MD5 depuis /var/lib/dpkg/info/*.md5sums.

## Commandes utiles

### EXEMPLES

```debsums foo bar```
    Vérifie les sommes de contrôle des paquets installés foo et bar.
```debsums foo.deb bar.deb```
    Comme ci-dessus, en utilisant les sommes de contrôle des archives (ou celles calculées à partir de celles-ci).
```debsums -l```
    Liste les paquets installés ne possédant pas de somme de contrôle.
```debsums -ca```
    Liste les fichiers modifiés des paquets installés ayant une somme de contrôle.
```debsums -ce```
    Liste les fichiers de configuration modifiés.
```debsums -cagp /var/cache/apt/archives```
    Comme ci-dessus, en utilisant les sommes de contrôle des archives .deb disponibles en cache.
```apt-get install --reinstall $(dpkg -S $(debsums -c) | cut -d : -f 1 | sort -u)```
    Réinstalle les paquets ayant des fichiers modifiés.

## Conformité ANSSI DEBSUMS

Ce rôle n'est pas requis par les guides de l'ANSSI, cependant il est nécessaire au bon fonctionnement du système
