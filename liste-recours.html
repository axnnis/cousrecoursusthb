<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Liste pour le recours</title>
<style>
:root{
  --bg:#f4f6f9; --card:#ffffff; --text:#1c2430; --muted:#66707d;
  --accent:#2f6fed; --accent-text:#ffffff; --border:#e2e6ec; --danger:#d64545;
}
*{box-sizing:border-box;}
body{margin:0; background:var(--bg); color:var(--text); font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Arial,sans-serif;}
.wrap{max-width:760px; margin:0 auto; padding:24px 16px 48px;}
h1{font-size:1.4rem; margin:8px 0 2px;}
.sub{color:var(--muted); font-size:0.92rem; margin:0 0 20px;}
.card{background:var(--card); border:1px solid var(--border); border-radius:14px; padding:18px; margin-bottom:20px;}
label{display:block; font-size:0.85rem; color:var(--muted); margin:12px 0 4px;}
label:first-of-type{margin-top:0;}
input{width:100%; padding:10px 12px; border-radius:9px; border:1px solid var(--border); background:var(--bg); color:var(--text); font-size:1rem;}
input:focus{outline:2px solid var(--accent); outline-offset:1px;}
button{margin-top:16px; width:100%; padding:12px; border:none; border-radius:9px; background:var(--accent); color:var(--accent-text); font-size:1rem; font-weight:600; cursor:pointer;}
#status{min-height:20px; font-size:0.88rem; margin-top:10px;}
#status.ok{color:#1f9d55;} #status.err{color:var(--danger);}
.list-head{display:flex; justify-content:space-between; align-items:baseline; margin-bottom:8px;}
.list-head h2{font-size:1.05rem; margin:0;}
.count{color:var(--muted); font-size:0.85rem;}
.table-scroll{overflow-x:auto; border:1px solid var(--border); border-radius:12px;}
table{width:100%; border-collapse:collapse; min-width:560px; background:var(--card);}
th,td{text-align:left; padding:10px 12px; font-size:0.9rem; border-bottom:1px solid var(--border); white-space:nowrap;}
th{color:var(--muted); font-weight:600; font-size:0.78rem; text-transform:uppercase;}
tr:last-child td{border-bottom:none;}
.del-btn{background:none; border:none; color:var(--danger); cursor:pointer; font-size:1rem; padding:2px 6px;}
.empty{padding:20px; text-align:center; color:var(--muted); font-size:0.9rem;}
.warn{background:#fff7e6; border:1px solid #f0d38a; color:#7a5a00; border-radius:10px; padding:10px 14px; font-size:0.85rem; margin-bottom:18px;}
button.export{background:var(--card); color:var(--text); border:1px solid var(--border); margin-top:10px;}
</style>
</head>
<body>
<div class="wrap">
  <h1>📋 Liste pour le recours</h1>
  <p class="sub">Chaque élève renseigne ses informations ci-dessous.</p>
  <div class="warn">⚠️ Ce fichier stocke les données uniquement dans <b>ce navigateur, sur cet appareil</b> (localStorage). Si chaque élève ouvre le fichier sur son propre téléphone/PC, les listes ne seront <b>pas partagées automatiquement</b> entre eux. Pour une vraie liste commune en ligne, il faut héberger ce fichier avec une base de données partagée.</div>

  <div class="card">
    <form id="entry-form">
      <label for="etab">Établissement / lieu d'étude</label>
      <input id="etab" type="text" placeholder="Ex : Faculté de médecine, Blida" required>
      <label for="nom">Nom</label>
      <input id="nom" type="text" required>
      <label for="prenom">Prénom</label>
      <input id="prenom" type="text" required>
      <label for="matricule">Matricule</label>
      <input id="matricule" type="text" required>
      <button id="submit-btn" type="submit">Ajouter mon nom à la liste</button>
      <div id="status"></div>
    </form>
  </div>

  <div class="list-head">
    <h2>Liste des inscrits</h2>
    <span class="count" id="count-label"></span>
  </div>
  <div class="table-scroll">
    <div id="list-container"></div>
  </div>
  <button class="export" id="export-btn">⬇️ Exporter en CSV</button>
</div>

<script>
(function(){
  var KEY = 'recours_entries';

  function getEntries(){
    try{ return JSON.parse(localStorage.getItem(KEY) || '[]'); }
    catch(e){ return []; }
  }
  function saveEntries(entries){
    localStorage.setItem(KEY, JSON.stringify(entries));
  }
  function escapeHtml(s){
    return String(s).replace(/[&<>"']/g, function(c){
      return {'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c];
    });
  }
  function render(){
    var entries = getEntries();
    document.getElementById('count-label').textContent = entries.length + ' élève(s)';
    var container = document.getElementById('list-container');
    if(!entries.length){
      container.innerHTML = '<div class="empty">Aucune entrée pour le moment.</div>';
      return;
    }
    var rows = entries.map(function(e, i){
      return '<tr><td>'+(i+1)+'</td><td>'+escapeHtml(e.nom)+'</td><td>'+escapeHtml(e.prenom)+
        '</td><td>'+escapeHtml(e.matricule)+'</td><td>'+escapeHtml(e.etablissement)+
        '</td><td>'+escapeHtml(e.date||'')+'</td>'+
        '<td><button class="del-btn" data-i="'+i+'" title="Supprimer">✕</button></td></tr>';
    }).join('');
    container.innerHTML = '<table><thead><tr><th>#</th><th>Nom</th><th>Prénom</th><th>Matricule</th>'+
      '<th>Établissement</th><th>Date</th><th></th></tr></thead><tbody>'+rows+'</tbody></table>';
    container.querySelectorAll('.del-btn').forEach(function(btn){
      btn.addEventListener('click', function(){
        if(!confirm('Supprimer cette entrée ?')) return;
        var entries = getEntries();
        entries.splice(parseInt(btn.dataset.i,10), 1);
        saveEntries(entries);
        render();
      });
    });
  }
  function setStatus(msg, kind){
    var el = document.getElementById('status');
    el.textContent = msg;
    el.className = kind || '';
  }

  document.getElementById('entry-form').addEventListener('submit', function(ev){
    ev.preventDefault();
    var etab = document.getElementById('etab').value.trim();
    var nom = document.getElementById('nom').value.trim();
    var prenom = document.getElementById('prenom').value.trim();
    var matricule = document.getElementById('matricule').value.trim();
    if(!etab || !nom || !prenom || !matricule){
      setStatus('Merci de remplir tous les champs.', 'err');
      return;
    }
    var entries = getEntries();
    entries.push({
      etablissement: etab, nom: nom, prenom: prenom, matricule: matricule,
      date: new Date().toLocaleDateString('fr-FR')
    });
    saveEntries(entries);
    setStatus('✅ Ajouté à la liste.', 'ok');
    document.getElementById('entry-form').reset();
    render();
  });

  document.getElementById('export-btn').addEventListener('click', function(){
    var entries = getEntries();
    var header = 'Nom;Prenom;Matricule;Etablissement;Date\n';
    var rows = entries.map(function(e){
      return [e.nom,e.prenom,e.matricule,e.etablissement,e.date].join(';');
    }).join('\n');
    var blob = new Blob(['\uFEFF'+header+rows], {type:'text/csv;charset=utf-8;'});
    var url = URL.createObjectURL(blob);
    var a = document.createElement('a');
    a.href = url; a.download = 'liste-recours.csv';
    document.body.appendChild(a); a.click(); document.body.removeChild(a);
    URL.revokeObjectURL(url);
  });

  render();
})();
</script>
</body>
</html>
