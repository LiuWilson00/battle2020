<template>
  <div id="app">
    <!-- <div id="nav">
      <h1>Battle of Taiwan</h1>
      <router-link to="/about" class="nav-link">About</router-link>
    </div> -->
    <router-view />
  </div>
</template>

<style>

@font-face {
  font-family: Game-of-Thrones;
  src: url("/font/Game of Thrones.ttf")
    format("truetype");
  font-weight: normal; /* 可預設字型粗細 */
  font-style: normal; /* 可預設字型樣式，mormal為一般，也可設定斜體italic */
}
@font-face {
  font-family: CSong3HK-Medium;
  src: url("/font/CSong3HK-Medium.otf") format("opentype");
  font-weight: normal; /* 可預設字型粗細 */
  font-style: normal; /* 可預設字型樣式，mormal為一般，也可設定斜體italic */
}

#app {
  overflow: hidden;
  font-family: "Avenir", Helvetica, Arial, sans-serif,CSong3HK-Medium;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
}

#nav {
  padding: 0.5rem;
  background-color: #373f47;
}
h1{
  font-family: Game-of-Thrones,CSong3HK-Medium
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
@media only screen and (max-width: 768px) {
#app {
  overflow:auto;
}
}

</style>
