<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8" />
  <title>Data dari Google Sheet</title>
  <style>
    body {
      font-family: sans-serif;
      padding: 2em;
      background: #f9f9f9;
    }
    h1 {
      color: #333;
    }
    pre {
      background: #eee;
      padding: 1em;
      border-radius: 6px;
      overflow-x: auto;
    }
  </style>
</head>
<body>
  <h1>Data dari Google Sheet</h1>
  <pre id="output">Memuat data...</pre>

  <script>
    fetch("https://script.google.com/macros/s/AKfycbz18VrmRMZgmFiukKbJveShsJdynNa9SeFpae_CgRur1_jIRwbDQGWQJ6uL9IJhbiLO/exec")
      .then(res => {
        if (!res.ok) throw new Error("Network response was not ok: " + res.status);
        return res.json();
      })
      .then(data => {
        document.getElementById("output").textContent = JSON.stringify(data, null, 2);
      })
      .catch(err => {
        console.error("Fetch error:", err);
        document.getElementById("output").textContent = "Gagal memuat data: " + err.message;
      });
  </script>
</body>
</html>
