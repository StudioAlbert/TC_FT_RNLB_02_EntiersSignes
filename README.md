# Entiers signés et dépassements — companion TC-FT-RNLB-02

Tous les exemples de code du cours, prêts à compiler et à modifier.

| Fichier | Rôle |
|---|---|
| `01_entiers_signes/include/entiers_signes.h` | **Toutes les démos**, une fonction par slide, dans l'ordre du deck |
| `01_entiers_signes/include/affichage.h` | Outils d'affichage : titre de slide, bits d'un octet, pause |
| `01_entiers_signes/main.cc` | Enchaîne les démos, partie par partie |
| `02_selon_la_plateforme/main.cc` | Les `sizeof` à coller dans [Compiler Explorer](https://godbolt.org) pour comparer x64 msvc, ARM64 gcc, AVR gcc |

Chaque fonction porte en commentaire le nom de sa slide, et l'affiche en première ligne.

## Compiler et lancer

```powershell
cmake -S . -B build
cmake --build build
```

Puis `build/01_entiers_signes/01_entiers_signes.exe`.

Deux avertissements de compilation sont **voulus** : la comparaison signé / non signé
(`melange`) et la boucle `i >= 0` toujours vraie (`piegeNonSigne`). Lisez-les.

## Voir le comportement indéfini (GCC / Clang)

```bash
cmake -S . -B build-ub -DSANITIZE=ON
cmake --build build-ub
./build-ub/01_entiers_signes/01_entiers_signes
```

Le programme signale `signed integer overflow` à la ligne de `INT_MAX + 1`.

## À essayer

- Changer `niveau = 254` dans `pacMan()` et prévoir la sortie avant de relancer.
- Lire `plusGrandQueLui` : pourquoi le compilateur a-t-il le droit de répondre `true` ?
- Lancer le programme sur un autre système et comparer `mesurerSaPlateforme()`.
