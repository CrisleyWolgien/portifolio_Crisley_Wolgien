<template>
    <div :class="['theSkills', { dark: isDarkTheme }]">
        <h1 class="title_name_skills">Skills</h1>
        <div class="theSkills__description">
            <ul>
                <li v-for="skill in skills" :key="skill.id">
                    <img :src="skill.icon" :alt="skill.name" class="skill-icon" />
                    {{ skill.name }}
                </li>
            </ul>
        </div>
    </div>
</template>

<script>

import htmlIcon from "../assets/img/html.svg";
import cssIcon from "../assets/img/css.svg";
import jsIcon from "../assets/img/js.svg";
import vueIcon from "../assets/img/vuejs.svg";
import reactIcon from "../assets/img/react.svg";
import csharpIcon from "../assets/img/csharp.svg";

export default {
    name: "TheSkills",
    props: {
        isDarkTheme: {
            type: Boolean,
            default: false,
        },
    },
    data() {
        return {
            skills: [
                { id: 1, name: "HTML", icon: htmlIcon },
                { id: 2, name: "CSS", icon: cssIcon },
                { id: 3, name: "JavaScript", icon: jsIcon },
                { id: 4, name: "Vue.js", icon: vueIcon },
                { id: 5, name: "React", icon: reactIcon },
                { id: 6, name: "C#", icon: csharpIcon },
            ],
        };
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

/* Estilos da página */
.theSkills {
    margin: 2rem auto;
    width: 85%;
    max-width: 1200px;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: var(--color-light-bg);
    color: var(--color-light-text);
    border-radius: 15px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    transition: background-color 0.3s ease, color 0.3s ease, box-shadow 0.3s ease;
    position: relative;
    overflow: hidden;
}

.theSkills::before {
    content: "";
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle, rgba(0, 204, 153, 0.2), transparent 70%);
    z-index: 0;
}

.theSkills.dark {
    background-color: var(--color-dark-bg);
    color: var(--color-dark-text);
}

.theSkills.dark {
    background-color: #010B40;
    /* Fundo escuro original */
    color: #e9e5e5;

    /* Texto claro no tema escuro */
}

#title_name_skills {
    font-size: 3rem;
    margin-bottom: 1rem;
}

.theSkills__description {
    font-size: 1.2rem;
    line-height: 1.6;
    width: 100%;
    z-index: 1;
}

.theSkills__description ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}


.theSkills__description ul li {
    margin: 0.5rem;
    padding: 0.5rem 1rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.theSkills__description ul li:hover {
    transform: scale(1.05);
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
}

.skill-icon {
    width: 50px;
    height: 50px;
    object-fit: contain;
}



/* Responsividade */
@media (min-width: 1900px) {
    .theSkills {
        width: 82%;
        max-width: 1950px;
    }
}

@media (min-width: 1400px) and (max-width: 1899px) {
    .theSkills {
        width: 82%;
        max-width: 1450px;
    }
}

@media (min-width: 1200px) and (max-width: 1399px) {
    .theSkills {
        width: 82%;
        max-width: 1250px;
    }
}

/* Responsividade geral */
@media (max-width: 768px) {
    .skill-icon {
        width: 24px;
        height: 24px;
    }

    .theSkills__description ul li {
        gap: 0.3rem;
    }
}

</style>