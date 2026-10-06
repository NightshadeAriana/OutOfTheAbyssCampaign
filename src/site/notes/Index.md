---
{"dg-publish":true,"permalink":"/index/","tags":["gardenEntry"],"dg-note-properties":{}}
---

<div style="display: flex; flex-direction: column; gap: 12px; margin: 24px 0px;"><script>
    if (!window.waLeaderboardSort) {
        window.waLeaderboardSort = function(th, colIdx) {
            const table = th.closest('table');
            const tbody = table.querySelector('tbody');
            const rows = Array.from(tbody.querySelectorAll('tr'));
            const isAsc = th.dataset.sort === 'asc';
            const multiplier = isAsc ? 1 : -1; // Default to Descending on first click
            
            // Reset all other headers
            Array.from(th.parentNode.children).forEach(sib => {
                if (sib !== th) {
                    sib.dataset.sort = '';
                    sib.innerText = sib.innerText.replace(/ [▲▼]/, '');
                }
            });

            // Sort Rows
            rows.sort((a, b) => {
                let aVal = a.cells[colIdx].innerText.trim();
                let bVal = b.cells[colIdx].innerText.trim();
                
                // Extract numbers safely (treat blanks as 0)
                let aNum = aVal ? parseFloat(aVal.replace(/[^0-9.-]+/g, "")) : 0;
                let bNum = bVal ? parseFloat(bVal.replace(/[^0-9.-]+/g, "")) : 0;
                
                if (!isNaN(aNum) && !isNaN(bNum)) return (aNum - bNum) * multiplier;
                return aVal.localeCompare(bVal) * multiplier;
            });

            // Update Header State
            th.dataset.sort = isAsc ? 'desc' : 'asc';
            th.innerText = th.innerText.replace(/ [▲▼]/, '') + (isAsc ? ' ▲' : ' ▼');
            tbody.append(...rows);
        };
    }
</script><style>
    .lb-wrap.hide-npcs .npc-row { display: none !important; }
    .lb-table { width: 100%; border-collapse: collapse; white-space: nowrap; font-family: system-ui, sans-serif; font-size: 0.9em; text-align: left; margin: 0; }
    .lb-table th { padding: 12px 16px; background: var(--background-secondary); border-bottom: 2px solid var(--background-modifier-border); color: var(--text-normal); font-weight: bold; cursor: pointer; user-select: none; transition: color 0.2s; }
    .lb-table th:hover { color: var(--text-accent); }
    .lb-table td { padding: 8px 16px; border-bottom: 1px solid var(--background-modifier-border); }
    .lb-row { transition: background 0.2s; }
    .lb-row:hover { background: var(--background-secondary); }
    .lb-sticky-col { position: sticky; left: 0; background: var(--background-primary); z-index: 2; border-right: 1px solid var(--background-modifier-border); }
    .lb-table th.lb-sticky-col { z-index: 3; background: var(--background-secondary); }
</style><div style="align-self: flex-end;">
    <label style="cursor: pointer; display: flex; align-items: center; gap: 8px; font-weight: bold; color: var(--text-muted); font-size: 0.9em; user-select: none;">
        <input type="checkbox" style="cursor: pointer;" onchange="this.closest('div').nextElementSibling.classList.toggle('hide-npcs', this.checked)">
        Hide NPCs
    </label>
