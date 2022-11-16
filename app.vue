<script lang="ts" setup>
const storeMain = useStoreMain();
const state = reactive({
  text: "",
  files: [],
});
function postAdd() {
  console.log("postAdd");
  const postPayload = {
    text: state.text,
  };
  state.text = "";
  storeMain.postAdd(postPayload);
}
</script>

<template>
  <div class="flex flex-col">
    <input
      type="text"
      v-model="state.text"
      placeholder="Enter text"
      class="bg-red-300"
      @keyup.enter="postAdd()"
    />
    <div
      v-for="p in storeMain.posts"
      :key="p.id"
      class="flex flex-col w-full items-start content-start br"
    >
      <pre>{{ p }} </pre>
      <button @click="storeMain.postDelete(p.id)">delete post</button>
      Likes: {{ p.likes_count }}
      <button @click="storeMain.postLike(p.id)">Like</button>
      <button @click="storeMain.postDislike(p.id)">Dislike</button>
      <BaseImg
        src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQNiIAHrL1a5mw8hOHR6gi2ETS7DYWAe6xxl2EdwJ5r&s"
      />
    </div>
  </div>
</template>

<style>
.br {
  border: 1px solid red;
}
</style>
