<script setup>
  const produtos = [
    {
      id: 1,
      titulo: 'Livro 1',
      resenha: 'Descrição breve 1',
      preco: 49.9,
      capa: 'https://placehold.co/600x400.png',

    },
    {
      id: 2,
      titulo: 'Livro 2',
      resenha: 'Descrição breve 2',
      preco: 99.9,
      capa: 'https://placehold.co/600x400.png',
    },
    {
      id: 3,
      titulo: 'Livro 3',
      resenha: 'Descrição breve 3',
      preco: 9.9,
      capa: 'https://placehold.co/600x400.png',
    },
    {
      id: 4,
      titulo: 'Livro 4',
      resenha: 'Descrição breve 4',
      preco: 199.9,
      capa: 'https://placehold.co/600x400.png',
    },
    {
      id: 5,
      titulo: 'Livro 5',
      resenha: 'Descrição breve 5',
      preco: 29.9,
      capa: 'https://placehold.co/600x400.png',
    }
  ];
  const carrinho = {
    items: [
      {
        id: 1,
        nome: 'Livro 1',
        preco: 49.9,
        quantidade: 1,
        valorTotal: 49.9,
      },
      {
        id: 2,
        nome: 'Livro 2',
        preco: 99.9,
        quantidade: 2,
        valorTotal: 199.8,
      },
    ],
    frete: 0,
    desconto: 0,
    total: 288.3,
  };
</script>

