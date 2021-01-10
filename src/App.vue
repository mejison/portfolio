<template>
  <div class="app">
    <sidebar />
    <hello />
    <slider />
    <blog />
    <contact />
  </div>
</template>

<script>
import { Contact, Blog, Slider, Sidebar, Hello } from "@/components";

export default {
  name: "App",
  components: {
    Sidebar,
    Contact,
    Blog,
    Slider,
    Hello,
  },
};
</script>

<style>
.app {
  height: 100%;
  display: flex;
  flex-direction: column;
  background-image: url("/assets/background.svg");
}
</style>
