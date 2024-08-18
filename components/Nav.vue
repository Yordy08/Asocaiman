<template>
    <nav class="navbar is-dark">
      <div class="container">
        <!-- Logo -->
        <div class="navbar-brand">
          <a href="/" class="navbar-item">
            <img
              src="https://img1.wsimg.com/isteam/ip/ff4aebe6-4dda-43e4-8481-67b120390fb6/asocaiman-1-0001.png/:/rs=w:1440,h:1440"
              alt="Logo Asocaiman"
              width="250"
              height="auto"
            />
          </a>
          <!-- Menú móvil -->
          <a
            role="button"
            class="navbar-burger"
            aria-label="menu"
            aria-expanded="false"
            @click="toggleMenu"
            :class="{ 'is-active': isMenuActive }"
          >
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
          </a>
        </div>
        
        <!-- Menú de navegación -->
        <div :class="['navbar-menu', { 'is-active': isMenuActive }]">
          <div class="navbar-start">
            <NuxtLink to="/" class="navbar-item">Inicio</NuxtLink>
            <div class="navbar-item has-dropdown" @click="toggleDropdown('investigation')">
              <a class="navbar-link">Investigación</a>
              <div :class="['navbar-dropdown', { 'is-active': isDropdownActive.investigation }]">
                <NuxtLink to="/antec" class="navbar-item">ANTECEDENTES</NuxtLink>
                <NuxtLink to="/actual" class="navbar-item">ACTUALIDAD</NuxtLink>
                <NuxtLink to="/result" class="navbar-item">RESULTADOS</NuxtLink>
                <NuxtLink to="/cites" class="navbar-item">ENMIENDA CITES</NuxtLink>
              </div>
            </div>
            <div class="navbar-item has-dropdown" @click="toggleDropdown('programs')">
              <a class="navbar-link">Programas</a>
              <div :class="['navbar-dropdown', { 'is-active': isDropdownActive.programs }]">
                <NuxtLink to="/educ" class="navbar-item">EDUCACIÓN</NuxtLink>
                <NuxtLink to="/sosten" class="navbar-item">USO SOSTENIBLE</NuxtLink>
              </div>
            </div>
            <NuxtLink to="/trayect" class="navbar-item">Trayectoria</NuxtLink>
            <NuxtLink to="/somo" class="navbar-item">Quiénes somos</NuxtLink>
            <NuxtLink to="/contac" class="navbar-item">Contáctanos</NuxtLink>
          </div>
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
  /* Estilos para la barra de navegación */
  .navbar {
    background-color: #363636; /* Color de fondo oscuro para la barra de navegación */
    padding: 1rem 1.5rem; /* Aumentar el espaciado en la barra de navegación */
    border-bottom: 2px solid #444; /* Engrosar la barra de navegación */
  }
  
  /* Estilos para el botón de hamburguesa */
  .navbar-burger {
    display: none; /* Oculta el botón de hamburguesa en pantallas grandes */
    flex-direction: column;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    border: none;
    background: transparent;
  }
  
  .navbar-burger span {
    display: block;
    width: 1.5rem;
    height: 2px;
    background-color: white;
    margin: 0.3rem 0;
  }
  
  /* Estilos para el menú desplegable */
  .navbar-menu {
    display: flex;
    align-items: center;
  }
  
  /* Menú desplegable en pantallas móviles */
  @media (max-width: 1023px) {
    .navbar-menu {
      display: none;
      flex-direction: column;
      width: 100%;
      background-color: #363636;
      position: absolute;
      top: 4rem;
      left: 0;
      z-index: 1000;
    }
  
    .navbar-menu.is-active {
      display: flex;
    }
  
    .navbar-burger {
      display: flex;
    }
  }
  
  /* Estilo de los enlaces del menú */
  .navbar-item {
    color: white;
    padding: 0.80rem 1.9rem; /* Aumentar el espaciado de los enlaces */
  }
  
  .navbar-item:hover {
    background-color: #555;
  }
  
  /* Estilos para el dropdown */
  .navbar-dropdown {
    display: none;
    position: absolute;
    background-color: #363636;
    top: 100%;
    left: 0;
    z-index: 1000;
    width: 100%;
  }
  
  .navbar-dropdown.is-active {
    display: block;
  }
  
  .navbar-dropdown .navbar-item {
    color: #fff;
    padding: 0.75rem 1rem; /* Aumentar el espaciado de los elementos del dropdown */
  }
  
  .navbar-dropdown .navbar-item:hover {
    background-color: #555;
  }
  </style>
  