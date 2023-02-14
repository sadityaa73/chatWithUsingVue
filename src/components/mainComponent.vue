<template>
  <div class="main-container">
    <div class="chat-btn" v-if="!isActive">
      <button class="chat-on" @click="chatActivate">
        <i class="fa-brands fa-rocketchat"></i>
      </button>
    </div>
    <chat v-if="isActive" :activate="isActive" @status="getStatus($event)" />
  </div>
</template>
<script>
import chat from "./chat/chat.vue";
export default {
  name: "mainComponent",
  components: { chat },
  data() {
    return {
      isActive: false,
    };
  },
  created() {
    this.getStatus();
  },
  methods: {
    chatActivate() {
      this.isActive = !this.isActive;
    },
    getStatus(event) {
      console.log(`priting emitting event ${event}`);
      this.isActive = event;
    },
  },
};
</script>
<style scoped>
.main-container {
  border: 1px solid black;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.chat-btn {
  border: 1px solid black;
  width: 50px;
  height: 48px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 25px;
}
.chat-on {
  width: 100%;
  height: 100%;
  border-radius: 27px;
  border: none;
}
.fa-brands {
  font-size: 21px;
}
</style>
