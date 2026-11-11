# Scenarii de Utilizare - UniMeet

Scenariile de mai jos descriu functionalitatile MVP si cateva extensii posibile.

## 1. Vizualizarea si crearea evenimentelor

- **Pasi:**
  1. Vizitatorul deschide lista de evenimente si selecteaza un eveniment pentru a-i vedea detaliile.
  2. Organizatorul se autentifica si deschide formularul de creare a unui eveniment.
  3. Organizatorul completeaza detaliile si publica evenimentul.
- **Rezultat:** Evenimentul creat apare in lista publica.

## 2. Inscrierea la un eveniment sau trimiterea unei propuneri

- **Actor:** Utilizator autentificat.
- **Pasi:**
  1. Utilizatorul selecteaza un eveniment.
  2. Alege sa se inscrie ca participant sau sa trimita o propunere de prezentare.
  3. Daca trimite o propunere, completeaza titlul si abstractul.
  4. Sistemul salveaza inscrierea sau propunerea; propunerea primeste statusul `In asteptare`.
- **Rezultat:** Inscrierea sau propunerea apare in sectiunea „Activitatea mea”.
- **Exceptii:** Sistemul respinge inscrierile duplicate si propunerile fara titlu sau abstract.

## 3. Evaluarea propunerilor si verificarea statusului

- **Pasi:**
  1. Organizatorul deschide lista propunerilor pentru evenimentul sau.
  2. Organizatorul analizeaza o propunere si o aproba sau o respinge.
  3. Utilizatorul deschide sectiunea „Activitatea mea”.
  4. Utilizatorul vede statusul actualizat al propunerii.
- **Rezultat:** Statusul propunerii este vizibil utilizatorului care a trimis-o.

## 4. Adaugarea unei prezentari in agenda (Extensie)

- **Pasi:**
  1. Organizatorul deschide agenda evenimentului.
  2. Alege o propunere aprobata si ii atribuie o sala si un interval orar.
  3. Salveaza programul.
  4. Vizitatorul deschide pagina evenimentului si consulta agenda.
- **Rezultat:** Programul evenimentului este vizibil participantilor.

## 5. Trimiterea feedbackului si descarcarea certificatului (Optional)

- **Pasi:**
  1. Participantul deschide evenimentul incheiat din lista activitatilor sale.
  2. Completeaza si trimite formularul de feedback.
  3. Daca este disponibil, participantul selecteaza optiunea de descarcare a certificatului.
- **Rezultat:** Feedbackul este salvat, iar certificatul este disponibil pentru descarcare.