# Algoritmi pe Matrice – Vizualizator Interactiv

Aplicație web care permite explorarea algoritmilor de căutare a drumului optim într-o matrice, printr-o interfață vizuală intuitivă. Realizat cu HTML, CSS și JavaScript.

## Demo live

Aplicația poate fi vizitată la linkul acesta: [https://alessio-antochi.github.io/algoritmi-matrice/](https://alessio-antochi.github.io/algoritmi-matrice/)

---

## Funcționalități principale

### 🔹 Selectarea punctelor de start și finish

-   **Buton Start**: activează selecția celulei de start.
-   **Buton Finish**: activează selecția celulei de sosire.

### 🔹 Editarea matricei

-   **Desenare pereți**: adaugă obstacole.
-   **Radieră**: șterge celulele personalizate.

### 🔹 Controlul execuției

-   **Play**: pornește algoritmul selectat.
-   **Generare labirint**: creează un labirint valid folosind DSU (Disjoint Set Union) pe o listă de muchii aleatoare.
-   **Ștergere**: curăță matricea cu o animație progresivă.

### 🔹 Selectare algoritm

-   Interfață pentru alegerea dintre: **BFS**, **DFS**, **A\***.
-   Fiecare algoritm este implementat separat.

### 🔹 Vizualizare cod sursă

-   Secțiune interactivă cu exemple de cod pentru algoritmul selectat, disponibile în:
    -   C++
    -   C#
    -   Java
    -   Python

### 🔹 Cod viewer

-   La alegerea unui limbaj + algoritm se deschide un `<div>` care:
    -   Afișează cod HTML-encoded din `./algorithms-encoded/[limbaj]/[algoritm].txt`
    -   Folosește **Prism.js** pentru evidențierea sintaxei
    -   Include 3 butoane:
        -   **Copiere** cod
        -   **Descărcare** fișier original (`./algorithms/[limbaj]/[algoritm].[extensie]`)
        -   **Close** pentru închidere viewer

---

## Animații și logică asincronă

-   Se folosește `async/await` împreună cu o funcție `sleep(ms)` pentru a crea efectul de animare.
-   Permite observarea pas cu pas a execuției algoritmilor.

## Reconstrucția drumului

-   Toți algoritmii utilizează un vector de **părinți** (tati) pentru fiecare celulă:
    ```js
    parentMap[cell] = parentCell;
    ```
-   Drumul optim este reconstruit de la finish spre start folosind aceste referințe.

## Statistici afișate

După execuția unui algoritm, este generat un div care conține:

-   Numărul total de pași executați
-   Distanța minimă dacă a fost găsit un drum

---

## Structura proiectului

```
.
├── index.html
├── styles.css
├── icon.png
├── astar.js
├── bfs.js
├── dfs.js
├── main.js
├── buttons.js
├── gridStuff.js
├── dialogue.js
├── drawer.js
├── mazeGen.js
├── codeHandler.js
├── sidebarStuff.js
├── algorithms/
│   └── [limbaj]/[algoritm].[extensie]
├── algorithms-encoded/
│   └── [limbaj]/[algoritm].txt
├── prism/
│   ├── prism.js
│   └── prism.css
```

## Licență

Acest proiect este realizat pentru scop educațional și poate fi extins sau modificat liber.

---

## Autor

**Antochi Alessio Roberto** – GitHub: [https://github.com/alessio-antochi](https://github.com/aliessio-antochi)
