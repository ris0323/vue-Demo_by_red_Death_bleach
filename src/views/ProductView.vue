<template>
  <div>
    <input type="text" v-model="name" />
    <h1>HEllo,{{ name }}</h1>
    <h1 v-text="name"></h1>
    <div v-html="htmlContent"></div>
    <hr />
    <div>
      <!--  <button v-on:click="addCount">add</button> -->
      <button @click="changLink">change</button>
    </div>
    click: <span>{{ count }}</span>
    <hr />
    <a v-bind:href="link" :title="linkName">{{ linkName }}</a>
    <hr />
    <div class="box" :class="{ active: ifActive }"></div>
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
      this.linkName = "Meta元宇宙";
      this.link = "https://www.facebook.com";
    },
    toggleActive() {
      this.ifActive = !this.ifActive;
    },
  },
};
</script>

<style>
.wrapper {
  max-width: 150px;
  margin: 0 auto;
}
.box {
  width: 150px;
  hyphens: 150px;
  background: pink;
  transition: 0.5s;
}
.box.active {
  background: red;
}
</style>
