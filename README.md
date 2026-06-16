<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Zapatilla IA SECCIÓN 710</title>

<!-- Bootstrap -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

<style>
:root{
    --shadow: 0 15px 35px rgba(0,0,0,.12);
}

body{
    background:#f8f9fa;
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    font-family:'Segoe UI',sans-serif;
}

.product-card{
    width:100%;
    max-width:520px;
    background:#fff;
    border:none;
    border-radius:25px;
    padding:35px;
    box-shadow:var(--shadow);
    text-align:center;
}

.product-title{
    font-size:1.7rem;
    font-weight:700;
    color:#222;
    margin-bottom:20px;
    letter-spacing:.5px;
}

.color-options{
    display:flex;
    justify-content:center;
    gap:12px;
    margin-bottom:25px;
}

.color-box{
    width:32px;
    height:32px;
    border-radius:8px;
    cursor:pointer;
    border:2px solid #ddd;
    transition:.3s;
}

.color-box:hover{
    transform:scale(1.15);
    box-shadow:0 0 12px rgba(0,0,0,.15);
}

.color-box.active{
    border:3px solid #0d6efd;
}

.tenis-container{
    display:flex;
    justify-content:center;
    align-items:center;
    min-height:280px;
}

.tenis-img{
    max-width:100%;
    max-height:260px;
    object-fit:contain;
    cursor:pointer;
    transition:.4s;
    filter:drop-shadow(0 15px 20px rgba(0,0,0,.15));
}

.tenis-img:hover{
    transform:scale(1.04);
}

.price{
    margin-top:20px;
    font-size:2rem;
    font-weight:700;
    color:#111;
}

.size-selector{
    margin:20px 0;
}

.form-select{
    max-width:200px;
    margin:auto;
    border-radius:12px;
}

.btn-buy{
    width:100%;
    padding:14px;
    border:none;
    border-radius:14px;
    font-weight:700;
    letter-spacing:1px;
    background:#111;
    color:#fff;
    transition:.3s;
}

.btn-buy:hover{
    background:#000;
    transform:translateY(-2px);
}

.modal-content{
    background:rgba(255,255,255,.98);
    border:none;
    border-radius:20px;
}

.modal-body{
    display:flex;
    justify-content:center;
    align-items:center;
    min-height:75vh;
}

.modal-img{
    width:100%;
    max-height:80vh;
    object-fit:contain;
}

.btn-close{
    position:absolute;
    right:15px;
    top:15px;
    z-index:100;
}
</style>
</head>
<body>

<div class="product-card">

    <h1 class="product-title">
        Zapatilla IA SECCIÓN 710
    </h1>

    <!-- Colores -->
    <div class="color-options">

        <div
            class="color-box active"
            style="background:white"
            title="Color Blanco - Diseño limpio y elegante"
            data-img="img/blanco.png">
        </div>

        <div
            class="color-box"
            style="background:black"
            title="Color Negro - Estilo urbano premium"
            data-img="img/negro.png">
        </div>

        <div
            class="color-box"
            style="background:#FFD600"
            title="Color Amarillo - Energía y personalidad"
            data-img="img/amarillo.png">
        </div>

        <div
            class="color-box"
            style="background:#e53935"
            title="Color Rojo - Deportivo y moderno"
            data-img="img/rojo.png">
        </div>

    </div>

    <!-- Imagen -->
    <div class="tenis-container">
        <img
            id="shoeImage"
            src="img/blanco.png"
            alt="Tenis Air Force"
            class="tenis-img"
            data-bs-toggle="modal"
            data-bs-target="#shoeModal">
    </div>

    <div class="price">
        $120 USD
    </div>

    <!-- Tallas -->
    <div class="size-selector">
        <select class="form-select">
            <option selected>Seleccionar talla</option>
            <option>38</option>
            <option>40</option>
            <option>42</option>
        </select>
    </div>

    <!-- Botón -->
    <button class="btn-buy">
        COMPRAR
    </button>

</div>

<!-- Modal -->
<div class="modal fade" id="shoeModal" tabindex="-1">

    <div class="modal-dialog modal-dialog-centered modal-xl">

        <div class="modal-content">

            <button
                type="button"
                class="btn-close"
                data-bs-dismiss="modal">
            </button>

            <div class="modal-body">

                <img
                    id="modalImage"
                    src="img/blanco.png"
                    class="modal-img"
                    alt="Vista ampliada">

            </div>

        </div>

    </div>

</div>

<!-- Bootstrap JS -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>

<script>
const shoeImage = document.getElementById("shoeImage");
const modalImage = document.getElementById("modalImage");
const colors = document.querySelectorAll(".color-box");

colors.forEach(color => {

    color.addEventListener("click", () => {

        const img = color.dataset.img;

        shoeImage.src = img;
        modalImage.src = img;

        colors.forEach(c => c.classList.remove("active"));
        color.classList.add("active");
    });

});


shoeImage.addEventListener("click", () => {
    modalImage.src = shoeImage.src;
});
</script>

</body>
</html>
