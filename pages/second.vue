<template>
  <div>
    <nuxt-link to="/">В начало</nuxt-link>
    <inputItem @input-item="inputItem" />
    <listItems :lists="lists" @delete-item="deleteItem" />
  </div>
</template>

<script>
import inputItem from "@/components/inputItem";
import listItems from "@/components/listItems";
export default {
  data() {
    return {
      lists: [
        { id: 1, text: "баклажаны", important: false },
        { id: 2, text: "свинина", important: false },
        { id: 3, text: "помидоры", important: false },
      ],
    };
  },
  methods: {
    deleteItem(id) {
      this.lists = this.lists.filter((i) => i.id !== id);
    },
    inputItem(list) {
      this.lists.push(list);
    },
  },
  components: {
    listItems,
    inputItem,
  },
};
</script>
