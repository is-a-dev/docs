---
icon: /media/hashnode.svg
label: Hashnode
tags: guides
---
# Blog Hashnode

Când creezi blogul tău Hashnode, Hashnode îți oferă gratuit un subdomeniu `hashnode.dev`. Cu toate acestea, poți configura propriul tău subdomeniu `is-a.dev`.
În acest ghid vei învăța cum să realizezi acest lucru.

---

1. Conectează-te la contul tău Hashnode.
2. Dă click pe **avatarul** tău din colțul din stânga-jos al paginii pe **desktop** sau din colțul din dreapta-sus pe **mobil**.
   ![Feed-ul Hashnode](https://cdn.hashnode.com/res/hashnode/image/upload/v1614932849541/cBNDGKXMj.png?auto=compress)
3. Dă click pe opțiunea **Blog Dashboard** din fereastra popup pentru a accesa panoul de control al blogului tău.
   ![Feed-ul Hashnode](https://cdn.hashnode.com/res/hashnode/image/upload/v1614937218081/InvxVHXDy.png?auto=compress)
4. Navighează la fila **Domain** și introdu domeniul tău fără prefixele **www** sau **https://** în câmpul de text furnizat. Apoi dă click pe butonul **Update** pentru a continua.
   ![Fila Domain a blogului Hashnode](https://cdn.hashnode.com/res/hashnode/image/upload/v1614937377176/0cwddAywO.png?auto=compress)
5. Mergi la fork-ul tău al repository-ului `is-a-dev/register`, editează fișierul JSON al subdomeniului tău, asigură-te că ștergi orice înregistrări vechi, apoi adaugă aceasta la cheia `record` și creează un PR:
```json
"CNAME": "hashnode.network"
```

## Configurare

Odată finalizat, blogul tău Hashnode ar trebui să fie configurat pentru a utiliza subdomeniul tău. Aceste modificări ar putea dura de la 1 oră până la aproximativ 48 de ore, așa că te rugăm să fii răbdător. Cel mai probabil va fi gata în decurs de o oră.
După ce DNS-ul s-a propagat, poți începe să te bucuri de blogul tău Hashnode cu drăgălașul tău subdomeniu `.is-a.dev`!

## Ai nevoie de mai mult ajutor?

Dacă întâmpini probleme sau ai nevoie de asistență suplimentară, ia în considerare următoarele resurse:
- [Ghidul de mapare a domeniului Hashnode](https://support.hashnode.com/docs/mapping-domain/): Acest articol de asistență oferă instrucțiuni detaliate despre maparea domeniului tău în Hashnode.
- [Centrul de asistență Hashnode](https://support.hashnode.com/): Pentru ajutor mai general legat de Hashnode, vizitează Centrul lor de asistență.

Te rugăm să reții că is-a.dev nu este afiliat cu Hashnode. Dacă întâmpini probleme cu blogul tău Hashnode, te rugăm să cauți ajutor prin canalele de asistență Hashnode. Nu putem oferi asistență pentru probleme specifice Hashnode.