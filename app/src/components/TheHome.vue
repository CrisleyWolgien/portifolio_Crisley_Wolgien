<template>
    <div :class="['theHome', { dark: isDarkTheme }]">
        <h2 id="title_name">Olá, prazer Crisley</h2>
        <div class="theHome__description">
            <h1>Estudante de Engenharia de</h1>
            <h1>Software</h1>
        </div>
        <button id="btn_contateMe" aria-label="Contate-me">
            <a href="#contato" class="nav-items">Contate-me</a>
        </button>
        <button id="btn_github">
            <a id="linkgit" href="https://github.com/CrisleyWolgien" target="_blank"><i class="fa-brands fa-github"></i></a>
        </button>
    </div>
</template>

<script>
export default {
    name: "TheHome",
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

.theHome {
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

.theHome.dark {
    background-color: #010B40;
    /* Fundo escuro original */
    color: #e9e5e5;

    /* Texto claro no tema escuro */
    .theHome__description {
        color: #0CF25D;
    }
}

#title_name {
    font-size: 2.5rem;
    font-weight: bold;
    margin-bottom: 1rem;
    line-height: 1.2;
}

.theHome__description {
    display: flex;
    flex-direction: column;
    margin-bottom: 2rem;
}

.theHome__description h1 {
    font-size: 2rem;
    font-weight: 700;
    line-height: 1.2;
    margin: 0;
    /* Remove margens extras */
}

/* Espaçamento adicional entre o texto e o botão */
.theHome__description+#btn_contateMe {
    margin-top: 1.5rem;
}

#btn_contateMe {
    padding: 0.75rem 1.5rem;
    font-size: 1rem;
    font-weight: 600;
    background-color: #048ABF;
    color: #ffffff;
    border: none;
    border-radius: 30px;
    cursor: pointer;
    text-transform: uppercase;
    text-align: center;
    transition: background-color 0.3s, transform 0.2s;
}

#btn_contateMe:hover {
    background-color: #037eaf;
    transform: translateY(-3px);
}

#btn_contateMe:active {
    transform: translateY(0);
}
#btn_github {
    margin-top: 1rem;
    font-size: 1.5rem; 
    color: #333333; /* Cor escura para o texto */
    background-color: #f7f7f7; /* Cor de fundo suave */
    border: 2px solid #333333; /* Borda fina para destacar o botão */
    border-radius: 30px; /* Borda arredondada */
    cursor: pointer;
    transition: all 0.3s ease-in-out; /* Transição suave */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Sombra suave */
    display: flex;
    justify-content: center; /* Centraliza o conteúdo do botão */
    align-items: center; /* Alinha verticalmente */
    padding: 5px;
    text-decoration: none; /* Remove o sublinhado */
}

#btn_github a {
    display: flex;
    align-items: center; /* Alinha o ícone e o texto horizontalmente */
    color: inherit; /* Garante que a cor do texto herde da cor do botão */
    text-decoration: none; /* Remove sublinhado do link */
    gap: 10px; /* Espaço entre o ícone e o texto */
}

#btn_github i {
    font-size: 1.8rem; /* Tamanho maior para o ícone */
    transition: transform 0.2s ease-in-out; /* Animação para o ícone */
}

#btn_github:hover {
    background-color: #333333; /* Fundo escuro no hover */
    color: #fff; /* Cor do texto muda para branco */
    transform: translateY(-3px); /* Efeito de levantar o botão */
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2); /* Sombra mais forte */
}

#btn_github:hover i {
    transform: scale(1.2); /* Aumenta o ícone no hover */
}

#btn_github:focus {
    outline: none; /* Remove o contorno padrão */
    box-shadow: 0 0 5px 2px rgba(0, 123, 255, 0.7); /* Efeito de destaque no foco */
}

#btn_github:active {
    transform: translateY(2px); /* Efeito de pressionamento do botão */
    box-shadow: none; /* Remove sombra ao clicar */
}

.nav-items {
    text-decoration: none;
    color: inherit;
}

/* Responsividade */
@media (max-width: 768px) {
    .theHome {
        width: 90%;
        padding: 1.5rem;
    }

    #title_name {
        font-size: 2rem;
    }

    .theHome__description h1 {
        font-size: 1.5rem;
    }

    #btn_contateMe {
        width: 100%;
        text-align: center;
    }

    #btn_github {
        width: 100%; /* O botão ocupa 100% da largura em telas pequenas */
        justify-content: center; /* Centraliza o conteúdo */
        padding: 1rem;
    }

    #btn_github a {
        justify-content: center; /* Centraliza o conteúdo */
    }
}
</style>