<!DOCTYPE html>
<html>
<head>
  <title>Ambil Data Google Sheet</title>
</head>
<body>
  <h1>Data dari Google Sheet</h1>
  <div id="output"></div>

  <script>
    fetch("https://script.google.com/macros/s/AKfycbz18VrmRMZgmFiukKbJveShsJdynNa9SeFpae_CgRur1_jIRwbDQGWQJ6uL9IJhbiLO/exec")
      .then(response => response.json())
      .then(data => {
        const output = document.getElementById("output");
        output.innerHTML = "<pre>" + JSON.stringify(data, null, 2) + "</pre>";
      })
      .catch(error => {
        console.error("Error:", error);
      });
  </script>
</body>
</html>
