<template>
  <div class="app">
    <sidebar />
    <hello />
    <slider />
    <blog />
    <contact />
    <footer>
      <div class="container">
        <span class="line"></span>
      </div>
      <div class="container footer">
        <span class="copyright"> All Rights Reserved. </span>
        <a href="#" class="back-to-top"> Back to top </a>
      </div>
    </footer>
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

.container {
  max-width: 1200px;
  margin: 0 auto;
}

footer {
  position: relative;
}

footer .line {
  width: 100%;
  height: 2px;
  background-color: #222;
  display: flex;
}

footer .footer {
  padding: 30px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