</div><div class="lb-wrap" style="overflow-x: auto; border: 1px solid var(--background-modifier-border); border-radius: 8px; box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 6px -1px;"><table class="lb-table"><thead><tr><th class="lb-sticky-col" onclick="window.waLeaderboardSort(this, 0)">Name</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 1)">Damage Dealt</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 2)">Damage Taken</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 3)">Downs</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 4)">Friendly Damage</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 5)">Friendly Kills</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 6)">HP Healed (Others)</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 7)">HP Healed (Self)</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 8)">Highest Hit</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 9)">Kills</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 10)">Most successive nat 1s</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 11)">Most successive nat 20s</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 12)">Nat 1s</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 13)">Nat 20s</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 14)">One-shot Kills</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 15)">Structure HP Healed</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 16)">THP Granted (Others)</th><th style="text-align: center;" onclick="window.waLeaderboardSort(this, 17)">THP Granted (Self)</th></tr></thead><tbody><tr class="lb-row npc-row"><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Monsters/Tressym%20Token.png?1790920745000" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="NPCs/Other/Max.md" data-href="NPCs/Other/Max.md" style="text-decoration: none; color: var(--text-normal); font-weight: bold;">Max</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">21</td><td style="text-align: center; color: #ef4444; font-weight: bold;">28</td><td style="text-align: center; color: #ef4444; font-weight: bold;">3</td><td style="text-align: center; color: #ef4444; font-weight: bold;">5</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">11</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row npc-row"><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <div style="width: 28px; height: 28px; border-radius: 50%; background: var(--background-modifier-border); flex-shrink: 0;"></div>
        <a class="internal-link" href="NPCs/Other/Owlbear Cub.md" data-href="NPCs/Other/Owlbear Cub.md" style="text-decoration: none; color: #ef4444; font-weight: bold;">Owlbear Cub (Dead)</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row npc-row"><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <div style="width: 28px; height: 28px; border-radius: 50%; background: var(--background-modifier-border); flex-shrink: 0;"></div>
        <a class="internal-link" href="NPCs/Other/Sassani.md" data-href="NPCs/Other/Sassani.md" style="text-decoration: none; color: #ef4444; font-weight: bold;">Sassani (Dead)</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">101</td><td style="text-align: center; color: #ef4444; font-weight: bold;">117</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">12</td><td style="text-align: center; color: #10b981; font-weight: bold;">4</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row npc-row"><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/NPCs/Out%20of%20the%20Abyss/Buppido%20Token.png?1790950054645" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="NPCs/Out of the Abyss/Allies/Buppido.md" data-href="NPCs/Out of the Abyss/Allies/Buppido.md" style="text-decoration: none; color: #ef4444; font-weight: bold;">Buppido (Dead)</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">42</td><td style="text-align: center; color: #ef4444; font-weight: bold;">2</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row npc-row"><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <div style="width: 28px; height: 28px; border-radius: 50%; background: var(--background-modifier-border); flex-shrink: 0;"></div>
        <a class="internal-link" href="NPCs/Out of the Abyss/Allies/Eldeth Feldrun.md" data-href="NPCs/Out of the Abyss/Allies/Eldeth Feldrun.md" style="text-decoration: none; color: #ef4444; font-weight: bold;">Eldeth Feldrun (Dead)</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">58</td><td style="text-align: center; color: #ef4444; font-weight: bold;">8</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">7</td><td style="text-align: center; color: #10b981; font-weight: bold;">3</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row npc-row"><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/NPCs/Out%20of%20the%20Abyss/Jimjar%20Token.png?1790949629666" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="NPCs/Out of the Abyss/Allies/Jimjar.md" data-href="NPCs/Out of the Abyss/Allies/Jimjar.md" style="text-decoration: none; color: #ef4444; font-weight: bold;">Jimjar (Dead)</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">55</td><td style="text-align: center; color: #ef4444; font-weight: bold;">22</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">17</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">3</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row npc-row"><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/NPCs/Out%20of%20the%20Abyss/Prince%20Derendil%20Token.png?1790950123898" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="NPCs/Out of the Abyss/Allies/Prince Derendil.md" data-href="NPCs/Out of the Abyss/Allies/Prince Derendil.md" style="text-decoration: none; color: #ef4444; font-weight: bold;">Prince Derendil (Dead)</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">45</td><td style="text-align: center; color: #ef4444; font-weight: bold;">11</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">14</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">3</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row npc-row"><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/NPCs/Out%20of%20the%20Abyss/Ront%20Token.png?1790949851872" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="NPCs/Out of the Abyss/Allies/Ront.md" data-href="NPCs/Out of the Abyss/Allies/Ront.md" style="text-decoration: none; color: #ef4444; font-weight: bold;">Ront (Dead)</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">40</td><td style="text-align: center; color: #ef4444; font-weight: bold;">9</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">9</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row npc-row"><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <div style="width: 28px; height: 28px; border-radius: 50%; background: var(--background-modifier-border); flex-shrink: 0;"></div>
        <a class="internal-link" href="NPCs/Out of the Abyss/Allies/Topsy.md" data-href="NPCs/Out of the Abyss/Allies/Topsy.md" style="text-decoration: none; color: var(--text-normal); font-weight: bold;">Topsy</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row npc-row"><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <div style="width: 28px; height: 28px; border-radius: 50%; background: var(--background-modifier-border); flex-shrink: 0;"></div>
        <a class="internal-link" href="NPCs/Out of the Abyss/Allies/Turvy.md" data-href="NPCs/Out of the Abyss/Allies/Turvy.md" style="text-decoration: none; color: var(--text-normal); font-weight: bold;">Turvy</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row "><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="Players/Fallen Leaf.md" data-href="Players/Fallen Leaf.md" style="text-decoration: none; color: #ef4444; font-weight: bold;">Fallen Leaf (Dead)</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">765</td><td style="text-align: center; color: #ef4444; font-weight: bold;">392</td><td style="text-align: center; color: #ef4444; font-weight: bold;">5</td><td style="text-align: center; color: #ef4444; font-weight: bold;">24</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">246</td><td style="text-align: center; color: #10b981; font-weight: bold;">69</td><td style="text-align: center; color: #10b981; font-weight: bold;">28</td><td style="text-align: center; color: #10b981; font-weight: bold;">13</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #ef4444; font-weight: bold;">7</td><td style="text-align: center; color: #10b981; font-weight: bold;">12</td><td style="text-align: center; color: #10b981; font-weight: bold;">4</td><td style="text-align: center; color: #10b981; font-weight: bold;">259</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">8</td></tr><tr class="lb-row "><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Merv%20Image.png?1790919429000" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="Players/Merv.md" data-href="Players/Merv.md" style="text-decoration: none; color: var(--text-normal); font-weight: bold;">Merv</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">406</td><td style="text-align: center; color: #ef4444; font-weight: bold;">100</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">15</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">36</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">30</td><td style="text-align: center; color: #10b981; font-weight: bold;">12</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">11</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row "><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Nyako%20Image.png?1790919494000" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="Players/Nyako.md" data-href="Players/Nyako.md" style="text-decoration: none; color: var(--text-normal); font-weight: bold;">Nyako</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">183</td><td style="text-align: center; color: #ef4444; font-weight: bold;">35</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">22</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">35</td><td style="text-align: center; color: #10b981; font-weight: bold;">4</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row "><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="Players/Magnus.md" data-href="Players/Magnus.md" style="text-decoration: none; color: var(--text-normal); font-weight: bold;">Magnus</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">1399</td><td style="text-align: center; color: #ef4444; font-weight: bold;">185</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">35</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">20</td><td style="text-align: center; color: #10b981; font-weight: bold;">6</td><td style="text-align: center; color: #10b981; font-weight: bold;">38</td><td style="text-align: center; color: #10b981; font-weight: bold;">34</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">8</td><td style="text-align: center; color: #10b981; font-weight: bold;">9</td><td style="text-align: center; color: #10b981; font-weight: bold;">20</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row "><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Torin%20Lionheart%20Image.png?1790919408000" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="Players/Torin Lionheart.md" data-href="Players/Torin Lionheart.md" style="text-decoration: none; color: #ef4444; font-weight: bold;">Torin Lionheart (Dead)</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">508</td><td style="text-align: center; color: #ef4444; font-weight: bold;">287</td><td style="text-align: center; color: #ef4444; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">36</td><td style="text-align: center; color: #10b981; font-weight: bold;">9</td><td style="text-align: center; color: #10b981; font-weight: bold;">43</td><td style="text-align: center; color: #10b981; font-weight: bold;">11</td><td style="text-align: center; color: #ef4444; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #ef4444; font-weight: bold;">3</td><td style="text-align: center; color: #10b981; font-weight: bold;">8</td><td style="text-align: center; color: #10b981; font-weight: bold;">5</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row "><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Shota%20Image.png?1790919419000" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="Players/Shota.md" data-href="Players/Shota.md" style="text-decoration: none; color: var(--text-normal); font-weight: bold;">Shota</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">163</td><td style="text-align: center; color: #ef4444; font-weight: bold;">199</td><td style="text-align: center; color: #ef4444; font-weight: bold;">2</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">16</td><td style="text-align: center; color: #10b981; font-weight: bold;">30</td><td style="text-align: center; color: #10b981; font-weight: bold;">3</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td></tr><tr class="lb-row "><td class="lb-sticky-col" style="display: flex; align-items: center; gap: 12px;">
        <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 28px; height: 28px; border-radius: 50%; object-fit: cover; flex-shrink: 0; box-shadow: 0 1px 3px rgba(0,0,0,0.3);">
        <a class="internal-link" href="Players/Tyr.md" data-href="Players/Tyr.md" style="text-decoration: none; color: var(--text-normal); font-weight: bold;">Tyr</a>
    </td><td style="text-align: center; color: #10b981; font-weight: bold;">1064</td><td style="text-align: center; color: #ef4444; font-weight: bold;">398</td><td style="text-align: center; color: #ef4444; font-weight: bold;">3</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #ef4444; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">27</td><td style="text-align: center; color: #10b981; font-weight: bold;">26</td><td style="text-align: center; color: #10b981; font-weight: bold;">31</td><td style="text-align: center; color: #ef4444; font-weight: bold;">2</td><td style="text-align: center; color: #10b981; font-weight: bold;">1</td><td style="text-align: center; color: #ef4444; font-weight: bold;">13</td><td style="text-align: center; color: #10b981; font-weight: bold;">14</td><td style="text-align: center; color: #10b981; font-weight: bold;">4</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">0</td><td style="text-align: center; color: #10b981; font-weight: bold;">10</td></tr></tbody></table></div></div>

