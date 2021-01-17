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
  <div class="about">
    <h2>about</h2>
    <div class="about-wrapper">
      <div class="image">
        <img src="/assets/photo-map.svg" alt="" class="photo" />
      </div>
      <div class="description">
        Donec vitae nulla lacus. Praesent metus mi, sit amet sit amet fermentum.
        Curabitur tempor lacus risus, nec placerat dui finibus non. Sed mollis
        elit quis mi dapibus consequat.Phasellus vitae arcu sit amet massa
        ullamcorper commodo ut sit amet tortor.
        <br />
        <br />
        Praesent placerat odio urna, sit amet commodo massa dictum sit amet.
        Pellentesque vel eros et dui sodales tincidunt a id purus.
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
  height: calc(100vh - 200px);

  h1 {
    font-size: 10rem;
    font-weight: 400;
    margin-top: auto;
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
    margin-bottom: 50px;
    align-items: center;
    justify-content: center;

    .social {
      margin-right: 25px;
    }
  }

  .scroll-down {
    margin-top: auto;

    .scroll {
      transform: rotate(180deg);
      margin-bottom: 15px;
      animation: sk-bouncedelay 1.4s infinite ease-in-out both;

      &:nth-child(1) {
        animation-delay: -0.32s;
      }

      &:nth-child(2) {
        animation-delay: -0.16s;
      }
    }
  }
}

.about {
  max-width: 850px;
  margin: 0 auto;
  background-image: url("/assets/about.svg");
  background-repeat: no-repeat;
  background-size: contain;
  padding: 70px 100px;

  h2 {
    font-size: 35px;
    text-align: center;
    margin-bottom: 15px;
    font-weight: normal;
  }

  .about-wrapper {
    display: flex;

    .image {
      margin-right: 25px;
    }

    .description {
      margin-top: 25px;
    }
  }
}

@-webkit-keyframes sk-bouncedelay {
  0%,
  80%,
  100% {
    -webkit-transform: scale(0);
  }
  40% {
    -webkit-transform: scale(1);
  }
}

@keyframes sk-bouncedelay {
  0%,
  80%,
  100% {
    -webkit-transform: scale(0);
    transform: scale(0);
  }
  40% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}
</style>