<template>
  <main>
    <section v-if="posts" class="w-full max-w-5xl mx-auto">
      <h1 class="title">videos</h1>
      <posts post-type="videos" :amount="10" />
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, error }) {
    let posts;
    try {
      posts = await $content("videos").fetch();
    } catch (e) {
      error({ message: "videos not found" });
    }
    return { posts };
  },
}
</script>
