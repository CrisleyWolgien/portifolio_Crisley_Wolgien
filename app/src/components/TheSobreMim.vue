<template>
    <div :class="['theSobreMim', { dark: isDarkTheme }]">
      <h3 id="title_name">Sobre Mim</h3>
      <div class="theSobreMim__description">
        <h2>Estudante de Engenharia de
        <br/>Software</h2>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "TheSobreMim",
    props: {
      isDarkTheme: {
        type: Boolean,
        default: false,
      },
    },
  };
  </script>
  
  <style>
  /* Variáveis de tema */
  :root {
    --color-light-bg: #f9f9f9;
    --color-light-text: #333333;
    --color-dark-bg: #010B40; /* Tema escuro com fundo azul mais escuro */
    --color-dark-text: #e9e5e5; /* Texto claro para o tema escuro */
    --color-button-bg: #048abf;
    --color-button-hover: #036a91;
    --color-highlight: #0cf25d;
  }
  .theSobreMim {
    margin: 2rem auto;
    width: 85%;
    max-width: 1200px;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    background-color: #ffffff;
    color: #000000;
    border-radius: 15px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    transition: background-color 0.3s, color 0.3s, box-shadow 0.3s;
  }

  .theSobreMim.dark {
    background-color: #010B40; /* Fundo escuro original */
    color: #e9e5e5; /* Texto claro no tema escuro */
  }

  #title_name {
    font-size: 1.5rem;
    font-weight: normal;
    margin-bottom: 0.5rem;
    margin-top: 0%;
    line-height: 1.2;
  }

  .theSobreMim__description {
    display: flex;
    flex-direction: column;
  }
  </style>
  