<template>
  <header>
    <nav>
      <div class="IFbooks">
        <ul>
          <li class="espacoLogo">
            <a href="App.vue">IFbooks</a>
          </li>
          <li>
            <p class="espaco">Apreço a <br> leitura</p>
          </li>
        </ul>
      </div>
      <div class="barraDePesquisa">
        <input type="text" id="txtBusca" placeholder="Buscar..." />
        <img src="#" id="btnBusca" alt="Buscar" />
      </div>
      <div class="menuTopo">
        <ul>
          <li>
            <a href="App.vue">Termos</a>
          </li>
          <li>
            <a href="App.vue">Equpe</a>
          </li>
          <li>
            <a href="App.vue">Envio</a>
          </li>
          <li>
            <a href="App.vue">Devoluções</a>
          </li>
        </ul>
      </div>
      <div class="icons">
        <ul>
          <li>
            <a href="App.vue">
              <span class="fa-solid fa-cart-shopping"></span>
            </a>
          </li>
          <li>
            <a href="App.vue">
              <span class="fa-solid fa-heart"></span>
            </a>
          </li>
          <li>
            <a href="App.vue">
              <span class="fa-solid fa-user-large"></span>
            </a>
          </li>
        </ul>
      </div>
    </nav>
  </header>
  <main>
    <section class="banner">
      <div class="divLadoALado">
        <div class="lado1">
          <p class="autor">Autor de Abril</p>
          <h1>Eric-Emanuel Schmitt </h1>
          <p class="texto">Eric-Emmanuel Schmitt has been awarded more than 20 literary prizes and distinctions, and in
            2001 he received the title of Chevalier des Arts et des Lettres. His books have been translated into over 40
            languages.</p>
          <button>Acessar página do livro</button>
        </div>
        <div class="lado2">
          <img src="../public/img/livro.png" alt="Capa do Livro">
          <p class="descricao">*within the stock limit</p>
        </div>
      </div>
    </section>
    <section class="menuFrete">
      <div class="menuMeio">
        <ul>
          <li>
            <p><span class="fa-solid fa-truck"></span></p>
            <p>Frete grátis para SC</p>
          </li>
          <li class="barrasMenuFrete">
            <p><span class="fa-solid fa-star"></span></p>
            <p>Livros recomendados</p>
          </li>
          <li>
            <p><span class="fa-solid fa-book-open"></span></p>
            <p class="sublinhado">Mais vendidos</p>
          </li>
        </ul>
      </div>
    </section>
    <section class="lancamentos">
      <h2>Lançamentos</h2>
      <div class="colunas">
        <div class="bloco">
          <img src="../public/img/capa1.png" alt="capa 1">
          <h3 id="titulo">Chain of Iron: Volume 2</h3>
          <p id="autor" class="by">Cassandra Clare</p>
          <div>
            <p id="preco" class="preco">R$23.24</p>
            <button id="botao" class="botao">
              <span class="fa-regular fa-heart" style="color: #27AE60;"></span>
            </button>
          </div>
          <button id="comprar" class="comprar"><span class="fa-solid fa-cart-shopping" style="color: #ffffff;"></span>
            Comprar</button>
        </div>
        <div class="bloco">
          <img src="../public/img/capa2.png" alt="capa 2">
          <h3 id="titulo">Chain of Thorns</h3>
          <p id="autor" class="by">Cassandra Clare</p>
          <div>
            <p id="preco" class="preco">R$23.24</p>
            <button id="botao" class="botao">
              <span class="fa-regular fa-heart" style="color: #27AE60;"></span>
            </button>
          </div>
          <button id="comprar" class="comprar"><span class="fa-solid fa-cart-shopping" style="color: #ffffff;"></span>
            Comprar</button>
        </div>
        <div class="bloco">
          <img src="../public/img/capa3.png" alt="capa 3">
          <h3 id="titulo">City of Fallen Angels</h3>
          <p id="autor" class="by">Cassandra Clare</p>
          <div>
            <p id="preco" class="preco">R$13.94</p>
            <button id="botao">
              <span class="fa-regular fa-heart" style="color: #27AE60;"></span>
            </button>
          </div>
          <button id="comprar" class="comprar"><span class="fa-solid fa-cart-shopping" style="color: #ffffff;"></span>
            Comprar</button>
        </div>
        <div class="bloco">
          <img src="../public/img/capa4.png" alt="capa 4">
          <h3 id="titulo">Nona the Ninth</h3>
          <p id="autor" class="by">Cassandra Clare</p>
          <div>
            <p id="preco" class="preco">R$16.84</p>
            <button id="botao">
              <span class="fa-regular fa-heart" style="color: #27AE60;"></span>
            </button>
          </div>
          <button id="comprar" class="comprar"><span class="fa-solid fa-cart-shopping" style="color: #ffffff;"></span>
            Comprar</button>
        </div>
      </div>
      <div class="colunas">
        <div class="bloco">
          <img src="../public/img/capa5.png" alt="capa 5">
          <h3 id="titulo">Harlem Shuffle</h3>
          <p id="autor" class="by">Colson Whitehead</p>
          <div>
            <p id="preco" class="preco">R$26.92</p>
            <button id="botao">
              <span class="fa-regular fa-heart" style="color: #27AE60;"></span>
            </button>
          </div>
          <button id="comprar" class="comprar"><span class="fa-solid fa-cart-shopping" style="color: #ffffff;"></span>
            Comprar</button>
        </div>
        <div class="bloco">
          <img src="../public/img/capa6.png" alt="capa 6">
          <h3 id="titulo">Two Old Women</h3>
          <p id="autor" class="by">Velma Wallis</p>
          <div>
            <p id="preco" class="preco">R$13.95</p>
            <button id="botao">
              <span class="fa-regular fa-heart" style="color: #27AE60;"></span>
            </button>
          </div>
          <button id="comprar" class="comprar"><span class="fa-solid fa-cart-shopping" style="color: #ffffff;"></span>
            Comprar</button>
        </div>
        <div class="bloco">
          <img src="../public/img/capa7.png" alt="capa 7">
          <h3 id="titulo">Carrie Soto Is Back</h3>
          <p id="autor" class="by">Taylor Jenkins Reid</p>
          <div>
            <p id="preco" class="preco">R$26.04</p>
            <button id="botao">
              <span class="fa-regular fa-heart" style="color: #27AE60;"></span>
            </button>
          </div>
          <button id="comprar" class="comprar"><span class="fa-solid fa-cart-shopping" style="color: #ffffff;"></span>
            Comprar</button>
        </div>
        <div class="bloco">
          <img src="../public/img/capa8.png" alt="capa 8">
          <h3 id="titulo">Book Lovers</h3>
          <p id="autor" class="by">Emily Henry</p>
          <div>
            <p id="preco" class="preco">R$15.81</p>
            <button id="botao">
              <span class="fa-regular fa-heart" style="color: #27AE60;"></span>
            </button>
          </div>
          <button id="comprar" class="comprar"><span class="fa-solid fa-cart-shopping" style="color: #ffffff;"></span>
            Comprar</button>
        </div>
      </div>
    </section>
  </main>
  <footer>
    <div class="separacaoFooter">
      <div class="footer1">
        <p>IFbooks</p>
        <ul>
          <li>
            <a href="https://www.facebook.com/">
              <span class="fa-brands fa-square-facebook"></span>
            </a>
          </li>
          <li>
            <a href="https://www.instagram.com/">
              <span class="fa-brands fa-square-instagram"></span>
            </a>
          </li>
          <li>
            <a href="https://x.com/">
              <span class="fa-brands fa-square-twitter"></span>
            </a>
          </li>
        </ul>
      </div>
      <div class="footer2">
        <h3>Contato</h3>
        <ul>
          <li>
            <p><span class="fa-solid fa-phone"></span> +55 47 40045263</p>
          </li>
          <li>
            <p><span class="fa-solid fa-clock"></span> 8h às 23h - Seg a Sex</p>
          </li>
          <li>
            <p><span class="fa-solid fa-envelope"></span>contato@ifbooks.com</p>
          </li>
        </ul>
        <ul class="logos">
          <li>
            <img src="../public/img/paypal.png" alt="Logo PayPal">
          </li>
          <li>
            <img src="../public/img/mastercar.png" alt="Logo MasterCar">
          </li>
          <li>
            <img src="../public/img/visa.png" alt="Logo Visa">
          </li>
        </ul>
      </div>
    </div>
    <p class="direitos">&copy; Alguns direitos reservados. IFbooks 2025. </p>
  </footer>
