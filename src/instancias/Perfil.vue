<template>
  <main class="flex" v-if="mostrar">
    <article class="card">
      <img src="./images/bg-pattern-card.svg" alt="" class="card-header" />
      <div class="card-body">
        <img src="./images/image-victor.jpg" alt="" class="card-body-img" />
        <h1 class="card-body-title">
          Víctor charst
          <span>26</span>
        </h1>
        <p class="card-body-text">London</p>
      </div>
      <div class="card-footer">
        <div class="card-footer-social">
          <h3>80K</h3>
          <p>Followers</p>
        </div>
        <div class="card-footer-social">
          <h3>803K</h3>
          <p>Likes</p>
        </div>
        <div class="card-footer-social">
          <h3>1.4K</h3>
          <p>Photos</p>
        </div>
      </div>
    </article>
  </main>
</template>
  <script>
export default {
  data: () => {
    return {
      mostrar: false,
    };
  },
  methods: {

    setProfile() {
      this.mostrar = true;

    },
    closeProfile() {
      this.mostrar=false;
    },
  },
};
</script>