<template>
  <div :class="['theSobreMim', { dark: isDarkTheme }]">
    <h3 id="title_name">Sobre Mim</h3>
    <div class="theSobreMim__description">
      <h2>Estudante de Engenharia de
        <br />Software
      </h2>
    </div>
    <div class="text_sobreMim ">
      <p>
        Olá, sou Crisley Wolgien Simões, tenho 20 anos e sou apaixonado por tecnologia desde a infância. Jogos e
        computadores sempre me fascinaram, o que despertou meu interesse pelo mundo da computação.<br />
        Durante o ensino médio, decidi dar um passo a mais nessa paixão e adquiri um curso de desenvolvimento web. Foi
        nesse momento que descobri minha vocação para programação. No final do ensino médio, tomei a decisão de cursar
        Engenharia de Software, e já estou nessa jornada há dois anos.<br />
        No início, enfrentei desafios, especialmente na lógica de programação, mas com esforço e dedicação, superei
        essas barreiras e me sinto cada vez mais confortável com as linguagens de programação. Atualmente, estou focado
        no estudo de HTML, CSS, JavaScript, Vue.js, React.js e C#. Como próximo passo, pretendo explorar novas áreas,
        como Python, Java e banco de dados, ampliando ainda mais meu conhecimento.<br />
        Meu principal objetivo no momento é ingressar na área de desenvolvimento, adquirir experiência prática e me
        aperfeiçoar profissionalmente. Estou determinado a crescer nesse campo e a contribuir com minhas habilidades
        para projetos e equipes.<br />
      </p>
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
  --color-dark-bg: #010B40;
  --color-dark-text: #e9e5e5;
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
  background-color: var(--color-light-bg);
  color: var(--color-light-text);
  border-radius: 15px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s ease, color 0.3s ease, box-shadow 0.3s ease;
  position: relative;
  overflow: hidden;
}

.theSobreMim::before {
  content: "";
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(0, 204, 153, 0.2), transparent 70%);
  z-index: 0;
}

.theSobreMim.dark {
  background-color: var(--color-dark-bg);
  color: var(--color-dark-text);
}

#title_name {
  font-size: 1.2rem;
  font-weight: bold;
  margin-bottom: 1rem;
  line-height: 1.4;
  width: 100%;
  border-bottom: 2px solid var(--color-highlight);
  padding-bottom: 0.5rem;
  position: relative;
  z-index: 1;
}

.theSobreMim__description {
  display: flex;
  flex-direction: column;
  margin-bottom: 1.5rem;
  position: relative;
  z-index: 1;
}

.theSobreMim__description h2 {
  font-size: 2rem;
  font-weight: bold;
  margin: 0;
  line-height: 1.2;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
}

.text_sobreMim {
  width: 100%;
  font-size: 1rem;
  line-height: 1.6;
  color: inherit;
  text-align: justify;
  line-height: 30px;
  position: relative;
  z-index: 1;
}

.text_sobreMim p {
  margin: 0;
}

@media (min-width: 768px) {
  .theSobreMim {
    padding: 3rem;
  }

  .theSobreMim__description h2 {
    font-size: 2.5rem;
  }

  .text_sobreMim {
    font-size: 1.1rem;
    width: 90%;
  }
}

@media (min-width: 1200px) and (max-width: 1399px) {
  .theSobreMim {
    width: 80%;
    max-width: 1200px;
    padding: 3.5rem;
  }

  .theSobreMim__description h2 {
    font-size: 2.8rem;
  }

  .text_sobreMim {
    font-size: 1.2rem;
  }
}

@media (min-width: 1400px) and (max-width: 1899px) {
  .theSobreMim {
    width: 80%;
    max-width: 1400px;
    padding: 3.8rem;
  }

  .theSobreMim__description h2 {
    font-size: 3rem;
  }

  .text_sobreMim {
    font-size: 1.3rem;
  }
}

@media (min-width: 1900px) {
  .theSobreMim {
    width: 80%;
    max-width: 1900px;
    padding: 4rem;
  }

  .theSobreMim__description h2 {
    font-size: 3.2rem;
  }

  .text_sobreMim {
    font-size: 1.4rem;
  }
}
</style>
