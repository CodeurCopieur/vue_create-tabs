<template>
  <div id="app">

    <section class="tabs__container">
  <ul class="tabs__container-onglets">
    <li class="onglets" @click="activeTab = '1'" :class="[activeTab === '1' ? 'active' : '']">Titre 1</li>
    <li class="onglets"  @click="activeTab = '2'" :class="[activeTab === '2' ? 'active' : '']">Titre 2</li>
    <li class="onglets"  @click="activeTab = '3'" :class="[activeTab === '3' ? 'active' : '']">Titre 3</li>
  </ul>
  
  <div class="tabs__container-contenu" v-if="activeTab === '1'">
    <h3>Lorem ipsum dolor sit amet consectetur. 1</h3>
    <hr>
    <p>1-Lorem ipsum dolor sit, amet consectetur adipisicing elit. Natus officia repellendus, officiis nihil quos soluta quisquam voluptas atque reprehenderit reiciendis maiores doloremque? Saepe, alias. Optio corrupti alias itaque illo ut.</p>
  </div>
  <div class="tabs__container-contenu" v-if="activeTab === '2'">
    <h3>Lorem ipsum dolor sit amet consectetur. 2</h3>
    <hr>
    <p>2-Lorem ipsum dolor sit, amet consectetur adipisicing elit. Natus officia repellendus, officiis nihil quos soluta quisquam voluptas atque reprehenderit reiciendis maiores doloremque? Saepe, alias. Optio corrupti alias itaque illo ut.</p>
  </div>
  <div class="tabs__container-contenu" v-if="activeTab === '3'">
    <h3>Lorem ipsum dolor sit amet consectetur. 3</h3>
    <hr>
    <p>3-Lorem ipsum dolor sit, amet consectetur adipisicing elit. Natus officia repellendus, officiis nihil quos soluta quisquam voluptas atque reprehenderit reiciendis maiores doloremque? Saepe, alias. Optio corrupti alias itaque illo ut.</p>
  </div>
</section>

  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      activeTab: "1"
    }
  }
}
</script>

<style lang="scss">

@mixin center($display, $justiC, $aliI){
  display: $display;
  justify-content: $justiC;
  align-items: $aliI;
}


body {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;

}

#app {
  
  .tabs__container {
    width: 660px;
    height: 300px;
    border-radius: 2px;
    box-shadow: 0 0 10px rgba(0, 0, 0, .5);
    position: relative;

    .tabs__container-onglets {
      width: 100%;
      height: 30%;
      padding: 0;
      border-bottom: 2px solid #333;
      @include center(flex, center, center);

      .onglets {
        width: calc(100%/3);
        @include center(flex, center, center);
        cursor: pointer;
        font-size: 22px;
        font-weight: 700;
        height: 100%;

        &:not(:nth-child(3)) {
          border-right: 1px solid #333;
        }
      }
    }

    .tabs__container-contenu {
      height: 70%;
      padding: 0 20px;
      position: absolute;

      h3 {
        padding-bottom: 20px;
      }

      hr {
        width: 20%;
        height: 2px;
        border: none;
        background: #333;
      }
      
      p {
        padding-top: 20px;
      }
    }

    /* Anim  */
    .active {
      background-color: midnightblue;
      color: white;
      transition: all .3s ease;
    }

    .active-contenu{
      animation: fade .5s forwards;
      z-index: -1;
    }

     @keyframes fade {
      from {
        opacity: 0;
        top: -10%;
      }

      to {
        opacity: 1;
        top: 50%;
        transform: translateY(-20%);
      }
    }
  }
}

</style>
