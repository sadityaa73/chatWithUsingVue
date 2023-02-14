<template>
  <div id="chat-container">
    <div class="chat-header">
      <div class="user-avtar">
        <img
          src="../../assets/profile.png"
          alt="user-avtar-image"
          class="user-avtar-image"
        />
      </div>
      <div class="user-status">
        <div class="status-symbol"></div>
        <div class="status">Active</div>
      </div>
      <div class="close-container" v-if="activate" @click="close">
        <i class="fa-solid fa-xmark"></i>
      </div>
    </div>
    <div class="chat-body"></div>
    <div class="chat-fotter">
      <div class="message-input-container">
        <input type="text" class="input-box" placeholder="enter text" />
      </div>
      <div class="send-button-container">
        <button class="send">
          <img
            src="../../assets/send-message.png"
            alt="send"
            class="send-icon"
          />
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    activate: Boolean,
  },
  name: "chat",
  component: {},
  data() {
    return {};
  },
  created() {
    console.log(`printing props  active ${this.activate}`);
  },
  methods: {
    close() {
      this.$emit("status", false);
    },
  },
};
</script>
<style scoped>
#chat-container {
  border: none;
  border-radius: 0px 35px 0px 35px;
  width: 30%;
  height: 80%;
  box-shadow: 0px 0px 27px 6px grey;
  animation: chat 2s ease-in;
}
@keyframes chat {
  0% {
    height: 0%;
  }

  100% {
    height: 80%;
  }
}
.chat-header {
  border: none;
  width: 100%;
  height: 10%;
  border-radius: 0px 35px 0px 0px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  background-color: rgba(46, 163, 242, 0.929);
}
.user-avtar {
  border: 1px solid black;
  height: 77%;
  width: 12%;
  margin-left: 2%;
  border-radius: 39px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.user-avtar-image {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.user-status {
  border: none;
  width: 16%;
  height: 70%;
  display: flex;
  justify-content: center;
  align-items: flex-end;
  color: white;
}
.status-symbol {
  border: 1px solid;
  width: 10%;
  height: 13%;
  border-radius: 24px;
  background-color: green;
  margin-bottom: 11%;
  margin-right: 4%;
}
.close-container {
  margin-left: 59%;
}
.fa-solid {
  font-size: 21px;
}
.chat-body {
  border: none;
  height: 79%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: auto;
}
.chat-fotter {
  border: none;
  width: 100%;
  height: 10%;
  border-radius: 0px 0px 0px 35px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
.message-input-container {
  border: 1px solid black;
  width: 70%;
  height: 55%;

  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  margin-left: 8%;
  overflow: hidden;
}
.input-box {
  width: 100%;
  height: 100%;
  font-size: 18px;
  color: black;
  font-family: helvetica;
  border: none;
}
.send-button-container {
  border: 1px solid black;
  width: 10%;
  height: 50%;
  border-radius: 13px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 3%;
}
.send {
  width: 100%;
  height: 100%;
  border-radius: 13px;
  border: none;
  display: flex;
  justify-content: center;
  align-items: center;
}
.send-icon {
  width: 72%;
  height: 80%;
}
</style>
