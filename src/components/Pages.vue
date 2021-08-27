<template>
  <div id="pages">
    <div class="s_pages">
      <component :is="page" />
    </div>
  </div>
</template>

<script>
import Info from "@/components/Pages/Info.vue";
import Ability from "@/components/Pages/Ability.vue";

export default {
  components: {
    Info,
    Ability
  },
  props: ["page"]
  // data() {
  //   return {
  //     page: "Info"
  //   };
  // }
};
</script>

<style>
#pages {
  float: right;
  width: 700px;
  height: 700px;
  /* background-color: red; */
  padding: 20px 0 20px 20px;
  color: #333;
}
#pages .s_pages {
  background-color: rgba(255, 255, 255, 0.6);
  border-radius: 10px;
  height: 100%;
  padding: 20px;
}
</style>
