<script>
import Toastr from "../../src/Toastr.vue";
export default {
  components: {
    Toastr,
  },
  data() {
    return {
      title: "",
      type: "succes",
    };
  },
  methods: {
    addToastr() {
      this.$refs.toastr.addToastr(this.title, this.type);
      this.title = "";
    },
  },
};
</script>

<template>
  <input type="text" v-model="title" />
  <button @click="addToastr">Add toastr</button>
  <section>
    <h3>radio buttons</h3>
    <input type="radio" v-model="type" value="warning" />Warning (red)
    <input type="radio" v-model="type" value="information" />Information
    (yellow) (yellow)
    <input type="radio" v-model="type" value="succes" />Success (green)
    <br />
  </section>
  <Toastr ref="toastr" />
</template>

<style></style>
