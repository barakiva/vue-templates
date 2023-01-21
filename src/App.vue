<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import TheWelcome from "./components/TheWelcome.vue";

import { ref, reactive } from "vue";
const msg = ref("my message");
// const data = ref("this is data");
const formData = reactive({
  user: "",
  pass: "0",
});
function handleSubmit() {
  console.log(this.fromData);
}
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <HelloWorld :msg="msg" />
    </div>
  </header>

  <main>
    <form @submit.prevent="handleSubmit">
      <label for="Username">Username</label>
      <input
        v-model="formData.user"
        type="text"
        placeholder="Type a username"
      />
      <label for="Password">Password</label>
      <input
        v-model="formData.pass"
        type="text"
        placeholder="Type a password"
      />
    </form>
    <div>{{ formData }}</div>
  </main>

  <!-- <main>
    <TheWelcome :data="data" />
  </main> -->
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
