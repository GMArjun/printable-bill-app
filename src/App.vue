<template>
  Lorem ipsum dolor, sit amet consectetur adipisicing elit. Dignissimos, eius.
</template>

<script setup>
import { onMounted } from "vue";

onMounted(() => {
  document.addEventListener("keydown", function (event) {
    if (event.key === "p") {
      event.preventDefault();
      window.print();
    }
  });
});
</script>
