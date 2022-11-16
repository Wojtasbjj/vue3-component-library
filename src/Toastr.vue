<template>
  <ul class="toastrs-container">
    <li
      v-for="(toastr, index) in toastrs"
      :key="index"
      class="toastr"
      :style="{ background: getToastrColor(toastr.type) }"
    >
      <div>{{ toastr.title }}</div>
      <button @click="deleteToastr(index)">X</button>
    </li>
  </ul>
</template>
<script>
export default {
  name: "Toastr",
  data() {
    return {
      toastrs: [],
      toastrTypes: [
        { type: "warning", color: "red" },
        { type: "information", color: "yellow" },
        { type: "succes", color: "green" },
      ],
    };
  },
  methods: {
    addToastr(title, type) {
      this.toastrs.push({ title: title, type: type });
    },
    deleteToastr(index) {
      this.toastrs.splice(index, 1);
    },
    getToastrColor(type) {
      const toastrType = this.toastrTypes.find(
        (toastrType) => type === toastrType.type
      );

      return toastrType.color;
    },
  },
};
</script>

<style scoped>
.toastrs-container {
  position: absolute;
  bottom: 0;
}

.toastr {
  width: 400px;
  /* background: white; */
  display: flex;
  justify-content: space-between;
  margin: 10px;
  color: black;
}
</style>