# Players
<div style="display: flex; flex-direction: column; gap: 56px; margin: 32px 0px; font-family: system-ui, sans-serif;">
    <div style="display: flex; flex-direction: column; gap: 16px;">
        
        <div style="position: relative; height: 100px; display: flex; align-items: flex-end;">
            
            
            <div style="position: absolute; left: 0; bottom: -8px; z-index: 2;">
                <a class="internal-link" href="Players/Fallen Leaf.md">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 130px; height: 130px; object-fit: cover; border: 4px solid var(--text-accent); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.3); background: var(--background-primary); display: block;">
                </a>
            </div>
            
            <div style="width: 100%; padding: 12px 0 12px 154px; position: relative; z-index: 1;">
                
                <div style="position: absolute; top: 0; bottom: 0; left: calc(-50vw + 50%); width: 100vw; background: var(--background-secondary); border-top: 1px solid var(--background-modifier-border); border-bottom: 1px solid var(--background-modifier-border); z-index: -1;"></div>
                
                <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 8px;">
                    <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; color: var(--text-normal); letter-spacing: -0.5px;">
                        <a class="internal-link" href="Players/Fallen Leaf.md" style="text-decoration: none; color: inherit;">Fallen Leaf</a>
                    </h2>
                    <span style="font-size: 0.8rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">
                        Tabaxi • Nature Domain Cleric • Female
                    </span>
                </div>
            </div>
        </div>
        
        <div style="padding: 0 0 0 154px; margin-top: 4px;">
            <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
                Fallen Leaf is a magic-user with a strong affinity for nature and animals, frequently using spells like Spike Growth to control the battlefield. She also has a reckless streak that occasionally results in her being knocked unconscious during combat. Originally she met her companion <a class="internal-link" data-href="Players/Magnus" href="Players/Magnus" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Magnus</a> in <a class="internal-link" data-href="Locations/Lost Mine of Phandelver/Neverwinter" href="Locations/Lost Mine of Phandelver/Neverwinter" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Neverwinter</a> to take on a caravan job. She escaped drow enslavement in <a class="internal-link" data-href="Locations/Out of the Abyss/Velkynvelve" href="Locations/Out of the Abyss/Velkynvelve" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Velkynvelve</a>. She was tricked by a <a class="internal-link" data-href="Assets/Stat Blocks/Out of the Abyss/Skum" href="Assets/Stat Blocks/Out of the Abyss/Skum" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Skum</a> and killed by an <a class="internal-link" data-href="Assets/Stat Blocks/Out of the Abyss/Aboleth" href="Assets/Stat Blocks/Out of the Abyss/Aboleth" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Aboleth</a>.
            </div>
        </div>
        
    </div>
    <div style="display: flex; flex-direction: column; gap: 16px;">
        
        <div style="position: relative; height: 100px; display: flex; align-items: flex-end;">
            
            
            <div style="position: absolute; left: 0; bottom: -8px; z-index: 2;">
                <a class="internal-link" href="Players/Glumshanks.md">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Glumshanks%20Image.png?1790913604000" style="width: 130px; height: 130px; object-fit: cover; border: 4px solid var(--text-accent); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.3); background: var(--background-primary); display: block;">
                </a>
            </div>
            
            <div style="width: 100%; padding: 12px 0 12px 154px; position: relative; z-index: 1;">
                
                <div style="position: absolute; top: 0; bottom: 0; left: calc(-50vw + 50%); width: 100vw; background: var(--background-secondary); border-top: 1px solid var(--background-modifier-border); border-bottom: 1px solid var(--background-modifier-border); z-index: -1;"></div>
                
                <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 8px;">
                    <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; color: var(--text-normal); letter-spacing: -0.5px;">
                        <a class="internal-link" href="Players/Glumshanks.md" style="text-decoration: none; color: inherit;">Glumshanks</a>
                    </h2>
                    <span style="font-size: 0.8rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">
                        Goblin • Assassin Rogue • Male
                    </span>
                </div>
            </div>
        </div>
        
        <div style="padding: 0 0 0 154px; margin-top: 4px;">
            <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
                Glumshanks is a goblin who used to work for the <a class="internal-link" data-href="Groups/Redbrands" href="Groups/Redbrands" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Redbrands</a> before joining the party. Kidnapped by <a class="internal-link" data-href="NPCs/Charlotte" href="NPCs/Charlotte" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Charlotte Mizzrym</a>, he escaped <a class="internal-link" data-href="Locations/Out of the Abyss/Velkynvelve" href="Locations/Out of the Abyss/Velkynvelve" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Velkynvelve</a> with his party. He was charmed by a <a class="internal-link" data-href="Assets/Stat Blocks/Succubus" href="Assets/Stat Blocks/Succubus" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Succubus</a> during the <a class="internal-link" data-href="Sessions/Session 12" href="Sessions/Session 12" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">assassination of the Deepking</a> in Gracklstugh.
            </div>
        </div>
        
    </div>
    <div style="display: flex; flex-direction: column; gap: 16px;">
        
        <div style="position: relative; height: 100px; display: flex; align-items: flex-end;">
            
            
            <div style="position: absolute; left: 0; bottom: -8px; z-index: 2;">
                <a class="internal-link" href="Players/Merv.md">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Merv%20Image.png?1790919429000" style="width: 130px; height: 130px; object-fit: cover; border: 4px solid var(--text-accent); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.3); background: var(--background-primary); display: block;">
                </a>
            </div>
            
            <div style="width: 100%; padding: 12px 0 12px 154px; position: relative; z-index: 1;">
                
                <div style="position: absolute; top: 0; bottom: 0; left: calc(-50vw + 50%); width: 100vw; background: var(--background-secondary); border-top: 1px solid var(--background-modifier-border); border-bottom: 1px solid var(--background-modifier-border); z-index: -1;"></div>
                
                <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 8px;">
                    <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; color: var(--text-normal); letter-spacing: -0.5px;">
                        <a class="internal-link" href="Players/Merv.md" style="text-decoration: none; color: inherit;">Merv</a>
                    </h2>
                    <span style="font-size: 0.8rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">
                        Human • Lore Bard • Male
                    </span>
                </div>
            </div>
        </div>
        
        <div style="padding: 0 0 0 154px; margin-top: 4px;">
            <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
                No description provided.
            </div>
        </div>
        
    </div>
    <div style="display: flex; flex-direction: column; gap: 16px;">
        
        <div style="position: relative; height: 100px; display: flex; align-items: flex-end;">
            
            
            <div style="position: absolute; left: 0; bottom: -8px; z-index: 2;">
                <a class="internal-link" href="Players/Nyako.md">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Nyako%20Image.png?1790919494000" style="width: 130px; height: 130px; object-fit: cover; border: 4px solid var(--text-accent); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.3); background: var(--background-primary); display: block;">
                </a>
            </div>
            
            <div style="width: 100%; padding: 12px 0 12px 154px; position: relative; z-index: 1;">
                
                <div style="position: absolute; top: 0; bottom: 0; left: calc(-50vw + 50%); width: 100vw; background: var(--background-secondary); border-top: 1px solid var(--background-modifier-border); border-bottom: 1px solid var(--background-modifier-border); z-index: -1;"></div>
                
                <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 8px;">
                    <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; color: var(--text-normal); letter-spacing: -0.5px;">
                        <a class="internal-link" href="Players/Nyako.md" style="text-decoration: none; color: inherit;">Nyako</a>
                    </h2>
                    <span style="font-size: 0.8rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">
                        Custom Lineage (Catgirl) • Battle Smith Artificer • Female
                    </span>
                </div>
            </div>
        </div>
        
        <div style="padding: 0 0 0 154px; margin-top: 4px;">
            <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
                No description provided.
            </div>
        </div>
        
    </div>
    <div style="display: flex; flex-direction: column; gap: 16px;">
        
        <div style="position: relative; height: 100px; display: flex; align-items: flex-end;">
            
            
            <div style="position: absolute; left: 0; bottom: -8px; z-index: 2;">
                <a class="internal-link" href="Players/Luca Rendor.md">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Luca%20Rendor%20Image.png?1790919570000" style="width: 130px; height: 130px; object-fit: cover; border: 4px solid var(--text-accent); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.3); background: var(--background-primary); display: block;">
                </a>
            </div>
            
            <div style="width: 100%; padding: 12px 0 12px 154px; position: relative; z-index: 1;">
                
                <div style="position: absolute; top: 0; bottom: 0; left: calc(-50vw + 50%); width: 100vw; background: var(--background-secondary); border-top: 1px solid var(--background-modifier-border); border-bottom: 1px solid var(--background-modifier-border); z-index: -1;"></div>
                
                <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 8px;">
                    <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; color: var(--text-normal); letter-spacing: -0.5px;">
                        <a class="internal-link" href="Players/Luca Rendor.md" style="text-decoration: none; color: inherit;">Luca Rendor</a>
                    </h2>
                    <span style="font-size: 0.8rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">
                        Dwarf • Bard • Male
                    </span>
                </div>
            </div>
        </div>
        
        <div style="padding: 0 0 0 154px; margin-top: 4px;">
            <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
                Luca Rendor is a former member of the adventuring party who participated in the initial journey toward <a class="internal-link" data-href="Locations/Lost Mine of Phandelver/Phandalin" href="Locations/Lost Mine of Phandelver/Phandalin" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Phandalin</a>. After a brief stint with the group during their first major encounter, he left the party entirely.
            </div>
        </div>
        
    </div>
    <div style="display: flex; flex-direction: column; gap: 16px;">
        
        <div style="position: relative; height: 100px; display: flex; align-items: flex-end;">
            
            
            <div style="position: absolute; left: 0; bottom: -8px; z-index: 2;">
                <a class="internal-link" href="Players/Magnus.md">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 130px; height: 130px; object-fit: cover; border: 4px solid var(--text-accent); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.3); background: var(--background-primary); display: block;">
                </a>
            </div>
            
            <div style="width: 100%; padding: 12px 0 12px 154px; position: relative; z-index: 1;">
                
                <div style="position: absolute; top: 0; bottom: 0; left: calc(-50vw + 50%); width: 100vw; background: var(--background-secondary); border-top: 1px solid var(--background-modifier-border); border-bottom: 1px solid var(--background-modifier-border); z-index: -1;"></div>
                
                <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 8px;">
                    <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; color: var(--text-normal); letter-spacing: -0.5px;">
                        <a class="internal-link" href="Players/Magnus.md" style="text-decoration: none; color: inherit;">Magnus</a>
                    </h2>
                    <span style="font-size: 0.8rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">
                        Tiefling • Order of Scribes Wizard • Male
                    </span>
                </div>
            </div>
        </div>
        
        <div style="padding: 0 0 0 154px; margin-top: 4px;">
            <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
                Magnus is a highly secretive, masked magic-user who commands a winged cat familiar named <a class="internal-link" data-href="NPCs/Other/Max" href="NPCs/Other/Max" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Max</a>, utilizes a wide range of magic from trickery to summoning <a class="internal-link" data-href="Assets/Stat Blocks/Lemure" href="Assets/Stat Blocks/Lemure" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Lemures</a>, and frequently employs manipulation or deception to achieve his goals. After concluding the <a class="internal-link" data-href="Modules/Lost Mine of Phandelver" href="Modules/Lost Mine of Phandelver" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Lost Mine of Phandelver</a> and being betrayed by <a class="internal-link" data-href="NPCs/Charlotte" href="NPCs/Charlotte" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Charlotte</a>, he recently escaped from drow enslavement in <a class="internal-link" data-href="Locations/Out of the Abyss/Velkynvelve" href="Locations/Out of the Abyss/Velkynvelve" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Velkynvelve</a>.
            </div>
        </div>
        
    </div>
    <div style="display: flex; flex-direction: column; gap: 16px;">
        
        <div style="position: relative; height: 100px; display: flex; align-items: flex-end;">
            
            
            <div style="position: absolute; left: 0; bottom: -8px; z-index: 2;">
                <a class="internal-link" href="Players/Torin Lionheart.md">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Torin%20Lionheart%20Image.png?1790919408000" style="width: 130px; height: 130px; object-fit: cover; border: 4px solid var(--text-accent); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.3); background: var(--background-primary); display: block;">
                </a>
            </div>
            
            <div style="width: 100%; padding: 12px 0 12px 154px; position: relative; z-index: 1;">
                
                <div style="position: absolute; top: 0; bottom: 0; left: calc(-50vw + 50%); width: 100vw; background: var(--background-secondary); border-top: 1px solid var(--background-modifier-border); border-bottom: 1px solid var(--background-modifier-border); z-index: -1;"></div>
                
                <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 8px;">
                    <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; color: var(--text-normal); letter-spacing: -0.5px;">
                        <a class="internal-link" href="Players/Torin Lionheart.md" style="text-decoration: none; color: inherit;">Torin Lionheart</a>
                    </h2>
                    <span style="font-size: 0.8rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">
                        Drow • Paladin (Unknown Subclass) • Male
                    </span>
                </div>
            </div>
        </div>
        
        <div style="padding: 0 0 0 154px; margin-top: 4px;">
            <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
                He is a Drow, however he doesn't have any of the signs of the kidnapper Drow.
            </div>
        </div>
        
    </div>
    <div style="display: flex; flex-direction: column; gap: 16px;">
        
        <div style="position: relative; height: 100px; display: flex; align-items: flex-end;">
            
            
            <div style="position: absolute; left: 0; bottom: -8px; z-index: 2;">
                <a class="internal-link" href="Players/Unknown Character.md">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Tokens/Unknown%20Character%20Token.png?1790764997000" style="width: 130px; height: 130px; object-fit: cover; border: 4px solid var(--text-accent); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.3); background: var(--background-primary); display: block;">
                </a>
            </div>
            
            <div style="width: 100%; padding: 12px 0 12px 154px; position: relative; z-index: 1;">
                
                <div style="position: absolute; top: 0; bottom: 0; left: calc(-50vw + 50%); width: 100vw; background: var(--background-secondary); border-top: 1px solid var(--background-modifier-border); border-bottom: 1px solid var(--background-modifier-border); z-index: -1;"></div>
                
                <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 8px;">
                    <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; color: var(--text-normal); letter-spacing: -0.5px;">
                        <a class="internal-link" href="Players/Unknown Character.md" style="text-decoration: none; color: inherit;">Unknown Character</a>
                    </h2>
                    <span style="font-size: 0.8rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">
                        
                    </span>
                </div>
            </div>
        </div>
        
        <div style="padding: 0 0 0 154px; margin-top: 4px;">
            <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
                The player left the game after learning the game was 5e, not 5.5e.
            </div>
        </div>
        
    </div>
    <div style="display: flex; flex-direction: column; gap: 16px;">
        
        <div style="position: relative; height: 100px; display: flex; align-items: flex-end;">
            
            
            <div style="position: absolute; left: 0; bottom: -8px; z-index: 2;">
                <a class="internal-link" href="Players/Shota.md">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Shota%20Image.png?1790919419000" style="width: 130px; height: 130px; object-fit: cover; border: 4px solid var(--text-accent); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.3); background: var(--background-primary); display: block;">
                </a>
            </div>
            
            <div style="width: 100%; padding: 12px 0 12px 154px; position: relative; z-index: 1;">
                
                <div style="position: absolute; top: 0; bottom: 0; left: calc(-50vw + 50%); width: 100vw; background: var(--background-secondary); border-top: 1px solid var(--background-modifier-border); border-bottom: 1px solid var(--background-modifier-border); z-index: -1;"></div>
                
                <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 8px;">
                    <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; color: var(--text-normal); letter-spacing: -0.5px;">
                        <a class="internal-link" href="Players/Shota.md" style="text-decoration: none; color: inherit;">Shota</a>
                    </h2>
                    <span style="font-size: 0.8rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">
                        Human • Fiend Warlock / Rune Knight Fighter • Male
                    </span>
                </div>
            </div>
        </div>
        
        <div style="padding: 0 0 0 154px; margin-top: 4px;">
            <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
                No description provided.
            </div>
        </div>
        
    </div>
    <div style="display: flex; flex-direction: column; gap: 16px;">
        
        <div style="position: relative; height: 100px; display: flex; align-items: flex-end;">
            
            
            <div style="position: absolute; left: 0; bottom: -8px; z-index: 2;">
                <a class="internal-link" href="Players/Tyr.md">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 130px; height: 130px; object-fit: cover; border: 4px solid var(--text-accent); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.3); background: var(--background-primary); display: block;">
                </a>
            </div>
            
            <div style="width: 100%; padding: 12px 0 12px 154px; position: relative; z-index: 1;">
                
                <div style="position: absolute; top: 0; bottom: 0; left: calc(-50vw + 50%); width: 100vw; background: var(--background-secondary); border-top: 1px solid var(--background-modifier-border); border-bottom: 1px solid var(--background-modifier-border); z-index: -1;"></div>
                
                <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; gap: 8px;">
                    <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; color: var(--text-normal); letter-spacing: -0.5px;">
                        <a class="internal-link" href="Players/Tyr.md" style="text-decoration: none; color: inherit;">Tyr</a>
                    </h2>
                    <span style="font-size: 0.8rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">
                        Goliath • Samurai Fighter • Male
                    </span>
                </div>
            </div>
        </div>
        
        <div style="padding: 0 0 0 154px; margin-top: 4px;">
            <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
                Tyr is a formidable warrior whose intimidating presence often precedes him, having once terrified a barmaid who mistook him for an orc. He is a capable frontline fighter with a documented dislike for goblins, yet he possesses surprising cunning, using his knowledge of the Orcish language to deceive and manipulate enemy camps. After being poisoned and captured by <a class="internal-link" data-href="NPCs/Charlotte" href="NPCs/Charlotte" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Charlotte</a> in <a class="internal-link" data-href="Waterdeep" href="Waterdeep" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Waterdeep</a>, he recently fought his way out of the drow slave pens of <a class="internal-link" data-href="Locations/Out of the Abyss/Velkynvelve" href="Locations/Out of the Abyss/Velkynvelve" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Velkynvelve</a>.
            </div>
        </div>
        
    </div></div>

# Sessions


[[Sessions/Session 0\|Session 0]]
[[Sessions/Session 1\|Session 1]]
[[Sessions/Session 2\|Session 2]]
[[Sessions/Session 3\|Session 3]]
[[Sessions/Session 4\|Session 4]]
[[Sessions/Session 5\|Session 5]]
[[Sessions/Session 6\|Session 6]]
