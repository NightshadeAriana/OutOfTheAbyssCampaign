---
{"dg-publish":true,"permalink":"/index/","dg-note-properties":{}}
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
<div style="display: flex; flex-direction: column; gap: 16px; margin: 32px 0px; font-family: system-ui, sans-serif;"><style>
    .session-facepile-link { display: inline-block; position: relative; transition: transform 0.2s, z-index 0s; text-decoration: none; }
    .session-facepile-link:hover { transform: translateY(-4px) scale(1.1); z-index: 30 !important; }
</style><div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 0.md" style="text-decoration: none; color: var(--text-normal);">Session 0</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">April 4, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 19;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Unknown Character" href="Players/Unknown Character" style="margin-left: -8px; z-index: 18;" title="Unknown Character">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Tokens/Unknown%20Character%20Token.png?1790764997000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            Events in this session were retconned. <a class="internal-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Fallen Leaf</a> and <a class="internal-link" data-href="Players/Magnus" href="Players/Magnus" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Magnus</a> meet in <a class="internal-link" data-href="Locations/Lost Mine of Phandelver/Neverwinter" href="Locations/Lost Mine of Phandelver/Neverwinter" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Neverwinter</a>.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 1.md" style="text-decoration: none; color: var(--text-normal);">Session 1</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">April 11, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 19;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Tyr" href="Players/Tyr" style="margin-left: -8px; z-index: 18;" title="Tyr">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Luca Rendor" href="Players/Luca Rendor" style="margin-left: -8px; z-index: 17;" title="Luca Rendor">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Luca%20Rendor%20Image.png?1790919570000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            The party starts in <a class="internal-link" data-href="Locations/Lost Mine of Phandelver/Neverwinter" href="Locations/Lost Mine of Phandelver/Neverwinter" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Neverwinter</a> and accepts the <a class="internal-link" data-href="Deliver Supplies to Phandalin" href="Deliver Supplies to Phandalin" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">job to deliver supplies</a> to <a class="internal-link" data-href="Locations/Lost Mine of Phandelver/Phandalin" href="Locations/Lost Mine of Phandelver/Phandalin" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Phandalin</a>.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 2.md" style="text-decoration: none; color: var(--text-normal);">Session 2</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">April 25, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 19;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Tyr" href="Players/Tyr" style="margin-left: -8px; z-index: 18;" title="Tyr">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            The party arrives into <a class="internal-link" data-href="Locations/Lost Mine of Phandelver/Phandalin" href="Locations/Lost Mine of Phandelver/Phandalin" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Phandalin</a>, meets <a class="internal-link" data-href="Charlotte Mizzrym" href="Charlotte Mizzrym" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Charlotte Mizzrym</a> and accepts a <a class="internal-link" data-href="Quests/Lost Mine of Phandelver/Finding Iarno" href="Quests/Lost Mine of Phandelver/Finding Iarno" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">job</a> to find <a class="internal-link" data-href="NPCs/Lost Mine of Phandelver/Iarno Albrek" href="NPCs/Lost Mine of Phandelver/Iarno Albrek" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Iarno</a>.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 3.md" style="text-decoration: none; color: var(--text-normal);">Session 3</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">May 2, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 19;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Tyr" href="Players/Tyr" style="margin-left: -8px; z-index: 18;" title="Tyr">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Glumshanks" href="Players/Glumshanks" style="margin-left: -8px; z-index: 17;" title="Glumshanks">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Glumshanks%20Image.png?1790913604000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            The party finishes the <a class="internal-link" data-href="Quests/Lost Mine of Phandelver/Finding Iarno" href="Quests/Lost Mine of Phandelver/Finding Iarno" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">quest</a> to find <a class="internal-link" data-href="NPCs/Lost Mine of Phandelver/Iarno Albrek" href="NPCs/Lost Mine of Phandelver/Iarno Albrek" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Iarno</a>. They succeed, and take on a few more quests, like <a class="internal-link" data-href="Quests/Lost Mine of Phandelver/Wyvern Tor" href="Quests/Lost Mine of Phandelver/Wyvern Tor" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">fighting orcs</a> and <a class="internal-link" data-href="Quests/Lost Mine of Phandelver/Find the druid Reidoth" href="Quests/Lost Mine of Phandelver/Find the druid Reidoth" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">locating a druid</a>. The party meets <a class="internal-link" data-href="Players/Glumshanks" href="Players/Glumshanks" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Glumshanks</a> and <a class="internal-link" data-href="NPCs/Other/Sassani" href="NPCs/Other/Sassani" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Sassani</a>.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 4.md" style="text-decoration: none; color: var(--text-normal);">Session 4</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">May 9, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 19;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Glumshanks" href="Players/Glumshanks" style="margin-left: -8px; z-index: 18;" title="Glumshanks">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Glumshanks%20Image.png?1790913604000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            The party finishes their final <a class="internal-link" data-href="Quests/Lost Mine of Phandelver/Old Owl Well" href="Quests/Lost Mine of Phandelver/Old Owl Well" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">quest</a>, and tames an <a class="internal-link" data-href="NPCs/Other/Owlbear Cub" href="NPCs/Other/Owlbear Cub" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">owlbear cub</a>
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 5.md" style="text-decoration: none; color: var(--text-normal);">Session 5</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">May 23, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 19;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Tyr" href="Players/Tyr" style="margin-left: -8px; z-index: 18;" title="Tyr">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Glumshanks" href="Players/Glumshanks" style="margin-left: -8px; z-index: 17;" title="Glumshanks">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Glumshanks%20Image.png?1790913604000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            The party saved <a class="internal-link" data-href="NPCs/Lost Mine of Phandelver/Gundren Rockseeker" href="NPCs/Lost Mine of Phandelver/Gundren Rockseeker" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Gundren Rockseeker</a> before descending into the depths of the <a class="internal-link" data-href="Locations/Lost Mine of Phandelver/Wave Echo Cave" href="Locations/Lost Mine of Phandelver/Wave Echo Cave" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Wave Echo Cave</a>.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 6.md" style="text-decoration: none; color: var(--text-normal);">Session 6</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">May 30, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 19;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Tyr" href="Players/Tyr" style="margin-left: -8px; z-index: 18;" title="Tyr">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            After defeating the <a class="internal-link" data-href="NPCs/Lost Mine of Phandelver/Nezznar the Black Spider" href="NPCs/Lost Mine of Phandelver/Nezznar the Black Spider" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Black Spider</a> in <a class="internal-link" data-href="Locations/Lost Mine of Phandelver/Wave Echo Cave" href="Locations/Lost Mine of Phandelver/Wave Echo Cave" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Wave Echo Cave</a> and returning to <a class="internal-link" data-href="Locations/Lost Mine of Phandelver/Phandalin" href="Locations/Lost Mine of Phandelver/Phandalin" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Phandalin</a> as heroes, the party traveled to <a class="internal-link" data-href="Locations/Other/Waterdeep" href="Locations/Other/Waterdeep" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Waterdeep</a> only to be poisoned, betrayed, and captured by their supposed ally <a class="internal-link" data-href="NPCs/Out of the Abyss/Charlotte Mizzrym" href="NPCs/Out of the Abyss/Charlotte Mizzrym" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Charlotte</a>.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 6.5.md" style="text-decoration: none; color: var(--text-normal);">Session 6.5</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">Varied date</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 19;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Tyr" href="Players/Tyr" style="margin-left: -8px; z-index: 18;" title="Tyr">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Glumshanks" href="Players/Glumshanks" style="margin-left: -8px; z-index: 17;" title="Glumshanks">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Glumshanks%20Image.png?1790913604000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            Session 0 for the Out of the Abyss module.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 7.md" style="text-decoration: none; color: var(--text-normal);">Session 7</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">June 13, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Tyr" href="Players/Tyr" style="margin-left: -8px; z-index: 19;" title="Tyr">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Glumshanks" href="Players/Glumshanks" style="margin-left: -8px; z-index: 18;" title="Glumshanks">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Glumshanks%20Image.png?1790913604000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            The party orchestrated a chaotic, bloody jailbreak from the drow slave pens of <a class="internal-link" data-href="Locations/Out of the Abyss/Velkynvelve" href="Locations/Out of the Abyss/Velkynvelve" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Velkynvelve</a>, recovering their gear and fighting their way past <a class="internal-link" data-href="NPCs/Out of the Abyss/Charlotte Mizzrym" href="NPCs/Out of the Abyss/Charlotte Mizzrym" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Charlotte Mizzrym</a>'s forces to escape down an elevator shaft, though the victory tragically cost them the lives of <a class="internal-link" data-href="NPCs/Out of the Abyss/Allies/Jimjar" href="NPCs/Out of the Abyss/Allies/Jimjar" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Jimjar</a>  and the <a class="internal-link" data-href="NPCs/Other/Owlbear Cub" href="NPCs/Other/Owlbear Cub" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">owlbear cub</a>.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 8.md" style="text-decoration: none; color: var(--text-normal);">Session 8</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">June 20, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 19;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Glumshanks" href="Players/Glumshanks" style="margin-left: -8px; z-index: 18;" title="Glumshanks">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Glumshanks%20Image.png?1790913604000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            Fleeing their previous escape, the party survived a harrowing crossfire between illithid forces and <a class="internal-link" data-href="NPCs/Out of the Abyss/Githyanki Knights" href="NPCs/Out of the Abyss/Githyanki Knights" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Githyanki knights</a> that claimed the lives of <a class="internal-link" data-href="NPCs/Out of the Abyss/Allies/Prince Derendil" href="NPCs/Out of the Abyss/Allies/Prince Derendil" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Prince Derendil</a> and <a class="internal-link" data-href="NPCs/Out of the Abyss/Allies/Ront" href="NPCs/Out of the Abyss/Allies/Ront" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Ront</a>, before escaping a subsequent <a class="internal-link" data-href="Assets/Stat Blocks/Drow" href="Assets/Stat Blocks/Drow" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Drow</a> ambush to arrive at the aquatic settlement of <a class="internal-link" data-href="Locations/Out of the Abyss/Sloobludop" href="Locations/Out of the Abyss/Sloobludop" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Sloobludop</a>.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 11.md" style="text-decoration: none; color: var(--text-normal);">Session 11</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">July 11, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Glumshanks" href="Players/Glumshanks" style="margin-left: -8px; z-index: 19;" title="Glumshanks">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Glumshanks%20Image.png?1790913604000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Torin Lionheart" href="Players/Torin Lionheart" style="margin-left: -8px; z-index: 18;" title="Torin Lionheart">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Torin%20Lionheart%20Image.png?1790919408000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            The party continues exploring <a class="internal-link" data-href="Minor Locations/Cairngorm Cavern" href="Minor Locations/Cairngorm Cavern" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Cairngorm Cavern</a>, and has split.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 12.md" style="text-decoration: none; color: var(--text-normal);">Session 12</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">July 25, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Glumshanks" href="Players/Glumshanks" style="margin-left: -8px; z-index: 19;" title="Glumshanks">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Glumshanks%20Image.png?1790913604000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Torin Lionheart" href="Players/Torin Lionheart" style="margin-left: -8px; z-index: 18;" title="Torin Lionheart">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Torin%20Lionheart%20Image.png?1790919408000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            After reuniting in the caves and allying with <a class="internal-link" data-href="NPCs/Out of the Abyss/Themberchaud" href="NPCs/Out of the Abyss/Themberchaud" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Themberchaud</a> to <a class="internal-link" data-href="Quests/Out of the Abyss/Slay the Deepking" href="Quests/Out of the Abyss/Slay the Deepking" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">assassinate the Deepking</a>, the party's mission ends in a catastrophic demonic ambush that leaves <a class="internal-link" data-href="Players/Glumshanks" href="Players/Glumshanks" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Glumshanks</a> abducted, <a class="internal-link" data-href="Players/Torin Lionheart" href="Players/Torin Lionheart" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Torin</a> feebleminded, <a class="internal-link" data-href="NPCs/Out of the Abyss/Themberchaud" href="NPCs/Out of the Abyss/Themberchaud" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Themberchaud</a> dead, and the remaining members desperately fleeing <a class="internal-link" data-href="Locations/Out of the Abyss/Gracklstugh" href="Locations/Out of the Abyss/Gracklstugh" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Gracklstugh</a> on a ship.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 13.md" style="text-decoration: none; color: var(--text-normal);">Session 13</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">August 8, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="margin-left: 0; z-index: 20;" title="Fallen Leaf">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Fallen%20Leaf%20Image.png?1790746471000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Shota" href="Players/Shota" style="margin-left: -8px; z-index: 19;" title="Shota">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Shota%20Image.png?1790919419000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Merv" href="Players/Merv" style="margin-left: -8px; z-index: 18;" title="Merv">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Merv%20Image.png?1790919429000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 17;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Tyr" href="Players/Tyr" style="margin-left: -8px; z-index: 16;" title="Tyr">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            After surviving a <a class="internal-link" data-href="NPCs/Out of the Abyss/Demons/Demogorgon" href="NPCs/Out of the Abyss/Demons/Demogorgon" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Demogorgon</a> attack and meeting new allies during a naval ambush, the party's journey takes a tragic turn when <a class="internal-link" data-href="Players/Fallen Leaf" href="Players/Fallen Leaf" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Fallen Leaf</a> is manipulated by an <a class="internal-link" data-href="NPCs/Out of the Abyss/Aboleth" href="NPCs/Out of the Abyss/Aboleth" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Aboleth</a>, lured into its underwater lair, and killed while fighting to the bitter end.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 14.md" style="text-decoration: none; color: var(--text-normal);">Session 14</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">August 22, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Nyako" href="Players/Nyako" style="margin-left: 0; z-index: 20;" title="Nyako">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Nyako%20Image.png?1790919494000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Shota" href="Players/Shota" style="margin-left: -8px; z-index: 19;" title="Shota">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Shota%20Image.png?1790919419000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Merv" href="Players/Merv" style="margin-left: -8px; z-index: 18;" title="Merv">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Merv%20Image.png?1790919429000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 17;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Tyr" href="Players/Tyr" style="margin-left: -8px; z-index: 16;" title="Tyr">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            The party navigates a treacherous <a class="internal-link" data-href="Locations/Out of the Abyss/Hook Horror Lair" href="Locations/Out of the Abyss/Hook Horror Lair" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Hook Horror Lair</a> and battles a gnoll ambush with the help of a new ally, <a class="internal-link" data-href="Players/Nyako" href="Players/Nyako" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Nyako</a>, but their desperate escape from the demon Yeenoghu ultimately results in the tragic deaths of <a class="internal-link" data-href="Players/Torin Lionheart" href="Players/Torin Lionheart" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Torin Lionheart</a> and <a class="internal-link" data-href="NPCs/Other/Sassani" href="NPCs/Other/Sassani" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Sassani</a>.
        </div>
    </div>
    <div style="background: var(--background-primary); border: 1px solid var(--background-modifier-border); border-radius: 8px; padding: 16px; transition: transform 0.2s, box-shadow 0.2s; display: flex; flex-direction: column; gap: 12px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);" onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 15px -3px rgba(0,0,0,0.1)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(0,0,0,0.05)'">
        
        <!-- Top Row: Title, Date, Facepile -->
        <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;">
            
            <!-- Left Side: Title -->
            <div style="flex: 1; min-width: 200px;">
                <h2 style="margin: 0; font-size: 1.5rem; font-weight: 800; letter-spacing: -0.5px; line-height: 1.2;">
                    <a class="internal-link" href="Sessions/Session 15.md" style="text-decoration: none; color: var(--text-normal);">Session 15</a>
                </h2>
            </div>
            
            <!-- Right Side: Date & Facepile -->
            <div style="display: flex; align-items: center; gap: 12px; flex-shrink: 0;">
                <span style="font-size: 0.85rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px;">September 12, 2026</span>
                
            <div style="display: flex; align-items: center; padding-left: 12px; border-left: 1px solid var(--background-modifier-border); margin-left: 12px; flex-shrink: 0;">
                
                <a class="internal-link session-facepile-link" data-href="Players/Nyako" href="Players/Nyako" style="margin-left: 0; z-index: 20;" title="Nyako">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Nyako%20Image.png?1790919494000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Shota" href="Players/Shota" style="margin-left: -8px; z-index: 19;" title="Shota">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Shota%20Image.png?1790919419000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Magnus" href="Players/Magnus" style="margin-left: -8px; z-index: 18;" title="Magnus">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Magnus%20Image.png?1790751602000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
                <a class="internal-link session-facepile-link" data-href="Players/Tyr" href="Players/Tyr" style="margin-left: -8px; z-index: 17;" title="Tyr">
                    <img src="app://d3b7c9209be0e6d1ef4e9586f600890b2a07/C:/Data/Code/HTML/DnD/Out%20of%20the%20Abyss/Assets/Players/Images/Tyr%20Image.png?1790919376000" style="width: 32px; height: 32px; border-radius: 6px; object-fit: cover; border: 2px solid var(--background-primary); box-shadow: 0 2px 4px rgba(0,0,0,0.2); background: var(--background-secondary); display: block;">
                </a>
            
            </div>
            </div>
        </div>
        
        <!-- Description Container -->
        <div style="font-size: 0.95rem; line-height: 1.6; color: var(--text-normal);">
            The party explores the spore-filled <a class="internal-link" data-href="Locations/Out of the Abyss/Neverlight Grove" href="Locations/Out of the Abyss/Neverlight Grove" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Neverlight Grove</a>, slays a <a class="internal-link" data-href="Assets/Monsters/Shambling Mound" href="Assets/Monsters/Shambling Mound" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Shambling Mound</a> and a <a class="internal-link" data-href="Assets/Monsters/Roper" href="Assets/Monsters/Roper" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Roper</a> for the local hunters, and flees in terror upon discovering the demon <a class="internal-link" data-href="NPCs/Out of the Abyss/Demons/Zuggtmoy" href="NPCs/Out of the Abyss/Demons/Zuggtmoy" style="color: var(--text-accent); text-decoration: none; font-weight: 600;">Zuggtmoy</a> concealed within a massive mushroom.
        </div>
    </div></div></div>

[[Sessions/Session 0\|Session 0]]
[[Sessions/Session 1\|Session 1]]
[[Sessions/Session 2\|Session 2]]
[[Sessions/Session 3\|Session 3]]
[[Sessions/Session 4\|Session 4]]
[[Sessions/Session 5\|Session 5]]
[[Sessions/Session 6\|Session 6]]
