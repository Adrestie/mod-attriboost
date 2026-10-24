# mod-attriboost

An AzerothCore module (WotLK 3.3.5a) that gives players attribute points to spend across ten statistics, and extra talent points, earned from two books.

## Key features

- Ten statistics: Stamina, Strength, Agility, Intellect, Spirit, spell damage, critical strike damage, all resistances, spell penetration, healing power.
- Two books, the *Tome of Knowledge* (attribute points) and the *Book of Talents* (talent points), handed out as you like.
- Points spent in a window, with a reset for gold.
- Texts in English, French, German, Spanish and Russian.

## Dependencies

| Dependency | For |
|---|---|
| [AzerothCore](https://github.com/azerothcore/azerothcore-wotlk) (WotLK 3.3.5a) | the server |
| [mod-ale](https://github.com/azerothcore/mod-ale) | the window (server side); without it, chat commands only |
| [AIO](https://github.com/Rochet2/AIO) | the window: `AIO_Server` in `lua_scripts`, and the `AIO_Client` addon on every client |
| [mod-forever-ui](https://github.com/Adrestie/mod-forever-ui) | optional: the window becomes a tab of its Progression window |

## How to install

1. Download `installer.exe` from the [WoW-mods-installer releases](https://github.com/Adrestie/WoW-mods-installer/releases).
2. Stop the worldserver and close the game.
3. Run `installer.exe`, give it this folder and the folders it asks for, click **Check**, then **Install**.
4. Rebuild the worldserver. On its next start, the core applies the module's SQL.
5. The installer writes the spells, items and images into `Data\patch-Z.MPQ`: give that archive to the other players.

## How to update

Same steps with the new version's folder, choosing **Update** instead of **Install**. Players' points and your `attriboost.conf` settings are kept. Rebuild the worldserver, then give the players the new `patch-Z.MPQ`.

## How to uninstall

Same steps, choosing **Remove**. Everything goes, database included: the talent points the books granted are taken back. Rebuild the worldserver.

## Credits

- [AnchyDev/Attriboost](https://github.com/AnchyDev/Attriboost), the original module this one forks.
- Foe, for the idea of using auras as attributes.

## Configuration

`attriboost.conf` sets:

- the module on or off;
- the cost of a reset;
- the maximum points per statistic.

## Commands

| Command | |
|---|---|
| `/attriboost` | opens the window (also `/attributs`) |
| `.attriboost exchange <count>` | trades Tomes of Knowledge for attribute points |
| `.attriboost talents <count>` | trades Books of Talents for talent points |
| `.attriboost allocate <statistic> <count>` | spends points on a statistic |
| `.attriboost reset` | returns every point to the pool, for gold |
