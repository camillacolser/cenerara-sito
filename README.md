# Sito della Cenerara

Sito statico di una pagina pubblicato con GitHub Pages su **www.lacenerara.com**
(`lacenerara.com` reindirizza lì da solo).

- `index.html`, `style.css`, `favicon.svg`: il sito; non c'è niente da compilare.
- `CNAME`: il dominio del sito, serve a GitHub Pages. Non cancellarlo.
- `.nojekyll`: dice a GitHub di pubblicare i file così come sono.

Ogni modifica pushata su `main` va online da sola in un paio di minuti.

## Pagina provvisoria
Oggi il sito è una pagina sola con sfondo, contatti, link ad Airbnb, Instagram e Google Maps,
in attesa del sito completo. La bozza del sito completo è nel branch `bozza-completa`.

- **Foto di sfondo**: caricarla come `foto/sfondo.jpg` (JPG orizzontale, ~2000 px di lato,
  meno di 500 KB). Non serve toccare il codice: finché il file non c'è resta lo sfondo verde.
- **Logo**: caricarlo come `logo.png` (o `.svg`) e in `index.html` sostituire il titolo
  `<h1 class="title">` con la riga indicata nel commento.

## Attivare GitHub Pages (una volta sola)
Settings → Pages:
1. Source: "Deploy from a branch", branch `main`, cartella `/ (root)`, Save.
2. Custom domain: `www.lacenerara.com`, Save.
3. Quando il controllo DNS è verde, spuntare **Enforce HTTPS** (il certificato è gratuito,
   può volerci fino a un'ora).

## DNS su Squarespace
Squarespace → Domini → lacenerara.com → DNS:

1. Togliere i record "Squarespace Defaults" (puntano al vecchio sito scaduto).
   **Non toccare** eventuali record MX/TXT dell'email, se l'email del dominio è in uso.
2. Aggiungere:

| Host | Tipo  | Dati                     |
|------|-------|--------------------------|
| @    | A     | 185.199.108.153          |
| @    | A     | 185.199.109.153          |
| @    | A     | 185.199.110.153          |
| @    | A     | 185.199.111.153          |
| www  | CNAME | camillacolser.github.io  |

La propagazione richiede da qualche minuto a qualche ora.

Consigliato: impostazioni dell'account GitHub → Pages → **Verified domains**, aggiungere
`lacenerara.com` e creare su Squarespace il record TXT che GitHub indica: così nessun altro
può usare il dominio su GitHub Pages.

Costo: 0 € di hosting; resta solo il rinnovo annuale del dominio su Squarespace.
