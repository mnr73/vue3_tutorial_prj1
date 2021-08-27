<template>
  <div id="menu">
    <div class="s_menu">
      <div class="logo"><img src="@/assets/logo.png" alt="logo" /></div>
      <div class="nav">
        <button
          class="nav-btn"
          type="button"
          :class="{ active: active == 'Info' }"
          @click="changePage('Info')"
        >
          درباره من
        </button>
        <button
          class="nav-btn"
          type="button"
          :class="{ active: active == 'Ability' }"
          @click="changePage('Ability')"
        >
          مهارت های من
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      active: "Info"
    };
  },
  methods: {
    changePage(pageName) {
      this.$emit("changePage", pageName);
      this.active = pageName;
    }
  }
};
</script>

<style>
#menu {
  float: right;
  width: 300px;
  height: 700px;
  /* background-color: red; */
  padding: 20px;
}
#menu .s_menu {
  background-color: rgba(255, 255, 255, 0.6);
  border-radius: 10px;
  height: 100%;
}
.logo {
  text-align: center;
  padding: 20px;
}
.nav .nav-btn {
  display: block;
  width: 100%;
  border: none;
  background-color: rgba(255, 255, 255, 0);
  color: #666;
  padding: 10px;
  cursor: pointer;
}
.nav .nav-btn:hover:not(.active) {
  color: #333;
  background-color: rgba(255, 255, 255, 0.5);
}
.nav .nav-btn.active {
  color: #35495e;
  font-weight: bold;
  font-size: 1.2em;
}
</style>
