# Black box: kijk naar input en output

Een **black box** is een systeem waarvan je de binnenkant niet bekijkt. Je geeft het een input en observeert de output.

```{figure} figures/blackbox.jpeg
---
width: 50%
align: center
---
<Je ziet niet wat er gebeurt in de black box, je ziet alleen het output van een input>
```



Door verschillende input-outputcombinaties te vergelijken, kun je proberen af te leiden welke regel het systeem volgt.

Bijvoorbeeld:

| Invoer | Uitvoer |
|---:|---:|
| 1 | 2 |
| 2 | 3 |
| 11 | 12 |

Deze voorbeelden passen bij de regel: tel er 1 bij op. We weten dat doordat we het gedrag hebben getest; bij een echte black box hoeven we de code binnenin niet te zien.

## Oefening: welke code hoort bij welke tabel?

Hieronder zie je vier tabellen met waargenomen invoer en uitvoer, en vier Java-codefragmenten. Sleep elk programma naar de tabel waarvan de uitkomsten erbij passen. Gebruik alle programma’s precies één keer. Klik daarna op **Controleer**.

In deze oefening zijn de codefragmenten dus wél zichtbaar: je gebruikt ze om de waargenomen black-boxgegevens aan het juiste programma te koppelen. Kijk steeds naar alle rijen in een tabel, niet alleen naar één voorbeeld. In elk fragment is `getal` de ingevoerde waarde en wordt `uitvoer` geprint.

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
    #blackbox-match button { border: 1px solid #64748b; border-radius: 6px; padding: .4rem .6rem; background: #fff; color: #172033; cursor: pointer; }
    #blackbox-match button:hover { background: #f1f5f9; }
    #blackbox-match .bb-remove { display: block; margin-top: .45rem; font-size: .85rem; }
    #blackbox-match .bb-actions { display: flex; gap: .6rem; margin-top: 1rem; flex-wrap: wrap; }
    #blackbox-match .bb-feedback { min-height: 1.5em; margin: .75rem 0 0; font-weight: 600; }
    @media (max-width: 700px) {
      #blackbox-match .bb-layout { grid-template-columns: 1fr; }
      #blackbox-match .bb-tables { grid-template-columns: 1fr; }
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
      { id: 'A', title: 'Programma A', code: 'int uitvoer = (int) Math.pow(2, getal);' },
      { id: 'B', title: 'Programma B', code: 'int uitvoer = getal + 1;' },
      { id: 'C', title: 'Programma C', code: 'int uitvoer = getal * getal;' },
      { id: 'D', title: 'Programma D', code: 'int uitvoer = getal * 2;' }
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

1. Welke invoer-uitvoercombinatie hielp jou het meest bij het kiezen?
2. Waarom is één voorbeeld soms niet genoeg om een programma te herkennen?
3. Welk programma geeft bij invoer 4 de uitvoer 16?

```{admonition} Voor de docent: test de interactieve versie
:class: tip

De sleepfunctie gebruikt alleen HTML en JavaScript en heeft geen externe bibliotheken nodig. De oefening staat in een MyST `raw`-directive. Of JavaScript in de uiteindelijke Jupyter Book-pagina wordt uitgevoerd, hangt af van de MyST/Sphinx-configuratie en eventuele beveiligingsinstellingen van de publicatieomgeving. Test daarom de gebouwde pagina én de gepubliceerde versie. Als scripts worden verwijderd of geblokkeerd, moet de interactieve code via een door jullie omgeving toegestane route worden toegevoegd.
```

<!-- Antwoordsleutel: Tabel 1 = C, Tabel 2 = B, Tabel 3 = A, Tabel 4 = D. -->