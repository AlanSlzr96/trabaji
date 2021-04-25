<template>
  <div class="container">
    <img
      alt="Vue logo"
      src="https://upload.wikimedia.org/wikipedia/commons/9/98/International_Pok%C3%A9mon_logo.svg"
    />

    <Busqueda :apiUrl="apiUrl" @setPokemonUrl="setPokemonUrl" />

    <Lista
      :imageUrl="imageUrl"
      :apiUrl="apiUrl"
      @setPokemonUrl="setPokemonUrl"
    />

    <Detalles
      v-if="showDetail"
      :pokemonUrl="pokemonUrl"
      :imageUrl="imageUrl"
      @closeDetail="closeDetail"
    />

    <Perfil
      v-if="showProfile"
      @setProfile="setProfile"
      @closeProfile="closeProfile"
    />
  </div>
</template>
<script>
import Busqueda from "./Busqueda.vue";
import Lista from "./Lista.vue";
import Detalles from "./Detalles.vue";
import Perfil from "./Perfil.vue";

export default {
  data: () => {
    return {
      imageUrl:
        "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/",
      apiUrl: "https://pokeapi.co/api/v2/pokemon/",
      pokemonUrl: "",
      showDetail: false,
      showProfile: false,
    };
  },
  components: {
    Busqueda,
    Lista,
    Detalles,
    Perfil,
  },
  methods: {
    setProfile() {
      this.showProfile = true;
    },

    closeProfile() {
      this.showProfile = false;
    },

    setPokemonUrl(url) {
      this.pokemonUrl = url;
      this.showDetail = true;
    },

    closeDetail() {
      this.pokemonUrl = "";
      this.showDetail = false;
    },
  },
};
</script>


<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 10px;
  width: calc(100% - 20px);
  min-height: calc(100vh - 20px);
  font-family: "Acme", arial;
  font-size: 1rem;
  font-weight: normal;
}

h1 {
  color: #ad5454;
}
</style>