<script lang="ts" setup>
const props = defineProps({
  src: { type: String },
});
</script>

<template>
  <div class="flex bg-blue-300">
    <img :src="props.src" />
  </div>
</template>
