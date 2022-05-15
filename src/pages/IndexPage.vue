<template>
  <q-page class="row items-center justify-evenly">
    <div class="q-pa-md">
      <q-carousel
        v-model="slide"
        transition-prev="scale"
        transition-next="scale"
        swipeable
        animated
        control-color="white"
        navigation
        padding
        arrows
        height="400px"
        class="bg-primary text-white shadow-1 rounded-borders"
      >
        <template v-slot:navigation-icon="{ active, btnProps, onClick }">
          <q-btn
            v-if="active"
            size="lg"
            icon="psychology"
            color="yellow"
            flat
            round
            dense
            @click="onClick"
          />
          <q-btn
            v-else
            size="sm"
            :icon="btnProps.icon"
            color="white"
            flat
            round
            dense
            @click="onClick"
          />
        </template>

        <q-carousel-slide name="style" class="column no-wrap flex-center">
          <q-icon name="slow_motion_video" size="56px" />
          <div class="q-mt-md text-weight-bolder text-center">
            {{ ppt1 }}
          </div>
        </q-carousel-slide>
        <q-carousel-slide name="tv" class="column no-wrap flex-center">
          <q-icon name="speed" size="56px" />
          <div class="q-mt-md text-weight-bolder text-center">
            {{ ppt2 }}
          </div>
        </q-carousel-slide>
        <q-carousel-slide name="terrain" class="column no-wrap flex-center">
          <q-icon name="emoji_objects" size="56px" />
          <div class="q-mt-md text-weight-bolder text-center">
            {{ ppt3 }}
          </div>
          <div class="q-mt-md text-weight-bolder text-center">
            <q-btn
              href="#/salud"
              color="orange"
              icon="brush"
              label="Diseña una Vida que Disfrutes"
            />
          </div>
        </q-carousel-slide>
      </q-carousel>
    </div>

    <example-component
      title="Example component"
      active
      :todos="todos"
      :meta="meta"
    ></example-component>
  </q-page>
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models';
import ExampleComponent from 'components/ExampleComponent.vue';
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'IndexPage',
  components: { ExampleComponent },
  setup() {
    const todos = ref<Todo[]>([
      {
        id: 1,
        content: 'ct1',
      },
      {
        id: 2,
        content: 'ct2',
      },
      {
        id: 3,
        content: 'ct3',
      },
      {
        id: 4,
        content: 'ct4',
      },
      {
        id: 5,
        content: 'ct5',
      },
    ]);
    const meta = ref<Meta>({
      totalCount: 1200,
    });
    return {
      todos,
      meta,
      slide: ref('style'),
      ppt1: 'Mientras que la mente conciente puede procesar 40 bits de informacion por segundo',
      ppt2: 'La mente subconciente puede procesar 40 Millones de bits de informacion por segundo',
      ppt3: 'Si bien condicion humana nos predispone a vivir entre un 90% a un 95% del tiempo de forma inconciente, no seria genial, darle forma a nuestra vida usando nuestra mente conciente. ',
    };
  },
});
</script>
