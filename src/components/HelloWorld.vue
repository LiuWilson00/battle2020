<template>
  <div class="hello">
    <div class="container">
      <h1 class="msg" :class="{active:urlOrage.isHover||urlBlue.isHover||urlGreen.isHover}">請選擇您的陣營</h1>
      <div class="row">
        <div
          class="person-area orage col-md-4"
          @mouseenter="srcChange(urlOrage)"
          @mouseleave="srcChange(urlOrage)"
        >
          <div class="container">
            <div class="text" :class="{active:urlOrage.isHover}">
              <h1>The king in the Province</h1>
              <hr class="my-2" />
              <p>史塔宋家族是來自古老的台灣省,儘管年歲已高但還是具有影響力,現在傳說中每四年都有一個重天而降的掌法-宋神掌正是該狼家的獨門秘術</p>
              <button
                type="button"
                class="btn btn-light"
                :class="{btnDisplay:urlOrage.isHover}"
                @click="btnClick(1)"
              >選擇1號-史塔宋家族</button>
            </div>

            <img :src="urlOrage.now" class="person" alt />
          </div>
        </div>

        <div
          class="person-area blue col-md-4"
          @mouseenter="srcChange(urlBlue)"
          @mouseleave="srcChange(urlBlue)"
        >
          <div class="container">
            <div class="text" :class="{active:urlBlue.isHover}">
              <h1>Korea FISH</h1>
              <p>
                蘭尼思汗家族擁有深遠的歷史及資源,過去曾長期掌握權力核心,這次該家族出現了強而有力的領導人,擅長動魄人心的口號,得罪獅家的人小心了,
                蘭尼司汗有債必還!
              </p>
              <button
                type="button"
                class="btn btn-light"
                :class="{btnDisplay:urlBlue.isHover}"
                @click="btnClick(2)"
              >選擇2號-蘭尼思汗家族</button>
            </div>
            <img :src="urlBlue.now" class="person" alt />
          </div>
        </div>

        <div
          class="person-area green col-md-4"
          @mouseenter="srcChange(urlGreen)"
          @mouseleave="srcChange(urlGreen)"
        >
          <div class="container">
            <div class="text" :class="{active:urlGreen.isHover}">
              <h1>English Tsai</h1>
              <p>塔格安麗家族是現任鐵王座的擁有者,以安麗芒果乾聞名,其中領導人</p>
              <p class="hl">
                福爾摩沙蔡氏家族霸海皇英.不沉霧島 綠營女主.
                台大法律系康乃爾法學院暨倫敦政治經濟學院法學博士學霸女王.
                特殊國與國關係論述起草者台灣主權守護者.
                民進黨浴火重生舵手.九二共識謊言擊碎者.
                喵之母排灣守護神之女.
                蔡英文大統領，
              </p>
              <p>更是讓人印象深刻。</p>
              <button
                type="button"
                class="btn btn-light"
                :class="{btnDisplay:urlGreen.isHover}"
                @click="btnClick(3)"
              >選擇3號-塔格安麗家族</button>
            </div>
            <img :src="urlGreen.now" class="person" alt />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  mounted: {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.hello {
  .msg {
    display: inline-block;
    position: absolute;
    top: 0;
    left: 38%;
    z-index: 20;
    transition: all 1s ease;
  }
  .msg.active {
    transition: all 1s ease;
    opacity: 0;
  }
  .row {
    height: 40rem;
    .text {
      height: 0px;
      opacity: 0;
      -webkit-transition: all 1s ease;
      -moz-transition: all 1s ease;
      transition: all 1s ease;
      h1 {
        font-size: 2rem;
      }
      p.hl {
        font-size: 1rem;
        color: aliceblue;
      }
    }
    .btn {
      opacity: 0;
    }
    .btn.btnDisplay {
      animation-name: displayBtn;
      animation-duration: 1s;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
    }
    @keyframes displayBtn {
      0% {
        opacity: 0;
      }
      25% {
        opacity: 0;
      }
      100% {
        opacity: 1;
      }
    }

    .text.active {
      height: 100px;
      opacity: 1;
      -webkit-transition: all 1s ease;
      -moz-transition: all 1s ease;
      transition: all 1s ease;
    }
    .person-area {
      background-color: #00a2e7;
      padding: 2rem;
      background-size: contain;
      background-repeat: no-repeat;
      background-position: center;
    }
    .orage {
      background-color: #f8b400;
      background-image: url("/image/冰與火_狼.png");
    }
    .green {
      background-color: #52de97;
      background-image: url("/image/冰與火_龍貓.png");
    }
    .blue {
      background-color: #3282b8;
      background-image: url("/image/冰與火_獅子.png");
    }
    img.person {
      margin-top: 10rem;
      height: 25rem;
    }
  }
}

@media screen and (max-width: 768px) {
  .hello {
    .msg {
      display: inline-block;
      position: absolute;
      top: 0;
      left: 15%;
      z-index: 20;
      transition: all 1s ease;
    }
  }
}
</style>


<script>
// @ is an alias to /src

export default {
  name: "Hello",
  data() {
    return {
      urlOrage: {
        isHover: false,
        now: "/image/宋主席.png",
        nomal: "/image/宋主席.png",
        hover: "/image/宋主席_hover.png"
      },
      urlBlue: {
        isHover: false,
        now: "/image/韓總機.png",
        nomal: "/image/韓總機.png",
        hover: "/image/韓總機_hover_1.png"
      },
      urlGreen: {
        isHover: false,
        now: "/image/蔡總統.png",
        nomal: "/image/蔡總統.png",
        hover: "/image/蔡總統_hover.png"
      }
    };
  },
  methods: {
    btnClick(num) {
      this.$emit("isSelected", num);
    },
    srcChange(target) {
      if (target.now == target.nomal) {
        target.now = target.hover;
      } else if (target.now == target.hover) {
        target.now = target.nomal;
      }
      target.isHover = !target.isHover;
    }
  }
};
</script>
