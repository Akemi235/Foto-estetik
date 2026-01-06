<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Galeri Foto Estetik</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Galeri Foto Estetik</h1>
        <p>Temukan keindahan dalam setiap momen.</p>
    </header>
    
    <main>
        <div class="gallery">
            <img src="images/foto1.jpg" alt="Foto Estetik 1" onclick="openModal(this)">
            <img src="images/foto2.jpg" alt="Foto Estetik 2" onclick="openModal(this)">
            <img src="images/foto3.jpg" alt="Foto Estetik 3" onclick="openModal(this)">
            <!-- Tambahkan lebih banyak img sesuai kebutuhan -->
        </div>
    </main>
    
    <!-- Modal untuk zoom foto -->
    <div id="modal" class="modal">
        <span class="close" onclick="closeModal()">&times;</span>
        <img id="modal-img" class="modal-content">
    </div>
    
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: 'Arial', sans-serif;
    margin: 0;
    padding: 0;
    background: linear-gradient(135deg, #f5f7fa, #c3cfe2);
    color: #333;
    text-align: center;
}

header {
    padding: 50px 20px;
    background: rgba(255, 255, 255, 0.8);
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

h1 {
    font-size: 2.5em;
    margin: 0;
}

.gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
    padding: 20px;
    max-width: 1200px;
    margin: 0 auto;
}

.gallery img {
    width: 100%;
    height: 200px;
    object-fit: cover;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s ease;
    cursor: pointer;
}

.gallery img:hover {
    transform: scale(1.05);
}

/* Modal styling */
.modal {
    display: none;
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.9);
    justify-content: center;
    align-items: center;
}

.modal-content {
    max-width: 90%;
    max-height: 90%;
}

.close {
    position: absolute;
    top: 15px;
    right: 35px;
    color: #fff;
    font-size: 40px;
    font-weight: bold;
    cursor: pointer;
}
function openModal(img) {
    const modal = document.getElementById('modal');
    const modalImg = document.getElementById('modal-img');
    modal.style.display = 'flex';
    modalImg.src = img.src;
}

function closeModal() {
    document.getElementById('modal').style.display = 'none';
}

// Tutup modal jika klik di luar gambar
window.onclick = function(event) {
    const modal = document.getElementById('modal');
    if (event.target === modal) {
        modal.style.display = 'none';
    }
}
