<script setup>
  import { ref, computed, reactive } from 'vue';
  
  const lancamentos = ref([
    {
      id: 1,
      titulo: 'Chain of Iron: Volume 2',
      autor: 'Cassandra Clare',
      preco: 23.24,
      capa: '/img/capa1.png',
      favorito: false,
    },
    {
      id: 2,
      titulo: 'Chain of Thorns',
      autor: 'Cassandra Clare',
      preco: 23.24,
      capa: '/img/capa2.png',
      favorito: false,
    },
    {
      id: 3,
      titulo: 'City of Fallen Angels',
      autor: 'Cassandra Clare',
      preco: 13.94,
      capa: '/img/capa3.png',
      favorito: false,
    },
    {
      id: 4,
      titulo: 'Nona the Ninth',
      autor: 'Cassandra Clare',
      preco: 16.84,
      capa: '/img/capa4.png',
      favorito: false,
    },
    {
      id: 5,
      titulo: 'Harlem Shuffle',
      autor: 'Colson Whitehead',
      preco: 26.92,
      capa: '/img/capa5.png',  
      favorito: false,
    },
    {
      id: 6,
      titulo: 'Two Old Women',
      autor: 'Velma Wallis',
      preco: 13.95,
      capa: '/img/capa6.png',
      favorito: false,
    },
    {
      id: 7,
      titulo: 'Carrie Soto Is Back',
      autor: 'Taylor Jenkins Reid',
      preco: 26.04,
      capa: '/img/capa7.png',
      favorito: false,
    },
    {
      id: 8,
      titulo: 'Book Lovers',
      autor: 'Emily Henry',
      preco: 15.81,
      capa: '/img/capa8.png',
      favorito: false,
    },
  ]);
  
  function favoritarLivro(livro) {
  livro.favorito = !livro.favorito;
}

  const carrinho = reactive({
    items: [],
    frete: 0,
    desconto: 0,
    total: 0,
  });
  
  function adicionarAoCarrinho(produto) {
    const itemExistente = carrinho.items.find(item => item.id === produto.id);
  
    if (itemExistente) {
      itemExistente.quantidade++;
      itemExistente.valorTotal = itemExistente.quantidade * itemExistente.preco;
    } else {
      carrinho.items.push({
        id: produto.id,
        nome: produto.titulo,
        preco: produto.preco,
        quantidade: 1,
        valorTotal: produto.preco,
      });
    }
  
    atualizarTotalCarrinho();
  }
  
  function atualizarTotalCarrinho() {
    const subtotal = carrinho.items.reduce((total, item) => total + item.valorTotal, 0);
    carrinho.total = subtotal + carrinho.frete - carrinho.desconto;
  }
  function alterarQuantidade(item, delta) {
  item.quantidade += delta;
  if (item.quantidade < 1) {
    carrinho.items = carrinho.items.filter(i => i.id !== item.id);
  } else {
    item.valorTotal = item.quantidade * item.preco;
  }
  atualizarTotalCarrinho();
}
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
        <input type="text" id="txtBusca" placeholder="Pesquisar" />
        <img src="../public/img/lupa.png" id="btnBusca" alt="Buscar" />
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
            <a href="#compra">
              <span class="fa-solid fa-cart-shopping"></span>
            </a>
          </li>
          <li class="coracaoBarra">
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
      <h2 id="lancamento">Lançamentos</h2>
      <div class="colunas">
        <div class="bloco" v-for="livro in lancamentos" :key="livro.id">
          <img :src="livro.capa" :alt="livro.titulo" />
          <h3>{{ livro.titulo }}</h3>
          <p class="by">{{ livro.autor }}</p>
          <div class="livro-fav">
            <p class="preco">R$ {{ livro.preco.toFixed(2) }}</p>
            <span :class="livro.favorito ? 'fa-solid fa-heart' : 'fa-regular fa-heart'" :style="{ color: livro.favorito ? '#27AE60' : '#ccc', cursor: 'pointer' }" @click="favoritarLivro(livro)"></span>
          </div>
          <button class="comprar" @click="adicionarAoCarrinho(livro)">
            <span class="fa-solid fa-cart-shopping" style="color: #fff;"></span> Comprar
          </button>
        </div>
      </div>
    </section>
    <section class="listaCompra">
      <h2 id="compra">Carrinho</h2>
      <div v-if="carrinho.items.length" class="tabela-carrinho">
        <div class="linha-cabecalho">
          <span class="coluna titulo">Título</span>
          <span class="coluna quantidade">Quantidade</span>
          <span class="coluna subtotal">Subtotal</span>
        </div>
        <div class="linha-item" v-for="item in carrinho.items" :key="item.id">
          <div class="coluna titulo">
            <p class="nome">{{ item.nome }}</p>
            <p class="preco-unidade">R$ {{ item.preco.toFixed(2) }}</p>
          </div>
          <div class="coluna quantidade">
            <button @click="alterarQuantidade(item, -1)">-</button>
            <span>{{ item.quantidade }}</span>
            <button @click="alterarQuantidade(item, 1)">+</button>
          </div>
          <div class="coluna subtotal">
            <span>R$ {{ item.valorTotal.toFixed(2) }}</span>
          </div>
        </div>
      </div>
      <p v-else>Seu carrinho está vazio.</p>
    </section>
    <section class="menuTotal">
    
      <div class="integrar">
        <button><a href="#lancamento">Voltar para loja</a></button>
        <div class="cupom">
          <input class="diminuirBarra" type="text" id="txtBusca" placeholder="Código do cupom" />
          <img src="#" id="btnBusca" alt="" />
          <button class="butaoCupom">Inserir Cupom</button>
      </div>
      </div>
      <div class="bordaM">
        <h3>Total da Compra:</h3>
        <div class="total">
          <p>Produtos:</p> <span>R$ {{ carrinho.total.toFixed(2) }}</span>
        </div>
        <div class="totalFrete">
          <p>Frete:</p> <p>Grátis</p>
        </div>
        <div class="total">
          <p>Total:</p> <span>R$ {{ carrinho.total.toFixed(2) }}</span>
        </div>
        <div class="total">
          <button class="pagamento">Ir para o pagamento</button>
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
  header nav div.icons ul li.coracaoBarra{
    border-left: 1px solid #27AE60;
    padding-left: 14px;
    border-right: 1px solid #27AE60;
    padding-right: 14px;
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
    font-size: 20px;
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

  section.lancamentos div.colunas div.bloco div.livro-fav{
    display: flex;
    justify-content: space-between;

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

  section.lancamentos div.colunas div.bloco p.preco{
    font-size: 1.2rem;
    font-weight: bold;
    color: #382C2C;
    margin: 0 3vw 0 0;
  }
  .lancamentos {
  padding: 20px;
}

.lancamentos h2 {
  font-size: 24px;
  margin-bottom: 20px;
}

.colunas {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.bloco {
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 16px;
  width: calc(25% - 20px);
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.bloco img {
  width: 100%;
  height: auto;
  max-height: 200px;
  object-fit: cover;
  border-radius: 4px;
}

.bloco h3 {
  font-size: 18px;
  margin: 10px 0 5px;
}

.bloco p {
  margin: 0 0 5px;
}

.livro\.fav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  margin: 10px 0;
}

.preco {
  font-weight: bold;
  color: #27AE60;
}

.comprar {
  background-color: #27AE60;
  color: white;
  border: none;
  padding: 10px;
  border-radius: 5px;
  cursor: pointer;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 8px;
}

.comprar:hover {
  background-color: #219150;
}

  /*ALINHAMENTO CARRINHO*/
  section.listaCompra{
    margin: 3vw 10vw;
  }
    section.listaCompra h2{
      font-weight: 600;
      font-size: 38px;
      line-height: 49px;
      letter-spacing: 0%;
      color: #27AE60;

    }

    /*ESTILO CARRINHO*/
    .tabela-carrinho {
      width: 100%;
  }

.linha-cabecalho,
.linha-item {
  display: flex;
  justify-content: space-between;
  padding: 1rem 0;
  align-items: center;
  border-bottom: 1px solid #ccc;
}

.coluna {
  flex: 1;
  text-align: center;
}

.coluna.titulo {
  text-align: left;
  flex: 2;
}

.coluna.quantidade button {
  margin: 0 0.5rem;
  padding: 0.3rem 0.6rem;
}

.preco-unidade {
  font-size: 0.85rem;
  color: #666;
}

/*carrinho*/
section.menuTotal{
  margin: 0 10vw;
  display: flex;
  justify-content: space-between;
}
section.menuTotal div.bordaM div.total{
  display: flex;
  justify-content: space-between;
}
section.menuTotal div.bordaM div.totalFrete{
  display: flex;
  justify-content: space-between;
}
section.menuTotal div.bordaM{
  border: 1px solid black;
  border-radius: 4px;
  padding: 1vw;
}
section.menuTotal div.bordaM div.total p{
  font-weight: 400;
  font-size: 16px;
  line-height: 30px;
  letter-spacing: 0%;
  margin: 3px 10px;
}
section.menuTotal div.bordaM div.total span{
  margin: 3px 10px;
}
section.menuTotal div.bordaM h3{
font-weight: 500;
font-size: 20px;
line-height: 28px;
letter-spacing: 0%;
margin: 20px 10px;
}
section.menuTotal div.bordaM div.totalFrete{
  font-weight: 400;
  font-size: 16px;
  line-height: 30px;
  letter-spacing: 0%;
  margin: 3px 10px;
  border-bottom:1px solid #000000;
  padding: 5px 0;
  border-top:1px solid #000000;
  padding: 5px 0;
}
section.menuTotal div.integrar div.cupom button.butaoCupom{
    border: none;
    background-color: #27AE60;
    border-radius: 2px;
    color: white;
    padding: 10px 16px;
    margin-left: 10px;
} 
  section.menuTotal div.integrar button a{
      text-decoration: none;
      color: #000000;
      font-weight: 500;
      font-size: 16px;
      line-height: 24px;
      letter-spacing: 0%;
      width: 221;
    }

  section.menuTotal div.integrar button{
    background-color: white;
    border: none;
    border: 1px solid #000000;
    border-radius: 4px;
    padding: 15px 20px;
    margin: 3vw 0;
}
  section.menuTotal div.bordaM div.total button.pagamento{
    border: none;
    background-color: #27AE60;
    border-radius: 2px;
    color: white;
    padding: 10px 16px;
    margin-left: 10px;
    font-size: 16px;
    margin-top: 2vw ;
}
.barraDePesquisa {
  position: relative;
  width: 23%;
  margin: 20px 10px 10px 6vw;
}

#txtBusca {
  width: 100%;
  padding-left: 30px; 
  padding: 8px 10px;
  font-size: 16px;
  background-color: #F1F1F1;
  border: none;
}

#btnBusca {
  position: absolute;
  right: 4px; 
  top: 40%;
  transform: translateY(-50%); 
  width: 20px; 
  height: 20px;
  pointer-events: none; 
}

section.menuTotal div.integrar div.cupom{
  display: flex;
  width: 70%;
  height: 10%;

}
</style>