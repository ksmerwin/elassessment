<template>
  <div class="icon-container full-height q-mx-lg">
    <draggable
      v-model="icons"
      @start="drag = true"
      :delay="1000"
      @end="drag = false"
      class="row"
      :class="$q.screen.sm || $q.screen.xs ? 'justify-center q-mx-none' : ''"
    >
      <div
        v-for="icon in icons"
        :class="
          $q.screen.xl || $q.screen.lg
            ? 'col-2'
            : $q.screen.md
            ? 'col-3'
            : $q.screen.sm || $q.screen.xs
            ? 'col-5'
            : 'col-auto'
        "
        :key="icon.id"
      >
        <div class="col-auto">
          <q-icon
            size="80px"
            :name="icon.name"
            :color="icon.color"
            label="test"
          />
          <div class="text-white text-bold">{{ icon.description }}</div>
        </div>
      </div>
    </draggable>
  </div>
</template>

<script>
import { VueDraggableNext } from "vue-draggable-next";
console.log(VueDraggableNext);
export default {
  name: "IconContainer",
  components: {
    draggable: VueDraggableNext,
  },
  data() {
    return {
      drag: false,
      icons: [
        { id: 1, name: "shop", description: "Store", color: "light-blue" },
        { id: 2, name: "outbox", description: "Mail", color: "blue-9" },
        { id: 3, name: "rocket", description: "RocketCam", color: "cyan" },
        { id: 4, name: "home", description: "Home", color: "brown" },
        { id: 5, name: "school", description: "Grades", color: "light-blue" },
        { id: 6, name: "whatshot", description: "Hinder", color: "red-6" },
        { id: 7, name: "group", description: "Group", color: "teal" },
        {
          id: 8,
          name: "catching_pokemon",
          description: "Pokemon",
          color: "red-10",
        },
        {
          id: 9,
          name: "sports_esports",
          description: "Esports",
          color: "indigo",
        },
        { id: 10, name: "whatsapp", description: "WhatsApp", color: "green" },
      ],
    };
  },

  computed: {},
};
</script>

<style scoped>
.icon-container {
  background: #33cccc;
  animation: color 9s infinite linear;
  text-align: center;
  padding: 2em;
  border: solid 5px white;
  border-radius: 25px;
}

@keyframes color {
  0% {
    background: #33cccc;
  }
  20% {
    background: #33cc36;
  }
  40% {
    background: #b8cc33;
  }
  60% {
    background: #fcca00;
  }
  80% {
    background: #33cc36;
  }
  100% {
    background: #33cccc;
  }
}
</style>
