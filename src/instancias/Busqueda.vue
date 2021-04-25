<template>
  <div class="searchbar">
    <form @submit.prevent="setPokemonUrl">
      <input
        type="text"
        placeholder="Inserta el nombre de tu pokemon"
        v-model="searchvalue"
      />
    </form>
    <i class="fas fa-search" @click="setPokemonUrl"></i>

    <button class="fas fa-id-badge" @click="setProfile"></button>
  </div>
</template>

<script>
export default {
  props: ["apiUrl"],
  data: () => {
    return {
      searchvalue: "",
    };
  },

  methods: {
    setPokemonUrl(url, setProfile) {
      if (this.searchvalue !== "")
        this.$emit(
          "setPokemonUrl",
          this.apiUrl + this.searchvalue.toLowerCase()
        );
    },
  },
};
</script>

<style scoped>
.searchbar {
  position: relative;
  width: 100%;
  max-width: 510px;
  padding-bottom: 20px;
}
input {
  border: none;
  outline: none;
  border-radius: 5px;
  padding: 1px 1px 1px 0px;
  width: calc(100% - 50px);
  font-size: 1rem;
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2), 0 10px 10px rgba(0, 0, 0, 0.2);
}
.legenda {
  color: #fff;
}
i {
  position: absolute;
  top: 5px;
  right: 10px;
  font-size: 1.25rem;
  color: #0A2E50;
  cursor: pointer;
}
button {
  position: relative;
  top: 5px;
  right: 10px;
  font-size: 1.25rem;
  color: #0A2E50;
  cursor: pointer;
}
</style>
