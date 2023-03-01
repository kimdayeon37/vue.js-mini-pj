<script setup lang="ts">
import { ref } from "vue";
import TableContent from "../components/TableContent.vue";

let index = 0;

interface numberNumber {
  index: number;
  randNum: number;
}
const tableElements = ref<numberNumber[]>([]);
const createRow = (e: MouseEvent) => {
  console.log(e);
  tableElements.value?.push({
    index: index++,
    randNum: Math.round(Math.random() * 10),
  });
};
const deleteRow = () => {
  console.log(index);
  tableElements.value?.pop();
};
</script>

<template>
  <button @click="(e:MouseEvent)=>createRow(e)">+</button>
  <button @click="deleteRow">-</button>
  <hr/>
  <table>
    <TableContent
      v-for="item in tableElements"
      :key="item.index"
      :index="item.index"
      :randNum="item.randNum"
      @divided-rand="item.randNum -= 1"
    ></TableContent>
  </table>
</template>
