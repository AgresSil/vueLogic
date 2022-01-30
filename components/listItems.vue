<template>
  <div class="list">
    <ul>
      <oneItem
        v-for="(list, i) in lists"
        :list="list"
        :index="i"
        :key="list.id"
        v-on:delete-item="deleteItem"
      />
    </ul>
  </div>
</template>
<script>
import inputItem from "@/components/inputItem";
import oneItem from "@/components/oneItem";
export default {
  props: {
    lists: {
      type: Array,
      required: true,
    },
  },

  components: {
    inputItem,
    oneItem,
  },
  methods: {
    deleteItem(id) {
      this.$emit("delete-item", id);
    },
  },
};
</script>

<style>
.list {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  /* background-color: green; */
  font-size: 40px;
}
</style>