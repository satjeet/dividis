<template>
  <q-page class="row items-center justify-evenly">
    <div id="q-app" style="min-height: 100vh">
      <div class="q-pa-md">
        <q-carousel
          v-model="slide"
          transition-prev="slide-right"
          transition-next="slide-left"
          animated
          swipeable
          control-color="primary"
          class="rounded-borders q-ma-lg"
        >
          <q-carousel-slide name="style" class="column no-wrap flex-center">
            <q-icon name="style" color="primary" size="56px"></q-icon>
            <div class="q-mt-md text-center">
              {{ lorem }}
            </div>
          </q-carousel-slide>
          <q-carousel-slide name="tv" class="column no-wrap flex-center">
            <q-icon name="live_tv" color="primary" size="56px"></q-icon>
            <div class="q-mt-md text-center">
              {{ lorem }}
            </div>
          </q-carousel-slide>
          <q-carousel-slide name="layers" class="column no-wrap flex-center">
            <q-icon name="layers" color="primary" size="56px"></q-icon>
            <div class="q-mt-md text-center">
              {{ lorem }}
            </div>
          </q-carousel-slide>
          <q-carousel-slide name="map" class="column no-wrap flex-center">
            <q-icon name="terrain" color="primary" size="56px"></q-icon>
            <div class="q-mt-md text-center">
              {{ lorem }}
            </div>
          </q-carousel-slide>
        </q-carousel>

        <div class="row justify-center q-ma-lg">
          <q-btn-toggle
            glossy
            v-model="slide"
            :options="[
              { label: 'Premisas', value: 'style' },
              { label: 'Vision', value: 'tv' },
              { label: 'Proposito', value: 'layers' },
              { label: 'Estrategias', value: 'map' },
            ]"
          ></q-btn-toggle>
        </div>
      </div>
    </div>
    <div id="q-app" style="min-height: 100vh">
      <div class="q-mt-md">
        <q-fab
          v-model="fab2"
          label="Actions"
          label-position="bottom"
          glossy
          color="purple"
          icon="keyboard_arrow_down"
          direction="down"
          :hide-label="hideLabels"
        >
          <q-fab-action
            :hide-label="hideLabels"
            color="primary"
            @click="onClick"
            icon="mail"
            label="Email"
          ></q-fab-action>
          <q-fab-action
            :hide-label="hideLabels"
            color="secondary"
            @click="onClick"
            icon="alarm"
            label="Alarm"
          ></q-fab-action>
          <q-fab-action
            :hide-label="hideLabels"
            color="orange"
            @click="onClick"
            icon="airplay"
            label="Airplay"
          ></q-fab-action>
          <q-fab-action
            :hide-label="hideLabels"
            color="accent"
            @click="onClick"
            icon="room"
            label="Map"
          ></q-fab-action>
        </q-fab>
      </div>
      <div class="q-pa-md" style="max-width: 350px">
        <q-list>
          <q-expansion-item
            popup
            default-opened
            icon="mail"
            label="Inbox"
            caption="5 unread emails"
          >
            <q-separator></q-separator>
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
                numquam, dolorum officiis modi facere maiores architecto
                suscipit iste eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>
          <q-expansion-item popup icon="send" label="Outbox" caption="Empty">
            <q-separator></q-separator>
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
                numquam, dolorum officiis modi facere maiores architecto
                suscipit iste eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>
          <q-expansion-item
            popup
            icon="drafts"
            label="Draft"
            caption="Draft a new email"
          >
            <q-separator></q-separator>
            <q-card>
              <q-card-section>
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Quidem, eius reprehenderit eos corrupti commodi magni quaerat ex
                numquam, dolorum officiis modi facere maiores architecto
                suscipit iste eveniet doloribus ullam aliquid.
              </q-card-section>
            </q-card>
          </q-expansion-item>
        </q-list>
      </div>
    </div>
    <div class="q-ma-lg">
      dentro de este div voy a mostrar ejemplo de premisa y tendra un boton que
      la hara desaparecer
    </div>
    <q-card class="my-card">
      <q-card-section class="bg-purple text-white">
        <div class="text-h6">
          Our Changing Planet ffffffffffffffffffffffffffffffffffffffffffff
        </div>
        <div class="text-subtitle2">by John Doe</div>
      </q-card-section>

      <q-card-actions align="around">
        <q-btn flat>Action 1</q-btn>
        <q-btn flat>Action 2</q-btn>
      </q-card-actions>
    </q-card>
  </q-page>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
export default defineComponent({
  name: 'SaludPage',
  components: {},
  setup() {
    const options = {
      type: 'loop',
      padding: '5rem',
    };
    return {
      options,
      slide: ref('style'),
      lorem:
        'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo provident incidunt ducimus iusto perferendis porro earum. Totam, numquam?',
    };
  },
});
</script>
