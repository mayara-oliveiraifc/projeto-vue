<script setup>


</script>

<template>
  <header>
    <nav>
      <div class="IFbooks">
       <ul>
        <li class="espacoLogo" >
          <a href="App.vue">IFbooks</a>
        </li>
        <li>
          <p class="espaco">Apreço a <br> leitura</p>
        </li>
       </ul>
      </div>
      <div class="barraDePesquisa">
        <input type="text" id="txtBusca" placeholder="Buscar..."/>
        <img src="#" id="btnBusca" alt="Buscar"/>
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
        <p class="texto">Eric-Emmanuel Schmitt has been awarded more than 20 literary prizes and distinctions, and in 2001 he received the title of Chevalier des Arts et des Lettres. His books have been translated into over 40 languages.</p>
        <button>Acessar página do livro</button>
       </div>
       <div class="lado2">
        <img src="../public/img/livro.png" alt="Capa do Livro">
        <p class="descricao">*within the stock limit</p>
       </div>
      </div>
    </section>
    <section class="menuFrete">
      <ul>
        <li>
          <span class="fa-solid fa-truck"></span>
          <p>Frete grátis para SC</p>
        </li>
        <li>
          <span class="fa-solid fa-star"></span>
          <p>Livros recomendados</p>
        </li>
        <li>
          <span class="fa-solid fa-book-open"></span>
          <p>Mais vendidos</p>
        </li>
      </ul>

    </section>
  </main>
</template>

<style scoped>

  /*ALINHAMENTO MENU*/
  header nav {
    display: flex;
  }
  header nav div.IFbooks ul{
    display: flex;
  }
  header nav div.menuTopo ul{
  display: flex;
  }
  header nav div.icons ul{
    display: flex;
  }
  /* ESPAÇAMENTO MENU*/ 

  header nav div.IFbooks ul li p.espaco{
    margin: 20px 4px 10px 0;
  }
  header nav div.IFbooks ul li.espacoLogo{
    margin: 20px 10px 10px 8vw;
  }
  header nav div.barraDePesquisa{
    margin: 20px 10px 10px 6vw;
  }
  header nav div.menuTopo ul li a{
    margin: 23px;
  }
  header nav div.menuTopo ul li {
   margin: 20px 10px 10px 0;
  }
  header nav div.icons ul li  {
    margin: 10px;
  }
  header nav div.icons ul{
    margin: 10px 2vw 10px 0;
  }

   /*ESTILIZAÇÃO MENU*/

  header nav div.IFbooks ul li.espacoLogo a{
   text-decoration: none;
   color: black;
  }
  header nav div.menuTopo ul li a{
   text-decoration: none;
   color: #7B7881;
  }

  header nav div.icons ul li a span{
   color: #27AE60;
  }

  header nav div.IFbooks ul li p.espaco{
    color: #27AE6099;
  }

  /*BORDA MENU*/

  header nav{
    border-bottom: 1.5px solid #27AE60;
  }

 
  header nav div.IFbooks ul li p.espaco{
    border-left: 1.5px solid #27AE60;
    padding: 0 0 0 12px;
  }

  /*ALINHAMENTO BANNER*/

  section.banner div.divLadoALado  {
    display: flex;
  }

  /*ESPAÇAMENTO BANNER*/

  section.banner div.divLadoALado div.lado1 p.autor {
    margin: 9.5vw 37vw 2.5vw 11vw ;
  }
  section.banner div.divLadoALado div.lado1 h1 {
    margin: 0 0 3vw 11vw ;
  }
  section.banner div.divLadoALado div.lado1 p.texto {
    margin: 0 7vw 4vw 11vw ;
  }
  section.banner div.divLadoALado div.lado1 button {
    margin: 0 15vw 4vw 11vw ;
  }
  section.banner div.divLadoALado div.lado2 img{
    margin: 2vw 8vw 0 0;
  }
  section.banner div.divLadoALado div.lado2 p.descricao{
    margin: 0 3vw 0 20vw;
  }

  /*ESTILIZAÇÃO BANNER*/

  section.banner div.divLadoALado div.lado1 p.autor {
    border:1px solid #27AE60 ;
    background-color: white;
    padding: 12px 11px 12px 12px;
    border-radius: 3px;
    color: #27AE60;
    font-size: 14px;
  }
  section.banner div.divLadoALado div.lado1 h1 {
    font-size: 43px;
    font-weight: bold;
  }
  section.banner div.divLadoALado div.lado1 p.texto {
    line-height: 24px;
    color: #4D4C4C;
  }
  section.banner div.divLadoALado div.lado1 button{
    background-color: #27AE60;
    padding: 12.02px 32.04px 12.02px 32.04px;
    color: white;
    border: none;
    border-radius: 1px;  
    font-size: 16.02px;
  }
  section.banner div.divLadoALado div.lado2 p.descricao{
    font-size: 16px;
  }
</style>