</template>

<style scoped>
  /*ALINHAMENTO MENU*/
  header {
    margin: 3vw 10vw;
  }

  header nav {
    display: flex;
  }

  header nav div.IFbooks ul {
    display: flex;
  }

  header nav div.menuTopo ul {
    display: flex;
  }

  header nav div.icons ul {
    display: flex;
  }

  /* ESPAÇAMENTO MENU*/

  header nav div.IFbooks ul li p.espaco {
    margin: 20px 4px 10px 0;
  }

  header nav div.IFbooks ul li.espacoLogo {
    margin: 20px 10px 10px 8vw;
  }

  header nav div.barraDePesquisa {
    margin: 20px 10px 10px 6vw;
  }

  header nav div.menuTopo ul li a {
    margin: 23px;
  }

  header nav div.menuTopo ul li {
    margin: 20px 10px 10px 0;
  }

  header nav div.icons ul li {
    margin: 10px;
  }

  header nav div.icons ul {
    margin: 10px 2vw 10px 0;
  }

  /*ESTILIZAÇÃO MENU*/

  header nav div.IFbooks ul li.espacoLogo a {
    text-decoration: none;
    color: black;
  }

  header nav div.menuTopo ul li a {
    text-decoration: none;
    color: #7B7881;
  }

  header nav div.icons ul li a span {
    color: #27AE60;
  }

  header nav div.IFbooks ul li p.espaco {
    color: #27AE6099;
  }

  /*BORDA MENU*/

  header nav {
    border-bottom: 1.5px solid #27AE60;
  }


  header nav div.IFbooks ul li p.espaco {
    border-left: 1.5px solid #27AE60;
    padding: 0 0 0 12px;
  }

  /*ALINHAMENTO BANNER*/

  section.banner div.divLadoALado {
    display: flex;
    justify-content: space-between;
    margin: 0 10vw;
  }

  section.banner div.divLadoALado div.lado1 {
    margin: 0 10vw 0 10vw;
  }

  section.banner div.divLadoALado div.lado1 p.texto {
    margin: 2vw 0;
  }

  section.banner div.divLadoALado div.lado1 p.autor {
    margin: 5vw 0 2vw 0;
  }

  section.banner div.divLadoALado div.lado2 {
    margin: 0 8vw 0 0;
  }

  section.banner div.divLadoALado div.lado2 p.descricao {
    margin: 0 0 2vw 10vw
  }

  /*ESTILIZAÇÃO BANNER*/

  section.banner div.divLadoALado div.lado1 p.autor {
    font-weight: 400;
    font-size: 14px;
    line-height: 20.03px;
    letter-spacing: 0%;
    color: #27AE60;
    border: 1px solid #27AE60;
    width: 100px;
    height: 41.02777862548828;
    top: 216.43px;
    left: 164.23px;
    border-width: 1px;
    border-radius: 3px;
    padding: 10.01px;
    gap: 10.01px;

  }

  section.banner div.divLadoALado div.lado1 p.texto {
    display: block;
    font-weight: 400;
    font-size: 16px;
    line-height: 24.03px;
    letter-spacing: 0%;
    color: #4D4C4C;
    width: 477.6625061035156;
    height: 97;
    top: 380.66px;
    left: 164.23px;

  }

  section.banner div.divLadoALado div.lado1 button {
    width: 243.08889770507812;
    height: 49.03333282470703;
    top: 516.85px;
    left: 164.23px;
    border-radius: 2px;
    gap: 10.01px;
    padding-top: 12.02px;
    padding-right: 32.04px;
    padding-bottom: 12.02px;
    padding-left: 32.04px;
    font-weight: 500;
    font-size: 16.02px;
    line-height: 24.03px;
    letter-spacing: 0%;
    border: none;
    background-color: #27AE60;
    color: white;

  }


  section.banner div.divLadoALado div.lado1 h1 {
    font-weight: 700;
    font-size: 48px;
    line-height: 60px;
    letter-spacing: 0%;
    color: #231F2D;
    width: 512.711181640625;
    height: 60;
    top: 288.53px;
    left: 164.23px;

  }


  /*ALINHAMENTO MENU FRETE*/

  section.menuFrete ul {
    display: flex;
  }

  section.menuFrete ul li {
    display: flex;
    justify-content: space-between;

  }

  /*ESPAÇAMENTO MENU FRETE*/

  section.menuFrete {
    margin: 0 10vw 0 10vw;
    justify-content: space-between;
    border-top: 1px solid #27AE60;
    padding: 3vw;
    border-bottom: 1px solid #27AE60;
    padding: 3vw;
  }

  section.menuFrete ul li p {
    margin: 0 1vw;
  }

  section.menuFrete ul li {
    margin: 0 2vw;
  }

  /*ESTILIZAÇÃO MENU FRETRE*/

  section.menuFrete ul li p {
    font-size: 24px;
  }

  section.menuFrete ul li.barrasMenuFrete {
    border-right: 1px solid #937DC2;
    padding: 0 3vw;
    border-left: 1px solid #937DC2;

  }

  /*ALINHAMENTO CSS*/

  footer div.separacaoFooter {
    display: flex;
    justify-content: space-between;
    margin: 3vw 10vw;
  }

  footer div.separacaoFooter div.footer1 {
    margin-top: 2vw;
  }

  footer div.separacaoFooter div.footer1 ul li {
    margin: 10px;
  }

  footer div.separacaoFooter div.footer2 {
    margin-top: 2vw;
  }

  footer div.separacaoFooter div.footer2 ul li {
    margin: 10px;
  }

  footer div.separacaoFooter div.footer1 ul {
    display: flex;
  }

  footer div.separacaoFooter div.footer2 ul.logos {
    display: flex;
    margin: 2vw 0;
  }


  /*ESTILIZAÇÃO FOOTER*/
  footer {
    background-color: #27AE60;
    color: white;
  }

  footer div.separacaoFooter div.footer1 p {
    font-weight: 400;
    font-size: 1.5rem;
    line-height: 24.03px;
    letter-spacing: 0%;
  }

  footer div.separacaoFooter div.footer1 ul li a {
    font-size: 1.5rem;
    color: white;
  }

  footer div.separacaoFooter div.footer2 h3 {
    font-weight: bold;
    margin-bottom: 20px
  }

  footer p.direitos {
    text-align: center;
    border-top: 1px solid white;
    padding: 10px;
  }

  /*ALINHAMENTO LANÇAMENTOS*/
  section.lancamentos {
    margin: 0 10vw;
  }

  section.lancamentos div.colunas {
    display: flex;
    justify-content: space-between;

  }

  section.lancamentos h2 {}

  /*ESTILIZAÇÃO LANÇAMENTOS*/
  section.lancamentos h2 {
    font-weight: 600;
    font-size: 38px;
    line-height: 49px;
    letter-spacing: 0%;
    color: #231F2D;
    margin: 1vw 0 2vw 4vw;
  }

  section.lancamentos div.colunas div.bloco h3 {
    font-weight: 600;
    font-size: 24px;
    line-height: 32.04px;
    letter-spacing: 0%;
    color: #382C2C;
  }

  section.lancamentos div.colunas div.bloco p.by {
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0%;
    color: #4F4C57;
    width: 125;
    height: 24;
    top: 1518px;
    left: 124px;
    margin: 7px 0;
  }

  section.lancamentos div.colunas div.bloco div {
    display: flex;
    justify-content: space-between;
  }

  section.lancamentos div.colunas div.bloco div button {
    border: none;
    background-color: white;
    font-size: 1.5rem;
  }

  section.lancamentos div.colunas div.bloco button.comprar {
    border: none;
    padding: 14px 100px;
    background-color: #27AE60;
    border-radius: 2px;
    color: white;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0%;
    margin-top: 1vw;
    margin-bottom: 4vw;
  }

  section.lancamentos div.colunas div.bloco p.preco {
    font-size: 1.2rem;
    font-weight: bold;
    color: #382C2C;
  }
  /*ALINHAMENTO CARRINHO*/
  
</style>