<template>
  <div class="itemrow">
    <li>
      <span>{{ item.text }}</span>
      <button @click="deleteItem(item)">Sil</button>
    </li>
  </div>
</template>

<script>
export default {
  props: ["item"],
  inject: ["deleteItem"],
};
</script>
