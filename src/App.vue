<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" width="25%" />
    <br />
    <!-- Trigger/Open The Modal -->
    <button id="parent">
      Open Modal from parent where component is imported
    </button>
    <SuccessAlertBox
      headingMessage="Confirm"
      :confirmationMessage="confirmationMessageAlertBox"
      @confirmation="confirmationStatus"
    />
  </div>
</template>

<script>
import SuccessAlertBox from "./components/SuccessAlertBox";
export default {
  name: "App",
  data() {
    return {
      confirmationMessageAlertBox: "Are you Sure you want to delete ?",
    };
  },
  components: {
    SuccessAlertBox,
  },
  methods: {
    confirmationStatus(value) {
      alert("Status Received in parent. Confirm: " + value);
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
