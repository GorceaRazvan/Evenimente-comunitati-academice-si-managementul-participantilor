# Cerinte Functionale si Nefunctionale - UniMeet

Acest document contine lista preliminara de cerinte pentru platforma **UniMeet**, stabilite in urma definirii temei. Unele detalii pot suferi mici ajustari pe masura ce avansam cu implementarea.

---

## 1. Cerinte Functionale si Prioritizare

Am impartit cerintele in **MVP** (necesare pentru fluxul de baza), **Extensie** (dupa MVP) si **Optional** (doar daca ramane timp).

| Nr. | Cerinta | Descriere pe scurt | Prioritate |
| :--- | :--- | :--- | :--- |
| 1 | Autentificare si Roluri | Utilizatorii isi pot face cont si se pot loga. Exista rolurile de baza Utilizator si Organizator; tipul de participare (Participant sau Speaker) se alege pentru fiecare eveniment. | **MVP** |
| 2 | Creare si Listare Evenimente | Organizatorul poate adauga un eveniment (titlu, descriere, data si locatie); vizitatorii pot vedea lista si detaliile. | **MVP** |
| 3 | Inscriere ca Participant | Un utilizator autentificat se poate inscrie ca participant la un eveniment. | **MVP** |
| 4 | Trimitere Lucrare (Call for Papers) | Un utilizator autentificat poate trimite o propunere cu titlu si abstract pentru un eveniment. | **MVP** |
| 5 | Aprobare / Respingere Lucrari | Organizatorul evenimentului poate aproba sau respinge propunerile primite. | **MVP** |
| 6 | Verificare Status Personal | Utilizatorul isi poate vedea inscrierile si statusul propunerilor. | **MVP** |
| 7 | Construire Agenda | Organizatorul poate aloca prezentarile aprobate unei sali si unui interval orar. | **Extensie** |
| 8 | Afisare Publica Agenda | Pe pagina evenimentului se afiseaza programul pe ore si sali. | **Extensie** |
| 9 | Verificare Suprapuneri Agenda | La adaugarea unei prezentari, backend-ul verifica suprapunerile din aceeasi sala. | **Extensie** |
| 10 | Formular de Feedback | Dupa eveniment, participantii pot lasa o nota (de la 1 la 5) si un comentariu scurt despre cum a decurs conferinta/workshopul. | **Optional** |
| 11 | Generare Diploma PDF | Dupa completarea feedback-ului, utilizatorul poate apasa pe un buton care ii genereaza o diploma PDF cu numele lui si numele evenimentului. | **Optional** |

---

## 2. Cerinte Nefunctionale

1. **Securitate de baza (Critic):** Parolele nu se salveaza in clar in baza de date, ci criptate (hash). Rutele de organizator trebuie sa verifice daca utilizatorul chiar are dreptul sa modifice evenimentul.
2. **Validarea datelor (Critic):** Formularele nu trebuie sa permita trimiterea de campuri goale obligatorii sau inscrieri duble ale aceluiasi utilizator la acelasi eveniment.
3. **Interfata usor de folosit / Responsive (Important):** Paginile sa arate decent atat pe laptop, cat si pe telefon (vom folosi probabil Tailwind CSS sau Bootstrap pentru a nu scrie tot CSS-ul de la zero).
4. **Timp de raspuns rezonabil (Important):** Incarcarea listei de evenimente si a agendei sa se faca rapid, iar generarea PDF-ului (daca ajungem sa o implementam complet) sa foloseasca un template simplu ca sa nu blocheze serverul.    