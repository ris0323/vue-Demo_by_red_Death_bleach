<template>
  <div class="wrapper">
    <input type="text" v-model="name" />
    <h1>HEllo,{{ name }}</h1>
    <h1 v-text="name"></h1>
    <div v-html="htmlContent"></div>

    <hr />
    <div>
      <button v-on:click="addCount">add</button>
    </div>
    click: <span>{{ count }}</span>

    <hr />
    <div>
      <button @click="changLink">change點我跳轉頁面</button>
    </div>

    <a v-bind:href="link" :title="linkName">{{ linkName }}</a>

    <hr />
    <div @click="toggleActive" class="box" :class="{ active: ifActive }"></div>
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  name: "TestView",
  data() {
    return {
      name: "Ris",
      htmlContent: "test <span>countent</span>",
      count: 0,
      linkName: "Google",
      link: "https://www.google.com",
      ifActive: false,
    };
  },
  methods: {
    addCount() {
      console.log("click");
      this.count++;
    },
    changLink() {
      this.linkName = "Meta元宇宙"; //如何跳轉頁面
      this.link = "https://www.facebook.com";
    },
    toggleActive() {
      this.ifActive = !this.ifActive;
    },
    //跳轉頁面
    /* changLink(){
      this.$$router.push{{path:'/link'}}
    } */
  },
};
</script>

<style>
.wrapper {
  max-width: 880px;
  margin: 0 auto;
}
.box {
  width: 150px;
  height: 150px;
  background: pink;
  transition: 0.5s;
}
.box.active {
  background: red;
}
</style>
