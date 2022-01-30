<template>
  <form class="input" @submit.prevent="onSubmit">
    <p>
      <input type="text" v-model="text" placeholder="пиши продукты!" value="" />
      <button type="submit">опубликовать</button>
    </p>
  </form>
</template>
<script>
export default {
  data() {
    return {
      text: "",
    };
  },
  methods: {
    onSubmit() {
      console.log(this.text);
      if (this.text.trim()) {
        const newItem = {
          id: Date.now(),
          text: this.text,
          important: false,
        };
        this.$emit("input-item", newItem);
        this.text = "";
      }
    },
  },
};
</script>
<style scoped>
.input {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: pink;
  height: 160px;
}
input {
  width: 400px;
  line-height: 34px;
  background-color: lime;
  font-size: 20px;
  color: blueviolet;
  border: none;
}
button {
  line-height: 34px;
  font-size: 20px;
  color: purple;
}
</style>