<template>

  <div id="nav" > 
  <img src="../public/Lojinhas.jpg"  class="Imagem"/> 
 
  
    <!--Talvez as rotas estejam erradas-->
    <router-link :class="{ active: $route.name === 'Home' }" to="/" class="Inicio">
      🏠
    </router-link>
    |
    <router-link :class="{ active: $route.name === 'Cart' }" to="/Cart"
      class="Carrinho">🛒</router-link
    >
    |
  </div>
  <router-view />
</template>
<script>
export default {
  mounted() {
    this.$store.commit("updateCartFromStorage");
  },
};
</script>

<style lang="scss">
.Imagem{
  width: 50px;
  height: 40px;
  position: absolute;
  left: 10px ;
  
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: right;
  color: #2c3e50;
}


html,
body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

body {
  background-color: rgb(245, 245, 245);
}

#nav {
  padding: 10px;
  width: 100%;
  height: 30px;
  background-color: rgb(100, 112, 128);
  line-height: 30px;
  
  
  
}

a {
  font-weight: bold;
  color: darkgrey;
  text-decoration: none;
  margin: 0 5px 0 5px;
  font-size: 1.25rem;

  &.active {
    color: white;
  }
}

.text {
  text-align: center;
    padding: 1px;
        border-radius: 5px;
        height: 15px;
}
.Inicio{
text-align: right;
&:hover {
    background-color: blue;
    
  }

  
}

.Carrinho {
  text-align: right;
    &:hover {
    background-color: blue;
   
  }
  }
</style>
