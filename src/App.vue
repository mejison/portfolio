<template>
  <div class="app">
    <div class="hero">
      <div class="container">
        <div class="name">
          <h1 class="fname">{{ user.fname }}</h1>
          <h1>{{ user.lname }}</h1>
          <span class="job">{{ user.job }}</span>
        </div>
        <div class="info">
          <div class="avatar">
            <img :src="user.avatar" alt="avatar" />
          </div>
          <div class="contact">
            <ul>
              <li>
                Phone:
                <span>{{ user.phone }}</span>
              </li>
              <li>
                Email:
                <span>{{ user.email }}</span>
              </li>
              <li>
                Address:
                <span>Your Street Address</span>
                <span>Here, Zip code</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <main>adsf</main>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      user: {
        fname: "Alex",
        lname: "Kovalchuk",
        job: "Full-Stack Web Developer",
        phone: "+380986604726",
        email: "dev.mejison@gmail.com",
        address: "",
        avatar: "/avatar.jpeg",
      },
    };
  },
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

html,
body,
.app {
  height: 100%;
  font-family: "Poppins", sans-serif;
}

.container {
  width: 1440px;
  margin: 0 auto;
}

.app {
  .hero {
    background-color: #171b26;
    color: #fff;
    height: 100vh;

    .container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-gap: 100px;
      align-items: center;
      height: 100%;
    }

    .name {
      text-align: right;

      .fname {
        display: inline;
        padding: 0 50px;
        position: relative;
        z-index: 2;
        color: #171b26;

        &::after {
          content: "";
          display: block;
          position: absolute;
          width: 100%;
          height: 1000px;
          z-index: -1;
          left: 0;
          right: 0;
          bottom: 0;
          background: #ffcc01;
        }
      }

      h1 {
        font-size: 80px;
      }

      span {
        font-size: 48px;
      }
    }

    .job {
      font-weight: 300;
    }
  }

  .info {
    display: flex;
    align-items: flex-end;
    font-size: 18px;

    .avatar {
      margin-right: 50px;
      width: 250px;
      height: 450px;

      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center center;
      }
    }

    .contact {
      ul {
        list-style: none;

        li {
          margin-bottom: 15px;

          span {
            color: #d7d7d7;
            display: block;
            font-weight: 300;
          }
        }
      }
    }
  }
}
</style>
