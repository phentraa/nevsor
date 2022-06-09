### PM Manuális tesztelő - GIT gyakorlati feladat
# Tesztelői névsor összeállítása

A feladatsor célja, hogy segítse a GIT verziókezelő rendszer alapjainak elsajátítását.

### Érintett területek

- Egyéni
-- Információk megjelenítése a leklónozott repository-ról (_status, log_)
-- Módosítások elvégzése a **csoport.html** fájlon (_add, commit_)
-- Váltás a verziók között (_checkout_)
- Csoportos
-- Az egyéni változtatások felküldése a távoli repository-ba
-- A legfrisebb főverzió összehasonlító lekérése (fetch), majd felülíró lehúzása (pull)

### Feladatok
Másoljuk le magunknak [ezt a repository][repo]-t egy tetszőleges könyvtárba:

```sh
cd /path/to/my_dir
git clone https://github.com/phentraa/nevsor.git
cd nevsor
```

Miközben a terminált nyitva hagyjuk, jelenítsük meg a 'nevsor' mappában található _csoport.html_ fájlt egy böngészőben az elérési út megadásával. Vizsgáljuk meg az oldalt.

Nyissuk meg a _csoport.html_ fájlt egy tetszőleges szövegszerkesztőben is.
Írjunk át a benne található keresztnevet, majd mentsük a fájlt Ctrl+S-el.
Ellenőrizzük a projekt aktuális státuszát:
```sh
git status
```

Minden változást állítsunk staged állapotba, majd véglegesítsük őket a commit paranccsal:
```sh
git add .
git commit -m "Átírtam a keresztnevet!"
```
> Figyelj, hogy az add után lévő 'pont' is meglegyen!

...majd nézzünk bele a változás történetbe:
```sh
git log
```

Miután ellenőriztük a honlapon az új adat megjelenítését (frissítés szükséges lesz), lépjünk vissza az előző verzióra!
Ehhez szükségünk lesz a 'git log' parancs kimenetében található commit azonosítóra, ami formailag hasonló lesz a következő parancsban láthatóhoz:
```sh
git checkout 4185f6553f81154ada3c8d68382d595d02b01ed2 .
```
> Figyelj az utasítás végén lévő pontra!
> E nélkül egy "detached head" állapotba kerül a rendszer. Visszaállítás: git checkout master

Frissítés után látszik az oldal tartalmán, hogy visszatértünk egy előző verióhoz.
A html kód módosításával töltsük ki a táblázatot a saját adatainkkal, majd az előző lépések ismétlésével commitoljuk a változtatásainkat!

Most fedjük le egy paranccsal a staged ill. commit állapotba küldést:
```sh
git commit -a -m "Saját adatok felvétele a táblázatba"
```

A push parancs segítségével küldjük fel a közös szerverre a változásainkat!
```sh
git push
```

Majd ha mindenki felküldte, húzzuk le magunkhoz a legfrissebb verziót és nézzük meg a böngészőben a közös eredményt!
```sh
git pull
```

[repo]: https://github.com/phentraa/nevsor.git
