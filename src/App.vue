<script>
import NotificationMessage from "./components/NotificationMessage.vue";
export default {
  components: {
    NotificationMessage
  }
}
</script>
<template>
  <h1>Notification Center</h1>
  <NotificationMessage :type="'info'" :header="'You are eligible for a reward'">
    <p>
      Go to
      <b>special offers</b> page to see now
    </p>
  </NotificationMessage>
  <NotificationMessage :type="'error'" :header="'Oh no! We have an error'">
    <p>Reload this page</p>
  </NotificationMessage>
</template>

<style>
</style>
