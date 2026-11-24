# Black box: kijk naar input en output

## TODO benoem even wat input en output zijn. Verwerk dan in uitleg het woord "methode".
Als je een programma ontwerpt, hoef je niet meteen te weten hoe je het gaat programmeren. Begin met de vraag: **wat moet erin gaan, en wat moet eruit komen?**

Een **black box** helpt je om op dat gewenste gedrag te focussen. Je beschrijft of test het systeem aan de hand van de input die je geeft en de output die je verwacht. Wat er binnenin gebeurt, is op dat moment nog niet belangrijk. De implementatie kan later komen.

```{figure} ../../figures/blackbox.jpg
---
width: 50%
align: center
---
Je ziet de input en de output. Wat er binnenin de black box gebeurt, hoef je nog niet te weten.
```

Bijvoorbeeld: stel dat we een programma willen maken dat bij elk ingevoerd getal 1 optelt. We kunnen eerst vastleggen welk gedrag we verwachten:

| Input | Verwachte output |
|---:|---:|
| 1 | 2 |
| 2 | 3 |
| 11 | 12 |

Deze tabel beschrijft wat het programma moet doen. We hebben nog niet besloten hoe we dat programmeren. Later kunnen we de code schrijven en testen of die bij de voorbeelden de verwachte output geeft. Verschillende implementaties kunnen hetzelfde gedrag opleveren.

## Functies/Methode
Functies zijn ..., ze zijn handig omdat ... In Java worden functies ook wel **methode** genoemd. Het blackbox principe is hier handig om in te zetten, je hoeft bij methodes namelijk niet precies te weten wat erin gebeurt, alleen wat je erin moet stoppen, en wat er vervolgens uit komt, oftewel **hoe je het gebruikt**.

## Oefening: welke code past bij welke beschrijving?

Hieronder staan vier tabellen met input en verwachte output, en vier Java-codefragmenten. Sleep elk programma naar de tabel waarvan de voorbeelden passen bij het gedrag van dat programma. Gebruik alle programma’s precies één keer. Klik daarna op **Controleer**.


