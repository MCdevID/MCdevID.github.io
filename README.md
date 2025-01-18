# UUID Generator
<div id="uuid-generator">
  <button onclick="generateUUID()">Generate UUID</button>
  <p id="uuid-result">UUID akan muncul di sini.</p>
</div>

<script>
  function generateUUID() {
    const uuid = ([1e7]+-1e3+-4e3+-8e3+-1e11).replace(/[018]/g, c =>
      (c ^ crypto.getRandomValues(new Uint8Array(1))[0] & 15 >> c / 4).toString(16)
    );
    document.getElementById('uuid-result').innerText = uuid;
  }
</script>
