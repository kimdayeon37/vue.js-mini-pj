<script setup lang="ts">
import { defineProps, defineEmits } from "vue";
defineProps({ index: Number, randNum: Number });
defineEmits(['divided-rand'])

</script>

<template>
    <th>index</th>
    <th>random</th>
  <tr>
    <td>{{ index }}</td>
    <td>{{ randNum }}</td>
    <button @click="$emit('divided-rand')">-1</button>
  </tr>

</template>