<template>
  <div class="info">
    <div class="jumbotron">
      <div class="row orange" :class="{isDisplay:oDisplay}">
        <div class="col-md-5">
          <img src="/image/宋主席_info.png" alt="宋主席" />
        </div>
        <div class="col-md-7">
          <h1 class="display-3 titleText">James Soong</h1>
          <hr class="my-2" />
          <p>恭喜你搶先加入1號的陣營,請1/11攜帶身分證,準時前往支持宋神掌!</p>
          <button type="button" class="btn btn-outline-dark" @click="btnClick">再玩一次</button>
        </div>
      </div>
      <div class="row blue" :class="{isDisplay:bDisplay}">
        <div class="col-md-5">
          <img src="/image/韓總機_大頭.png" alt="韓總機" />
        </div>
        <div class="col-md-7">
          <h1 class="display-3 titleText">Korea FISH</h1>
          <hr class="my-2" />
          <p>恭喜你搶先加入2號的陣營,請1/11攜帶身分證,準時前往支持韓市長!</p>
          <button type="button" class="btn btn-outline-dark" @click="btnClick">再玩一次</button>
        </div>
      </div>
      <div class="row green" :class="{isDisplay:gDisplay}">
        <div class="col-md-5">
          <img src="/image/蔡總統_大頭.png" alt="蔡總統" />
        </div>
        <div class="col-md-7">
          <h1 class="display-3 titleText">English Tsai</h1>
          <hr class="my-2" />
          <p>恭喜你搶先加入3號的陣營,請1/11攜帶身分證,準時前往支持蔡總統!</p>
          <button type="button" class="btn btn-outline-dark" @click="btnClick" >再玩一次</button>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.info {
  .jumbotron {
    padding: 0;
    .orange {
      background-color: #f8b400;
      background-image: url("/image/冰與火_狼_小圖.png");
      background-size: 25rem;
    }

    .blue {
      background-color: #3282b8;
      background-image: url("/image/冰與火_獅子.png");
      background-size: 25rem;
    }

    .green {
      background-color: #52de97;
      background-image: url("/image/冰與火_龍貓.png");
      background-size: 25rem;
    }

    .row {
      padding: 5rem;
      position: relative;
      display: none;
      .col-md-5 {
        display: inline-block;
        img {
          height: 30rem;
        }
      }
      .col-md-7 {
        display: inline-block;
        position: relative;
        .titleText {
          z-index: 10;
        }
        img {
          position: absolute;
          opacity: 0.7;
          top: 20%;
          left: 20%;
          height: 25rem;
        }
      }
    }

    .row.isDisplay {
      display: block;
    }
  }
}
@media screen and (max-width: 768px) {
  .info {
    .jumbotron {
      .row {
        padding: 5rem;
        position: relative;
        display: none;
        .col-md-5 {
          display: inline-block;
          img {
            height: 20rem;
          }
        }
        .col-md-7 {
          display: inline-block;
          position: relative;
          .titleText {
            z-index: 10;
            font-size: 2.5rem;
          }
          img {
            position: absolute;
            opacity: 0.7;
            top: 20%;
            left: 20%;
            height: 25rem;
          }
        }
      }
    }
  }
}
</style>

<script>
export default {
  name: "InfoComponent",
  data() {
    return {};
  },
  props: {
    bDisplay: {
      type: Boolean,
      default: false
    },
    oDisplay: {
      type: Boolean,
      default: false
    },
    gDisplay: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    btnClick() {
      this.$emit("reSeter");
    }
  }
};
</script>