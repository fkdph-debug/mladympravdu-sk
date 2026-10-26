# mladympravdu.sk

Statická landing page pre **Mladým pravdu** – dielo Renáty Ocilkovej.
Čisté HTML + CSS, bez buildu. Hostované na Verceli, doména na Webglobe.

## Štruktúra
```
index.html        – celá stránka (texty, štýly)
assets/logo.svg   – logo (farebné)
assets/logo-white.svg – logo s bielym textom (na tmavé pozadie)
assets/icon.svg   – samotná ikona (favicon)
vercel.json       – nastavenie Vercelu
```

## Nasadenie (GitHub → Vercel)
1. Na GitHube vytvor nový repozitár (napr. `mladympravdu-sk`) a nahraj doň obsah tohto priečinka.
2. Na vercel.com → **Add New… → Project** → importuj repozitár.
   Framework Preset: **Other**, Build Command: prázdne, Output Directory: prázdne (koreň). → **Deploy**.
3. V projekte na Verceli: **Settings → Domains** → pridaj `mladympravdu.sk` aj `www.mladympravdu.sk`
   (odporúčané: `www` ako hlavná, holá doména presmeruje na `www`).

## DNS na Webglobe
V administrácii Webglobe → doména `mladympravdu.sk` → **DNS záznamy**:

| Typ   | Názov / Host | Hodnota                |
|-------|--------------|------------------------|
| A     | `@` (prázdne) | `76.76.21.21`          |
| CNAME | `www`        | `cname.vercel-dns.com.` |

- Zmaž staré A / CNAME záznamy pre `@` a `www` (aktuálne doména smeruje na Shoptet).
- Presné hodnoty vždy over v Verceli (Settings → Domains) – Vercel môže ukázať aj vlastný CNAME pre projekt; vtedy použi ten.
- MX záznamy (e-mail) nechaj tak.
- Propagácia trvá zvyčajne do hodiny, SSL certifikát vystaví Vercel automaticky.

## Úpravy
Texty sa menia priamo v `index.html`. Každý `git push` do hlavnej vetvy Vercel automaticky nasadí.
Obálky kníh sa načítavajú z CDN luc.sk; odkazy na tituly vedú na luc.sk.
