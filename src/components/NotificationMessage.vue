<script>
import IconCross from "./IconCross.vue";
export default {
  components: {
    IconCross
  },
  props: {
    type: { type: String, default: "info" },
    header: { type: String, default: "Notification message" },
  },
  data() {
    return {
      hidden: false
    }
  },
  methods: {
    hide() {
      this.hidden = true;
    }
  }
}

</script>

<template>
  <div class="notification" v-if="!hidden" :class="type">
    <div class="header">{{ header }}</div>
    <slot></slot>
    <IconCross class="close" @click="hide"></IconCross>
  </div>
</template>

<style scoped>
.notification {
  position: relative;
  width: 90%;
  padding: 0.5rem;
  margin: 8px auto;

  border-radius: 12px;
  text-align: center;
}
.header {
  font-weight: bold;
}
.info {
  background: rgb(137, 196, 248);
  border: 1px solid rgb(33, 111, 179);
}
.error {
  background: rgb(248, 137, 155);
  border: 1px solid rgb(179, 33, 77);
}
div.alert svg path {
  fill: rgb(179, 33, 77);
}
div.info svg path {
  fill: rgb(33, 111, 179);
}
.close {
  position: absolute;
  top: 5px;
  right: 5px;
  cursor: pointer;
}
</style>
