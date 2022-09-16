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
    <div class="_container">
      <div class="location__map">
        <yandex-map 
          :coords="coords" 
          :zoom="18" 
          :settings="{
                apiKey: '',
                lang: 'ru_RU',
                enterprise: false,
                version: '2.1',
            }"
          :controls="[]"
          @click="onClick"
        >
          <div></div>
          <ymap-marker :coords="coords" marker-id="123" hint-content="some hint" />
        </yandex-map>
      </div>
    </div>
  </section>
</template>

<script>
import { yandexMap, ymapMarker } from 'vue-yandex-maps'

export default {
  data: () => ({
    coords: [40.754364, 72.357309],
  }),
  methods: {
    onClick(e) {
      this.coords = e.get("coords");
    },
  },
  components: { yandexMap, ymapMarker },
};
</script>

<style>
.location__map {
  width: 70%;
  height: 350px;
  margin: 0 auto;
  overflow: hidden;
}

.ymap-container {
  height: 100%;
  display: flex;
}
</style>
