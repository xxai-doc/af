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

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Die agtervoegsel is `.mdt` , jy kan die sintaksis soortgelyk aan `<+ ./coffee_plus/import.js>` gebruik om na eksterne lêers te verwys, en afmerking genereer met die agtervoegsel `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Markdown-vertaling sal nie kodes en skakels vertaal nie, en sal vertaalde sinne kas. As die vertaling gewysig word, maar die oorspronklike teks is nie gewysig nie, sal dit nie die wysiging van die vertaling oorskryf as u dit weer uitvoer nie.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Taallêers vir die vertaling `yaml` gegenereerde webwerwe.

### Dokumentvertalingsoutomatiseringsinstruksies

Sien bewaarplek [xxai-art/doc](https://github.com/xxai-art/doc)

Dit word aanbeveel om eers nodejs, [direnv](https://direnv.net) en [bun](https://github.com/oven-sh/bun) te installeer, en dan `direnv allow` uit te voer nadat u die gids binnegegaan het.

Om té groot pakhuise wat in honderde tale vertaal word te vermy, het ek 'n aparte kodepakhuis vir elke taal geskep en 'n organisasie geskep om hierdie pakhuis te stoor

Deur die omgewingsveranderlike `GITHUB_ACCESS_TOKEN` te stel en dan [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) te laat loop, sal die pakhuis outomaties geskep word.

U kan dit natuurlik ook in 'n pakhuis plaas.

Vertaling skrif verwysing [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Die skrifkode word soos volg geïnterpreteer:

[bunx](https://bun.sh/docs/cli/bunx) is 'n plaasvervanger vir npx, wat vinniger is. Natuurlik, as jy nie bun geïnstalleer het nie, kan jy eerder `npx` gebruik.

`bunx mdt zh` gee `.mdt` in die zh-gids as `.md` , sien die 2 gekoppelde lêers hieronder

* [koffie_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [koffie_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` is die kernkode vir vertaling (as jy net `nodejs` geïnstalleer het, maar `bun` en `direnv` is nie geïnstalleer nie, kan jy ook `npx i18n` laat loop om te vertaal).

Dit sal [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) ontleed, die konfigurasie van `i18n.yml` in hierdie dokument is soos volg:

```
en:
zh: ja ko en
```

Die betekenis is: Chinese vertaling na Japannees, Koreaans, Engels, Engelse vertaling na alle ander tale. As jy net Chinees en Engels wil ondersteun, kan jy net skryf `zh: en` .

Die laaste is [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , wat die inhoud tussen die hooftitel en die eerste ondertitel van elke taal se `README.md` onttrek om 'n inskrywing `README.md` te genereer. Die kode is baie eenvoudig, jy kan self daarna kyk.

Google API word gebruik vir gratis vertaling. As jy nie toegang tot Google kan kry nie, stel asseblief 'n instaanbediener op en stel, soos:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Die vertalingskrip sal 'n vertaalkas in `.i18n` -gids genereer, kontroleer dit asseblief met `git status` en voeg dit by die kodebewaarplek om herhaalde vertalings te vermy.
