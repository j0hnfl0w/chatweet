<script lang="ts" setup>
const route = useRoute();
const router = useRouter();
const storeMain = useStoreMain();
const tweet = computed(() => {
  return storeMain.posts.find((p: any) => p.id === route.params.id);
});
</script>

<template>
  <div class="flex flex-col w-full">
    <span @click="router.back()">back</span>
    <pre>{{ tweet }}</pre>
  </div>
</template>
