<!DOCTYPE html>
<html>
<head><title>Ambil Data Google Sheet</title></head>
<body>
  <h1>Data dari Google Sheet</h1>
  <pre id="output"></pre>

  <script>
    fetch("https://script.google.com/macros/s/AKfycbz18VrmRMZgmFiukKbJveShsJdynNa9SeFpae_CgRur1_jIRwbDQGWQJ6uL9IJhbiLO/exec")
      .then(res => res.json())
      .then(data => {
        document.getElementById("output").textContent = JSON.stringify(data, null, 2);
      })
      .catch(err => console.error("Fetch error:", err));
  </script>
</body>
</html>
