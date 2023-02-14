<template>
  <div class="home">
    <mainComponent />
  </div>
</template>

<script>
// @ is an alias to /src
import mainComponent from "@/components/mainComponent.vue";

export default {
  name: "HomeView",
  components: {
    mainComponent,
  },
};
</script>
