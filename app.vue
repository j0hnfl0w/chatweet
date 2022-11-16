<template>
  <div class="flex flex-row w-full min-h-screen">
    <div class="flex flex-col w-200px">
      <span>left navigation</span>
    </div>
    <div class="flex-grow br">
      <NuxtPage />
    </div>
  </div>
</template>

<style>
html,
body,
#__nuxt {
  min-height: 100vh;
  margin: 0;
  padding: 0;
  /* @apply font-sans; */
}

.br {
  border: 1px solid red;
}
</style>
