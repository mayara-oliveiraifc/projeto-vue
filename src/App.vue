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
</style>
