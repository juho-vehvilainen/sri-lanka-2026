# Sri Lanka 9.–18.10.2026

Juhon, Svenin, Macosin ja Markon yhteinen matkaopas: kuka on missä ja milloin, päivät, kyydit, illat, varaukset ja käytännöt.

Staattinen sivu ilman build-vaihetta: `index.html` + `images/`. Fontti (Bricolage Grotesque) ladataan Google Fontsista, muuten kaikki on repossa.

## Julkaisu

- **Live:** https://juho-vehvilainen.github.io/sri-lanka-2026/
- **Repo:** https://github.com/juho-vehvilainen/sri-lanka-2026

Jokainen `main`-haaraan puskettu muutos julkaistaan automaattisesti GitHub Actionsilla (`.github/workflows/`), noin minuutissa.

### GitHub Pagesin päälle kytkeminen (uuteen repoon)

1. Luo GitHubiin julkinen repo ja puske tämä kansio sinne.
2. Avaa repossa **Settings → Pages**.
3. Kohdassa **Build and deployment** valitse *Source: GitHub Actions*. Repon workflow hoitaa julkaisun jokaisella puskulla.
4. Ilman workflowta toimii myös *Source: Deploy from a branch*, *Branch: `main`*, kansio *`/ (root)`*.
5. Osoite näkyy samalla Pages-sivulla, muotoa `https://<käyttäjä>.github.io/<repo>/`.

`robots.txt` ja `noindex` pitävät sivun poissa hakukoneista, mutta sivu ei ole yksityinen: kuka tahansa osoitteen tietävä näkee sen.

## Rakenne

- `index.html`: koko sivu, CSS ja JS samassa tiedostossa. Aikajana, reittikartta ja kuvakkeet ovat inline-SVG:tä.
- `images/`: WebP-kuvat kahtena kokona (`nimi.webp` 1600 px, `nimi-800.webp` 800 px).
- `reference.html`: sivun aiempi versio, jäi pohjaksi.

## Muokkaaminen

- **Aikajana** (`<svg class="tl">`): 920 px = 240 tuntia, eli x = 72 + tunnit × 3,833, kun tunnit lasketaan pe 9.10 klo 00.00 alkaen. Palkkien värit vaihtuvat siirtymähetkillä: la 14.30 (Colombo → Weligama), to 11.30 (→ Ella), la 6.00 (→ Negombo).
- **Värit** ovat CSS-muuttujia `:root`issa: `--city` Colombo, `--ocean` Weligama, `--train` Ella, `--dusk` Negombo, `--tea` kotiin. Tumma teema määritellään samoille muuttujille.
- **Varauslista** tallentuu selaimen `localStorage`en avaimilla `sl26-check-*`. Ruksit näkyvät vain sillä laitteella, jolla ne on tehty.
- **Uusi kuva**: tarkista lisenssi lähdesivulta, pienennä enintään 1600 px leveäksi, tallenna WebP:ksi, lisää `width`, `height`, suomenkielinen `alt` ja `loading="lazy"` sekä rivi Kuvat-osioon.

## Kuvat

Kaikki valokuvat Wikimedia Commonsista (CC BY, CC BY-SA, Free Art License) tai Unsplashista (Unsplash License). Kuvaajat, lisenssit ja lähdelinkit ovat sivun Kuvat-osiossa.
