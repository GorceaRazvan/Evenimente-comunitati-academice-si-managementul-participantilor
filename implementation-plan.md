# Planul de Implementare si Justificarea Tehnologiilor - UniMeet

Acest document prezinta o abordare etapizata, potrivita pentru inceputul proiectului: finalizam mai intai un MVP mic si testabil, apoi adaugam extensii daca timpul permite.

---

## 1. Justificarea Tehnologiilor Propuse

- **Frontend - React.js:**
  Am ales o interfata de tip *Single Page Application (SPA)* pentru ca aplicatia are mai multe formulare si tabele care trebuie sa se actualizeze rapid (cum ar fi filtrarea agendei pe sali sau schimbarea statusului unei lucrari din `In asteptare` in `Aprobat` fara sa dam refresh la toata pagina). Inclinam spre **React.js** deoarece suntem mai familiari cu el.
- **Backend - Python (FastAPI sau Django):**
  Python este foarte comod pentru lucrul cu date si ne ajuta mult la partea de generare de fisiere PDF (unde exista librarii simple precum `ReportLab` sau `FPDF`). Ca framework web, prima optiune este **FastAPI** pentru ca este rapid de configurat si face automat pagina de Swagger (unde putem testa rutele API inainte sa fie gata frontend-ul). Pastram si **Django** ca varianta de rezerva daca vedem ca ne ajuta mai mult sistemul lui de autentificare predefinit.
- **Baza de date - PostgreSQL:**
  Datele din proiectul nostru au legaturi clare intre ele (un eveniment are mai multe lucrari, o lucrare apartine unui speaker si este pusa intr-un slot de agenda). O baza de date relationala precum PostgreSQL ne ajuta sa pastram aceste legaturi corecte.

---

## 2. Planul de Implementare

Implementam functionalitatile in pasi mici. MVP-ul se considera gata cand utilizatorul poate parcurge fluxul de evenimente si propuneri cap-coada.

### Etapa 1: Documentatie si Setup
- Stabilirea cerintelor MVP si a structurii preliminare a datelor.
- Crearea documentatiei si a wireframe-urilor.
- Alegerea unei singure variante pentru frontend si backend, apoi configurarea proiectelor.

### Etapa 2: Evenimente si propuneri
- Implementarea autentificarii si a rolurilor minime: utilizator si organizator.
- Crearea si listarea publica a evenimentelor.
- Inscrierea ca participant sau trimiterea unei propuneri de prezentare.
- Panou simplu pentru organizator: vizualizare, aprobare si respingere a propunerilor.
- Pagina „Activitatea mea” pentru afisarea inscrierilor si statusurilor.
- Testarea fluxului complet si a validarilor esentiale (campuri obligatorii, inscrieri duplicate si acces organizator).
- Alocarea prezentarilor aprobate la o sala si un interval orar.
- Afisarea publica a agendei si prevenirea suprapunerilor in aceeasi sala.

---

## 3. Riscuri Identificate si Cum le Gestionam

1. **Extinderea prea rapida a MVP-ului:**
   - *Risc:* Agenda si certificatele pot consuma timp inainte ca fluxul principal sa fie functional.
   - *Solutie:* Finalizam si testam mai intai evenimentele, propunerile si statusurile; extensiile raman in afara criteriilor de finalizare a MVP-ului.
2. **Drepturi incorecte in panoul organizatorului:**
   - *Risc:* Un utilizator obisnuit ar putea incerca sa modifice evenimente sau propuneri.
   - *Solutie:* Verificam rolul in backend pentru fiecare actiune de organizator; interfata singura nu este o masura de securitate.

---

## 4. Impartirea Responsabilitatilor in Echipa

Chiar daca ne vom ajuta reciproc la integrare si testare, responsabilitatile principale sunt impartite astfel:

### Bogdan Alessio (`alessio.bogdan06@e-uvt.ro`) - Backend & Baza de Date
- Configurarea bazei de date PostgreSQL si scrierea modelelor pentru tabele.
- Implementarea serverului Python, a autentificarii si a verificarilor de roluri.
- Crearea rutelor API pentru evenimente, inscrieri, aprobarea lucrarilor si validarea agendei.
- Implementarea functiei care genereaza certificatul PDF pe baza datelor din baza de date.

### Gorcea Razvan-Alin (`razvan.gorcea06@e-uvt.ro`) - Frontend (UI/UX) & Integrare API
- Realizarea wireframe-urilor si a designului paginilor in React.js.
- Crearea formularelor (Login, Creare Eveniment, Inscriere / Call for Papers, Feedback) si validarea campurilor in interfata.
- Dezvoltarea paginii de administrare pentru organizator si a tabelului interactiv pentru agenda evenimentului.
- Legarea interfetei de backend prin request-uri HTTP si afisarea mesajelor de confirmare sau de eroare.