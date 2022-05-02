<template>
  <div class="q-pa-md">
    <q-carousel
      v-model="slide"
      transition-prev="slide-right"
      transition-next="slide-left"
      animated
      control-color="primary"
      class="rounded-borders"
    >
      <q-carousel-slide name="style" class="column no-wrap flex-center">
        <q-icon name="style" color="primary" size="56px" />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="tv" class="column no-wrap flex-center">
        <q-icon name="live_tv" color="primary" size="56px" />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="layers" class="column no-wrap flex-center">
        <q-icon name="layers" color="primary" size="56px" />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="map" class="column no-wrap flex-center">
        <q-icon name="terrain" color="primary" size="56px" />
        <div class="q-mt-md text-center">
          {{ lorem }}
        </div>
      </q-carousel-slide>
    </q-carousel>

    <div class="row justify-center">
      <q-btn-toggle
        glossy
        v-model="slide"
        :options="[
          { label: 1, value: 'style' },
          { label: 2, value: 'tv' },
          { label: 3, value: 'layers' },
          { label: 4, value: 'map' },
        ]"
      />
    </div>
  </div>

  <q-card
    class="my-card text-white q-ma-sm"
    style="background: radial-gradient(circle, #35a2ff 0%, #014a88 100%)"
  >
    <q-toolbar class="bg-accent text-white q-pa-md">
      <q-toolbar-title>공부하는 한의원</q-toolbar-title>
    </q-toolbar>
    <q-card-section>
      <div class="text-h6"></div>
      <div class="text-subtitle2">by Body Identity</div>
      <div class="text-body2">
        {{ lorem }}
      </div>
    </q-card-section>
    <q-img
      :src="`https://images.unsplash.com/photo-1456513080510-7bf3a84b82f8?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb`"
      spinner-color="white"
      class="rounded-borders"
      style="width: 100%"
    >
      <div
        class="text-caption absolute-bottom text-subtitle1 text-center shadow-9"
      >
        {{ intro }}
      </div>
    </q-img>
  </q-card>

  <q-img
    rounded
    bordered
    :src="imgSrc"
    spinner-color="white"
    style="max-width: 200px"
  ></q-img>

  <div class="flex flex-center">
    <q-card class="q-ma-sm" dark square>
      <q-card-section horizontal>
        <q-card-section style lang="deep-purple-6">
          My Content1
        </q-card-section>

        <q-card-section style lang="deep-purple-6">
          <q-rating
            v-model="rating"
            color="secondary"
            size="xl"
            icon="favorite_border"
            no-dimming
            icon-selected="favorite"
          >
          </q-rating>
        </q-card-section>
      </q-card-section>
    </q-card>

    <q-card>
      <q-card-section horizontal>
        <q-icon name="font_download" color="secondary" size="4.4em" />
        <q-card-section> 이건 어떻게 나오는지 궁금하네. </q-card-section>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "IndexPage",
  setup() {
    return {
      slide: ref("style"),
      lorem:
        "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo provident incidunt ducimus iusto perferendis porro earum. Totam, numquam?",
      intro: "몸을 고치세요. 그리고 왜 그렇게 되었는지 찾아야 합니다",
      imgSrc: ref("https://picsum.photos/id/870/200/300?grayscale&blur=2"),
      rating: ref(5),
    };
  },
});
</script>

