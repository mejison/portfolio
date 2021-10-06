<template>
  <div class="sidebar" :class="{ open: isOpen }">
    <a href="#" class="close" @click.prevent="$emit('close')">
      <svg
        width="48"
        height="48"
        viewBox="0 0 48 48"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M35.18 10L24 21.18L12.82 10L10 12.82L21.18 24L10 35.18L12.82 38L24 26.82L35.18 38L38 35.18L26.82 24L38 12.82L35.18 10Z"
          fill="#E6DFC7"
        />
      </svg>
    </a>
    <div class="container">
      <div class="links">
        <a
          class="link"
          href="#"
          @click.prevent="go(link)"
          v-for="(link, index) in menus"
          :key="index"
        >
          {{ link.name }}
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "sidebar",

  props: ["is-open"],

  data() {
    return {
      menus: [
        {
          url: "/",
          name: "Home"
        },
        {
          url: "#about-me",
          name: "About me"
        },
        {
          url: "#portfolio",
          name: "Portfolio"
        },
        {
          url: "#contacts",
          name: "Contacts"
        }
      ]
    };
  },

  methods: {
    go(link) {
      console.log(link);
    }
  }
};
</script>

<style lang="scss">
.sidebar {
  position: fixed;
  z-index: -1;
  background: rgba(0, 0, 0, 0.8);
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  transition: all 0.3s;
  opacity: 0;

  .close {
    top: 50px;
    right: 80px;
    position: absolute;
    &:hover {
      svg {
        path {
          fill: #ebcf6f;
        }
      }
    }
  }

  &.open {
    z-index: 999;
    opacity: 1;
  }

  .links {
    margin-left: auto;
    display: flex;
    flex-direction: column;
    max-width: 400px;
    height: 100%;
    justify-content: center;
    text-align: right;
    margin-right: 50px;

    .link {
      color: #fff;
      margin-bottom: 10px;
      font-size: 22px;

      &:hover {
        color: #ebcf6f;
      }
    }
  }
}
</style>
