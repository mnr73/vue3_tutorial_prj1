<template>
  <h1>مهارت‌های من</h1>
  <hr />
  <input type="text" class="search" placeholder="جستجو" v-model.trim="search" />
  <button @click="search = ''">حذف فیلتر</button>
  <br />
  <span>
    شما <b>{{ countAbility }}</b> مهارت دارید
  </span>
  <br />
  <span>
    نمایش <b>{{ filterAbility.length }}</b> از <b>{{ abilities.length }}</b>
  </span>
  <br />
  <template v-for="ability in filterAbility" :key="ability.name">
    <label class="check-box">
      <input type="checkbox" v-model="ability.selected" />
      {{ ability.name }}
    </label>
  </template>
</template>

<script>
export default {
  data() {
    return {
      // abilities: ["PHP", "JavaScript"],
      search: "",
      abilities: [
        { name: "PHP", selected: true },
        { name: "JavaScript", selected: true },
        { name: "Java", selected: false },
        { name: "C++", selected: false },
        { name: "Lua", selected: false },
        { name: "Python", selected: false },
        { name: "C#", selected: false },
        { name: "HTML", selected: false },
        { name: "CSS", selected: false },
        { name: "GIT", selected: false },
        { name: "Docker", selected: false },
        { name: "Vue", selected: false },
        { name: "React", selected: false }
      ]
    };
  },
  computed: {
    countAbility() {
      return this.abilities.filter(item => item.selected).length;
    },
    filterAbility() {
      if (this.search == "") {
        return this.abilities;
      } else {
        let patt = new RegExp(this.search, "i");
        return this.abilities.filter(item => patt.test(item.name));
      }
    }
  }
};
</script>

<style>
.check-box {
  display: inline-block;
  background-color: rgba(255, 255, 255, 0.5);
  padding: 5px 10px;
  border-radius: 5px;
  cursor: pointer;
  margin: 10px;
  direction: ltr;
}
</style>
