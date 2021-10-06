<template>
  <div class="page">
    <div class="header">
      <div class="container">
        <a href="#" class="logo">
          <img src="/logo.svg" alt="logo" />
          <h3>{{ position }}</h3>
        </a>
        <a :href="`mailto:${email}`" class="contact">
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M5.124 12.1136L5.12669 12.1264C5.50897 13.9413 6.73214 15.4995 8.46323 16.2864L12 17.894V16H14C16.7614 16 19 13.7614 19 11V10C19 7.23858 16.7614 5 14 5H10C7.23858 5 5 7.23858 5 10V11C5 11.3804 5.04211 11.7485 5.12115 12.1009L5.124 12.1136ZM14 21L7.63562 18.1071C5.31787 17.0536 3.68127 14.9677 3.16963 12.5386C3.05859 12.0435 3 11.5286 3 11V10C3 6.13401 6.13401 3 10 3H14C17.866 3 21 6.13401 21 10V11C21 14.866 17.866 18 14 18V21Z"
              fill="#E6DFC7"
            />
          </svg>

          {{ email }}
        </a>
        <a href="#" class="burger" @click.prevent="onToggle">
          <svg
            width="48"
            height="48"
            viewBox="0 0 48 48"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M24 36H6V32H24V36ZM42 26H6V22H42V26ZM42 16H24V12H42V16Z"
              fill="#E6DFC7"
            />
          </svg>
        </a>
        <div class="avatar">
          <img src="/avatar.png" alt="" />
        </div>
      </div>
    </div>
    <div class="hero">
      <div class="container">
        <h1 class="name">
          {{ name }}
        </h1>
        <div class="hr"></div>
        <p class="bio" v-html="bio"></p>
        <a :href="hire" target="blank" class="btn">hire me</a>
      </div>
    </div>
    <socials />
    <sidebar :is-open="isOpen" @close="isOpen = false" />
  </div>
</template>

<script>
import { Socials, Sidebar } from "@/components";

export default {
  name: "App",

  components: {
    Sidebar,
    Socials
  },

  data() {
    return {
      position: "Full-Stack Developer",
      email: "dev.mejison@gmail.com",
      name: "Olexandr Kovalchuk",
      bio: `<p>Hi everyone!</p>
            <br />
            <p>
              I am a senior full-stack developer with huge experience and strong skills.<br />
              If you are looking for a developer that can create any project fast and clean - here I am. I'm always looking for new interesting projects.</br>
              If you have one, please let me know ;)
            </p>
            <br />
            Best regards,</br>
            Olexandr`,
      hire: "https://www.upwork.com/freelancers/~01ff6d9def9ac040c7",
      isOpen: false
    };
  },

  methods: {
    onToggle() {
      this.isOpen = !this.isOpen;
    }
  }
};
</script>

<style lang="scss">
.page {
  height: 100%;
  width: 100%;
  background-image: url("/bg.png");
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;

  .avatar {
    position: absolute;
    right: 100px;
    top: 50%;
    transform: translateY(-50%);
    filter: grayscale(100%);
  }

  .header {
    padding-top: 30px;

    .container {
      display: flex;
      justify-content: space-between;
      align-items: center;

      .logo {
        display: flex;
        align-items: center;

        h3 {
          margin-left: 25px;
        }
      }

      .contact {
        margin-left: auto;
        margin-right: 50px;
        display: flex;
        align-items: center;
        line-height: 0;

        &:hover {
          svg {
            path {
              transition: all 0.3s;
              fill: #ebcf6f;
            }
          }
        }

        svg {
          margin-right: 15px;
        }
      }

      .burger {
        width: 48px;
        height: 48px;
        display: inline-block;

        &:hover {
          svg {
            path {
              transition: all 0.3s;
              fill: #ebcf6f;
            }
          }
        }
      }
    }
  }

  .hero {
    color: #fff;
    margin-top: calc(100vh / 5);
    font-size: 24px;

    .hr {
      width: 100px;
      height: 1px;
      background-color: #e6dfc7;
      margin: 35px 0;
    }

    .bio {
      max-width: 50%;
      font-size: 16px;
      margin-bottom: 50px;
    }
  }
}
</style>
