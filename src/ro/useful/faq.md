---
icon: question
label: FAQ
route: /faq
tags: useful
---
# Întrebări Frecvente (FAQ)

## Ce tipuri de înregistrări sunt acceptate?

- A
- AAAA
- CAA
- CNAME
- DS
    - Notă: Acestea pot fi folosite doar în combinație cu înregistrări NS, care sunt utilizate pentru DNSSEC.
- MX
- NS
    - Notă: Acestea sunt oferite doar în cazuri specifice. Consultați [`Cine poate folosi înregistrări NS?`](#who-can-use-ns-records) pentru mai multe informații.
- SRV
- TXT
- URL
    - Notă: Aceste înregistrări folosesc Cloudflare pentru redirecționare, nu este un tip real de înregistrare DNS.

## De ce domeniul meu încă redirecționează către site-ul is-a.dev?
Acest lucru se întâmplă de obicei din cauza cache-ului browserului dvs. care devine invalid și [ștergerea cache-ului browserului](https://support.google.com/accounts/answer/32050) ar trebui să rezolve această problemă.

## Pot folosi o înregistrare CNAME împreună cu alte înregistrări?
Nu puteți solicita un subdomeniu și nici nu puteți trimite modificări care conțin un CNAME împreună cu alte înregistrări (A, AAAA, MX, TXT, etc...)

## Cât timp va dura până când PR-ul meu va fi acceptat?
Când ajungem la el. Întotdeauna dorim să așteptați cât mai puțin posibil. Dar administratorii nu pot fi mereu online. Avem școală și muncă, acesta este doar un proiect secundar. Fiți răbdători și vom ajunge la el cât mai curând posibil! Pentru o șansă de revizuire mai rapidă, trimiteți PR-ul dvs. în [#⁠pull-requests](https://discord.com/channels/830872854677422150/1130858271620726784) pe [serverul nostru Discord](https://discord.gg/is-a-dev-830872854677422150).

## Ce servicii acceptați?
Acceptăm aproape toate serviciile, însă acestea sunt principalele servicii pe care oamenii le folosesc cu is-a.dev:

- Cloudflare Pages
- GitHub Pages
- Netlify
- Railway
- Vercel

## Pot crea subdomenii imbricate? (sub-subdomenii)
Da, puteți! Pur și simplu creați un fișier precum `blog.example.json` și urmați aceleași instrucțiuni ca și în cazul înregistrării `example.json`. Vă rugăm să rețineți că pentru a avea `blog.example.is-a.dev`, trebuie să dețineți și `example.is-a.dev`.

## Cum îmi pot edita domeniul?
Puteți edita fișierul JSON al domeniului dvs. și puteți trimite un pull request pentru a vă edita domeniul.

## Cum îmi pot șterge domeniul?
Puteți șterge fișierul JSON al domeniului dvs. și puteți trimite un pull request pentru a vă șterge domeniul.

## Primesc în continuare o eroare SSL în timp ce folosesc GitHub Pages, cum o pot rezolva?
Trebuie să mergeți la setările GitHub Pages din repository-ul site-ului dvs. web (probabil numit ceva de genul `github-username.github.io`) și să vă asigurați că opțiunea `Enforce HTTPS` este activată pentru a evita această eroare.

## Pot fi administrator/mă pot alătura echipei?
Nu, alegem manual fiecare membru al echipei noastre. Vă puteți crește șansele de a fi ales ajutând oamenii în forumurile noastre de ajutor.

## Am divulgat accidental informații sensibile în PR-ul meu, cum pot obține ștergerea PR-ului?
Dacă PR-ul dvs. **nu a fost încă acceptat**, puteți trimite un email la [security@is-a.dev](mailto:security@is-a.dev) sau să trimiteți un DM lui [williamharrison pe Discord](https://discord.com/users/853158265466257448). Dacă PR-ul dvs. a fost deja acceptat, din păcate nu mai putem face nimic.

## Pot folosi domeniul meu pentru un server Minecraft?
Da, puteți. Puteți folosi o înregistrare A combinată cu o înregistrare SRV pentru aceasta.

Consultați [acest articol](https://www.namecheap.com/support/knowledgebase/article.aspx/9765/2208/how-can-i-link-my-domain-name-to-a-minecraft-server) de la Namecheap pentru suport.

## Cine poate folosi înregistrări NS?
Permitem înregistrări NS pentru următoarele motive și cazuri de utilizare:

- Utilizatorii care necesită o zonă privată, deoarece folosesc adresa IP de acasă prin **o înregistrare `A` SAU `AAAA`** în spatele unui serviciu proxy precum Cloudflare. **TREBUIE să furnizați dovezi de utilizare pentru ca acest motiv să fie aprobat.**
- Când un serviciu terț (de exemplu, Aternos, Wix sau Squarespace) impune înregistrări NS specifice și nu puteți gestiona înregistrările DNS direct sub acel domeniu. Aprobarea necesită:
  - Documentație sau dovezi de la serviciul terț care să specifice explicit această cerință.
  - Dovada că nicio configurație DNS alternativă (CNAME, înregistrări A etc.) nu poate obține același rezultat.

Nu permitem înregistrări NS pentru:

- Configurări doar pentru comoditate: Unde alternative precum înregistrări A, AAAA sau CNAME sunt suficiente.
- Scopuri non-operaționale: Configurări de vanitate, configurări estetice sau utilizare speculativă.
- Revendicări neverificabile: Orice configurare care nu are dovezi clare și concrete ale necesității.
- Configurări înșelătoare: Încercări de a denatura proprietatea, de a induce în eroare utilizatorii sau de a impersona o altă entitate.
- Riscuri de securitate: Configurații care introduc vulnerabilități, cum ar fi delegarea către servere neîncredere sau nesigure.

***Ne rezervăm dreptul de a refuza înregistrările NS la discreția noastră, indiferent de motiv.***

## De ce sunteți atât de stricți cu înregistrările NS?
Trebuie să fim stricți cu privire la cui delegăm înregistrări NS, deoarece acestea permit utilizatorului final să facă practic *orice dorește* cu subdomeniul său.

După cum vă puteți probabil imagina, acest lucru poate deschide ușa pentru multe abuzuri, motiv pentru care nu sunt disponibile gratuit pentru toată lumea.

Dacă am putea, am delega înregistrări NS tuturor celor care le-ar dori, dar nu trăim într-o lume perfectă, așa că din păcate nu putem face acest lucru.

## Cum pot face modificări la subdomeniul meu is-a.dev?
1. **Deschideți fișierul JSON:** Navigați la directorul `domains` în fork-ul dvs. și deschideți fișierul JSON corespunzător subdomeniului dvs. (`domains/subdomain.json`).
2. **Faceți modificările:** Editați fișierul JSON (sau ștergeți-l) pentru a reflecta modificările pe care doriți să le faceți.
3. **Salvați modificările:** După ce ați făcut modificările, salvați-le în fork-ul dvs.
4. **Încărcați modificările:** Încărcați modificările în repository-ul dvs. fork pe GitHub.
5. **Trimiteți un Pull Request:** Mergeți la repository-ul dvs. fork pe GitHub și deschideți un pull request.
6. **Așteptați ca PR-ul să fie acceptat:** După ce ați trimis pull request-ul, așteptați să fie revizuit și acceptat. După ce pull request-ul dvs. a fost acceptat, modificările ar trebui să fie active!

**Notă:** Asigurați-vă că monitorizați PR-ul pentru revizuiri în cazul în care sunt solicitate modificări.