```{raw} html
<div id="blackbox-match" class="bb-widget">
  <style>
    #blackbox-match { font-family: system-ui, sans-serif; color: #172033; max-width: 1050px; margin: 1rem 0; }
    #blackbox-match * { box-sizing: border-box; }
    #blackbox-match .bb-intro { margin: 0 0 1rem; }
    #blackbox-match .bb-layout { display: grid; grid-template-columns: minmax(230px, .8fr) minmax(450px, 1.5fr); gap: 1rem; align-items: start; }
    #blackbox-match .bb-panel { border: 1px solid #cbd5e1; border-radius: 10px; padding: 1rem; background: #fff; }
    #blackbox-match h3 { font-size: 1.1rem; margin: 0 0 .75rem; }
    #blackbox-match .bb-program { border: 1px solid #94a3b8; border-radius: 8px; padding: .7rem; margin: .6rem 0; background: #f8fafc; cursor: grab; }
    #blackbox-match .bb-program:active { cursor: grabbing; }
    #blackbox-match pre { white-space: pre-wrap; margin: .35rem 0 0; font-size: .88rem; }
    #blackbox-match code { font-family: ui-monospace, SFMono-Regular, Consolas, monospace; }
    #blackbox-match .bb-tables { display: grid; grid-template-columns: repeat(2, minmax(190px, 1fr)); gap: .75rem; }
    #blackbox-match .bb-table-card { border: 1px solid #cbd5e1; border-radius: 8px; padding: .75rem; }
    #blackbox-match .bb-table-card h4 { margin: 0 0 .5rem; }
    #blackbox-match table { border-collapse: collapse; width: 100%; margin-bottom: .6rem; }
    #blackbox-match th, #blackbox-match td { text-align: center; border: 1px solid #cbd5e1; padding: .3rem; }
    #blackbox-match th { background: #f1f5f9; }
    #blackbox-match .bb-drop { min-height: 56px; border: 2px dashed #94a3b8; border-radius: 7px; padding: .55rem; background: #f8fafc; }
    #blackbox-match .bb-drop.bb-over { border-color: #2563eb; background: #eff6ff; }
    #blackbox-match .bb-drop-label { color: #475569; font-size: .9rem; }
    #blackbox-match .bb-assigned { font-weight: 600; }
    #blackbox-match .bb-assigned-code { overflow-x: auto; padding: .45rem; background: #f1f5f9; border-radius: 5px; }
    #blackbox-match button { border: 1px solid #64748b; border-radius: 6px; padding: .4rem .6rem; background: #fff; color: #172033; cursor: pointer; }
    #blackbox-match button:hover { background: #f1f5f9; }
    #blackbox-match .bb-remove { display: block; margin-top: .45rem; font-size: .85rem; }
    #blackbox-match .bb-actions { display: flex; gap: .6rem; margin-top: 1rem; flex-wrap: wrap; }
    #blackbox-match .bb-feedback { min-height: 1.5em; margin: .75rem 0 0; font-weight: 600; }
    @media (max-width: 700px) {
      #blackbox-match .bb-layout { grid-template-columns: 1fr; }
      #blackbox-match .bb-tables { grid-template-columns: 1fr; }
    }
    #blackbox-match .bb-tables {
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: .5rem;
    }

    #blackbox-match .bb-table-card {
      padding: .5rem;
    }

    #blackbox-match .bb-table-card h4 {
      margin-bottom: .35rem;
      font-size: .95rem;
    }

    #blackbox-match table {
      margin-bottom: .4rem;
      font-size: .88rem;
    }

    #blackbox-match th,
    #blackbox-match td {
      padding: .2rem;
    }

    #blackbox-match .bb-drop {
      min-height: 42px;
      padding: .4rem;
    }

    @media (max-width: 420px) {
      #blackbox-match .bb-tables {
        grid-template-columns: 1fr;
      }
    }
  </style>

  <p class="bb-intro">Sleep elk programma naar één tabel. Je kunt een keuze ongedaan maken en opnieuw proberen.</p>
  <div class="bb-layout">
    <section class="bb-panel" aria-label="Java-programma's">
      <h3>Programma’s</h3>
      <div class="bb-programs"></div>
    </section>
    <section class="bb-panel" aria-label="Invoer-uitvoertabellen">
      <h3>Waarnemingen</h3>
      <div class="bb-tables"></div>
    </section>
  </div>
  <div class="bb-actions">
    <button type="button" class="bb-check">Controleer</button>
    <button type="button" class="bb-reset">Opnieuw beginnen</button>
  </div>
  <p class="bb-feedback" aria-live="polite"></p>

  <script>
  (() => {
    const root = document.getElementById('blackbox-match');
    if (!root) return;

    const programs = [
      { id: 'A', title: 'Programma A', code: 'int uitvoer = (int) Math.pow(2, invoer);' },
      { id: 'B', title: 'Programma B', code: 'int uitvoer = invoer + 1;' },
      { id: 'C', title: 'Programma C', code: 'int uitvoer = invoer * invoer;' },
      { id: 'D', title: 'Programma D', code: 'int uitvoer = invoer * 2;' }
    ];

    const tables = [
      { id: '1', rows: [[1, 1], [2, 4], [3, 9]], answer: 'C' },
      { id: '2', rows: [[1, 2], [2, 3], [11, 12]], answer: 'B' },
      { id: '3', rows: [[1, 2], [2, 4], [3, 8]], answer: 'A' },
      { id: '4', rows: [[1, 2], [2, 4], [11, 22]], answer: 'D' }
    ];

    let assignments = {};
    const programsBox = root.querySelector('.bb-programs');
    const tablesBox = root.querySelector('.bb-tables');
    const feedback = root.querySelector('.bb-feedback');

    function render() {
      programsBox.replaceChildren();
      programs.filter(p => !Object.values(assignments).includes(p.id)).forEach(program => {
        const card = document.createElement('div');
        card.className = 'bb-program';
        card.draggable = true;
        card.dataset.program = program.id;
        card.innerHTML = '<strong>' + program.title + '</strong><pre><code></code></pre>';
        card.querySelector('code').textContent = program.code;
        card.addEventListener('dragstart', event => {
          event.dataTransfer.setData('text/plain', program.id);
          event.dataTransfer.effectAllowed = 'move';
        });
        programsBox.appendChild(card);
      });

      tablesBox.replaceChildren();
      tables.forEach(table => {
        const card = document.createElement('div');
        card.className = 'bb-table-card';
        const heading = document.createElement('h4');
        heading.textContent = 'Tabel ' + table.id;
        card.appendChild(heading);

        const htmlTable = document.createElement('table');
        htmlTable.innerHTML = '<thead><tr><th>Invoer</th><th>Uitvoer</th></tr></thead>';
        const body = document.createElement('tbody');
        table.rows.forEach(([input, output]) => {
          const row = document.createElement('tr');
          const inputCell = document.createElement('td');
          const outputCell = document.createElement('td');
          inputCell.textContent = input;
          outputCell.textContent = output;
          row.append(inputCell, outputCell);
          body.appendChild(row);
        });
        htmlTable.appendChild(body);
        card.appendChild(htmlTable);

        const drop = document.createElement('div');
        drop.className = 'bb-drop';
        drop.dataset.table = table.id;
        drop.setAttribute('aria-label', 'Sleep een programma naar Tabel ' + table.id);
        drop.addEventListener('dragover', event => {
          event.preventDefault();
          drop.classList.add('bb-over');
        });
        drop.addEventListener('dragleave', () => drop.classList.remove('bb-over'));
        drop.addEventListener('drop', event => {
          event.preventDefault();
          drop.classList.remove('bb-over');
          const programId = event.dataTransfer.getData('text/plain');
          if (!programs.some(p => p.id === programId)) return;
          Object.keys(assignments).forEach(key => {
            if (assignments[key] === programId) delete assignments[key];
          });
          assignments[table.id] = programId;
          feedback.textContent = '';
          render();
        });

        const assignedId = assignments[table.id];
        if (assignedId) {
          const chosen = programs.find(p => p.id === assignedId);
          const label = document.createElement('div');
          label.className = 'bb-assigned';
          label.textContent = chosen.title;
          drop.appendChild(label);

          const snippet = document.createElement('pre');
          snippet.className = 'bb-assigned-code';
          const code = document.createElement('code');
          code.textContent = chosen.code;
          snippet.appendChild(code);
          drop.appendChild(snippet);

          const remove = document.createElement('button');
          remove.type = 'button';
          remove.className = 'bb-remove';
          remove.textContent = 'Keuze ongedaan maken';
          remove.addEventListener('click', () => {
            delete assignments[table.id];
            feedback.textContent = '';
            render();
          });
          drop.appendChild(remove);
        } else {
          const hint = document.createElement('span');
          hint.className = 'bb-drop-label';
          hint.textContent = 'Sleep een programma hierheen';
          drop.appendChild(hint);
        }
        card.appendChild(drop);
        tablesBox.appendChild(card);
      });
    }

    root.querySelector('.bb-check').addEventListener('click', () => {
      const count = Object.keys(assignments).length;
      if (count < tables.length) {
        feedback.textContent = 'Koppel eerst een programma aan elke tabel.';
        return;
      }
      const correct = tables.filter(table => assignments[table.id] === table.answer).length;
      feedback.textContent = correct === tables.length
        ? 'Helemaal goed! Je hebt alle programma’s aan de juiste tabel gekoppeld.'
        : 'Je hebt ' + correct + ' van de ' + tables.length + ' koppelingen goed. Vergelijk bij elke tabel alle invoer-uitvoerparen en probeer het opnieuw.';
    });

    root.querySelector('.bb-reset').addEventListener('click', () => {
      assignments = {};
      feedback.textContent = '';
      render();
    });

    render();
  })();
  </script>
</div>
```

## Denk na
```{raw} html
<details>
  <summary>Wat levert het op om vóór het programmeren vast te leggen wat er in een programma gaat en wat eruit moet komen?</summary>

  <p><strong>Mogelijk antwoord:</strong> Je weet vooraf wat het programma moet doen. Daardoor kun je gerichter programmeren en later controleren of het resultaat aan de verwachting voldoet.</p>
</details>

<details>
  <summary>Hoe helpt een input-outputtabel om te controleren of een programma doet wat je verwacht?</summary>

  <p><strong>Mogelijk antwoord:</strong> De tabel laat zien welke uitvoer bij verschillende inputs hoort. Je kunt de voorbeelden gebruiken om te testen of het programma de verwachte uitvoer geeft.</p>
</details>

<details>
  <summary>Wat zou er mis kunnen gaan als je meteen begint met code schrijven?</summary>

  <p><strong>Mogelijk antwoord:</strong> Je kunt een programma maken dat wel werkt, maar niet doet wat nodig is. Ook kun je belangrijke situaties over het hoofd zien of later veel code moeten aanpassen.</p>
</details>
```


<!-- Antwoordsleutel: Tabel 1 = C, Tabel 2 = B, Tabel 3 = A, Tabel 4 = D. -->