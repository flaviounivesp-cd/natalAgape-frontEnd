<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import 'bootstrap/dist/js/bootstrap.bundle.min.js'

const navLinks = ref<NodeListOf<Element>>()

const closeMobileMenu = () => {
  if (window.innerWidth < 992) { // Check if mobile view
    const navbarToggler = document.querySelector('.navbar-toggler')
    const navbarCollapse = document.querySelector('.navbar-collapse')
    
    if (navbarCollapse?.classList.contains('show')) {
      navbarToggler?.dispatchEvent(new Event('click'))
    }
  }
}
</script>

<template>
  <header>

    <div class="wrapper">
      <nav class="navbar navbar-expand-lg bg-success navbar-dark">
        <div class="container">
          <RouterLink class="navbar-brand" to="/" aria-current="Página Inicial"><b><h2>Ágape</h2></b></RouterLink>
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup"
            aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
            <div class="navbar-nav ms-auto mb-2 mb-lg-0">
                <RouterLink class="nav-link" to="/family" aria-current="Famílias"><b>Famílias</b></RouterLink>
                <RouterLink class="nav-link" to="/leader" aria-current="Lideres"><b>Lideres</b></RouterLink>
                <RouterLink class="nav-link" to="/sponsor" aria-current="Doadores"><b>Doadores</b></RouterLink>
                <RouterLink class="nav-link" to="/neighborhood" aria-current="Bairros"><b>Bairros</b></RouterLink>
                <RouterLink class="nav-link" to="/campaign" aria-current="Campanhas"><b>Campanhas</b></RouterLink>
                <RouterLink class="nav-link" to="/about" aria-current="Sobre"><b>Sobre</b></RouterLink>
            </div>
          </div>
        </div>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
.navbar-toggler:focus {
  box-shadow: 0 0 0 0.1rem rgba(255, 255, 255, 0.5);
}

@media (max-width: 991.98px) {
  .navbar-nav {
    padding-top: 1rem;
  }
  
  .nav-link {
    padding: 0.5rem 1rem;
  }
}</style>
