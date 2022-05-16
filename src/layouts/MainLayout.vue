<template>
  <q-layout>
    <div
      :class="
        $q.screen.lg || $q.screen.xl
          ? 'text-h1'
          : $q.screen.md
          ? 'text-h2'
          : $q.screen.sm
          ? 'text-h5'
          : ''
      "
      class="row justify-center text-center q-pa-lg text-white text-weight-bold"
    >
      Explore Learning Assessment
    </div>
    <q-page-container>
      <IconContainer />
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import IconContainer from "../components/IconContainer.vue";
export default defineComponent({
  name: "MainLayout",

  components: { IconContainer },
  created() {
    this.$q.screen.setSizes({ sm: 200, md: 500, lg: 1000, xl: 2000 });
  },
});
</script>
