<!DOCTYPE html><html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Galeria Moderna</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
  <style>
    * { box-sizing: border-box; }body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  background: linear-gradient(135deg, #667eea, #764ba2);
  min-height: 100vh;
  color: #333;
}

header {
  text-align: center;
  padding: 30px 15px;
  color: white;
}

header h1 {
  margin: 0;
  font-size: 2.2rem;
}

header p {
  margin-top: 8px;
  font-size: 1rem;
  opacity: 0.9;
}

.container {
  max-width: 1100px;
  margin: auto;
  padding: 15px;
}

.upload-box {
  background: white;
  border-radius: 16px;
  padding: 20px;
  text-align: center;
  box-shadow: 0 10px 25px rgba(0,0,0,0.15);
  margin-bottom: 25px;
}

.upload-box input {
  display: none;
}

.upload-label {
  display: inline-block;
  padding: 14px 22px;
  background: #667eea;
  color: white;
  border-radius: 30px;
  cursor: pointer;
  font-weight: 500;
  transition: 0.3s;
}

.upload-label:hover {
  background: #5563d6;
}

.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
  gap: 15px;
}

.gallery img {
  width: 100%;
  height: 160px;
  object-fit: cover;
  border-radius: 14px;
  box-shadow: 0 6px 15px rgba(0,0,0,0.25);
  transition: transform 0.3s;
}

.gallery img:hover {
  transform: scale(1.05);
}

@media (max-width: 600px) {
  header h1 { font-size: 1.8rem; }
  .gallery img { height: 140px; }
}

  </style>
</head>
<body>  <header>
    <h1>Minha Galeria</h1>
    <p>Adicione e visualize suas imagens</p>
  </header>  <div class="container">
    <div class="upload-box">
      <label class="upload-label" for="imageInput">Selecionar Imagens</label>
      <input type="file" id="imageInput" accept="image/*" multiple>
    </div><div class="gallery" id="gallery"></div>

  </div>  <script>
    const input = document.getElementById('imageInput');
    const gallery = document.getElementById('gallery');

    input.addEventListener('change', () => {
      [...input.files].forEach(file => {
        const reader = new FileReader();
        reader.onload = e => {
          const img = document.createElement('img');
          img.src = e.target.result;
          gallery.appendChild(img);
        };
        reader.readAsDataURL(file);
      });
    });
  </script></body>
</html># galeria
