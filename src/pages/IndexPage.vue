<template>
  <q-page>
    <IconContainer />
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import IconContainer from "../components/IconContainer.vue";

export default defineComponent({
  name: "IndexPage",
  components: { IconContainer },
});
</script>
