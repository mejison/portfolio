<template>
  <div class="hello">
    <h1>hello</h1>
    <h3 class="name">
      My name is <span class="">{{ name.fname }} {{ name.lname }}</span>
    </h3>
    <h5 class="intro">
      I am a senior full-stack developer with huge experience and strong skills.
    </h5>
    <div class="socials">
      <div
        class="social"
        v-for="(social, index) in socials"
        :key="`social-${index}`"
      >
        <img :src="`/assets/${social.type}.svg`" :alt="type" />
      </div>
    </div>
    <div class="scroll-down">
      <div class="scroll">
        <img src="/assets/scroll-down.svg" alt="scroll" />
      </div>
      <div class="scroll">
        <img src="/assets/scroll-down.svg" alt="scroll" />
      </div>
      <div class="scroll">
        <img src="/assets/scroll-down.svg" alt="scroll" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "hello",

  data() {
    return {
      name: {
        fname: "Olexandr",
        lname: "Kovalchuk",
      },
      socials: [
        {
          type: "gitHub",
          link: "https://github.com/mejison",
        },
        {
          type: "twitter",
          link: "https://twitter.com/mejison_dev",
        },
        {
          type: "facebook",
          link: "https://www.facebook.com/profile.php?id=100003850392866",
        },
        {
          type: "linkedin",
          link: "https://www.linkedin.com/in/olexandr-kovalchuk-95a924167/",
        },
      ],
    };
  },

  methods: {},
};
</script>

<style lang="scss">
.hello {
  width: 100%;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100vh;

  h1 {
    font-size: 200px;
    font-weight: 400;
  }

  .name {
    font-size: 45px;
    font-weight: 400;
    span {
      font-weight: 600;
    }
  }

  .intro {
    font-size: 20px;
    font-weight: 400;
  }

  .socials {
    display: flex;
    margin-top: 50px;
    align-items: center;
    justify-content: center;

    .social {
      margin-right: 25px;
    }
  }

  .scroll-down {
    margin-top: 100px;
    .scroll {
      transform: rotate(180deg);
      margin-bottom: 15px;
    }
  }
}
</style>