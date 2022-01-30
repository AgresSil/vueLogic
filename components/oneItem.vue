<template>
  <span>
    <li class="li" :class="{ important: list.important }">
      <div>
        <input type="checkbox" v-on:change="list.important = !list.important" />
        {{ index + 1 }}:
        {{ list.text }}
      </div>

      <button class="rm" @click="$emit('delete-item', list.id)">&times;</button>
    </li>
  </span>
</template>
<script>
export default {
  props: {
    list: {
      type: Array,
      required: true,
    },
    index: Number,
  },
};
</script>

<style scoped>
.oneItem {
  /* display: flex;
  justify-content: space-between;
  border: 1px solid purple;
  padding: 10px;
  list-style: none;
  font-size: 40px; */
}
.li {
  display: flex;
  justify-content: space-between;
  border: 1px solid purple;
  padding: 10px 20px;
  margin-bottom: 10px;
  box-shadow: inset 5px 5px 30px purple;
}
.rm {
  margin-left: 20px;
  border-radius: 30%;
  background-color: yellowgreen;
  color: white;
  font-weight: bold;
  font-size: 30px;
}
.important {
  color: brown;
  box-shadow: inset 5px 5px 30px maroon;
}
</style>