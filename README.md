<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Deel van die webwerf-kode is oopbron, welkom om te help om die vertaling te optimaliseer.

## front-end kode

* [front-end kode](https://github.com/xxai-art/web)
* [Taalpakke vir die webwerf as geheel](https://github.com/xxai-art/web/tree/main/i18n)
* [Taalpakke vir aanmeldmodules](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Webwerf Meertalige Dokumentasie](https://github.com/xxai-doc)

Die voorste programmeertaal is [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , wat 'n paar kenmerke byvoeg gebaseer op die coffeescript-sintaksis, sien [./coffee_plus.md](./coffee_plus.md) .

## Internasionalisering van webwerwe en dokumente

Bou op die volgende 3 projekte

### [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

Die markdown-sjabloon, met die agtervoegsel `.mdt` , kan verwys na eksterne lêers met 'n sintaksis soortgelyk aan `<+ ./coffee_plus/import.js>` .

[@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

Markdown-vertaling sal nie kodes en skakels vertaal nie, en sal vertaalde sinne kas. As die vertaling gewysig word, maar die oorspronklike teks is nie gewysig nie, sal dit nie die wysiging van die vertaling oorskryf as u dit weer uitvoer nie.

[@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

Taallêers vir die vertaling `yaml` gegenereerde webwerwe.
