## Primul exercițiu: crearea unui Docker container image

În primul rând, vom modifica `Makefile` pentru ca fiecare să aibă propriul tag pentru imaginea de Docker:

    $ sed -i 's/VERSION?=/VERSION?=vMY_NAME/g' ./Makefile

Apoi, putem rula `make` pentru a crea și exporta imaginea:

    $ make