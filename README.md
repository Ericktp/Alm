<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Controle de Almoxarifado</title>
  <style>
    /* Estilos CSS aqui */
    /* ... (mesmos estilos do exemplo anterior) ... */
  </style>
</head>
<body>
  <header>
    <h1>Controle de Almoxarifado</h1>
  </header>
  
  <main>
    <table id="mercadorias">
      <thead>
        <tr>
          <th>Mercadoria</th>
          <th>Quantidade</th>
          <th>Especificação</th>
          <th>Data/Hora</th>
        </tr>
      </thead>
      <tbody id="lista-mercadorias">
        <!-- Linhas de mercadorias serão adicionadas aqui via JavaScript -->
      </tbody>
    </table>
    
    <form id="form">
      <label for="nome">Mercadoria:</label>
      <input type="text" id="nome" required>
      
      <label for="quantidade">Quantidade:</label>
      <input type="number" id="quantidade" required>
      
      <label for="especificacao">Especificação:</label>
      <input type="text" id="especificacao" required>
      
      <button type="button" onclick="adicionarMercadoria()">Adicionar</button>
      <button type="button" onclick="salvarPDF()">Salvar como PDF</button>
      <button type="button" onclick="salvarWord()">Salvar como Word</button>
    </form>
  </main>
  
  <!-- Inclua as bibliotecas jsPDF e docxtemplater aqui -->
  
  <script>
    const listaMercadorias = document.getElementById('lista-mercadorias');
    
    function adicionarMercadoria() {
      const nome = document.getElementById('nome').value;
      const quantidade = document.getElementById('quantidade').value;
      const especificacao = document.getElementById('especificacao').value;
      const dataHora = new Date().toLocaleString();
      
      const novaMercadoria = `
        <tr>
          <td>${nome}</td>
          <td>${quantidade}</td>
          <td>${especificacao}</td>
          <td>${dataHora}</td>
        </tr>
      `;
      
      listaMercadorias.innerHTML += novaMercadoria;
      
      // Limpar campos do formulário
      document.getElementById('nome').value = '';
      document.getElementById('quantidade').value = '';
      document.getElementById('especificacao').value = '';
    }
    
    function salvarPDF() {
      // ... (código para salvar em PDF usando jsPDF) ...
    }
    
    function salvarWord() {
      // ... (código para salvar em Word usando docxtemplater) ...
    }
  </script>
</body>
</html>
