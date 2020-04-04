<template>
  <div class="login">
    <div class="jumbotron main" :class="{isClick:isClick}">
      <h1
        class="display-3 titleText"
        :class="{clickText:!isClick}"
        @click="btnClick"
      >Battle of Taiwan </h1>

      <div class="text">
        <h1 class="display-3">Battle of Taiwan</h1>

        <p class="lead">2020/1/11 火爆上線</p>
        <hr class="my-2" />

        <button type="button" class="btn btn-outline-light" @click="btnClick">搶先登入</button>
      </div>
      <img src="/image/蔡總統_大頭.png" class="green" alt="蔡總統" />
      <img src="/image/韓總機_大頭.png" class="blue" alt="韓總機" />
      <img src="/image/宋主席_小圖.png" class="orange" alt="宋主席" />

      <video class="smoke-video" autoplay loop muted>
        <source src="https://storage.googleapis.com/battle/video/smoke.mp4" type="video/mp4" />
      </video>
      <canvas class="smoke-canvas"></canvas>
    </div>
  </div>
</template>


<script>
export default {
  name: "LoginComponent",
  props: {
    msg: String
  },

  data() {
    return {
      isClick: false
    };
  },
  methods: {
    btnClick() {
      this.isClick = !this.isClick;
      this.$emit("loginBtnClick");
    }
  },

  mounted() {
    function video() {
      const canvas = document.querySelector(".smoke-canvas");
      const ctx = canvas.getContext("2d");
      const video = document.querySelector(".smoke-video");

      video.addEventListener("play", draw);

      function draw() {
        canvas.width = canvas.clientWidth;
        canvas.height = canvas.clientHeight;
        if (video.paused || video.ended) return false;
        ctx.drawImage(video, 0, 0, canvas.width, canvas.height);

        requestAnimationFrame(draw);
      }
    }
    var myVid = document.querySelector(".smoke-video");

    myVid.playbackRate = 0.5;
    video();
  }
};
</script>

<style lang="scss" scoped>
$displayTime: 1s;
$clickTime: 2s;

.login {
  color: white;

  .main.isClick {
    height: 6rem;
    padding: 1rem;
    margin-bottom: 0px;
    .display-3 {
      font-size: 3rem;
      z-index: 11;
      animation-name: displayText;
      animation-duration: $clickTime;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
    }
    .display-3:hover {
      color: rgb(146, 140, 140);
    }

    > :not(:first-child) {
      animation-name: displayNone;
      animation-duration: $displayTime;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
    }

    > img.green {
      animation-name: displayNone;
      animation-duration: $displayTime;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
    }
    > img.blue {
      animation-name: displayNone;
      animation-duration: $displayTime;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
    }
    > img.orange {
      animation-name: displayNone;
      animation-duration: $displayTime;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
    }

    @keyframes displayNone {
      form {
        opacity: 1;
        display: inline-block;
      }
      to {
        opacity: 0;
        width: 0px;
        display: none;
      }
    }
    @keyframes displayText {
      0% {
        opacity: 0;
      }
      50% {
        opacity: 0;
      }
      100% {
        opacity: 1;
      }
    }
  }

  .main {
    height: 55rem;
    position: relative;
    background-color: dimgray;
    transition: all 1s ease;

    .clickText {
      display: none;
    }

    .text {
      z-index: 10;
      margin: 20%;
      position: absolute;
      .display3-2 {
        text-align: right;
      }
      .btn {
        font-size: 2rem;
      }
    }

    .smoke-video {
      visibility: hidden;
      width: 100%;
      height: 100%;
    }
    img.green {
      position: absolute;
      width: 20%;
      left: 20%;
      z-index: 4;
      animation-name: breath;
      animation-duration: 4s;
      animation-iteration-count: infinite;
    }

    img.blue {
      position: absolute;
      width: 20%;
      left: 57%;
      z-index: 5;
      animation-name: breath;
      animation-duration: 4s;
      animation-iteration-count: infinite;
    }
    img.orange {
      width: 20%;
      position: absolute;
      top: 30%;
      left: 36%;
      z-index: 6;
      animation-name: move;
      animation-duration: 4s;
      animation-iteration-count: infinite;
    }

    @keyframes breath {
      0% {
        width: 20%;
      }
      25% {
        width: 20%;
      }
      50% {
        width: 20.5%;
      }
      100% {
        width: 20%;
      }
    }
    @keyframes move {
      0% {
        left: 36%;
      }
      25% {
        left: 36.5%;
      }
      50% {
        left: 36.5%;
      }
      100% {
        left: 36%;
      }
    }

    .smoke-canvas {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1;

      opacity: 0.2;
    }
  }

  @media screen and (max-width: 768px) {
    .main {
      margin: 0%;
      height: 50rem;
      .titleText.display-3 {
        font-size: 2rem;
      }
      .text {
        margin-top: 30%;
        .display-3 {
          font-size: 2.5rem;
        }
      }
      img.green {
        position: absolute;
        width: 40%;
        left: 5%;
        z-index: 4;
      }

      img.blue {
        position: absolute;
        width: 40%;
        top: 7%;
        left: 55%;
      }
      img.orange {
        width: 80%;
        position: absolute;
        top: 55%;
        left: 0%;
      }

      @keyframes breath {
        0% {
          width: 40%;
        }
        25% {
          width: 40%;
        }
        50% {
          width: 40.5%;
        }
        100% {
          width: 40%;
        }
      }
      @keyframes move {
        0% {
          left: 5%;
        }
        25% {
          left: 5.5%;
        }
        50% {
          left: 5.5%;
        }
        100% {
          left: 5%;
        }
      }
    }
  }
}
</style>