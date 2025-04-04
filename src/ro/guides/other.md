---
label: Alte servicii
icon: server
tags: guides
---

# Configurarea altor servicii cu is-a.dev

## Configurarea înregistrărilor DNS

Citiți [structura fișierului de domeniu](../useful/domain-structure) și configurați înregistrările în consecință.

## Configurarea serverului

După ce pull request-ul este aprobat, configurați serverul dvs. (apache, nginx, etc.) pentru a funcționa cu `subdomain.is-a.dev`. Dacă nu sunteți sigur cum să vă configurați serverul, puteți crea o problemă pentru asistență.

De asemenea, ar trebui să includeți `subdomain.is-a.dev` în certificatul dvs. SSL pentru a elimina erorile de certificat.