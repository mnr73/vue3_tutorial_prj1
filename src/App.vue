<template>
  <Menu @changePage="page = $event" />
  <Pages :page="page" />
</template>

<script>
import Menu from "@/components/Menu.vue";
import Pages from "@/components/Pages.vue";

export default {
  name: "App",
  components: {
    Menu,
    Pages
  },
  data() {
    return {
      page: "Info"
    };
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}
@font-face {
  font-family: vazir;
  src: url(/Vazir.woff);
}
body,
button,
input,
select,
textarea {
  font-family: vazir;
  font-size: 18px;
}
body {
  min-height: 100vh;
  box-sizing: border-box;
  background-image: url("/bg.jpg");
  background-size: cover;
  padding: 150px 0 0;
  margin: 0;
  background-position: center center;
  direction: rtl;
  text-align: right;
}

#app {
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 10px;
  min-height: 700px;
  width: 1000px;
  margin: 0 auto;
  /* margin-top: 100px; */
}
</style>
