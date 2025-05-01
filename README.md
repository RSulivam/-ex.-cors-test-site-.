# -ex.-cors-test-site-.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CORS Test</title>
</head>
<body>
  <h1>CORS Test Page</h1>
  <button id="testBtn">Test CORS Request</button>
  <pre id="output"></pre>
  
  <script>
    document.getElementById('testBtn').addEventListener('click', async () => {
      const output = document.getElementById('output');
      try {
        const response = await fetch('https://developer.gojek.com', {
          method: 'GET',
          mode: 'cors',
        });
        const text = await response.text();
        output.textContent = text;
      } catch (error) {
        output.textContent = 'Error: ' + error;
      }
    });
  </script>
</body>
</html>
