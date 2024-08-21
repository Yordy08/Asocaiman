<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
      <!-- Logo -->
      <a class="navbar-brand" href="#">
        <img
          src="https://img1.wsimg.com/isteam/ip/ff4aebe6-4dda-43e4-8481-67b120390fb6/asocaiman-1-0001.png/:/rs=w:1440,h:1440"
          alt="Logo Asocaiman"
          class="logo horizontal-logo"
          width="150"
          height="auto"
        />
      </a>

      <!-- Botón de menú móvil -->
      <button
        class="navbar-toggler"
        type="button"
        @click="toggleMenu"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <!-- Menú de navegación -->
      <div class="collapse navbar-collapse" :class="{ show: isMenuActive }" id="navbarNav">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <NuxtLink to="/" class="nav-link">Inicio</NuxtLink>
          </li>
          <li class="nav-item dropdown" @click="toggleDropdown('investigation')">
            <a
              class="nav-link dropdown-toggle"
              href="#"
              id="navbarDropdown1"
              role="button"
              :aria-expanded="isDropdownActive.investigation"
            >
              Investigación
            </a>
            <div
              class="dropdown-menu"
              :class="{ show: isDropdownActive.investigation }"
              aria-labelledby="navbarDropdown1"
            >
              <NuxtLink to="/antec" class="dropdown-item">ANTECEDENTES</NuxtLink>
              <NuxtLink to="/actual" class="dropdown-item">ACTUALIDAD</NuxtLink>
              <NuxtLink to="/result" class="dropdown-item">RESULTADOS</NuxtLink>
              <NuxtLink to="/cites" class="dropdown-item">ENMIENDA CITES</NuxtLink>
            </div>
          </li>
          <li class="nav-item dropdown" @click="toggleDropdown('programs')">
            <a
              class="nav-link dropdown-toggle"
              href="#"
              id="navbarDropdown2"
              role="button"
              :aria-expanded="isDropdownActive.programs"
            >
              Programas
            </a>
            <div
              class="dropdown-menu"
              :class="{ show: isDropdownActive.programs }"
              aria-labelledby="navbarDropdown2"
            >
              <NuxtLink to="/educ" class="dropdown-item">EDUCACIÓN</NuxtLink>
              <NuxtLink to="/sosten" class="dropdown-item">USO SOSTENIBLE</NuxtLink>
            </div>
          </li>
          <li class="nav-item">
            <NuxtLink to="/trayect" class="nav-link">Trayectoria</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink to="/somo" class="nav-link">Quiénes somos</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink to="/contac" class="nav-link">Contáctanos</NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const isMenuActive = ref(false)
const isDropdownActive = ref({
  investigation: false,
  programs: false,
})

const toggleMenu = () => {
  isMenuActive.value = !isMenuActive.value
}

const toggleDropdown = (dropdown) => {
  isDropdownActive.value[dropdown] = !isDropdownActive.value[dropdown]

  // Close other dropdowns
  if (dropdown === 'investigation') {
    isDropdownActive.value.programs = false
  } else if (dropdown === 'programs') {
    isDropdownActive.value.investigation = false
  }
}
</script>

<style scoped>
/* Espaciado entre los elementos de la barra de navegación */
.navbar .nav-item:not(:last-child) {
  margin-right: 35px;
}

/* Ajuste para el menú desplegable en modo móvil */
@media (max-width: 991.98px) {
  .navbar-collapse {
    position: absolute;
    top: 56px; /* Ajusta este valor si es necesario */
    right: 0;
    width: 100%;
    background-color: #343a40;
    padding: 0.5rem 1rem;
    z-index: 1000;
  }

  .navbar-nav {
    display: flex;
    flex-direction: column;
    width: 100%;
  }

  .nav-link {
    padding: 0.75rem 1.25rem; /* Ajusta el espaciado de los enlaces */
  }

  .dropdown-menu {
    width: 100%; /* Asegura que el menú desplegable ocupe todo el ancho */
    position: static; /* Cambia la posición a estática en modo móvil */
  }

  .dropdown-item {
    padding: 0.75rem 1.25rem; /* Ajusta el espaciado de los elementos del dropdown */
  }

  .navbar-toggler {
    margin-left: auto; /* Alinea el botón de menú a la derecha */
  }
}

/* Estilo para el icono de dropdown */
.dropdown-toggle::after {
   transition: transform 0.15s linear; 
}

.show.dropdown .dropdown-toggle::after {
  transform: translateY(3px);
}
</style>
