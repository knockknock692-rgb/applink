<!doctype html>
<html lang="fr">
<head>
  <meta charset="utf-8"/>
  <title>IP Leak</title>
  <style>
    body { font-family: system-ui, sans-serif; display:flex; align-items:center; justify-content:center;
           height:100vh; margin:0; background:#111; color:#eee; }
    .card { padding:28px; border-radius:12px; box-shadow: 0 8px 28px rgba(0,0,0,.6); text-align:center; }
    .title { font-size:18px; font-weight:600; letter-spacing:0.6px; }
    .ip { font-size:30px; margin-top:14px; font-weight:800; letter-spacing:1px; }
  </style>
</head>
<body>
  <div class="card">
    <div class="title">IP leaked</div>
    <div id="ip" class="ip">Chargement…</div>
  </div>

  <script>
    // Récupère l'IP publique via ipify
    fetch('https://api.ipify.org?format=json')
      .then(r => r.json())
      .then(j => {
        document.getElementById('ip').textContent = j.ip;
      })
      .catch(() => {
        document.getElementById('ip').textContent = 'Impossible de récupérer l\'IP';
      });
  </script>
</body>
</html>
