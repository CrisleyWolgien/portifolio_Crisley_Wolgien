<template>
  <div>
    <the-header :is-dark-theme="isDarkTheme" @toggle-theme="toggleTheme">
      <template #logo>
        <img src="../src/assets/logo_size.svg" alt="Logo" class="logo" />
      </template>
      <template #home>
        <a href="#home" class="nav-items">Home</a>
      </template>
      <template #sobreMim>
        <a href="#sobre" class="nav-items">Sobre Mim</a>
      </template>
      <template #skills>
        <a href="#skills" class="nav-items">Skills</a>
      </template>
      <template #portifolio>
        <a href="#portifolio" class="nav-items">Portfólio</a>
      </template>
      <template #contato>
        <a href="#contato" class="nav-items">Contato</a>
      </template>
      <template #toggleTheme>
        <button @click="toggleTheme">Alternar Tema</button>
      </template>
    </the-header>

    <theHome id="home" :is-dark-theme="isDarkTheme" />
    <theSobremim id="sobre" :is-dark-theme="isDarkTheme" />
    <theSkills id="skills" :is-dark-theme="isDarkTheme" />
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheHome from './components/TheHome.vue';
import TheSobremim from './components/TheSobreMim.vue';
import TheSkills from './components/TheSkills.vue';

export default {
  components: {
    TheHeader,
    TheHome,
    TheSobremim,
    TheSkills,
  },
  data() {
    return {
      isDarkTheme: true,
    };
  },
  watch: {
    isDarkTheme(newValue) {
      document.body.classList.toggle('dark', newValue);
    },
  },
  methods: {
    toggleTheme() {
      this.isDarkTheme = !this.isDarkTheme;
    },
  },
  mounted() {
    document.body.classList.toggle('dark', this.isDarkTheme);
  },
};
</script>

<style>
/* Estilo global para o tema claro */
html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  padding: 0;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  background-color: #f4f6f9; /* Cor de fundo suave */
  color: #333; /* Texto escuro suave */
  transition: background-color 0.3s, color 0.3s;
  line-height: 1.6;
}

/* Estilo global para o tema escuro */
body.dark {
  background-color: #010A26;
  color: white;
}

/* Estilo para o cabeçalho */
.theHeader {
  background-color: #ffffff;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1); /* Sombra suave */
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
}

/* Estilo adicional para os links */
.nav-items {
  text-decoration: none;
  font-size: 18px; /* Tamanho de fonte mais confortável */
  color: #555; /* Cor mais suave */
  margin: 0 10px;
  transition: color 0.3s, transform 0.2s;
}

.nav-items:hover {
  color: #f55252; /* Cor de destaque */
  transform: scale(1.05); /* Efeito de aumento suave */
}

body.dark .nav-items {
  color: #f4f6f9;
}

body.dark .nav-items:hover {
  color: #f55252;
}

body.dark .logo {
  width: 100px;
  height: auto;
}

.logo {
  width: 120px;
  height: auto;
  transition: transform 0.2s ease;
}

.logo:hover {
  transform: scale(1.1);
}

/* Responsividade */
@media (max-width: 768px) {
  .nav-items {
    font-size: 16px; /* Tamanho de fonte ajustado para dispositivos menores */
  }

  button {
    width: 100%;
    font-size: 18px;
  }
}
</style>
