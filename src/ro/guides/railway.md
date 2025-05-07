---
icon: /media/railway.png
label: Railway
tags: guides
---

# Configurarea is-a.dev cu Railway

## Obținerea înregistrării CNAME

1. Navigați la [dashboard](https://railway.app/dashboard)
2. Navigați la proiect.
3. Navigați la serviciu.
4. Comutați la fila **Setări**.
5. Faceți clic pe butonul **+ Domeniu personalizat**.
6. Introduceți subdomeniul `is-a.dev` pe care doriți să îl utilizați.
7. Copiați câmpul **Valoare**.
8. Pentru domeniu, creați JSON-ul astfel:
```json
{
  "owner": {
    "username": "your-username",
    "email": "your-email"
  },
  "record": {
    "CNAME": "the-value-railway-gave-you"
  }
}
```
9. După ce ați creat fișierul, trebuie să faceți un pull request.
!!!
**Adăugarea unei previzualizări a site-ului web este necesară**, deoarece valoarea CNAME oferită de Railway nu vă arată efectiv site-ul web pe care îl rulați.
!!!


**După ce PR-ul a fost acceptat, înregistrările DNS vor fi actualizate în câteva minute.**
**Dacă PR-ul a fost acceptat dar înregistrările DNS nu s-au actualizat și ați așteptat 48 de ore, deschideți o problemă pe GitHub sau un thread de ajutor pe serverul Discord is-a.dev.**