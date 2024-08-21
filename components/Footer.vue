<template>
   <!-- Footer -->
<footer class="bg-dark text-white mt-5">
  <div class="container py-4">
    <div class="row">
      <!-- Información principal -->
      <div class="col-md-6">
        <h5>Anímese a vivir esta experiencia</h5>
        <p>Estación CIMACI, Vereda Amaya, San Antero, Córdoba, Colombia</p>
        <p><strong>Teléfonos:</strong> 300 8101161 / 300 8101164 / 3127337450</p>
        <p><strong>Email:</strong> <a href="mailto:aasocaiman@gmail.com" class="text-white">aasocaiman@gmail.com</a></p>
        <p><strong>Contáctenos:</strong> <a href="#" class="text-white">Clic aquí</a></p>
      </div>

      <!-- Categorías -->
      <div class="col-md-3">
        <h5>Categorías</h5>
        <ul class="list-unstyled">
          <li><a href="#" class="text-white">Categoría 1</a></li>
          <li><a href="#" class="text-white">Categoría 2</a></li>
          <li><a href="#" class="text-white">Categoría 3</a></li>
          <li><a href="#" class="text-white">Categoría 4</a></li>
          <li><a href="#" class="text-white">Categoría 5</a></li>
        </ul>
      </div>

      <!-- Colaboradores con Slider -->
      <div class="col-md-3">
        <h5>Colaboradores</h5>
        <div id="colaboradoresCarousel" class="carousel slide" data-bs-ride="carousel">
          <div class="carousel-inner">
            <!-- Primer Slide -->
            <div class="carousel-item active">
              <img src="https://via.placeholder.com/100x100" class="d-block mx-auto logo-colaborador" alt="Colaborador 1">
            </div>
            <!-- Segundo Slide -->
            <div class="carousel-item">
              <img src="https://via.placeholder.com/100x100" class="d-block mx-auto logo-colaborador" alt="Colaborador 2">
            </div>
            <!-- Tercer Slide -->
            <div class="carousel-item">
              <img src="https://via.placeholder.com/100x100" class="d-block mx-auto logo-colaborador" alt="Colaborador 3">
            </div>
            <!-- Agrega más Slides si es necesario -->
          </div>
          <!-- Controles de Next y Previo -->
          <button class="carousel-control-prev" type="button" data-bs-target="#colaboradoresCarousel" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previo</span>
          </button>
          <button class="carousel-control-next" type="button" data-bs-target="#colaboradoresCarousel" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
          </button>
        </div>
      </div>
    </div>
  </div>

  <div class="bg-secondary text-center py-2">
    <p class="mb-0">&copy; 2024 Estación ASOCAIMAN. Todos los derechos reservados.</p>
  </div>
</footer>
  </template>
  
  <script>
  export default {
    name: 'Footer'
  }
  </script>
  
  <style scoped>
 @import "https://cdn.jsdelivr.net/npm/bulma@1.0.2/css/bulma.min.css";
 .logo-colaborador {
      max-width: 100px;
      max-height: 100px;
      object-fit: contain;
    }
  </style>
  