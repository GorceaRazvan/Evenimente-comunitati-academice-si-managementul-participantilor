# UniMeet - Platforma integrata pentru managementul evenimentelor academice

Proiect realizat pentru disciplina **Tehnologii Web (2026)** - Universitatea de Vest din Timisoara.  
**Tema:** P6 - Evenimente, comunitati academice si managementul participantilor  
**Repository:** [Link GitHub](https://github.com/GorceaRazvan/Evenimente-comunitati-academice-si-managementul-participantilor)

---

## Structura Documentatiei

Toate detaliile preliminare ale proiectului sunt impartite in folderul `docs/`:

- [Cerinte Functionale si Nefunctionale](./docs/requirements.md)
- [Scenarii de Utilizare (Use Cases)](./docs/use-cases.md)
- [Wireframe-uri si Flux de Navigare](./docs/wireframes/README.md)
- [Arhitectura Aplicatiei](./docs/architecture.md)
- [Modelul Preliminar de Date si Endpoint-uri](./docs/data-model.md)
- [Planul de Implementare si Tehnologii](./docs/implementation-plan.md)

---

## 1. Descrierea Proiectului si Problema Abordata

**UniMeet** isi propune sa aduca tot acest flux intr-o singura aplicatie web simpla. Ideea de baza este sa acoperim traseul de la "Call for Papers" (trimiterea unei propuneri de prezentare) si inscrierea simpla ca participant, pana la afisarea agendei pe sali si generarea diplomei de participare la final.

---

## 2. Obiectivele Proiectului

Pentru MVP, ne propunem sa livram fluxul de baza:

1. **Evenimente:** Organizatorul poate crea evenimente, iar vizitatorii pot vedea lista si detaliile acestora.
2. **Inscriere si propuneri:** Un utilizator autentificat se poate inscrie ca participant sau poate trimite o propunere de prezentare.
3. **Evaluare si status:** Organizatorul poate aproba sau respinge propunerile, iar utilizatorul isi poate vedea statusul.

Agenda publica, feedbackul si certificatele PDF sunt extensii ulterioare, nu conditii pentru finalizarea MVP-ului.

---

## 3. Utilizatori Vizati

- **Studenti (Licenta / Master / Doctorat):** Vor sa vada rapid ce evenimente au loc in facultate, sa se inscrie usor si sa primeasca adeverinta/diploma de participare.
- **Cadre didactice si Speakeri:** Vor un loc clar unde sa trimita prezentarile, sa vada daca au fost acceptate si in ce sala/interval orar au fost repartizati.
- **Organizatori (Profesori coordonatori, asociatii studentesti, secretariat):** Au nevoie de un panou de unde sa creeze evenimentul, sa accepte lucrarile si sa faca programul fara sa mai lucreze in mai multe fisiere separate.

---

## 4. Echipa si Responsabilitati

| Student | Email | Responsabilitati in proiect |
| :--- | :--- | :--- |
| **Bogdan Alessio** | `alessio.bogdan06@e-uvt.ro` | **Backend & Baza de date:** Proiectarea tabelelor in PostgreSQL, implementarea serverului in Python, logica de autentificare, rutele API si partea de generare a diplomelor PDF. |
| **Gorcea Razvan-Alin** | `razvan.gorcea06@e-uvt.ro` | **Frontend (UI/UX) & Integrare API:** Designul paginilor si al wireframe-urilor, dezvoltarea interfetei web, formularele de inscriere, afisarea agendei si legatura cu backend-ul prin request-uri HTTP. |

---

## 5. Functionalitati Propuse

1. **Gestionarea evenimentelor, inscrierilor si propunerilor:** Organizatorul creeaza evenimente; utilizatorii se inscriu ca participanti sau trimit propuneri; organizatorul le evalueaza, iar utilizatorii isi vad statusul (`In asteptare` / `Aprobat` / `Respins`).
2. **Agenda evenimentului:** Organizatorul asociaza prezentarile aprobate cu sali si intervale orare, iar agenda este afisata public.
3. **Feedback si certificate PDF:** Chestionar dupa eveniment si certificat simplu generat pentru participant.

---

## 6. Tehnologii Alese

- **Frontend:** **React.js** (sau Vue.js, dar in principiu mergem pe React pentru ca avem mai multe exemple si componente gata de folosit pentru formulare si tabele).
- **Backend:** **Python** cu **FastAPI** (luam in calcul si Django daca vedem ca avem nevoie de panoul de admin deja construit, dar momentan FastAPI ni se pare mai usor de legat cu React prin JSON).
- **Baza de date:** **PostgreSQL** (baza de date relationala, potrivita pentru legaturile dintre utilizatori, evenimente si inscrieri).
- **Alte librarii (de testat pe parcurs):** `ReportLab` sau `FPDF` in Python pentru generarea diplomelor PDF.