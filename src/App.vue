<template>
  <div class="app">
    <div class="container">
      <div class="run">
        <div class="left">
          <div class="avatar">
            <img src="" alt="" />
          </div>
          left
        </div>
        <div class="right">
          <div class="name">
            <h1>
              <span>{{ me.fname }}</span> {{ me.lname }}
            </h1>
            <h2>{{ me.position }}</h2>
          </div>
          <div class="content">
            <div class="about">
              <h2>About me</h2>
              <p>
                It is a long established fact that a reader will be distracted
                by the readable content of a page when looking at its layout.
                The point of using Lorem Ipsum is that it has a more-or-less
                normal distribution of letters, as opposed to using 'Content
                here, content here', making it look like readable English.
              </p>
            </div>
            <div class="work-experience">
              <h2>Work experience</h2>
              <div class="experiences">
                <div
                  class="experience"
                  v-for="(experience, index) in experiences"
                  :key="index"
                >
                  <div class="period">
                    {{ experience.period }}
                  </div>
                  <div>
                    <h3>{{ experience.job }}</h3>
                    <h4>{{ experience.company }}</h4>
                    {{ experience.description }}
                  </div>
                </div>
              </div>
            </div>
            <div class="software-skill">
              <h2>
                Software Skill
              </h2>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      me: {
        fname: "Alex",
        lname: "Kovalchuk",
        position: "Full-Stack Developer"
      },
      experiences: [
        {
          period: "2012-2014",
          job: "job position here",
          company: "Company Name/ California USA",
          description:
            "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout."
        },
        {
          period: "2014-2017",
          job: "job position here",
          company: "Company Name/ California USA",
          description:
            "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout."
        },
        {
          period: "2017-Present",
          job: "job position here",
          company: "Company Name/ California USA",
          description:
            "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout."
        }
      ]
    };
  }
};
</script>

<style lang="scss">
.app {
  height: 100%;

  .run {
    display: grid;
    grid-template-columns: 400px 1fr;
    height: 100%;

    .left {
      background: #202026;

      .avatar {
        background: #2d2f42;
        min-height: 450px;
      }
    }

    .right {
      background: #fff;
      margin-top: 100px;

      .name {
        background-color: #fecb00;
        color: #2d2d2d;
        width: 100%;
        font-size: 2rem;
        padding: 50px;
        text-transform: uppercase;
        position: relative;

        h1 {
          font-weight: 500;
          letter-spacing: 5px;

          span {
            font-weight: 700;
          }
        }

        h2 {
          font-size: 1.5rem;
          font-weight: 400;
          letter-spacing: 10px;
        }
      }

      .content {
        padding: 50px;

        .work-experience,
        .about {
          margin-bottom: 30px;
        }

        .experiences {
          display: flex;
          flex-direction: column;

          .experience {
            display: grid;
            grid-gap: 15px;
            grid-template-columns: 150px 1fr;
            margin-bottom: 25px;

            h3 {
              text-transform: uppercase;
              font-weight: 500;
            }

            h4 {
              font-size: 0.9rem;
              margin-bottom: 15px;
            }
          }
        }

        p {
          line-height: 1.3rem;
        }

        h2 {
          font-weight: 500;
          position: relative;
          margin-bottom: 25px;
          text-transform: uppercase;
          letter-spacing: 1.5px;
          margin-bottom: 40px;

          &:after {
            content: "";
            position: absolute;
            left: 0;
            right: 0;
            bottom: -15px;
            width: 100%;
            border-bottom: 2px solid #000;
          }
        }
      }
    }
  }
}
</style>
