<template>
  <div id="app">
    <br />
    <br />
    <b-avatar
      src="https://scontent.fbkk13-1.fna.fbcdn.net/v/t1.0-9/119161132_2829624320654949_2049276399592569660_n.jpg?_nc_cat=108&_nc_sid=09cbfe&_nc_ohc=PXgWT337WEQAX-0MIQR&_nc_ht=scontent.fbkk13-1.fna&oh=842f1118ab4fea753f23690f3c6e073d&oe=5F8C2189"
      size="15%"
    ></b-avatar>
    <HelloWorld id="text" msg="Nonog_narlux" />
    <br />
    <nn />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import nn from "./components/nn.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    nn,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-size: cover;
  background-image: url();
}
#text {
  color: rgb(0, 0, 0);
}
</style>
