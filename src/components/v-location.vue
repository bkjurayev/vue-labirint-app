<template>
  <section class="location">
    <div class="location__container _container">
      <h1 class="location__title _title">
        “Labirint” o’quv markazi qayerda joylashgan?
      </h1>
      <p class="location__subtitle">
        Qanday qilib biz bilan bog'lansa bo'ladi?
      </p>
    </div>

    <yandex-map 
    :coords="coords"
    :zoom="10" 
    @click="onClick"
  >
    <ymap-marker 
      :coords="coords" 
      marker-id="123" 
      hint-content="some hint" 
    />
  </yandex-map>
  </section>
</template>



<script>


export default {
  data: () => ({
    coords: [
      54.82896654088406,
      39.831893822753904,
    ],
  }),
  methods: {
    onClick(e) {
      this.coords = e.get('coords');
    },
  },
};
</script>

<style>
#app {
  width: 100%;
  height: 100vh;
}

.ymap-container {
  height: 100%;
}
</style>
