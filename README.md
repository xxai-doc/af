<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

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

Dit sal [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) ontleed, `i18n.yml` is soos volg gekonfigureer

af:

zh: ja ko en

`bunx i18n` is die kernkode vir vertaling (as jy net `nodejs` geïnstalleer het, maar `bun` en `direnv` is nie geïnstalleer nie, kan jy ook `npx i18n` laat loop om te vertaal).

Dit sal [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) ontleed, `i18n.yml` is soos volg gekonfigureer



af:

zh: ja ko en

* [koffie_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` is die kernkode vir vertaling (as jy net `nodejs` geïnstalleer het, maar `bun` en `direnv` is nie geïnstalleer nie, kan jy ook `npx i18n` laat loop om te vertaal).

Dit sal [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) ontleed, `i18n.yml` is soos volg gekonfigureer

af:
zh: ja ko en

`bunx i18n` is die kernkode vir vertaling (as jy net `nodejs` geïnstalleer het, maar `bun` en `direnv` is nie geïnstalleer nie, kan jy ook `npx i18n` laat loop om te vertaal).

Dit sal [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) ontleed, die konfigurasie van `i18n.yml` in hierdie dokument is soos volg:


af:
zh: ja ko en
```

它的含义是 :

中文翻译为日文、韩文、英文，英文翻译为其他所有语种。如果你只想支持中文、英文，可以只写 `zh: en`。

最后是 [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee)，它是提取每个语种 `README.md` 大标题 和 第一个子标题 之间的内容，来生成一个入口的 `README.md` 。代码很简单，可以自己看一下。

最后，因为用到了谷歌 API 来免费翻译，所以如果你不能访问谷歌，请配置并设置代理，比如 :

```
uitvoer https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890