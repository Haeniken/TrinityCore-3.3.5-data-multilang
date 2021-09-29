# Extracted data for TrinityCore 3.3.5a

![GitHub repo size](https://img.shields.io/github/repo-size/Haeniken/TrinityCore-3.3.5-data-multilang?style=for-the-badge) 

---

## Includes:

```bash 
    $ tree -d -L 2
    .
    ├── Cameras
    ├── dbc
    │   ├── deDE
    │   ├── esES
    │   ├── frFR
    │   └── ruRU
    ├── maps
    ├── mmaps
    └── vmaps
```
---

## Adding Language Locales to the Server
>*Hint:<br>
>Extra action is not required except default moving files to* `server/data/` *folder. Also you can place it in any needed location and configure the parameter* `DataDir` *into your* `worldserver.conf`.

In order for the server to recognize other languages, it will need access to the DBC files for that locale. The default locale is enUS and its DBC files are located in the normal DBC folder. However, the DBC files for other locales should be placed in a sub-folder with the four letter locale name.

In effect, you will end up with a folder structure like this (showing English US, French and German locales)
```
    + dbc  contains the English US (enUS) locale DBC files, also used for English UK (enGB)
       |
       + deDE   contains the German (deDE) locale DBC files
       + ruRU   contains the Russian (ruRU) locale DBC files
```
>*Note:<br>
>On Trinity servers (I'm not sure about other cores), the **enGB** and **enUS** locales are treated as the same. Therefore, it is rather redundant to have both of these locales on the same server as you won't get anything different.*

When you start the server (at least on Trinity) you should see a message saying which locales it has detected. For example:
```
    Using enUS DBC Locale as default. All available DBC locales: frFR enUS
```
On Trinity, the `DBC.Locale` entry in `worldserver.conf` controls which locale is used as the default, while the `RealmZone` entry controls the allowed character set. These should be set so that any of the locales supported can be used properly (the defaults should be fine).

---

## Environment

This was extracted on `Debian 10`, in case it's important to someone.<br>
TrinityCore rev. 0a2fca1aed4f 2021-09-27 19:00:55 +0300 (3.3.5 branch).
<br><br>Enjoy!
