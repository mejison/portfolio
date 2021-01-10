<template>
  <div class="sidebar">
    <a href="#" class="burger">
      <img src="/assets/burger.svg" alt="burger" />
    </a>
    <div class="navs-wrapper">
      <div class="line"></div>
      <div class="navs">
        <template v-for="(nav, index) in navs" :key="`nav-${index}`">
          <a class="nav" :href="nav.link">{{ nav.title }}</a>
          <img
            v-if="index != navs.length - 1"
            :src="`/assets/triangle.svg`"
            alt="triangle"
          />
        </template>
      </div>
      <div class="line"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "sidebar",

  data() {
    return {
      navs: [
        {
          title: "about",
          link: "#about",
        },
        {
          title: "portfolio",
          link: "#portfolio",
        },
        {
          title: "blog",
          link: "#blog",
        },
        {
          title: "contact",
          link: "#contact",
        },
      ],
    };
  },

  methods: {},
};
</script>

<style lang="scss">
.sidebar {
  margin: 50px auto;
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100%;

  .burger {
    margin-right: auto;
    transform: rotate(-5deg);
    transform: translateX(-5px);
  }

  .line {
    min-width: 200px;
    height: 2px;
    border-radius: 2px;
    background: #fae586;
  }

  .navs-wrapper {
    max-width: 980px;
    min-width: 980px;
    margin-right: auto;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .navs {
    display: flex;
    justify-content: space-around;
    width: 100%;

    .nav {
      color: #000;
    }
  }
}
</style>