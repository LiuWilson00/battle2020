<template>
  <div class="home">
    <LoginComponent :class="{isLogin:isLogin}" v-on:loginBtnClick="loginBtnClick" />
    <HelloWorld v-on:isSelected="displayTarget" :class="{selected:isSelected,isLogin:isLogin}" />
    <InfoComponent
      :oDisplay="selectTarget[0]"
      :bDisplay="selectTarget[1]"
      :gDisplay="selectTarget[2]"
      :class="{selected:isSelected}"
      v-on:reSeter="resBtnClick"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import LoginComponent from "@/components/LoginComponent.vue";
import InfoComponent from "@/components/InfoComponent.vue";

export default {
  name: "home",

  data() {
    return {
      isLogin: false,
      selectTarget: [false, false, false],
      isSelected: false
    };
  },
  methods: {
    loginBtnClick() {
      this.isLogin = !this.isLogin;
    },
    displayTarget(num) {
      this.selectTarget = [false, false, false];
      this.selectTarget[num - 1] = !this.selectTarget[num - 1];
      this.isSelected = !this.isSelected;
    },
    resBtnClick() {
      this.isSelected = false;
    }
  },
  components: {
    HelloWorld,
    LoginComponent,
    InfoComponent
  }
};
</script>

<style lang="scss" scoped>
.home {
  .login {
    position: absolute;
    z-index: 5;
    overflow: hidden;
  }
  .hello {
    position: absolute;
    left: 15%;
    transition: all 1.5s ease;
    opacity: 0;
  }
  .hello.isLogin {
    opacity: 1;
  }

  .hello.selected {
    position: absolute;
    left: -110%;
    opacity: 0;
    transition: all 1.5s ease;
  }
  .login.isLogin {
    position: relative;
  }
  .info {
    position: relative;
    opacity: 0;
    left: 110%;
    transition: all 1.5s ease;
  }

  .info.selected {
    position: relative;
    opacity: 1;
    left: 0;
    transition: all 1.5s ease;
  }
}

@media screen and (max-width: 768px) {
  .home {
    .hello {
      left: 0%;
    }
    .hello.selected {
      position: absolute;
      left: -110%;
      width: 0;
      opacity: 0;
      transition: all 1.5s ease;
    }
  }
}
</style>
