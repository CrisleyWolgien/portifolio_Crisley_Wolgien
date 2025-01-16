<template>
  <div :class="['theHeader', { dark: isDarkTheme }]">
    <slot name="logo"></slot>
    <nav :class="['theHeader__nav', { active: menuOpen }]">
      <slot name="home"></slot>
      <slot name="sobreMim"></slot>
      <slot name="skills"></slot>
      <slot name="portifolio"></slot>
      <slot name="contato"></slot>
    </nav>
    <!-- Exibe o ícone de menu ou o "X" de fechamento, dependendo do estado do menu -->
    <div class="menu-toggle" @click="toggleMenu">
      <div v-if="!menuOpen" class="bar"></div>
      <div v-if="!menuOpen" class="bar"></div>
      <div v-if="!menuOpen" class="bar"></div>
      <div v-if="menuOpen" class="close-menu">×</div>
    </div>
    <!-- Botão de alternar tema com ícones de sol e lua -->
    <div class="theme-toggle" @click="toggleTheme">
      <span v-if="!isDarkTheme" class="theme-icon sun">☀️</span> <!-- Sol -->
      <span v-if="isDarkTheme" class="theme-icon moon">🌙</span> <!-- Lua -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'TheHeader',
  props: {
    isDarkTheme: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      menuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
    toggleTheme() {
      this.$emit('toggle-theme');
    },
  },
};
</script>

<style>
.theHeader {
  margin-top: 2rem;
  justify-self: center;
  width: 90%;
  max-width: 1500px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5rem 2rem;
  background-color: #fafafa;
  color: #333333;
  border: 1px solid #e0e0e0;
  border-radius: 20px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s, color 0.3s, box-shadow 0.3s;
}

.theHeader.dark {
  background-color: #010B40;
  color: #e9e5e5;
  border-color: #048ABF;
  box-shadow: 0px 4px 12px rgba(4, 138, 191, 0.3);
}

.theHeader__nav {
  display: flex;
  gap: 1.5rem;
}

.theHeader__nav slot::slotted(a) {
  text-decoration: none;
  font-size: 1rem;
  font-weight: bold;
  color: #333333;
  transition: color 0.3s;
}

.theHeader__nav slot::slotted(a:hover) {
  color: #048ABF;
}

.theHeader.dark .theHeader__nav slot::slotted(a:hover) {
  color: #f55252;
}

.menu-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  gap: 5px;
}

.menu-toggle .bar {
  width: 25px;
  height: 3px;
  background-color: #333;
  transition: transform 0.3s, opacity 0.3s;
}

.menu-toggle .bar.active:nth-child(1) {
  transform: rotate(45deg);
  position: relative;
  top: 7px;
}

.menu-toggle .bar.active:nth-child(2) {
  opacity: 0;
}

.menu-toggle .bar.active:nth-child(3) {
  transform: rotate(-45deg);
  position: relative;
  bottom: 7px;
}

.theHeader__nav.active {
  display: block;
}

.close-menu {
  font-size: 2rem;
  color: #333333;
  cursor: pointer;
  position: absolute;
  top: 10px;
  right: 15px;
  padding: 5px;
  background-color: rgba(255, 255, 255, 0.6);
  border-radius: 50%;
  display: block;
  transition: background-color 0.3s, color 0.3s;
}

.close-menu:hover {
  color: #f55252;
}

.theme-toggle {
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}

.theme-icon {
  font-size: 1.5rem;
  transition: transform 0.3s;
}

.sun {
  color: #fbc02d;
}

.moon {
  color: #fff;
}

@media (max-width: 768px) {
  .theHeader__nav {
    display: none;
    width: 100%;
    flex-direction: column;
    align-items: center;
    background-color: #fafafa;
    position: absolute;
    top: 60px;
    left: 0;
    padding: 1rem 0;
  }

  .theHeader__nav slot::slotted(a) {
    margin: 10px 0;
    color: #333333;
  }

  .menu-toggle {
    display: flex;
  }

  .theHeader__nav.active {
    display: flex;
  }

  .theHeader.dark .menu-toggle .bar {
    background-color: #fff;
  }

  .theHeader.dark .theHeader__nav.active {
    background-color: #010B40;
  }
}
</style>
