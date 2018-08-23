---
title: "1 - /home/martin/easydb/5/documentation/de/SUMMARY.md"
# menu: "main"
---
# Summary

* [Allgemeine Hinweise](.)
* [Releases](releases)
* [Schnelleinstieg für Benutzer](getstarteduser)
* [Schnelleinstieg für Admins](getstartedadmin)
* [Benutzer-Handbuch](webfrontend)
  * [Datenverwaltung](webfrontend/datamanagement)
    * [Neue Datensätze](webfrontend/datamanagement/new_objects)
    * [Recherche](webfrontend/datamanagement/search)
      * [Suche](webfrontend/datamanagement/search/find)
        * [Script Runner](webfrontend/datamanagement/search/find/script_runner)
      * [Schnellzugriff](webfrontend/datamanagement/search/quickaccess)
        * [Gespeicherte Suche](webfrontend/datamanagement/search/quickaccess/search)
        * [Kategoriebrowser](webfrontend/datamanagement/search/quickaccess/category)
        * [Mappen](webfrontend/datamanagement/search/quickaccess/collection)
      * [Detailansicht](webfrontend/datamanagement/search/detail)
      * [Editor](webfrontend/datamanagement/search/editor)
      * [Datei-Versionen](webfrontend/datamanagement/search/assetversions)
    * [Listen](webfrontend/datamanagement/lists)
      * [CSV-Import](webfrontend/datamanagement/lists/csvimport)
      * [JSON-Import](webfrontend/datamanagement/lists/jsonimport)
      * [Dateien importieren](webfrontend/datamanagement/lists/importfiles)
    * [Weitere Funktionen](webfrontend/datamanagement/features)
      * [Export](webfrontend/datamanagement/features/export)
      * [Masken](webfrontend/datamanagement/features/masks)
      * [Präsentationen](webfrontend/datamanagement/features/presentation)
      * [Datentypen](webfrontend/datamanagement/features/datatypes)
      * [Links / Deep Links](webfrontend/datamanagement/features/deeplinks)
      * [CMS Plugins](webfrontend/datamanagement/features/plugins)
  * [Benutzerverwaltung](webfrontend/userprefs)
    * [Anmeldeseite](webfrontend/userprefs/loginscreen)
    * [Benutzereinstellungen](webfrontend/userprefs/userprefs)
    * [Spracheinstellungen](webfrontend/userprefs/language)
    * [Selbstregistrierung](webfrontend/userprefs/selfregister)
  * [Rechtemanagement](webfrontend/rightsmanagement)
    * [Benutzer](webfrontend/rightsmanagement/users)
    * [Gruppen](webfrontend/rightsmanagement/groups)
    * [Objekttypen](webfrontend/rightsmanagement/objecttypes)
    * [Pools](webfrontend/rightsmanagement/pools)
    * [Tags & Workflows](webfrontend/rightsmanagement/tags)
    * [Voreinstellungen](webfrontend/rightsmanagement/presets)
  * [Adminstration](webfrontend/administration)
    * [Basis-Konfiguration](webfrontend/administration/base-config)
      * [Allgemein](webfrontend/administration/base-config/general)
      * [Hochladen](webfrontend/administration/base-config/upload)
      * [Anmelden](webfrontend/administration/base-config/login)
      * [Erweiterte Funktionen](webfrontend/administration/base-config/extended)
      * [Export und OAI/PMH](webfrontend/administration/base-config/export)
      * [Cloud-Dienstleister](webfrontend/administration/base-config/cloud)
      * [CMS](webfrontend/administration/base-config/cms)
      * [Editor](webfrontend/administration/base-config/editor)
      * [Remote Plugins](webfrontend/administration/base-config/plugins)
      * [Server-Config](webfrontend/administration/base-config/server-config)
    * [Datenmodell](webfrontend/administration/datamodel)
      * [Objekttypen](webfrontend/administration/datamodel/objecttype)
      * [Masken](webfrontend/administration/datamodel/mask)
    * [Mitteilungen](webfrontend/administration/messages)
    * [Metadaten-Mapping](webfrontend/administration/profiles)
    * [Ereignisse](webfrontend/administration/events)
    * [Server-Status](webfrontend/administration/server-status)
    * [CSS-Plugin](webfrontend/administration/cssplugin)
* [Systemadministration](sysadmin)
  * [Voraussetzungen](sysadmin/requirements)
  * [Lizenzen](sysadmin/licenses)
  * [Installation](sysadmin/installation)
  * [Plugin-Installation](sysadmin/plugin)
  * [Konfiguration](sysadmin/konfiguration)
    * [YAML-Dateien](sysadmin/konfiguration/yaml)
    * [Logging](sysadmin/konfiguration/logging)
    * [E-Mail-Konfiguration](sysadmin/konfiguration/email)
    * [Pluginkonfiguration](sysadmin/konfiguration/plugin)
    * [HTTPS](sysadmin/konfiguration/https)
    * [LDAP](sysadmin/konfiguration/ldap)
    * [Single Sign-On](sysadmin/konfiguration/sso)
    * [Hotfolder](sysadmin/konfiguration/hotfolder)
    * [Datenmodell-Server](sysadmin/konfiguration/objectstore)
    * [Varianten für Dateigröße](sysadmin/konfiguration/produce)
  * [Betrieb](sysadmin/betrieb)
    * [Leistung Optimieren](sysadmin/betrieb/tuning)
  * [Migration](sysadmin/migration)
  * [easydb Asset Server](sysadmin/eas)
    * [Hauptbestandteile](sysadmin/eas/installation)
    * [Konfigurationsdatei](sysadmin/eas/conf)
    * [Konfiguration beim Programmstart](sysadmin/eas/initconf)
    * [Partitionen](sysadmin/eas/partitions)
    * [API](sysadmin/eas/api)
      * [/barcode](sysadmin/eas/api/barcode)
      * [/batch](sysadmin/eas/api/batch)
      * [/bulkfetch](sysadmin/eas/api/bulkfetch)
      * [/bulksynccommit](sysadmin/eas/api/bulksynccommit)
      * [/bulkversions](sysadmin/eas/api/bulkversions)
      * [/commit](sysadmin/eas/api/commit)
      * [/config](sysadmin/eas/api/config)
      * [/delete](sysadmin/eas/api/delete)
      * [/partitions](sysadmin/eas/api/partitions)
      * [/produce](sysadmin/eas/api/produce)
      * [/put](sysadmin/eas/api/put)
      * [/query](sysadmin/eas/api/query)
      * [/rput](sysadmin/eas/api/rput)
      * [/search](sysadmin/eas/api/search)
      * [/status](sysadmin/eas/api/status)
      * [/stream](sysadmin/eas/api/stream)
      * [/uncommit](sysadmin/eas/api/uncommit)
      * [/updatecustom](sysadmin/eas/api/updatecustom)
      * [/versions](sysadmin/eas/api/versions)
      * [/writemeta](sysadmin/eas/api/writemeta)
      * [/zoomer](sysadmin/eas/api/zoomer)
    * [Dateitypen](sysadmin/eas/filetypes)
    * [Problemlösungen](sysadmin/eas/faq)
  * [Instanziierung](sysadmin/instances)
* [Solutions](solutions)
  * [Base](solutions/base)
* [Technische Dokumentation](https://docs.easydb.de/en/technical)
* [Tutorials](tutorials)
  * [Rechte 1.1: Nutzer anlegen](tutorials/rechte1_1)
  * [Rechte 1.2: versch. Abteilungen](tutorials/rechte1_2)
  * [Mandantenfähigkeit](tutorials/mandanten)
* [Glossar](glossar)
* [FAQ](faq)
