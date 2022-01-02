<template>
  <main class="prose prose-sm sm:prose lg:prose-lg xl:prose-xl mx-auto  dark:prose-invert">
    <section v-if="posts" class="w-full max-w-5xl mx-auto">
      <posts post-type="blog" :amount="10" />
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, error }) {
    let posts;
    try {
      posts = await $content("blog").fetch();
    } catch (e) {
      error({ message: "Blog posts not found" });
    }
    return { posts };
  },
}
</script>
